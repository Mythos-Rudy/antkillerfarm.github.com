---
layout: post
title:  入行以来涉及的技术简史（二）, 我的AI简史
category: my story 
---

* toc
{:toc}

# 入行以来涉及的技术简史（续）

### 3）QT

同上。

### 4）.NET

.NET使用了一套与MFC不同的GUI框架。从接口来看，其实更像是MS的死敌Borland的VCL的那套东西。现在使用这个编写PC工具似乎已经非常普遍了，而且随着应用的广泛，目前自带.NET Framework的PC也越来越多。很多时候，我们只用发布程序就好了。同事W算是这方面的高手，基本上这边的PC工具有八成都是他主导制作的。将公司在这方面的水准提升了一个台阶。

### 5）GTK

这是去年下半年开始自学的GUI框架。主要原因是目前已有部分工作转移到Linux下，总要有个称手的GUI框架才好。其次，目前的工具代码，大多是copy自产品代码的某一部分。产品使用gcc作为编译器，而gcc的语法和VC也不尽相同。产品代码中使用的比较多的局部动态数组，VC到目前仍不支持。

## 3.移动平台

工作以来，一直在嵌入式领域打拼，也经历了不少的移动平台，罗列如下：

### 1）Wince/Windows Mobile

这是接触的第一个移动平台，在学校的时候，我甚至连SD卡都没见过。应该说Windows Mobile是iOs和Android崛起之前，最高端大气的移动平台。由于API与Win32 API高度兼容，上手难度也不高，着实风光了一把。同期的竞争对手Symbian由于对触摸屏的支持不好，加之硬件规格较低，对于导航地图之类的当时的“超级应用”来说，还是有些力不从心的。

### 2）Nucleares/Brew/MTK/Symbian S60/Symbian UIQ/Moblin

这些平台没有做过大的项目，但是看过其中的应用代码。应该说这些都是iOS和Android出现之前，功能手机和嵌入式设备的主流系统。

### 3）Android

没有在该平台上开发过商业产品。但是作为从其诞生之初就一直在关注的人士。无论对它的应用层，还是对它的中间层和驱动层都有一定的了解。基本上从见到Android的第一眼开始，我就预见到Nokia和黑莓的衰败。即便黑莓在稍后的2009～2010年达到它的顶峰，也不曾让我改变观点。

### 4）RTKE

这是飞利浦开发的一个实时内核，我在S公司工作期间主要用于手机基带芯片的控制。当时公司投入很大精力，想在一颗处理器上集成基带处理和应用处理的功能，其软件核心是在RTKE的基础上，搭建一个Linux虚拟机以运行Android应用。这个项目的初衷是推出千元以下的手机。但是后来随着硬件性能的提升和价格的下降，千元以下的手机的确是做出来了，但实际上所用的处理器的个数不仅没有减少，反而越来越多。

PS:RTKE的用途不仅于此，有同事说他之前在其他公司也用过RTKE，然后细谈才知道飞利浦的剃须刀上用的也是RTKE。

## 4.其他

研究生时代研究过CORBA技术，主要用于通信运营商的网管系统的应用。工作之后，很久都没有听说过这个名词。前段时间，在招聘网上，搜了一下，发现CORBA技术本身并未灭绝，但是用途居然还是局限在网管系统的应用上。而且由于体系的庞大低效，原先使用CORBA构筑的GNOME桌面等PC程序，也将IPC转为更高效（但不通用，也不支持联网）的DBUS技术了。

## 2018.8

https://coolshell.cn/articles/3008.html

Windows编程革命简史

这篇文章谈到的这些东西，我基本都经历过。ATL算是我曾经花费很长时间去学，但却最终没学会的东西。好在从事后的角度看，这东西也没多少公司用。可能安全领域用的比较多吧，比如网银插件。

当然，这些年也遇到了一些绕了一圈最终逃不过的技术。比如GPU里面的shader技术，当初做3D GIS用到过，现在做AI计算又遇到了。

