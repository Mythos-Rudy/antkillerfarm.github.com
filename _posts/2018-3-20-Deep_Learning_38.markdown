---
layout: post
title:  深度学习（三十八）——RNN进阶, 显著性检测
category: DL 
---

* toc
{:toc}

# RNN进阶

## IndRNN

https://mp.weixin.qq.com/s/cAqpclkkeVrTiifz07HC1g

新型循环神经网络IndRNN：可构建更长更深的RNN

https://mp.weixin.qq.com/s/7-K-nZTijoYCaprRNYXxFg

新型RNN：将层内神经元相互独立以提高长程记忆

## ODE

https://mp.weixin.qq.com/s/4CrPGKnR7RLN-2ROG5X4uw

ODE网络：一场颠覆RNN的革命即将到来

https://mp.weixin.qq.com/s/0vju0Q_DcIWwdEo9EEE3iQ

NeurIPS18最佳论文NeuralODE，现在有了TensorFlow实现

https://mp.weixin.qq.com/s/i6VEYjbac4QP3s51meN1VA

Hinton向量学院推出神经ODE：超越ResNet 4大性能优势

https://mp.weixin.qq.com/s/ZEIsyV-0aTvYn6K8GyANPA

硬核NeruIPS 2018最佳论文，一个神经了的常微分方程

https://mp.weixin.qq.com/s/uAiRTeYkZKy9q3d9v3dR5A

神经微分方程--钢琴和小提琴

## 参考

https://mp.weixin.qq.com/s/0TLaC8ACXAFEK5aMNK9O-Q

简单循环单元SRU：像CNN一样快速训练RNN

https://zhuanlan.zhihu.com/p/27104240

CW-RNN收益率时间序列回归

https://mp.weixin.qq.com/s/SeR_zNZTu4t7kqB6ltNrmQ

从循环到卷积，探索序列建模的奥秘

https://mp.weixin.qq.com/s/_q69BV1r46S9X5wnLuFPSw

关于序列建模，是时候抛弃RNN和LSTM了

https://mp.weixin.qq.com/s/m5GRNp6qDfVfC0mkQ4m4Yw

神经语言模型如何利用上下文信息：长距离上下文的词序并不重要

https://mp.weixin.qq.com/s/kuoUnt2Vhz9NhfnNqMFAhQ

DeepMind提出关系RNN：构建关系推理模块，强化学习利器

https://mp.weixin.qq.com/s/wfOzCxe3L2t11VguYLGC9Q

上海交大搞出SRNN，比普通RNN也就快135倍

https://mp.weixin.qq.com/s/f0sv7c-H5o5L_wy2sUonUQ

CNN取代RNN？当序列建模不再需要循环网络

https://mp.weixin.qq.com/s/h3fF6Zvr1rSzSMpqdu8B0A

电子科大提出BT-RNN：替代全连接操作而大幅度提升LSTM效率

https://mp.weixin.qq.com/s/OgN4rVDKH5WABIaRY7CHog

如何让RNN神经元拥有基础通用的注意力能力

https://mp.weixin.qq.com/s/KBLCrupGIuPa5nVrxcS5WQ

新研究将GRU简化成单门架构，或更适用于语音识别

https://mp.weixin.qq.com/s/kQozftKd_n_kYIF7KKCc8g

短视频那么多，快手如何利用GRU实现各种炫酷的语音应用

https://mp.weixin.qq.com/s/xwuM2Vj8G7UyuEyzTyO13A

将CNN与RNN组合使用，天才还是错乱？

https://mp.weixin.qq.com/s/c7XkzjLH1n5EtqdQik618g

Dropout在RNN中的应用综述

https://mp.weixin.qq.com/s/K6LK47_GCTeZJPAW0-Xp4Q

多伦多大学提出可逆RNN：内存大降，性能不减！

https://mp.weixin.qq.com/s/lvaWx7J4HFTvYxy7-B9vYg

周志华等提出RNN可解释性方法，看看RNN内部都干了些什么

https://mp.weixin.qq.com/s/YbdiEHb8ld1pp1ehgBzTOQ

将未来信息作为正则项，Twin Networks加强RNN对长期依赖的建模能力

https://mp.weixin.qq.com/s/ty8RyPREo_EA7O8vA2pQuQ

AI编曲震撼人心，RNN生成流行音乐

https://mp.weixin.qq.com/s/vIL-bKHZK-6eXZYWxrc9vw

这种有序神经元，像你熟知的循环神经网络吗？

https://mp.weixin.qq.com/s/GGK9T0DeyIdD5ahHy5uvfg

LightRNN：存储和计算高效的RNN

https://mp.weixin.qq.com/s/JGZpKSF5HPCMCD061jwq9A

Bengio等人提出新型循环架构，大幅提升模型泛化性能

https://mp.weixin.qq.com/s/GN0m5nWuV6VDYsTk0XLoDA

pytorch中如何处理RNN输入变长序列padding

https://mp.weixin.qq.com/s/bts9mdIrGIjO8UCUxSV-xg

Transformer的潜在竞争对手QRNN论文解读，训练更快的RNN

# 显著性检测

视觉显著性检测(Visual Saliency Detection)指通过智能算法模拟人的视觉特点，提取图像中的显著区域(即人类感兴趣的区域)。

https://blog.csdn.net/dawnlooo

一个显著性检测的专栏

https://mp.weixin.qq.com/s/Mi62oqtXUT5If_Dj4KmVYA

计算机视觉如何知道你想看什么？个人显著性检测

https://mp.weixin.qq.com/s/47TcGoasB9E_Et2zwl3OCw

全局对比度的图像显著性检测算法

