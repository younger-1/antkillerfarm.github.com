---
layout: post
title:  Linux学习心得（三）
category: linux 
---

* toc
{:toc}

# minicom

1.查看串口设备

`ls -l /dev`

2.连接串口设备

`minicom -D /dev/ttyS0`

3.菜单

Ctrl+A Z

4.退出

Ctrl+A X

# MobaXterm

MobaXterm是一个远程终端登录软件。

http://mobaxterm.mobatek.net/

# tmux

你是不是经常需要SSH或者telent远程登录到Linux服务器？你是不是经常为一些长时间运行的任务而头疼，比如系统备份、ftp传输等等。

通常情况下我们都是为每一个这样的任务开一个远程终端窗口，因为他们执行的时间太长了。必须等待它执行完毕，在此期间可不能关掉窗口或者断开连接，否则这个任务就会被杀掉，一切半途而废了。

这个问题的解决办法是安装一个会话管理工具。原先主要使用screen：

https://www.gnu.org/software/screen/

这是一个有30年历史（1987年）的软件。

现在的话，一般推荐使用tmux：

https://github.com/tmux/tmux/

安装：

`sudo apt install tmux`

tmux也有一些高端功能，比如分屏等。

常用命令：

`Ctrl+b c`: 创建窗口。

`Ctrl+b "`: 上下分屏。

`Ctrl+b %`: 左右分屏。

`Ctrl+b z`: 最大化/恢复原状。

`ctrl+b d`: 不销毁进程退出（detach）。

`ctrl+d`: 销毁进程退出。

`tmux ls`: 查看会话。

`tmux attach -t 0`: 重新接入某个已存在的会话。

复制粘贴有两种方法：

- 方法1：按住Shift，使用系统的复制粘贴。
- 方法2：`ctrl+b [`: 复制。 `ctrl+b ]`: 粘贴。

屏幕滚动：

`ctrl+b [`，就可以用鼠标滑轮滚动了，按q退出。

常用配置：`~/.tmux.conf`：

```bash
set -g mouse on
set -g history-limit 100000
```

如果不生效的话，可以用`tmux source ~/.tmux.conf`使其立即生效。

参考：

https://linuxtoy.org/archives/from-screen-to-tmux.html

从screen切换到tmux

http://mingxinglai.com/cn/2012/09/tmux/

tmux的使用方法和个性化配置

http://chengjin.li/2017/08/09/tmux-using-tutorial/

终端复用工具---tmux的安装及使用

https://www.ruanyifeng.com/blog/2019/10/tmux.html

Tmux使用教程

https://blog.csdn.net/mainking2003/article/details/120504004

用shell脚本运行Tmux

# 设置终端颜色

`printf "\033[1;42mH\033[4;32;49me\033[5ml\033[7ml\033[0;32mo\033[0m\n"`

参考：

https://zhuanlan.zhihu.com/p/81954911

如何改变你的终端颜色

http://easyos.net/articles/bsd/freebsd/output_control_in_freebsd_console

https://en-m.jinzhao.wiki/wiki/ANSI_escape_code

https://mp.weixin.qq.com/s/Q8RkA4cjko-sD5jn7NGzGw

一行命令堆出你的新垣结衣，不爆肝也能创作ASCII Art

# MOTD

motd：message of the day。即系统登陆时，通过终端展示给登陆用户的消息。

静态MOTD: `/etc/motd`

动态MOTD: `/etc/update-motd.d/`

https://www.cnblogs.com/gageshen/p/11565980.html

Linux中创建自己的MOTD

# 设置随机的MAC地址

1.设置MAC地址

`ifconfig eth0 hw ether 477265656e00`

其中eth0是网口的名称，477265656e00是要设置的MAC地址（十六进制）。

2.生成随机数

随机数的生成在Linux中有多种方法，这里使用openssl。因为它和MAC都属于网络编程的范畴，同时使用的概率较大。

`openssl rand -hex 6`

3.SIOCSIFHWADDR: Cannot assign requested address错误

MAC地址的某些位有特定的含义，并不能随意设置。仍以477265656e00为例，第一个字节0x47的最后两位含义如下：