## 2018.9

尽管我从未涉足游戏开发行业，但不可否认的是，游戏开发是我许多年前报考CS专业，并从事相关工作的初心。

2015年的时候，由于当时工作比较轻松，自己也进入了技术进步的瓶颈期。于是以玩票心态，操练了一下游戏开发，其实就是cocos2d-x和box2d，还为后者提供了中文手册，并被原作者接受为官方版本。

之后由于兴趣转移，加上自己也意识到错过了入行的最佳时间，遂搁置之。不料，3年之后，cocos2d-x已经败下阵来，江湖的主角换成了Unity和UE。。。

此间，还短暂接触了crossapp——一个在cocos2d-x上改造而成的跨平台UI库。不料，cocos2d-x的作者对这种用法很不赞成：

>因为app开发是：如果没事的话我就不刷新屏幕了。游戏引擎是：尽量每秒60帧刷新速度除非你叫我停下来。换句话说，app是事件驱动刷新的，游戏是自循环驱动刷新的。带来的结果就是耗电量、发热量等完全不同。

## 2019.1

我对于大数据平台一直很有兴趣，但由于工作内容更偏向于算法和DL，因此平台类的技术栈都只是略知一二的水平。

不得不说，平台类的技术栈更新换代十分迅速。2016年，还是Hadoop/Hbase的天下，Spark开始发力，OpenStack则已经走下坡路。到了2018年，主角换成了Docker、Kubernetes、Flink。

回顾2年前第一个舆情分析项目，自己对于NLP、DL一无所知，对于ML也只有肤浅的认识。仅仅凭借同事的一句提示——Solr，开始闷头开荒，一路下来竟也让我闯出了一番新天地。

那个时代的我对于分词用的HMM，也曾顶礼膜拜。如今想来，恍如隔世。

# 我的AI简史

2018.5

上一篇技术简史还是2014.12的事情，时间又过了3年半。除了在智能硬件上捣鼓了一年多以外，这几年就主要是在AI上折腾了。

2016.3的AlphaGo大战李世石事件，虽然新闻效应很大，对我的震撼也很大，但对于我从事AI，实际上并无直接关联。

我的AI之路的开端实际上非常偶然。某天闲逛，无意发现了一个开源app的UI使用了毛玻璃特效。作者特意指出该特效使用了Gauss filter。

接着便搜索到了一个介绍Gauss filter的blog，这是该博主OpenCV系列的其中一篇，于是从此入了CV的坑。这大概是2016年3月底的事情，距离AlphaGo大战李世石不过一周左右。

2016.4，公司开始涉足大数据研发，但暂时和我没有交集。

2016.5，参加某安防展，看到了CV在停车场中，对于车辆跟踪的应用，对CV兴趣更浓。同时得知同事L是此中高手。

2016.7，在OpenCV的官方手册中，发现了ML一词。接着找到了吴恩达早期的ML讲义，从此入坑ML。

2016.8，大数据项目进入开展阶段，我自告奋勇，负责算法的设计。从此成为职业AI人。

2016.10，入坑NLP。

2016.12，入坑DL。但是由于初期ML的基础较差，因此在看完MLP之后，暂时停了一阵子。2017.5以后，全面转入DL。

2017.10，入坑RL。

2018.3，入坑ASR。

---

2018.11

入坑AI已经有2年半了，相关的blog达150+。记得当初进入一个AI相关QQ群的时候，某AI书籍的作者进群推销。她的卖点是阅读过200篇论文，结果被群主鄙视了一番。当时作为萌新，颇有神仙打架的感觉，无从评判孰是孰非。直到如今，自己阅读论文的数量差不多也有200篇，才终于对AI略有心得。

---

2020.5

非常遗憾，ASR方面由于公司另有团队在做，没有跟下去了（2018.10）。

2018.8～10 研究Transformer。

2018.11~2019.3 研究style transfer。

2018.12 研究Wave-U-NET。

2019.3~5 研究GAN。

