---
layout: post
title:  机器学习（三十六）——LightGBM, CatBoost
category: ML 
---

* toc
{:toc}

# Kalman filters（续）

https://zhuanlan.zhihu.com/p/40413223

卡尔曼滤波器实现详解

https://mp.weixin.qq.com/s/kBGhHCxq6idOOSGoLX5Kaw

手把手教你写卡尔曼滤波器

https://mp.weixin.qq.com/s/x0twRIdONCp3-qjhFJuCEQ

手把手教你写扩展卡尔曼滤波器

https://mp.weixin.qq.com/s/Nta9ksUkAVoX8arBGm7qqg

手把手教你实现多传感器融合技术

https://zhuanlan.zhihu.com/p/41767489

概率机器人——扩展卡尔曼滤波、无迹卡尔曼滤波

https://mp.weixin.qq.com/s/J27fVvYMRdoAgQtfXsywxg

OpenCV卡尔曼滤波介绍与代码演示

https://zhuanlan.zhihu.com/p/64007212

卡尔曼滤波家族

https://zhuanlan.zhihu.com/p/66646519

IKF(IEKF)推导

https://blog.csdn.net/baidu_21807307/article/details/51843079

浅谈卡尔曼滤波（Kalman Filter）

https://mp.weixin.qq.com/s/ZlyF1GcmpwZoT-3o4T567A

卡尔曼滤波算法及其应用

https://zhuanlan.zhihu.com/p/77327349

如何理解那个能造导弹军舰还把嫦娥送上天的卡尔曼滤波算法Kalman filter?

https://mp.weixin.qq.com/s/vAm0QDp_i2ec5pZbTmdHNA

傻瓜也能懂的卡尔曼滤波器

https://mp.weixin.qq.com/s/na0vVhECfBppTb7BmhRyzA

从限价订单薄中推导预测因子：卡尔曼滤波来搞定！

https://mp.weixin.qq.com/s/v460ql4RnJGbzbV0iZH4kA

深度解读卡尔曼滤波原理

https://mp.weixin.qq.com/s/Jlux3pZ4keVzkwWzgoPrEQ

深入浅出讲解卡尔曼滤波

https://mp.weixin.qq.com/s/BeIEjASATt3Qpef_Ag-cSw

卡尔曼滤波系列——经典卡尔曼滤波推导

https://mp.weixin.qq.com/s/t4GIPMB-6Vq7i8Q5PN6L-w

追狗，从入门到精通

https://mp.weixin.qq.com/s/EZ4JQM2vynTevUjFpW1h_w

追狗，从入门到精通2.0

https://zhuanlan.zhihu.com/p/128520715

自动驾驶定位技术-马尔科夫定位

https://zhuanlan.zhihu.com/p/138684962

自动驾驶感知融合-卡尔曼及扩展卡尔曼滤波(Lidar&Radar)

https://zhuanlan.zhihu.com/p/141059329

自动驾驶感知融合-无迹卡尔曼滤波(Lidar&Radar)

https://zhuanlan.zhihu.com/p/134595781

卡尔曼滤波(Kalman filter)含详细数学推导

https://zhuanlan.zhihu.com/p/166342719

卡尔曼滤波器详解——从零开始(1)

https://zhuanlan.zhihu.com/p/179480833

卡尔曼滤波器详解——从零开始(2)

https://mp.weixin.qq.com/s/3K9qdH9FXnYABpJoJkFcqw

使用卡尔曼滤波平滑时间序列，提高时序预测的准确率

https://zhuanlan.zhihu.com/p/35978617

线性动态系统与卡尔曼滤波

https://mp.weixin.qq.com/s/2rX6iRTYBk47V29fSTAMQQ

图解卡尔曼滤波(Kalman Filter)

https://mp.weixin.qq.com/s/PuvTkDhwbYv8TK8t-Zhcug

基于卡尔曼滤波的注意力机制—广告点击率预估中的用户行为建模   

https://longaspire.github.io/blog/%E5%8D%A1%E5%B0%94%E6%9B%BC%E6%BB%A4%E6%B3%A2/

卡尔曼滤波器

https://zhuanlan.zhihu.com/p/36745755

卡尔曼滤波：从入门到精通

https://zhuanlan.zhihu.com/p/338269917

从全状态观测器到卡尔曼滤波器

https://mp.weixin.qq.com/s/gb7CX8mbQNkMFVe3DIDT6Q

卡尔曼滤波最完整公式推导

