---
layout: post
title:  深度学习（四十四）——多标签学习, 多模态学习
category: DL 
---

* toc
{:toc}

# 多标签学习

多标签分类问题（也称细粒度分类），通常有两种解决方案，即转换为多个单标签分类问题，或者直接联合研究。前者，可以训练多个分类器，来判断该维度属性的是否，损失函数常使用softmax loss。后者，则直接训练一个多标签的分类器，所使用的标签为0,1,0,0…这样的向量，使用hanmming距离等作为优化目标。

参考：

https://mp.weixin.qq.com/s/sdQ0rWbDDMN_P0B_RiYZmw

分段映射：帮助利用少量样本习得新类别细粒度分类器

https://mp.weixin.qq.com/s/zeN7rjmAnvh_7BbTmScrZw

细粒度分类你懂吗？——fine-gained image classification

https://mp.weixin.qq.com/s/SCsdWLrBDAKzc9NLAK1jxQ

最新综述：多标签学习的新趋势

https://mp.weixin.qq.com/s/LtWMGRBk2sbPDjeC9PmJ7g

弱监督学习下的商品识别：CVPR 2018细粒度识别挑战赛获胜方案简介

https://mp.weixin.qq.com/s/hcoAL1AHm_HtderWU8fSBw

大连理工大学在CVPR18大规模精细粒度物种识别竞赛中获得冠军

https://mp.weixin.qq.com/s/31r9FjuJn9yxrZMnfozkMQ

全卷积注意网络的细粒度识别

https://zhuanlan.zhihu.com/p/24738319

“见微知著”——细粒度图像分析进展综述

https://zhuanlan.zhihu.com/p/42067661

CVPR Look Closer to See Better

https://mp.weixin.qq.com/s/52hm3Cq3TFRnTMfDppivSQ

中山大学等提出HSE：基于层次语义嵌入模型的精细化物体分类

https://zhuanlan.zhihu.com/p/48192930

Object-Part Attention Model for FGVC

https://mp.weixin.qq.com/s/slmod5rW4qRhxGnbNN2J8g

双线性汇合(bilinear pooling)在细粒度图像分析及其他领域的进展综述

https://mp.weixin.qq.com/s/JGQdHS_yqkOMrN_Z3jEb7A

基于深度学习的细粒度图像分类综述

https://mp.weixin.qq.com/s/L-1gkElxsMtT369fgJl86Q

旷视南京研究院魏秀参：细粒度图像分析综述

https://zhuanlan.zhihu.com/p/57086099

细粒度识别之Local Attention Network

https://mp.weixin.qq.com/s/6K4tXPlYLaXhexh6gElP5Q

多标签图像分类综述

https://mp.weixin.qq.com/s/bb3ZsXtiRmPvzQ-lfSXrZQ

基于Pascal VOC2012增强数据的多标签图像分类实战

https://mp.weixin.qq.com/s/2pJt9hlUFhR6mo1ughKkiA

超全深度学习细粒度图像分析：项目、综述、教程一网打尽

https://mp.weixin.qq.com/s/jyIrREnJQv4mW-H9ghO7_A

细粒度图像分类是什么，有什么方法，发展的怎么样

https://mp.weixin.qq.com/s/5Y4sQlt6DvgkAYtncByjzw

基于Pytorch的细粒度图像分类实战

https://mp.weixin.qq.com/s/232DjhM5sqWqPTv7PCaORA

ElementAI提出超复杂多尺度细粒度图像分类Attention模型

https://mp.weixin.qq.com/s/G-4w5jMuN-_zVARPeb0cqA

细粒度实体分类论文综述

https://mp.weixin.qq.com/s/FcSzjphpsWCB-nrtbjs4gg

如何掌握好图像分类算法？

https://mp.weixin.qq.com/s/IeLYy0Pp3HC_UujA0KYn1Q

多标签长尾识别前沿进展

https://mp.weixin.qq.com/s/m3sgoG15dtacGt1_Anrq6Q

使用NTS理解细粒度图像分类

https://mp.weixin.qq.com/s/6fcqXac7ihAeDuwzl_MxPQ

“神奇的”标签增强技术（Label Enhancement）

https://mp.weixin.qq.com/s/uLyllVhO-U5RrT4Q5XpiLA

细粒度多标签分类

https://mp.weixin.qq.com/s/IhPavQZmXIxxUzNSnnFCKg

南理工最新“深度学习细粒度图像分析”综述论文，带你全面了解细粒度图像识别与检索方法

# 多模态学习

https://github.com/HuaizhengZhang/Awsome-Deep-Learning-for-Video-Analysis

深度学习视频分析/多模态学习资源大列表