（00）统一管理的单播MAC

（01）统一管理的多播MAC

（10）本地管理的单播MAC

（11）本地管理的多播MAC

由于针对ADSL路由等这样的网络终端，一般使用的都是统一管理的单播MAC。

# 设置网卡eth0的IP地址和子网掩码

`sudo ifconfig eth0 192.168.2.1 netmask 255.255.255.0`

# 无线设置

查看无线网卡状态：

`iwconfig`

`wpa_cli`

扫描周围的wifi信号：

`iwlist scanning`

# 下载工具

wget和curl是最常见的下载工具。这里推荐使用axel，该工具支持多路http下载。

示例：

`wget -c <URL>`

`curl -C -o <file name> <URL>`

`axel <URL>`

`wget -b -i XX.txt`

`-b`：后台，`-i`：批量。

参考：

http://os.51cto.com/art/201605/511423.htm

Linux用户宝典：用于下载的十大命令行工具

# NFS

## 客户端

`mount -t nfs 192.168.0.1:/tmp /mnt/nfs`

挂载NFS。挂载点（即上例中的/mnt/nfs）必须事先创建。

`mount: /bak: bad option; for several filesystems (e.g. nfs, cifs) you might need a /sbin/mount.<type> helper program`

出现上面的问题，需要：

`sudo apt install nfs-common libnfs-utils`

## 服务器端

```bash
sudo apt install nfs-server
cd /
sudo mkdir nfs-server
sudo chmod 777 nfs-server
sudo chmod 666 /etc/exports
echo "/nfs-server *(rw,sync,no_root_squash)">>/etc/exports
sudo service nfs-server restart
```

参考：

https://www.cnblogs.com/tu13/p/ubuntu_nfs.html

ubuntu18.04搭建NFS服务器

## 访问Windows共享文件夹

```
sudo apt install cifs-utils
sudo mkdir /mnt/share
sudo mount -t cifs -o username=XXX,password=XXX //192.168.0.81/abc /mnt/share
```

# 动态库

## 版本设置

linux动态库使用soname来设定动态库的版本兼容性。

`g++ -fPIC -shared -Wl,-soname,libbar.so.1 -o libbar.so.1.1.0`

这个命令生成的动态库的名字为`libbar.so.1.1.0`，soname为`libbar.so.1`。

soname的意思是：形如`libbar.so.1.x.y`的动态库，都可以兼容。

cmake写法：

`SET_TARGET_PROPERTIES(hello PROPERTIES VERSION 1.2 SOVERSION 1)`

参考：

https://www.jianshu.com/p/931a814083ce

Linux动态库soname的使用

https://tldp.org/HOWTO/Program-Library-HOWTO/shared-libraries.html

Shared Libraries

## PIC

position-independent code

不加`-fPIC`编译的`.so`必须要在加载到用户程序的地址空间时重定向所有表目，所以在它里面不能引用其它地方的代码。

而多个进程引用同一个PIC动态库时，可以共用内存。这个库在不同进程中的虚拟地址不同，操作系统会把它们映射到同一块物理内存上。

cmake写法：

`set(CMAKE_POSITION_INDEPENDENT_CODE ON)`

# popen

popen()函数通过创建一个管道，调用fork产生一个子进程，执行一个shell以运行命令来开启一个进程。也就是说这个函数可以执行shell命令，而且还可以用fread或fgets来获取命令执行后的输出结果。

例子如下：

```c
int8_t strcmd[256];
memset(strcmd, 0 , sizeof(strcmd));
sprintf(strcmd, "cat /etc/resolv.conf | awk '{printf $2}'");
pfile = popen(strcmd, "r");
if (pfile != NULL){
	int8_t str[64];
	bzero(str, sizeof(str));
	fgets(str, sizeof(str), pfile);
	pclose(pfile);
}
```

# Linux知识图谱

![](/images/article/linux_perf_tools_full.png)

![](/images/img3/linux_kernel_map.png)

原图地址：

http://www.brendangregg.com/linuxperf.html

![](/images/img4/Linux-storage-stack-diagram_v4.10.png)

BSP: Board Support Package

参考：

