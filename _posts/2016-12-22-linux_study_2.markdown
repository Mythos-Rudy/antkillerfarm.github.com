---
layout: post
title:  linux学习心得（二）, bash, SWIG
category: linux 
---

# 查看内存使用情况（续）

## free命令

free命令的内容比较概括，主要包含系统内存的整体使用情况，不深入到进程一级。

# 查看CPU核数

复杂版：

`cat /proc/cpuinfo`

简单版：

`lscpu`

# 查看查看磁盘IO情况

## vmstat

`vmstat`

## iostat

`iostat -d -k 1 10 #查看TPS和吞吐量信息`

`iostat -d -x -k 1 10 #查看设备使用率（%util）、响应时间（await）`

`iostat -c 1 10 #查看cpu状态`

## iotop

`sudo iotop`

## dstat

dstat是后起之秀，号称可以替代vmstat、iostat、ifstat。

`dstat -d --top-io`

# 性能分析

Linux上主要有perf、gprof和valgrind三个性能分析工具。

参考：

https://cloud.tencent.com/developer/article/1063652

Linux性能分析工具与图形化方法

# 时间的表示方法

一般遵循ISO 8601标准：

https://www.w3.org/TR/NOTE-datetime

YYYY-MM-DDThh:mm:ss.sTZD (eg 1997-07-16T19:20:30.45+01:00)

其中的TZD表示time zone designator。

# wifi配置

Linux下的wifi配置主要使用iw系列命令，包括iw、iwconfig、iwlist、iwpriv。参见：

http://blog.csdn.net/liangyamin/article/details/7209761

Linux下的iwpriv（iwlist、iwconfig）的简单应用

# Inotify

一种高效、实时的Linux文件系统事件监控框架。参考文档：

http://www.infoq.com/cn/articles/inotify-linux-file-system-event-monitoring

Inotify: 高效、实时的Linux文件系统事件监控框架

# /usr

usr很多人都认为是user缩写，其实不然，这是unix system resource的缩写。

# lsof命令

lsof(list open files)是一个列出当前系统打开文件的工具。在linux环境下，任何事物都以文件的形式存在，通过文件不仅仅可以访问常规数据，还可以访问网络连接和硬件。所以如传输控制协议 (TCP) 和用户数据报协议 (UDP) 套接字等，系统在后台都为该应用程序分配了一个文件描述符，无论这个文件的本质如何，该文件描述符为应用程序与基础操作系统之间的交互提供了通用接口。因为应用程序打开文件的描述符列表提供了大量关于这个应用程序本身的信息，因此通过lsof工具能够查看这个列表对系统监测以及排错将是很有帮助的。

# nc命令

NetCat，在网络工具中有“瑞士军刀”美誉。它短小精悍（1.84版本也不过25k，旧版本或缩减版甚至更小）、功能实用，被设计为一个简单、可靠的网络工具，可通过TCP或UDP协议传输读写数据。同时，它还是一个网络应用Debug分析器，因为它可以根据需要创建各种不同类型的网络连接。

http://blog.csdn.net/wang7dao/article/details/7684998

# 定时任务

定时执行的任务可用crontab命令设置。

参考：

http://www.cnblogs.com/peida/archive/2013/01/08/2850483.html

crontab命令

## 常用命令示例

`find . -name *.txt`

查找文件夹（包括子文件夹）中所有的txt文件。

`strings /lib/tls/libc.so.6 | grep GLIBC`

strings能输出文件中的可打印字符串（可指定字符串的最小长度），通常用来查看非文本文件（如二进制可执行文件）中的可读内容。上例可查看glibc支持的版本。

`ps -efww`

ps默认只显示当前用户的进程。这里是全显示的示例。

`iconv -f gbk -t utf-8 -c 1.txt -o 2.txt`

将文件从gbk编码转为utf-8编码。

`mount -t nfs 192.168.0.1:/tmp /mnt/nfs`

挂载NFS。挂载点（即上例中的/mnt/nfs）必须事先创建。

# GnuGo

GnuGo是一个著名的开源围棋软件，但是它只有文字界面。一般使用Quarry作为它的GUI。

`sudo apt-get install quarry`

# DosBox

DosBox是Linux平台玩DOS老游戏的法宝。

安装：

`sudo apt install dosbox`

启动DosBox之后，需要使用如下命令加载本地文件夹：

`mount c ~/dosprom`

# 大文件处理

在“大数据”时代，我们会经常遇到有大文本文件（上 GB 或更大）的情况。传统的文本编辑软件对处理这样的大文件不太有效，当我们试图打开一个大文件时会经常由于内存不足而郁闷的不行。

如果你只需要查看一个文本文件，并不对它做编辑，可以考虑下glogg。

`sudo apt-get install glogg`

如果需要修改的话，可以使用JOE。

`sudo apt-get install joe`

# Linux知识图谱

![](/images/article/linux_perf_tools_full.png)

原图地址：

http://www.brendangregg.com/linuxperf.html

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

参考：

https://linuxtoy.org/archives/from-screen-to-tmux.html

从screen切换到tmux

http://mingxinglai.com/cn/2012/09/tmux/

tmux的使用方法和个性化配置

http://chengjin.li/2017/08/09/tmux-using-tutorial/

终端复用工具---tmux的安装及使用

# 环境变量

设置环境变量的方法：

1）临时的：使用export命令声明即可，变量在关闭shell时失效。示例如下：

`export PATH=/home/xyz/bin:$PATH;`

2）永久的：需要修改配置文件，变量永久生效。

