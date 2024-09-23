# 命令

## 查看内存占用

### top命令

    top命令是Linux下常用的性能分析工具，能够实时显示系统中各个进程的资源占用状况，类似于Windows的任务管理器。

**命令示例**

1、top [-] [d delay] [q] [c] [S] [s] [i] [n] [b]

* `-d <秒数>`：指定 top 命令的刷新时间间隔，单位为秒。
* `-n <次数>`：指定 top 命令运行的次数后自动退出。
* `-p <进程ID>`：仅显示指定进程ID的信息。
* `-u <用户名>`：仅显示指定用户名的进程信息。
* `-H`：在进程信息中显示线程详细信息。
* `-i`：不显示闲置（idle）或无用的进程。
* `-b`：以批处理（batch）模式运行，直接将结果输出到文件。
* `-c`：显示完整的命令行而不截断。
* `-S`：累计显示进程的 CPU 使用时间。

如下表所示：

```
top - 13:08:16 up  4:03,  1 user,  load average: 0.92, 0.88, 0.59
任务: 328 total,   1 running, 326 sleeping,   0 stopped,   1 zombie
%Cpu(s):  5.0 us,  1.3 sy,  0.0 ni, 93.6 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :  15835.4 total,   9270.4 free,   3137.8 used,   3427.2 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.  12188.4 avail Mem 
 
  PID USER      PR   NI  VIRT   RES     SHR     %CPU   %MEM   TIME + COMMAND
   6310 jidan     20   0   12.2g 686952 389780 S  14.7   4.2   6:27.52 firefox  
   6946 jidan     20   0  439700 119268  98996 S  10.3   0.7   1:53.92 RDD Process  
   1603 jidan     20   0 5973144 428232 206380 S   5.0   2.6   5:20.29 gnome-shell  
   7367 jidan     20   0 2915292 341532 142468 S   4.7   2.1   2:55.14 Isolated Web Co  
   1444 jidan      9 -11 2220100  29512  22472 S   3.0   0.2   1:57.04 pulseaudio   
  13542 jidan     20   0 2603040 200404 111140 S   2.7   1.2   0:01.69 Isolated Web Co  
  11752 jidan     20   0 2744636 260824 118332 S   2.0   1.6   0:06.85 Isolated Web Co  
   6686 jidan     20   0  347160  64832  52992 S   0.7   0.4   0:15.61 Utility Process  
   7810 jidan     20   0  648060  70632  51812 R   0.7   0.4   0:05.73 gnome-terminal-  
  12203 root      20   0       0      0      0 I   0.7   0.0   0:01.36 kworker/u16:1-gfx_0.0.0  
  14312 jidan     20   0 2463364 106636  81152 S   0.7   0.7   0:00.20 Isolated Web Co  
     17 root      20   0       0      0      0 I   0.3   0.0   0:07.84 rcu_preempt  
    539 systemd+  20   0   14836   6784   6016 S   0.3   0.0   0:07.58 systemd-oomd   
   8868 root      20   0       0      0      0 D   0.3   0.0   0:02.66 kworker/u16:2+events_unbound   
  10075 jidan     20   0 2605508 193532 110816 S   0.3   1.2   0:02.58 Isolated Web Co  
  11098 jidan     20   0 2676148 225964 113008 S   0.3   1.4   0:05.97 Isolated Web Co  
  12356 jidan     20   0   21920   4224   3328 R   0.3   0.0   0:00.69 top  
```

上图中各信息如下：

* PID：进程的标识符。
* USER：运行进程的用户名。
* PR（优先级）：进程的优先级。
* NI（Nice值）：进程的优先级调整值。
* VIRT（虚拟内存）：进程使用的虚拟内存大小。
* RES（常驻内存）：进程实际使用的物理内存大小。
* SHR（共享内存）：进程共享的内存大小。
* %CPU：进程占用 CPU 的使用率。
* %MEM：进程占用内存的使用率。
* TIME+：进程的累计 CPU 时间。