https://mp.weixin.qq.com/s/vChWpG_2m53n8Bz-yfCohg

实操教程：用一维卡尔曼滤波器来估计运动物体的位置和速度

https://zhuanlan.zhihu.com/p/408783183

卡尔曼滤波的基本原理（也许是我写过最详细的推导）

https://www.zhihu.com/column/c_1303778703026126848

一个多传感器信息融合的专栏

https://www.zhihu.com/question/41823401

有什么将卡尔曼滤波讲得透彻的书籍或资料？

https://www.zhihu.com/question/588969519

组合导航和卡尔曼滤波，一个美国七十年代提出的理论，一个已经成熟的技术，研究生现在研究还有希望毕业吗？

# LightGBM

LightGBM是微软推出的boosting框架。

代码：

https://github.com/Microsoft/LightGBM

文档：

https://lightgbm.readthedocs.io/en/latest/

参考：

http://www.msra.cn/zh-cn/news/features/lightgbm-20170105

微软亚洲研究院：LightGBM介绍

https://zhuanlan.zhihu.com/p/25308051

比XGBOOST更快--LightGBM介绍

https://www.zhihu.com/question/51644470

如何看待微软新开源的LightGBM?

http://www.cnblogs.com/rocketfan/p/6005353.html

LightGBM中GBDT的实现

https://zhuanlan.zhihu.com/p/28768447

一个例子读懂LightGBM的模型文件

https://zhuanlan.zhihu.com/p/27916208

LightGBM调参指南(带贝叶斯优化代码)

https://mp.weixin.qq.com/s/zopaNDXABhPVqqUur9FFYg

lightgbm算法优化-不平衡二分类问题

https://mp.weixin.qq.com/s/JQasgzl-EpqBey7W6jKCTw

LightGBM大战XGBoost，谁将夺得桂冠？

http://blog.csdn.net/xwd18280820053/article/details/68927422

关于树的几个ensemble模型的比较（GBDT、xgBoost、lightGBM、RF）

https://mp.weixin.qq.com/s/TD3RbdDidCrcL45oWpxNmw

从结构到性能，一文概述XGBoost、Light GBM和CatBoost的同与不同

https://mp.weixin.qq.com/s/8IFKL0thCMBh40wUolbTVw

从XGB到LGB：美团外卖树模型的迭代之路

https://mp.weixin.qq.com/s/LoX987dypDg8jbeTJMpEPQ

终于有人把XGBoost和LightGBM讲明白了，项目中最主流的集成算法！

https://mp.weixin.qq.com/s/l6Fp5WTNH0b_cl2y7Az76Q

深入理解LightGBM

https://mp.weixin.qq.com/s/H9zkyO9oZAysWMyigd1tNw

LightGBM

https://mp.weixin.qq.com/s/RaWeiQwlQjCi1zz5S3tOmA

LightGBM的参数详解以及如何调优

https://mp.weixin.qq.com/s/9gEfkiZyZkoIgwRCYISQgQ

你应该知道的LightGBM各种操作！

https://mp.weixin.qq.com/s/YSDB6SSrU7xlzZ73PrjIAw

比赛杀器LightGBM常用操作总结！

https://mp.weixin.qq.com/s/_y16bW-afo9gOI5ObMBRYQ

Kaggle神器LightGBM最全解读！

https://mp.weixin.qq.com/s/A3b2L_0-atm5jJslhr50Bg

最新LightGBM进展介绍报告，39页ppt

https://mp.weixin.qq.com/s/M0W6-bLZcsdMsKBUAeKDnw

树模型奠基性论文解读——GBM: Gradient Boosting Machine

https://zhuanlan.zhihu.com/p/672584013

lleaves：使用LLVM编译梯度提升决策树将预测速度提升10+倍

# CatBoost

这是Yandex推出的Boost工具包。

官网：

https://catboost.yandex/

论文：

《Fighting biases with dynamic boosting》

代码：

https://github.com/catboost/catboost

官方还提供了一个可视化工具：

https://github.com/catboost/catboost-viewer

参考：

https://mp.weixin.qq.com/s/TAminQXid3qq5b8qkeN1rA

ClickHouse如何结合自家的GNDT算法库CatBoost来做机器学习

https://mp.weixin.qq.com/s/4qQxB4AthVAYKggEV3BHFw

ThunderGBM：快成一道闪电的梯度提升决策树

https://mp.weixin.qq.com/s/LxPkd6PUHWoHQCw-xyE9SQ

