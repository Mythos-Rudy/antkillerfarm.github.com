---
layout: post
title:  FreeType, FFmpeg, SDL, 图像处理软件
category: technology 
---

* toc
{:toc}

# FreeType使用指南

FreeType是一套跨平台的字体文件编程开发包。它的官网是www.freetype.org，你可以到这个网站获得最新的源代码。

网上的关于FreeType的文献很多。写得较好的有以下两篇：

http://www.cppblog.com/wlwlxj/archive/2006/11/08/14843.aspx   （文献A）

这篇文章比较概括，且有demo，适合入门之用。

本着原创的精神，上面文献提到过的，我不再复述，仅结合自己近来的研究，对一些关键点做一下说明。

## 1.编译FreeType库

由于我只用VC编过，所以这里只谈VC编库心得。这是我见到过的最友好的跨平台库，VS的工程文件都很齐全，不像其他的软件库往往只有make文件。而且FreeType库中，不但有PC的工程，还有Wince的工程。这里唯一要注意的是，在VS2005或更高版本中，有时需要调整工程的参数，以满足VS不同版本之间的移植需要。

## 2.字符对齐

文献A中的代码，显示单个字是没有问题的，但显示一排字尤其是数字符号时，就有问题了。虽然我们已经使用了FT_Set_Char_Size或FT_Set_Pixel_Sizes设定了字模的大小，但返回的字模并不都是一样大的。空白字符返回的字模，大小为0，逗号、句号返回的字模只有普通字的几分之一。这时就需要用glyph->bitmap_left和glyph->bitmap_top来指定起始位置。（详见文献B）

## 3.文献A勘误

文献A的代码中

`printf( " %d " , bitmap.buffer[i * bitmap.width + j] ? 1 : 0 );`

是不准确的，应该改为

`printf( " %d " , bitmap.buffer[i * bitmap.pitch + j] ? 1 : 0 );`

pitch指字模一行所占的字节数，在ft_render_mode_normal模式（即256灰度模式）下，pitch的值和width的值相等。但在ft_render_mode_mono模式（即黑白模式）下，这两个值一般就不等了。

黑白模式下，这句应为

`printf( " %d " , (bitmap.buffer[i * bitmap.pitch + (j>>3)]<<(j & 0x7 )) & 0x80 );`

## 4.小尺寸字体

并不是所有的矢量字库都包含小字体的，例如微软的宋体就不支持小于20*20的字模，所以，使用小尺寸字体时，必须仔细选择字库。

# FFmpeg

## 官网 & 安装

http://www.ffmpeg.org/

这是FFmpeg的官网。

值得注意的是，在官网的下载页面默认下载的是源代码。对于不需要源代码的使用者来说，需要在左下角的“Get the Package”处，根据所用平台选择合适的安装包。

安装包分为三类：

1.Static。只有一个可以自解压的exe文件。

2.Shared。相当于要用解压工具来解压的压缩文件。

3.Dev。相关链接库的的头文件和链接文件。

一般没有二次开发需要的话，下载Shared包是最佳的选择。

## 工具的使用

Fabrice Bellard是我崇拜的一位高人。他除了发明ffmpeg之外，还是Qemu和TinyCC的作者和圆周率计算记录的获得者（2009）。

之前的想法，ffmpeg主要是一套编解码框架，其本身的功能有限，需要进行二次开发方可使用。没想到其实它自带的程序，功能已经相当强大了。

安装包中包含三个命令行程序：

1.ffmpeg。编解码工具。功能十分强大，使用它可以很轻松的改变视频文件格式或者压缩视频文件。不过也因为视频格式及编辑选项实在太多，以至于想给ffmpeg做一个好用且功能齐全的GUI外壳都不是件容易的事情。

2.ffplay。播放工具。

3.ffprobe。多媒体流分析工具。

## 教程

官方教程《FFmpeg Basics》，在CSDN可以下载到。但该书偏重于如何使用ffmpeg的命令行工具以及编解码的基本流程。对于ffmpeg源代码，以及如何使用ffmpeg做二次开发讲的很少。

http://dranger.com/ffmpeg/

这篇文章是使用ffmpeg做二次开发的入门手册，写的不错。

## ffmpeg常见用法

1.转换视频格式

`ffmpeg -i src.avi des.mp4`

2.转换视频的尺寸

`ffmpeg -i src.mp4 -s 540x960 -acodec copy des.mp4`

3.屏幕录像

`ffmpeg -f alsa -ac 2 -i pulse -f x11grab -r 30 -s 1024x768 -i :0.0 -acodec pcm_s16le -vcodec libx264 -preset ultrafast -crf 0 -threads 0 output.mkv`

参考：

http://www.cnblogs.com/dwdxdy/p/3240167.html

FFmpeg常用基本命令

https://mp.weixin.qq.com/s/5S_NgjxoswrGcrQzBOyoYQ

视频数据处理方法！关于开源软件FFmpeg视频抽帧的学习

# SDL

目前网上查到的中文教程，多是针对SDL v1.2的。至于SDL v2.0的例子，Github上已经有不少了，可惜多是英文，查找起来还是不太方便。因此这里我也提供一个自己写的SDL v2.0的Hello World代码。

https://github.com/antkillerfarm/antkillerfarm_crazy/tree/master/HelloSDL

可以用这个代码确认SDL v2.0的环境搭建是否正确。

`sudo apt install libsdl2-dev`

# 图像处理软件

## GIMP

在linux下奋斗已经快半个月了，今天处理公务，需要处理一张图片，于是想到了GIMP。大名鼎鼎的Linux两大GUI库之一的GTK就是在GIMP开发的过程中做出来的。GIMP功能很强大，不过它的使用方法和windows自带的画笔还是有差异的。