https://zhuanlan.zhihu.com/p/65307842

快、好、实现简单并且开源的显著性检测方法

https://mp.weixin.qq.com/s/tmp1HXU7cLerLr0DY9NluQ

杂乱环境下的显著性物体： 将显著性物体检测推向新高度

https://mp.weixin.qq.com/s/urgkUcu2ZWQMGPZdArWzYg

PoolNet：基于池化技术的显著性目标检测

https://zhuanlan.zhihu.com/p/71538356

BASNet，一种能关注边缘的显著性检测算法

https://mp.weixin.qq.com/s/ntSH2aS4YHqrLaTAfWFLsQ

可选择性与不变性：关注边界的显著性目标检测

https://mp.weixin.qq.com/s/0T1QhiT_20BrerNcTjKreQ

南开提出边缘引导的显著目标检测算法EGNet，刷新主流数据集所有评价指标

https://mp.weixin.qq.com/s/p4lHnte3FYu6XtD3PnSeKw

光场显著性检测研究综述

https://mp.weixin.qq.com/s/8QrNvb-1zmrTWo5zThpyvg

U²-Net：使用显著性物体检测来生成真实的铅笔肖像画

# 秦汉+

岂止是尉比校大。要是太尉，那可是碾压一切将军的存在。

还有，唐朝时，十六卫的大将军是正三品。后来又增设十六卫上将军，从二品。那个年代，上将比大将还要高一级。

内地警衔，督比司高，香港警衔，司比督高。

https://www.zhihu.com/question/544068233

为什么古代尉比校大，而现代军衔制度要反过来？

---

麒麟阁十一功臣、云台二十八将、凌烟阁二十四功臣。

---

当时皇宫中南宫云台发生火灾，宦官中常侍张让、赵忠劝说汉灵帝聚敛天下钱，名曰“修宫钱“，每亩十钱，用来修宫室、铸造铜人。又下诏令州郡出纳材木文石，送到京师。大郡至二三千万，余各有差，百姓呼嗟。考虑到司马直在钜鹿郡太守任上清廉的名望，于是减免三百万钱，而司马直仍然拿不出，怅然说道：“我本应该是为民父母官，却反过来剥削百姓来应付朝廷的索取，我做不到！”于是称病不就，朝廷则再三催促司马直交钱。司马直无奈出发，行至孟津，留下遗书抨击卖官鬻爵的政策，然后服药自杀。

---

汉景帝刘启当太子的时候，有一天晚上要程姬侍寝。不巧的是，程姬来例假了，不能啪啪啪。但太子有欲望又不能憋着，她就把自己的一个姓唐的丫鬟梳妆打扮一番，给刘启送去。一夜风流之后，丫鬟竟然怀孕了，十月怀胎生下一个大胖小子，起名刘发。汉景帝即位后把丫鬟扶正，封了她做妃子，并把刘发封为长沙王。——因此后人把例假称之为“程姬之疾”。

后来刘发生舂陵节侯刘买，刘买生郁林太守刘外，刘外生巨鹿都尉刘回，刘回生南顿令刘钦，刘钦生刘秀。刘秀即东汉开国皇帝，光武帝刘秀。——所以，一个女人的一场例假，阴差阳错之间，竟然创造了一个两百年的帝国。

---

过去朝廷的官员从汉代开始每工作五天就要休息一天，称为“休沐”。就跟咱们现在公务员和国企员工休星期天一样。五天一休这个制度一直延续到隋代。而到了唐代则变成了十日一休，也就是每旬休一次，上旬，中旬，下旬都是逢十必休。一直延续。

---

九锡，先秦时通假为“赐”，读音作ci，汉以后改为“锡”，读音作xi。

---

长安令/咸阳令，陷害虐杀了一个平民。这人育有七个女儿，膝下没有儿子。按常理，女子柔弱，平民上告无门，这冤情只能含恨了。但是我大长安县自古民风彪悍，直到现在关中都有俚语：“金周至银户县，杀人放火长安县”。这七个女儿下了狠心要让父亲安息，于是苦修武艺，隐忍不发。终于有一天，她们逮住了机会，这日长安令/咸阳令出游，七女设法将仇人的车队堵截在了渭水桥上，一番苦斗，最终手刃了对方，为父报仇。

https://www.163.com/dy/article/DB1IE52K0521AU53.html

杀父之仇，弗与共戴天：汉代“七女为父复仇”的故事是如何失传的？

---

邯郸有个自称是汉成帝之子刘子舆的人被毫不留情地揭了老底。后汉书称他原名王昌，又名王郎，因为当初发生过有人自称是刘子舆而被王莽杀害的事件，便自称是真正的刘子舆，说自己出生时母亲为了逃避汉成帝皇后赵飞燕的迫害，将其假扮成其他人的孩子得以保全，辗转蜀郡、丹阳、长安、中山等地，以待天时。估计是王莽太不得人心，很多人都信了王郎的这套说辞，但刘秀不信，骂他是个假货。

https://www.zhihu.com/question/573860477

刘备到处渲染自己是不可考的中山靖王之后，当时的曹孟德与诸葛亮等人怎么就轻易相信了呢？

# 俄乌战争-

2014年7月，瑞典新纳粹分子、前本土防卫军狙击手米尔凯·斯基尔特加入“亚速”营。但他在2015年8月公开宣布：他在乌克兰的经历改变了自己，自己将不再相信纳粹主义，因为他在乌克兰的所见所闻让自己认识到——自己过去的纳粹思想是错误而愚蠢的。

https://mp.weixin.qq.com/s/wp8CBSc2cBJBddSws2ktzw

乌克兰正在进一步走向分裂！这次不在东部，而是西部。
