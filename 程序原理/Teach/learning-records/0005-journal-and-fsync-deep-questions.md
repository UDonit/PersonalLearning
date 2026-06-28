# 0005 — Journal + fsync: 学习前的深入追问

在进入第五课（ext4 Journal + fsync）之前，用户通过第四课学习中对 delalloc 崩溃风险的提问，自然过渡到了对 Journal 机制的关注。同时用户也纠正了对"已删除文件空间未释放"问题中 evict 路径的误解，以及深入追问了 mmap 对 inode 引用的精确机制。

## 内容

1. **"已删除文件空间未释放"的精确机制** — 用户自己推导了第一层原因（i_nlink=0 但 i_count!=0），但误以为 evict 有额外延迟。实际在 i_nlink=0 && i_count=0 时，evict() 同步调用 truncate_inode_pages() + ext4_free_inode() + ext4_free_blocks()，没有元数据清空延迟
2. **f_inode 不持有引用计数** — `struct file->f_inode` 只是缓存指针（等价于 f_path.dentry->d_inode 的加速快照），不参与 i_count。真正持有 inode 引用的是 dentry，由 d_instantiate() 中的 ihold() 增加 i_count。mmap 通过 VMA→vm_file→f_path.dentry→d_inode 这个链间接防止 inode 释放
3. **delalloc 的失败风险** — 用户自主推导出"delalloc 下 write() 返回成功但可能实际无磁盘块可分配"的风险，以及修订+追加时旧 block 不动、新 block 连续分配的正确结论
5. **第五课后的延伸问答** — 涉及日志延迟可见性、环形缓冲区写满的处理、ordered 模式的安全缺口（"写了的数据不一定被引用"）、三种模式下日志内容差异、data=journal 写大文件时的 checkpoint 流水线、ordered vs writeback 的核心区别（仅顺序约束）

**Status**: completed

**Implications**: 用户已经触及了事务系统"要么全部完成、要么像没发生过"这一核心契约的精确边界。特别值得注意的是用户独立发现了 ordered 模式的安全缺口——这是一个许多有几年工作经验的工程师都不一定意识到的细节。下一课可以转向虚拟文件系统（procfs/sysfs），或者进入 I/O 模块（BIO→blk-mq→I/O 调度器），取决于用户的兴趣方向。

**Why**: 用户对"引用"概念的精确性要求很高，这是理解内核对象生命周期管理的核心能力。Journal 的引入补上了 delalloc 讨论中自然产生的"崩溃一致性"缺环。

**How to apply**: 后续教学中涉及引用计数的解释需要精确到"哪个结构对哪个结构调用什么函数 +1"，不能停留在笼统的"持有引用"层面。应继续使用"三向对比"（ext3 vs ext4、flusher vs kswapd 等）教学模式。