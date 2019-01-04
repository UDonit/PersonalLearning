# Linux 文件系统 — Resources

## Knowledge

### Primary / Kernel Documentation
- [Linux Kernel VFS Documentation](https://docs.kernel.org/filesystems/vfs.html) — The official kernel docs on the Virtual File System. The authoritative source for VFS object structures and operations.
- [Linux Kernel ext4 Documentation](https://docs.kernel.org/filesystems/ext4/index.html) — Official ext4 on-disk format documentation.
- [Linux Kernel Page Cache Documentation](https://docs.kernel.org/filesystems/caching/fscache.html) — Official docs on the page cache and filesystem caching layer.

### High-Quality Books
- [Book: _Linux Kernel Development_ (3rd Edition) — Robert Love](https://www.amazon.com/Linux-Kernel-Development-Robert-Love/dp/0672329468) — Chapters 12–16 cover the VFS, ext2/3, page cache, and block I/O. The canonical textbook for kernel learners.
- [Book: _Understanding the Linux Kernel_ (3rd Edition) — Bovet & Cesati](https://www.amazon.com/Understanding-Linux-Kernel-Third-Daniel/dp/0596005652) — Chapters 12–18. More detail on the older kernel but excellent for deep internals.
- [Book: _The Design and Implementation of the FreeBSD Operating System_ (2nd Edition)](https://www.amazon.com/Design-Implementation-FreeBSD-Operating-System/dp/0321968972) — Cross-reference: how VFS concepts originated in BSD.

### Articles & Blog Posts
- [LWN: "The VFS: The Virtual File System"](https://lwn.net/Articles/97154/) — A classic LWN kernel tour of the VFS.
- [LWN: "Page cache: the view from the inside"](https://lwn.net/Articles/712467/) — Deep dive into the page cache internals.
- [LWN: "Understanding the Linux kernel's filesystem layer"](https://lwn.net/Articles/57369/) — The dentry cache and path resolution.
- [LWN: "Toward a faster page cache"](https://lwn.net/Articles/805312/) — Recent page cache improvements (folios).

### Chinese Resources
- [知乎: Linux 文件系统 VFS 详解](https://www.zhihu.com/search?type=content&q=Linux%20VFS%20%E6%96%87%E4%BB%B6%E7%B3%BB%E7%BB%9F) — Various high-quality Chinese blog posts.
- [Linux 内核修炼之道 — 文件系统篇](https://www.kancloud.cn/kancloud/linux-kernel-development) — Chinese-translated kernel learning resource.

## Wisdom (Communities)

- [Reddit r/linuxkernel](https://www.reddit.com/r/linuxkernel/) — Active kernel development discussions.
- [Reddit r/linuxdev](https://www.reddit.com/r/linuxdev/) — Linux programming, filesystem-related questions.
- [StackOverflow: filesystems tag](https://stackoverflow.com/questions/tagged/filesystems) — Practical debugging and troubleshooting.
- [内核月谈 (Kernel Monthly)](https://kerneltravel.net/) — Chinese Linux kernel community with regular meetups.