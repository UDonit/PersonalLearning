# dcache 深度参考

## 核心数据结构

```
dentry_hashtable[32768]  — 全局哈希表，桶数固定
        │
  每个桶存储一个链表，通过 hlist_bl_head 组织
        │
  哈希键 = hash(parent_dentry_ptr + d_name.string)
        │
  查找：无锁（RCU）→ 带锁（spinlock）→ 磁盘 I/O
```

## 查找三路径

| 路径 | 函数 | 锁 | 性能 | 命中场景 |
|------|------|----|------|---------|
| 快速路径 | `__d_lookup_rcu()` | RCU 无锁 | 纳秒级 | 最近访问过的路径 |
| 中速路径 | `__d_lookup()` | spinlock | 微秒级 | RCU 检测到并发写时退至此路 |
| 慢速路径 | `lookup_slow()` → `i_op->lookup()` | 全锁 + 磁盘 I/O | 毫秒级 | 首次访问或 dentry 被回收 |

## 生命周期关键函数

```
d_alloc()     — 分配 dentry 结构体（来自 slab 缓存）
d_add()       — 关联 dentry → inode，增加 i_count，挂入哈希表
d_delete()    — 从哈希表摘除，断开 inode 链接，iput(inode)
d_drop()      — 仅从哈希表摘除（不断开 inode）
d_rehash()    — 重新挂入哈希表
dget()        — 增加 dentry 引用计数（d_count++）
dput()        — 减少 dentry 引用计数，归零时触发回收
iput()        — 减少 inode 引用计数（i_count--），归零且 i_nlink==0 时 evict
```

## 担保链

```
dentry 在哈希表中
  → dentry->d_inode != NULL
    → inode->i_count >= 1
      → inode 无法被 evict
        → 数据安全
```

## 双引用计数模型

| 计数 | 类型 | 含义 | 操作 | 范围 |
|------|------|------|------|------|
| i_nlink | 磁盘级别 | 目录项指向 inode 的数量 | vfs_link() +1, vfs_unlink() -1 | 文件系统全局 |
| i_count | 内存级别 | inode 被内核对象引用的次数 | d_add() +1, iput() -1, file_hold() +1 | 内核内存 |

释放条件：**i_nlink == 0 且 i_count == 0**

## 负缓存（Negative Dentry）

- dentry->d_inode = NULL
- 标志位：DCACHE_MISS_TYPE
- 用途：避免反复 I/O 确认"文件不存在"
- 风险：可能被大量无效查询污染 dcache
- 防御：LRU 回收时优先回收负 dentry

## 可观测接口

```
/proc/sys/fs/dentry-state     — nr_dentry, nr_unused, age_limit, ...
/proc/sys/fs/inode-state      — nr_inodes, nr_free_inodes, ...
/proc/slabinfo                — dentry 和 inode 对应的 slab 缓存行
```

## 相关内核源码路径

```
fs/namei.c        — lookup_fast(), lookup_slow(), path_openat(), link_path_walk()
fs/dcache.c       — d_add(), d_delete(), __d_lookup(), __d_lookup_rcu(), dentry_lru_isolate()
fs/inode.c        — iput(), iput_final(), evict()
fs/file_table.c   — alloc_empty_file()
fs/file.c         — get_unused_fd_flags(), fd_install()
fs/open.c         — do_sys_open(), do_dentry_open(), may_open()
fs/ext4/namei.c   — ext4_lookup()
fs/ext4/inode.c   — ext4_iget(), __ext4_iget()
```