2019.8~2020.1 研究DRL。

2020.4 研究PGM。

---

2021.11

最近这一年，算法研究的不多，主要转向AI平台开发。

2020.4～2020.8 编写ONNX Runtime的Backend。

2020.8～2020.12 编写ARM NN的Backend。

2021.1～ 研究TF XLA和TVM。

# 机器人/无人驾驶参考资源+

https://zhuanlan.zhihu.com/p/73073753

基于深度学习的多传感器标定

https://mp.weixin.qq.com/s/m4KtRGoBgqcgF8ZBMjG6Hg

深层卷积神经网络在路面分类中的应用

https://mp.weixin.qq.com/s/nQq2tzK_2y2lEt9H14zdwA

自动驾驶中的决策规划算法概述

https://mp.weixin.qq.com/s/yIFgwxU-DI6NBogfmxqqKQ

基于深度学习的计算机视觉技术在无人驾驶中的应用

https://mp.weixin.qq.com/s/rA9AAVx7AlNuS1l4IUuG0w

深度学习技术在自动驾驶中的应用

https://mp.weixin.qq.com/s/4_jtb9gv20F6h1Ljw4JwEw

车载以太网通信的“套娃游戏”

https://zhuanlan.zhihu.com/p/86184886

行人的行为意图建模和预测(上)

https://zhuanlan.zhihu.com/p/86185203

行人的行为意图建模和预测(下)

https://zhuanlan.zhihu.com/p/90773462

多传感器数据深度图的融合：最近基于深度学习的方法

https://mp.weixin.qq.com/s/4tOYmCRiFN0xsG6vbedrrg

ADAS系统中的动态目标感知策略（一）

https://mp.weixin.qq.com/s/JT4p03m77ohOufL3JFecvA

从硬件角度剖析自动驾驶，为什么说它是复杂的系统工程？

https://mp.weixin.qq.com/s/UGdZCC80gQRTgHz9GV6USA

MEMS IMU/陀螺仪对准基础

https://mp.weixin.qq.com/s/v3gsmCWSI9pEwRolN8qWNA

基于深度卷积网络的自动驾驶多模态轨迹预测

https://mp.weixin.qq.com/s/R-17JgcGHG67KZ6yRYNFlA

基于Frenet优化轨迹的无人车动作规划方法

https://mp.weixin.qq.com/s/qZwqp5x6yEXbMBHGzevm0g

ACC自适应巡航控制系统介绍

https://zhuanlan.zhihu.com/p/57077589

自动驾驶中路上行人的行为和意图理解及预测

https://zhuanlan.zhihu.com/p/109900137

传感器融合-任务篇

https://zhuanlan.zhihu.com/p/109895639

传感器融合-数据篇

https://mp.weixin.qq.com/s/1sbL2vmugiIlSn_ehIOuig

车载多传感器融合定位方案：GPS +IMU+MM

https://mp.weixin.qq.com/s/5kJfhp3vi9uuSFaeONKfrA

打破传统方法，MIT新芯片帮自动驾驶汽车穿越浓雾

https://zhuanlan.zhihu.com/p/57781001

自动驾驶系统的硬件平台讨论

https://mp.weixin.qq.com/s/ZUxkZXLC0tPkzptFKtudhw

让机器人也能“问路”的视觉语言导航新方法

https://mp.weixin.qq.com/s/6OkLjK1bMbw6a3bvYn_DCQ

深度学习在自动驾驶感知领域的应用

https://zhuanlan.zhihu.com/p/57029694

自动驾驶中单目摄像头检测输出3-D边界框的方法一览

https://mp.weixin.qq.com/s/SZlwjnZrxCyaqRBg_sjQaA

浅谈自动驾驶中的行为风险识别（一）

https://mp.weixin.qq.com/s/QBnvLrD93b8cDEeNeZ5kAw

车联网正步入歧途，命悬一线的开始

https://zhuanlan.zhihu.com/p/553588646

最新的“视觉为中心的BEV感知”综述论文