1）画直线：

先在直线的起点单击，按住shift键然后点击直线的 终点位置，这样，你就可以获得一条很直的线了。

2）截屏

文件->创建->屏幕截图

3）图片格式转换

GIMP的格式转换功能非常强大，不但可以转换为常见的图片格式，还可以将图片导出成C语言头文件。但是需要注意的是，这些功能不在菜单项“另存为”中，而在菜单项“导出”中。

代码：

https://gitlab.gnome.org/GNOME/gimp/

自GIMP 2.10之后，核心代码转移到了一个叫做GEGL的项目中。GIMP只是调用GEGL的wrapper而已。

代码：

https://gitlab.gnome.org/GNOME/gegl/

参考：

https://mp.weixin.qq.com/s/PGBIPbKOqZb1WPZ-3x4CXQ

GIMP中的Noise Reduction算法原理及快速实现

## Inkscape使用技巧

关于绘图软件的认识，我是从Windows 3.1自带的“画图”开始的，那是1995年的事。到了1997年的时候，从杂志上知道了PhotoShop的大名，但是直到现在也从来没用过。再后来到了2007年的时候，开始使用Paint .NET。这个软件已经支持图层的概念，个人认为这是区分入门用户和中级用户的分水岭。

到了2013年，随着工作平台转向Ubuntu，开始接触并使用GIMP，但用的也不多。

一次偶然的机会，看到国外的一个牛人用Word绘制iOS桌面图标，从评论中才知道还有Illustrator这样的矢量绘图软件。

最近打算做一个软件，需要一组图标，无奈网上一直找不到合用的。于是只好自己来，然后就接触到了Inkscape。

以下就一些实用功能做一个备忘。这个备忘不能取代教程，仅是一种补充，自己也是找了好半天才弄清楚的。

1）画正圆、正方形

如果直接用椭圆工具，很难画出正圆来，这时可以按住Ctrl键，再调整大小的话，圆就是正圆了。同样的方法，也可用Ctrl键，绘制正方形，以及旋转特定的角度，例如45度。

2）旋转

选择图形之后，点击图形，会出现调整大小的箭头。再点击一下就会出现旋转的箭头。

3）中心对齐

打开“图形捕获->捕获对象中心”的功能之后，一但图形移动到另一个图形对象的中心时，屏幕上会出现相应的文字提示，这时松开按钮，图形就被对齐到另一个对象的中心了。

4）组合图形

有些图形可以分解为若干个简单图形。例如一个圆环由内圆和外圆组成。首先选中其中一个圆，按住Shift键后，再选中另一个圆。在菜单栏找到“Path->Difference”，这样就做好了一个圆环。

5)扇形

首先画一个圆，选中之后，点击左侧的“edit paths”工具的图标。然后会出现三个控制点，其中两个方形的控制点用于调整大小。选中其中的圆形控制点，并用左键拖动即可指定扇形的角度。这里需要注意拖动时鼠标所在的位置，当鼠标在圆内时，画出来的是弓形，否则，画出来的是扇形。

## ImageMagick

前面两个工具是典型的“所见即所得”的图形化工具，而ImageMagick是一个命令行工具。

通常来说图形化工具操作简单，效率也较高。但命令行工具也有其存在的价值，比如批处理。

假设需要批量处理10万张图片，如果没有自动化脚本，纯靠手工操作的话，绝对是一件囧事。

有的软件如ACDSee，虽然有批量处理的功能，但使用前提就是打开文件夹，并选中所需处理的图片。而打开一个有10万张图片的文件夹，是个非常耗时的操作，即使不使用缩略图也是如此。在这样的场合，命令行工具就有其存在的价值了。

我在之前的公司就遇到过这样的情况：

有一次（2008年），美工部门需要处理一批10万量级的图片。操作很简单，就是对每张图片生成一个尺寸较小的缩略图。但由于没有称手的工具，即使用ACDSee批量处理，半小时也只能处理1000张左右。整个工程预计耗时10天。而这样任务，大概每3个月就会进行一次。

于是，他们不得不求助技术部门提供解决办法。当时我花了2天的时间，写了一个批处理的图像处理工具，然后耗时20分钟处理完了所有的图片。不过该工具基于.NET平台，在Linux下无法使用。

而最近，我想将该软件移植到Linux上，于是查找Linux平台的图像处理工具库，找到了ImageMagick。仅花了半个小时，就编写好批处理的Python脚本，解决了这个问题。

ImageMagick调整图片尺寸的命令示例：

`convert src.jpg -resize 50% des.jpg`

ImageMagick将PDF转换为PNG的示例：

`convert -density 300 input.pdf -quality 95 output.png`

转换指定页（比如第一页）：

`convert -density 300 input.pdf[0] -quality 95 output.png`

为了转换PDF还需要修改配置文件/etc/ImageMagick-6/policy.xml:

`<!-- <policy domain="path" rights="none" pattern="@*" /> -->`

`<policy domain="coder" rights="read|write" pattern="PDF" />`

Word转PDF：

`libreoffice --convert-to pdf xxx.doc --outdir .`

## Others

Linux平台的绘图软件还有KolourPaint、mtPaint、MyPaint。

## Webp

WebP格式是google于2010年推出的一种旨在加快图片加载速度的图片格式。图片压缩体积大约只有JPEG的2/3，并能节省大量的服务器宽带资源和数据空间。

`sudo apt-get install webp`

`cwebp -q 80 image.png -o image.webp`

`dwebp image.webp -o image.png`