大战三回合：XGBoost、LightGBM和Catboost一决高低

https://mp.weixin.qq.com/s/E3pSPsG18053F5GG1Z8jNQ

一文详尽系列之CatBoost

https://mp.weixin.qq.com/s/eCZHpFvtDYnpI6jm2nEtnQ

深入理解CatBoost

https://mp.weixin.qq.com/s/pQ9_0d8sl5Sr5O360Risnw

使用CatBoost进行不确定度估算：模型为何不确定以及如何估计不确定性水平

https://mp.weixin.qq.com/s/o129MwpGzx8tzjUCkz1npw

使用CatBoost和NODE建模表格数据对比测试

# 明=

台湾开发史上，颜思齐最早率众纵横台湾海峡，招徕漳泉移民，对台湾进行大规模的有组织的拓垦，因而被尊为“开台王”。

郑军的海战模式不是后世英国海军的风帆战列纵队炮击战术，而是主动放弃大洋的制海权，将敌人引入水文条件复杂的峡湾，然后用火攻船四面封堵冲击敌舰，彼时西方海军尚未装备帕克转膛炮、哈乞开斯速射炮，对于小巧灵活的火攻船尚无有效遏制的方法。

但是只要在大洋上拉开距离，郑军就对36门炮的武装商船一筹莫展了（赫克托号）。

郑家缺乏先进生产力对制度的创新和建设，平日里扮演陆地和海上的黑社会，买郑氏令旗就可以做海贸，没令旗就直接劫财吞货，既没有颁布海事法令，对海上贸易和遇险救难发布明文规定，也没有鼓励和刺激外贸的措施，更没有引入西方的近代银行业和东印度公司制度，没有海事法院对贸易纠纷进行有效的管辖和治理，他们只躺平抽成，不建设。

海贼王：许心素、李魁奇、钟斌、刘香。

https://www.zhihu.com/question/341762009

如何评价明末的郑芝龙？

---

在明朝的时候，丽江土司是个很奇怪的存在，那就是它的上层土司汉化很深，能写诗作词还能丹青翰墨。甚至据说丽江土司家的姓氏木氏，都是大明黔宁王老朱皇帝的外甥沐英赏赐的，以显示黔国公和丽江府是一家。

但是它的下层也就是普通老百姓，却被严格禁止学习汉字汉文，也不准参加明朝科举。木家土司甚至找西藏的喇嘛另外发明了一种纳西文字。学会这种纳西文字的人可以在本地当喇嘛，要比其他百姓舒服一点，但是还是被土司压制的死死的。木家的公子颇有文化，在本地都找不到会汉字的文友，只好跑到云南鹤庆县去和当地汉人秀才混在一起。

这是为什么呢？土司不傻，它怕的就是属下百姓学会汉语汉字就去大明衙门那里去告状，说土司这不好那不好。那木家可就麻烦了，毕竟木家真的斗不过大明。因此木家土司只能禁止百姓和汉人接触禁止学习汉语，断绝一般人去大明衙门那里告状的可能。如果不这么做，那么土皇帝就当不稳。

最后木家被改土归流，其实过程也很简单。就是万历年间在丽江委派了学官，建立了学校。最后木家被改土归流，其实过程也很简单。就是万历年间在丽江委派了学官，建立了学校。然后也没有怎么样刻意削夺丽江的权力。到了满清雍正年间，丽江就降为土通判。到了民国年间就直接把它废除了，民国时期丽江被废的时候水花都没响。

---

今南方蛮子俱说辽人做官，不知辽人昔已杀尽，十无一二。初，清之破辽东也，恐民贫思乱，先拘贫民杀尽，号曰‘杀穷鬼’。又二年，恐民富聚众致乱，复尽杀之，号曰‘杀富户’。既屠二次，辽人遂空。-- by《明季北略》

https://www.zhihu.com/question/1898481086700427064

明军为何在辽东屡战屡败？

---

在穿越好望角时，耆英号展现出了高于英国船只的稳定性和极高的可操作性。

而随后因为一些主客观原因（客观风向风力原因，主观水手吃的太差要闹哗变），耆英号到达美国，在随后前往英国的过程中，耆英号又跑出了高于美国蒸汽邮轮的速度。。。

https://www.zhihu.com/question/3104098505

明朝造船技术已经很发达了，嘉靖年间倭寇犯边，当时朝廷为何不造船训练海军，直插岛国，从根源解决问题呢？
