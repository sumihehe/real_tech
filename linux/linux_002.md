# Memory Compression内存压缩

>Contents

>1. [Compression](#1-compression)

>1. [Deduplication](#2-deduplication)

## 1. Compression
Cleancache和Frontswap算是一个内核中内存压缩的“前端”，Zram、Zswap、Zcache和tmem这些属于”后端“。其中“Zproject”可以用于单机模式下，tmem更侧重Xen虚拟化环境中的应用。

#### Cleancache & Frontswap

> [Cleancache and Frontswap](https://lwn.net/Articles/386090/)

> [linux kernel DOC:cleancache](http://lxr.free-electrons.com/source/Documentation/vm/cleancache.txt)

> [linux kernel DOC:frontswap](http://lxr.free-electrons.com/source/Documentation/vm/frontswap.txt)

#### Zram & Zswap & Zcache

> [zram vs zswap vs zcache](http://askubuntu.com/questions/471912/zram-vs-zswap-vs-zcache-ultimate-guide-when-to-use-which-one/472227#472227)

> [In-kernel memory compression](https://lwn.net/Articles/545244/)  [[翻译](http://blog.jcix.top/2016-12-09/inkernel_memory_compression/)]

> [zcache: a compressed page cache](https://lwn.net/Articles/397574/)(Jonathan Corbet)

> [zcache: a compressed file page cache](https://lwn.net/Articles/562254/)(bob liu)

> [LSFMM: In-kernel memory compression](https://lwn.net/Articles/548109/)

> [https://www.kernel.org/doc/Documentation/vm/zswap.txt](https://www.kernel.org/doc/Documentation/vm/zswap.txt)

> [Linux下使用zram（压缩内存）](https://segmentfault.com/a/1190000000380500)

目前zram和zswap都在在内核中，而zcache进入过内核，后来被移出，其精简版由bob liu重写，并尝试加入mm模块中。

#### Transcendent Memory (tmem)

> [Transcendent memory in a nutshell](https://lwn.net/Articles/454795/) [[翻译](http://blog.chinaunix.net/uid-23531402-id-3199889.html)]

> [LINUX PATCH AND ENVIRONMENT FOR XEN TRANSCENDENT MEMORY](https://oss.oracle.com/projects/tmem/dist/documentation/internals/linuxpatch)

> [WHAT IS TRANSCENDENT MEMORY](https://oss.oracle.com/projects/tmem/)

> [kvm: Transcendent Memory (tmem) on KVM](https://groups.google.com/forum/#!starred/linux.kernel/KB2-YfAJhVc) [[github source](https://github.com/akshaykarle/kvm-tmem)]

## 2. Deduplication

#### KSM
>[LWN][/dev/ksm: dynamic memory sharing](https://lwn.net/Articles/306704/)

>[LWN][KSM tries again](https://lwn.net/Articles/330589/)

>[Wikipedia][Kernel same-page merging](https://en.wikipedia.org/wiki/Kernel_same-page_merging)

>[[Tmem-devel] [Xen-devel] Queries on KSM & Tmem](https://oss.oracle.com/pipermail/tmem-devel/2010-September/000174.html)

>[doc][kernel Document:vm/ksm.txt](https://www.kernel.org/doc/Documentation/vm/ksm.txt)

>[KVM的内存合并技术KSM--Kernel Samepage Merging](http://m.blog.chinaunix.net/uid-28326497-id-4008097.html)

>[experiment][KSM and KVM][http://serverascode.com/2012/11/11/ksm-kvm.html]
#### UKSM & PKSM

>[kerneldedup.org(UKSM & XenDedup)](http://kerneldedup.org/)

>[Google Code: PKSM](https://code.google.com/archive/p/pksm/)

>[PKSM: A New Data De-Duplication Method For Linux](http://www.phoronix.com/scan.php?page=news_item&px=MTM0OTQ)