https://mp.weixin.qq.com/s/ruRkqBEdyj2Dx0WTO5Jhcw

多模态学习研究进展综述

https://mp.weixin.qq.com/s/g3rwPsusYi7gQopOHvdNrA

多模态学习调研

https://mp.weixin.qq.com/s/xzeNAuuDt_VLHDgvIkc-Mg

多模态情感分析简述

https://mp.weixin.qq.com/s/vpBPkjuCebSWh5qPLYHCkw

上海交大提出多模态框架“EmotionMeter”，更精准地识别人类情绪

https://mp.weixin.qq.com/s/BBg04rDtiqU-XrWortufNA

康奈尔&英伟达提出多模态无监督图像转换新方法

http://mp.weixin.qq.com/s/khOINUyrNV3TFfgNRheH0A

卷积神经网络压缩、多模态的语义分析研究

https://mp.weixin.qq.com/s/ywU4L659iRcmIgmV6RtbXA

DeepMind新研究连接听与看，实现“听声辨位”的多模态学习

https://mp.weixin.qq.com/s/1qhcyTXttgKWlw-Oy556Tw

TPAMI2019最新《多模态机器学习综述》

https://mp.weixin.qq.com/s/BczgUuh2FIvP5MG9xh87wQ

多模态多任务学习新论文

https://zhuanlan.zhihu.com/p/427323610

多模态中预训练的演变史

https://mp.weixin.qq.com/s/ipj8qpYRiYbIeXn2PZb1SQ

5G时代下多模态理解做不到位注定要掉队

https://mp.weixin.qq.com/s/UghgWBN7mE8oJdMUvjAjcQ

何晖光：多模态情绪识别及跨被试迁移学习

https://mp.weixin.qq.com/s/EMWpBP5iB1Qrleo3XNjbuQ

IEEE Fellow何晓东&邓力：多模态智能论文综述：表示学习，信息融合与应用

https://mp.weixin.qq.com/s/Yus55s1utTrjuzsrebJu_w

让机器读懂视频：亿级淘宝视频背后的多模态AI算法揭秘

https://mp.weixin.qq.com/s/4AzF6utrQhhEweRIM6zV3A

文本+视觉，跨模态预训练新进展

https://mp.weixin.qq.com/s/dG7Lr5fdmqJQaYOWgkk8iw

如何构建多模态BERT?这份UNC76页《LXMERT: 从Transformer学习跨模态编码表示》PPT告诉您

https://mp.weixin.qq.com/s/QIJ2c4L7KfjVEhIyKayJ-Q

阿里文娱多模态视频分类算法中的特征改进

https://mp.weixin.qq.com/s/THxlQX2MPXua0_N0Ug0EWA

BERT在多模态领域中的应用

https://mp.weixin.qq.com/s/GxQ27vY5naaAXtp_ZTV0ZA

通用的图像-文本语言表征学习：多模态预训练模型 UNITER

https://mp.weixin.qq.com/s/rjWOkwzX3IE59Kc9P9leAQ

格“物”致知：多模态预训练再次入门

https://mp.weixin.qq.com/s/0CUGispeZS04D6NhGkrucw

多模态深度学习：用深度学习的方式融合各种信息

https://mp.weixin.qq.com/s/Tli19SOum_muBoBaTtXKUQ

多模态中NLP与CV融合的一些方式

https://mp.weixin.qq.com/s/ondgiFryYqB6-sf-v4pLXQ

多模态预训练模型简述

https://mp.weixin.qq.com/s/TFHS5lZYFwcjP_SC1dAckA

多模态信息如何嵌入推荐系统？RecSys2021《多模态推荐系统》教程

# Capsule+

https://jhui.github.io/2017/11/14/Matrix-Capsules-with-EM-routing-Capsule-Network/

