# Linux 文件系统 — 术语表 (Glossary)

本术语表包含了 Linux 文件系统相关的核心术语，按概念层级组织。

## 核心 VFS 对象

| 术语 | 英文 | 定义 |
|------|------|------|
| **VFS** | Virtual File System (Virtual Filesystem Switch) | 内核中的抽象层，为用户态程序提供统一的文件操作接口，屏蔽底层不同文件系统（ext4、XFS、procfs 等）的实现差异 |
| **超级块** | Superblock | 表示一个已挂载的文件系统实例。管理整个文件系统的全局元数据 —— 块大小、inode 总数、空余块数等。每个挂载点对应一个超极块 |
| **inode** | Index Node (Inode) | 表示文件系统中的一个对象（文件、目录、设备节点等）。存储对象的元数据（权限、大小、时间戳、数据块指针），**不包含文件名**。通过 inode 号唯一标识 |
| **dentry** | Directory Entry (Dentry) | 路径名的一个分量（component），"文件名 → inode" 的映射关系。**仅存在于内存中（dcache）**，不写入磁盘。用于加速路径解析 |
| **文件对象** | File Object (struct file) | 表示一个进程打开的文件。持有当前读写偏移量（f_pos）、指向 dentry 的指针、一组 file_operations。对应进程中的文件描述符 |

## 核心机制

| 术语 | 英文 | 定义 |
|------|------|------|
| **dcache** | Directory Entry Cache | dentry 的内存缓存。缓存已解析的路径名 → inode 映射，避免每次 open 都走磁盘 I/O |
| **页缓存** | Page Cache | 内核用物理内存缓存磁盘文件数据的机制。读文件时优先从 page cache 命中，未命中才发起 I/O。写文件时先写入 page cache（标记为脏页），内核异步回写到磁盘 |
| **Address Space** | Address Space (struct address_space) | 连接 page cache 和具体文件系统的桥梁。每个 inode 有一个 address_space，用于管理该文件的缓存页和与磁盘的交互（readpage、writepage） |
| **回写** | Writeback | 内核将 dirty page（脏页）写回磁盘的过程。由 pdflush/flusher 线程异步执行，也可通过 fsync() 同步触发 |

## 文件系统类型

| 术语 | 定义 |
|------|------|
| **ext4** | Linux 上最常用的日志文件系统，ext3 的继任者。支持 extents、延迟分配、大文件（16TB→1EB） |
| **procfs** | 挂载在 /proc 的虚拟文件系统。以文件形式暴露内核数据结构（进程信息、内存信息、设备信息等），数据动态生成而非存储在磁盘上 |
| **sysfs** | 挂载在 /sys 的虚拟文件系统。以结构化方式暴露内核对象（设备、驱动、总线）的层次关系 |
| **tmpfs** | 基于内存（+swap）的临时文件系统。挂载在 /dev/shm、/tmp 等位置。数据在内存中，重启即丢失 |

## 磁盘数据结构

| 术语 | 英文 | 定义 |
|------|------|------|
| **块组** | Block Group | ext4 将分区划分为多个块组，每个块组独立管理自己的 inode 表和数据块，目的在减少碎片、提高局部性 |
| **Extent** | Extent | ext4 中替代间接块映射的机制。一个 extent 结构体可以表示一段连续的物理块范围（起始块号 + 长度），减少对大文件的元数据开销 |
| **inode 表** | Inode Table | 每个块组中的连续磁盘区域，存储该块组内所有 inode 的元数据 |
| **超级块副本** | Superblock Copy | 主超级块位于块组 0，且块组 0、1 和其他备份块组中会保存冗余副本，用于容灾恢复 |

## 链接与挂载

| 术语 | 英文 | 定义 |
|------|------|------|
| **硬链接** | Hard Link | 多个 dentry 指向同一个 inode。inode 中维护链接计数（i_nlink），计数归零时才真正释放数据。硬链接不能跨文件系统、不能链接目录 |
| **软链接** | Symbolic Link (Symlink) | 一个特殊的文件，文件内容是要指向的目标路径。访问时 VFS 自动跳转。可以跨文件系统、可以指向目录 |
| **挂载** | Mount | 将一个文件系统实例附着到 VFS 目录树上的过程。mount 命令通过 sys_mount() 系统调用实现 |
| **挂载点** | Mount Point | 目录树上的一个目录，作为文件系统实例的访问入口。挂载后，该目录原有内容被隐藏 |

## 常用系统调用

| 调用 | 功能 |
|------|------|
| open() / creat() | 打开或创建文件。返回文件描述符 |
| read() / write() | 读写文件数据。通过文件描述符操作 |
| stat() / lstat() | 获取 inode 元数据（大小、权限、时间戳）。lstat 不跟随软链接 |
| link() / unlink() | 创建/删除硬链接。unlink 使 inode 链接计数减一 |
| symlink() / readlink() | 创建/读取软链接 |
| mount() / umount() | 挂载/卸载文件系统 |
| mkfs | 在设备上创建文件系统（格式化） |
| fsync() | 将文件的所有脏数据（数据+元数据）同步到磁盘 |

---

*本术语表会随着课程推进持续更新。*