https://mp.weixin.qq.com/s/-iCuxQjSghtDGaPMqaDSgQ

Linux思维导图整理

https://mp.weixin.qq.com/s/sLyD6z2xBXRxfBZnImTgtQ

40+张最全Linux/C/C++思维导图，收藏！

# 时间的表示方法

一般遵循ISO 8601标准：

https://www.w3.org/TR/NOTE-datetime

YYYY-MM-DDThh:mm:ss.sTZD (eg 1997-07-16T19:20:30.45+01:00)

其中的TZD表示time zone designator。

# U盘安装Linux

在程序中找到“启动盘创建器”即可。这也是防止变砖的最后一条路，反正BIOS是不可能安装坏的，随便折腾吧。

# wifi配置

Linux下的wifi配置主要使用iw系列命令，包括iw、iwconfig、iwlist、iwpriv。参见：

http://blog.csdn.net/liangyamin/article/details/7209761

Linux下的iwpriv（iwlist、iwconfig）的简单应用

# eBPF

BPF（Berkely Packet Filter）提供了一种当内核或应用特定事件发生时候，执行一段代码的能力。

这种能力最初被用于TCP包的过滤，正如名字所示，后来也被广泛用于profile领域。

BPF采用了虚拟机指令规范，所以也可以看成是一种虚拟机实现，使我们可以在不修改内核源码和重新编译的情况下，扩展内核的能力。

既然有虚拟机和bytecode，那么也需要相应的编译器了：

官网：

https://github.com/iovisor/bcc

参考：

https://ebpf.io/zh-cn/

一个eBPF的专栏

https://www.ebpf.top/

一个eBPF的专栏

https://zhuanlan.zhihu.com/p/659240633

再次实现了一个Lua性能分析器

https://zhuanlan.zhihu.com/p/590881470

万字长文让你深入了解BPF字节码

https://zhuanlan.zhihu.com/p/484788508

一文看懂eBPF：eBPF实现原理

https://zhuanlan.zhihu.com/p/393199226

BPF内部原理

# DTrace

https://zhuanlan.zhihu.com/p/24124082

动态追踪技术：Linux喜迎DTrace

# 大文件处理

在“大数据”时代，我们会经常遇到有大文本文件（上 GB 或更大）的情况。传统的文本编辑软件对处理这样的大文件不太有效，当我们试图打开一个大文件时会经常由于内存不足而郁闷的不行。

如果你只需要查看一个文本文件，并不对它做编辑，可以考虑下glogg。

`sudo apt install glogg`

如果需要修改的话，可以使用JOE。

`sudo apt install joe`

# 调整交换文件大小

```bash
fallocate -l 16G /swapfile
chmod 600 /swapfile
ls -lh /swapfile
mkswap /swapfile
swapon /swapfile
swapon --show
# Add this line to /etc/fstab to mount swap at boot
/swapfile swap swap defaults 0 0
swapoff /swapfile
```

# 剪贴板

Linux下的GUI程序的剪贴板功能一般是由X11提供的。

X11支持复数个剪贴板，每个剪贴板都有一个名字。一般常见/常用的：

PRIMARY剪贴板（选中的文本内容会被送到这个剪贴板，一般按鼠标中键可以粘贴）

CLIPBOARD剪贴板（更加接近于Windows下的剪贴板的存在，Ctrl-C/V功能一般作用于这个剪贴板）。

此外，X11的剪贴板里的内容似乎是由内容来源的程序来保存的，内容来源程序终止的话剪贴板就会被清空。这时一般需要一个常驻后台的剪贴板管理器（Clipboard Manager）来接管剪贴板的内容。

常用的Clipboard Manager的列表如下：

https://wiki.archlinux.org/title/Clipboard

相关的标准文件：

https://tronche.com/gui/x/icccm/

参考：

https://www.uninformativ.de/blog/postings/2017-04-02/0/POSTING-en.html

X11: How does “the” clipboard work?

https://wiki.archlinux.org/title/Clipboard

https://www.zhihu.com/question/66284095

电脑复制粘贴背后发生了什么？

https://linux.cn/article-7329-1.html

面向Linux的10款最佳剪贴板管理器