“Understanding Matrix capsules with EM Routing (Based on Hinton's Capsule Networks)”

https://zhuanlan.zhihu.com/p/42864711

胶囊网络到底是什么东东？

https://zhuanlan.zhihu.com/p/32106577

酉变换与递归神经网络

https://github.com/freefuiiismyname/capsule-mrc

基于capsule的观点型阅读理解模型

https://mp.weixin.qq.com/s/cskdgsysD7R_FKChAKmlDg

利用Capsule重构过程，Hinton等人实现对抗样本的自动检测

https://mp.weixin.qq.com/s/7fBXMvT4eyZrKhPKQTAIZQ

你听说过胶囊网络吗？

https://www.cnblogs.com/CZiFan/p/9803067.html

CapsNet胶囊网络

https://mp.weixin.qq.com/s/F9SGZPZj6gup_nOVuDel6A

与胶囊网络异曲同工：Bengio等提出四元数循环神经网络

https://mp.weixin.qq.com/s/4o9XHGwx5lYsJ7YfUNHSoQ

百年老图难倒谷歌AI，网友：是鸭是兔？连我都不能确定

https://mp.weixin.qq.com/s/dN1p7nuv6xtnIsSuY73CcA

基于GNN，强于GNN：胶囊图神经网络的PyTorch实现

https://mp.weixin.qq.com/s/lcJcaiMtYXGVOwa_sVsVfA

Hinton老爷子CapsNet再升级，结合无监督，接近当前最佳效果

https://mp.weixin.qq.com/s/A0m3lkIBCTFf5bzTQlYbgQ

基于胶囊网络的计算机视觉应用

https://mp.weixin.qq.com/s/BqsFIUrVEVz5kOFh3W93gQ

胶囊网络升级新版本，推特2000+赞

https://zhuanlan.zhihu.com/p/106330900

解读－Stacked Capsule AutoEncoder－堆叠的胶囊自编码器

https://mp.weixin.qq.com/s/ubi1L1Zlh4yZqCjZnpD58w

Capsule Network深度解读

# DRL参考资源++

https://mp.weixin.qq.com/s/0AM4eASolsPZ7GtPYVBqDQ

伯克利今年大热的DeepMimic开源了~

https://zhuanlan.zhihu.com/p/35567591

强化学习在关系抽取、QA场景的应用

https://mp.weixin.qq.com/s/zWo2iSiJBEBwnFF478xxfQ

DeepMind：探索人类行为中的强化学习机制

https://mp.weixin.qq.com/s/oOslkEklaZSbRb8eDDCRBw

天津大学、东京大学等研究：用深度强化学习检测模型缺陷

https://mp.weixin.qq.com/s/DNT9rMynbN4Th0AVDHeY_w

BAIR提出人机合作新范式：教你如何高效安全地在月球着陆

https://mp.weixin.qq.com/s/KqLCTSYk1C0wYpJw-hpc1g

论强化学习和概率推断的等价性：一种全新概率模型

https://mp.weixin.qq.com/s/zRXs3BCEqXUruw746rZusw

牛津大学联合7家单位发布AutoRL综述，还在手动调参吗？你已经落后了

https://mp.weixin.qq.com/s/wPWV6kxkRlYb9dMf6ADWkQ

史上首次，强化学习算法控制核聚变登上Nature：DeepMind让人造太阳向前一大步

https://mp.weixin.qq.com/s/U0K79ELLj4wsOR4sd5G4Vw

Vicarious详解新型图式网络：赋予强化学习泛化能力

https://mp.weixin.qq.com/s/C8hsGkHGtoaS9Vzm6Ub4tw

Berkeley提出“随机搜索”训练线性策略，提高RL的性能

https://mp.weixin.qq.com/s/uppNSwxNrw4_8NGBQv85xw

今日头条首次改进DQN网络，解决推荐中的在线广告投放问题

https://mp.weixin.qq.com/s/JtUuFdTK4Q5YwnVj3BFU2w

全参数化分布，提升强化学习中的收益分布拟合能力

https://mp.weixin.qq.com/s/amXiNKJPEkAnu2m5NAERVw

Top-K Oﬀ-Policy Correction

https://mp.weixin.qq.com/s/kNtzy9-6GbsRhlL-mxksew

基于强化学习的人机对话

https://mp.weixin.qq.com/s/w3SsadgKaL8-tlzYLvMm-A

讲真？一天就学会了自动驾驶——强化学习在自动驾驶的应用

https://mp.weixin.qq.com/s/nnWuIPk_6mI9IAKIUbx6KQ

深度强化学习解决交通控制问题

https://mp.weixin.qq.com/s/RNJonPJL9JY5OH2-1sZMQw

中山大学HCP实验室：基于树状结构策略的渐进强化学习

https://mp.weixin.qq.com/s/G2sFkuvSeYmhkFjjPRGI-Q

强化学习如何用于推荐？新南威尔士首篇《深度强化学习推荐系统》综述论文

https://mp.weixin.qq.com/s/fMjjGCzef-3SVIOlUf2EFA

强化学习如何用于推荐？厦大最新《强化学习推荐系统》综述论文

https://mp.weixin.qq.com/s/8cV3Z_vkC0_cyfO2nVKoSw

华人博士用强化学习回收了SpaceX火箭

https://mp.weixin.qq.com/s/_-WSoeOqXMhR7S0PtyYixQ

深度强化学习探索算法最新综述，近200篇文献揭示挑战和未来方向