在/etc/profile文件中添加变量（对所有用户生效）。修改文件后要想马上生效，还要运行`source /etc/profile`，不然只能在下次重进此用户时生效。

在用户目录下的.bash_profile文件中增加变量（对该用户生效）。同样需要source才能马上生效。

重要的环境变量：

PATH：可执行文件路径。

LD_LIBRARY_PATH：动态链接库文件路径

# 设置网卡eth0的IP地址和子网掩码

`sudo ifconfig eth0 192.168.2.1 netmask 255.255.255.0`

# 无线设置

查看无线网卡状态：

`iwconfig`

`wpa_cli`

扫描周围的wifi信号：

`iwlist scanning`

# tldr

tldr是一个采用示例说明的简化版的man。

官网：

http://tldr.sh/

该项目原生支持node.js，但也提供了其他多种语言的支持。

参考：

https://linuxtoy.org/archives/tldr.html

tldr: 简读Manpage

# 下载工具

wget和curl是最常见的下载工具。这里推荐使用axel，该工具支持多路http下载。

示例：

`wget -c <URL>`

`curl -C -o <file name> <URL>`

`axel <URL>`

参考：

http://os.51cto.com/art/201605/511423.htm

Linux用户宝典：用于下载的十大命令行工具

# OpenGrok

OpenGrok是一个阅读源码的Web系统。

官网：

http://oracle.github.io/opengrok/

代码：

https://github.com/oracle/opengrok

参考：

http://mazhuang.org/2016/12/14/rtfsc-with-opengrok/

搭建大型源码阅读环境——使用 OpenGrok

# Linux参考资源

https://www.zhihu.com/question/270348678/answer/460715569

生产力应用大汇总

https://mp.weixin.qq.com/s/QsgoONKwI7ds8Hnx2Wer6A

Linux从程序到进程

https://mp.weixin.qq.com/s/tguC-WOleKRWLfTmGdJlQg

Linux文件系统的实现

https://mp.weixin.qq.com/s/hTD9HEIbSx69wJhA_dv9Qg

Linux写时拷贝技术(copy-on-write)

https://mp.weixin.qq.com/s/1JiXL1f3SSjsBojlJSNOpQ

Linux的启动流程

https://mp.weixin.qq.com/s/ZfprFQjVANuCE2N693gZBQ

用户空间和内核空间

https://mp.weixin.qq.com/s/mTOzcdjaak-z6ypL9MR2Lw

小白科普：悲观锁和乐观锁

https://mp.weixin.qq.com/s/6MRi_UEcMybKn4YXi6qWng

操作系统中锁的实现原理

https://mp.weixin.qq.com/s/4tAxQ0auQfv5x7Dh3B-85g

Linux内存管理

https://mp.weixin.qq.com/s/w6t-_uZejmhWCVcPQgmFOg

进程与线程的一个简单解释

https://mp.weixin.qq.com/s/WZyuTtEfaTFLnCfvhOrp7g

虚拟化原理和分类

# bash

手册：

https://www.gnu.org/software/bash/manual/bash.pdf

## 空格和TAB的细节

在大多数编程语言中，空格和TAB都不是有意义的字符，有没有或者有多少都无所谓。但Linux Shell不是这样的，尽管它看起来并没有如python那样的对缩进的强制语言规定。

以下是它在使用空格和TAB时的一些细节：

1.makefile文件中，规则定义部分的shell脚本命令需要使用TAB开头，使用空格会出错。

2.if命令的格式：

{% highlight bash %}
if [ "$yn" == "Y" ] || [ "$yn" == "y" ]; then
	echo "OK, continue"
fi
{% endhighlight %}

注意一下上面脚本中的表达式[]之间的部分。其中所使用的空格不可省略，否则会出错。bash在处理[]表达式的时候，实际上调用了`/usr/bin/[`命令。如果把`[`当作特殊名称的普通命令的话，就会发现这里的空格用法实际上并不奇怪。

## 查看当前使用的shell

实时查看：

`ps |  grep $$  |  awk '{print $4}'`

非实时查看：

`echo $SHELL`

## return和exit的区别

return用于函数的返回，它只能用在函数中。

exit用于整个shell脚本的退出。

## 预定义变量

`$?`: 上条命令的返回值

`$$`: 当前shell的PID。

## shell如何把多行内容输出到一个文件

一行一行echo重定向显然是个笨办法，这里可以使用Here Documents语法。

例子：

{% highlight bash %}
(
cat<<EOF
line 1
line 2
EOF
)>a.txt
{% endhighlight %}

参考：

https://linux.die.net/abs-guide/here-docs.html

Here Documents

## 参考

https://blog.csdn.net/iot_flower/article/details/69055590

shell脚本第一行：#!/bin/bash的含义

https://mp.weixin.qq.com/s/ZaIX8jv9LMWmrHQb4ew-dQ

写好shell脚本的13个技巧

http://www.ywnds.com/?p=12325

Shell版俄罗斯方块

https://mp.weixin.qq.com/s/SBVEo53irSZfI40sBFZXWQ

shift：解决shell编程中的入参问题

https://mp.weixin.qq.com/s/T_XwLS6CIrkXbgXJVIo2Jw

一文了解十大Linux命令行工具！

https://mp.weixin.qq.com/s/euTQJy0HFVQotAY-KI2OzA

10个实战及面试常用Shell脚本编写

# SWIG

Simplified Wrapper and Interface Generator可以为C/C++的库生成其他高级脚本语言的Wrapper。

官网：

http://swig.org/
