# Linux及内核的同步机制

## Linux 

1. 互斥量
1. 读写锁
1. 条件变量
1. 自旋锁
1. 屏障

## Kernel

1. 原子操作
1. 自旋锁：有点在于进程阻塞时没有休眠，虽然浪费CPU，但没有进程切换的开销，适合预期阻塞时间短的情况。通常用于底层来实现其他种类的锁。（如RCU）
3. 读写自旋锁：读读不锁，读写和写写之间互斥。
4. 信号量
5. 读写信号量
6. 互斥体
7. 完成变量
8. 大内核锁
9. 顺序锁
10. 禁止抢占
11. 顺序和屏障

12. RCU(read-copy-update)：读写和读读不锁，写写之间互斥。

---

#### 参考

[1] APUE

[2] 《Linux内核设计与实现》读书笔记（十）- 内核同步方法, http://www.cnblogs.com/wang_yb/archive/2013/05/01/3052865.html