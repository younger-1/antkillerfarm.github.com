---
layout: post
title: 上古软件开发
category: resource 
---

* toc
{:toc}

# 上古软件开发

金山影霸的VCD解压部分是盗用当时国外的一个叫Xing的收费共享软件里面的解码DLL（动态链接库）。金山影霸播放帧速高的原因是它在Windows操作系统播放时把屏幕设置成320x200全屏（VCD标准分辨率是352x240，所以抽行抽列显示后对画质影响不大），省去了图像放大和复制显示大图的步骤。金山影霸本质上是盗版Xing的DLL外面套一个320x200的全屏播放模式。

后来梁肇新单干后推出了可以解码VCD和DVD的超级解霸。超级解霸的MPEG2解码部分是拿开源软件mpeg2dec（后来改名叫libmpeg2，一直是GPL License，梁肇新又违反开源协议了）改出来的。

超级解霸里强调的主要优点其实没有太多技术含量。

1.强力纠错。（实际上是遇到读盘错误后直接跳过几秒钟，读下一段，CD/DVD读取光盘的默认行为是反复重读）

2.解码速度快。（实际上是梁肇新用汇编重写了部分C代码，比如像素从YUV转换到RGB的代码）

https://www.zhihu.com/question/20795371

超级解霸为什么当年那么火？后来又是为什么衰落的？

---

ABCDE五大高手：

Anders Hejlsberg：Turbo Pascal/Delphi/C#/TypeScript

Blake Stone：JBuilder

Chuck Jazdzewski：VCL/Angular 2

Danny Thorpe：Delphi

Erich Gamma：Eclipse/VS Code

https://mp.weixin.qq.com/s/xe7R2UZsyTzHN9xpdDTlXg

地球程序员之神

https://mp.weixin.qq.com/s/qWX17XcLQFRnip3JOkpRFg

孙悟空和Web争霸

---

作为一款早期计算机，IBM 705的编程是通过打孔卡输入machine instruction完成的。通过autocoder(作用相当于现在的assembler，不过部分用电路实现)，705可以把自定义的虛拟instruction转成实际对应的一系列machine instruction。这样做其中一个好处就是可以減小程序体积，用更少的punch card，写起来更快，输入进计算机时也更快。

因为是相对于定义在machine instruction下一层的micro instruction(现在叫microcode多些，没错这也是IBM搞出来的)的概念，所以取名macro instruction。

https://www.zhihu.com/question/482003599

在计算机编程领域里，宏(macro)是哪里来的？为什么要叫这个名字呢？

---

https://github.com/chrislgarry/Apollo-11

Apollo 11登月代码成Github热度第一

https://mp.weixin.qq.com/s/0WAXiveeT3BPyowya0y2Ag

揭秘阿波罗11号大脑：人类的一大步，也是机器的一大步！

https://mp.weixin.qq.com/s/5aezQzLIqNwJBEYR62-TQg

我在1969年写代码

https://mp.weixin.qq.com/s/ksAz2w5F7GF5TGJtF13OLA

50年前的程序员们，拯救了阿波罗号登月飞船

https://mp.weixin.qq.com/s/t8q-i5k5V44RfbCtSVQonw

改变世界的代码行

https://mp.weixin.qq.com/s/t8q-i5k5V44RfbCtSVQonw

诺基亚经典游戏《贪吃蛇》的前世今生

https://mp.weixin.qq.com/s?__biz=MzA4MDExMDEyMw==&mid=2247487079&idx=1&sn=9d29f53cd518b4dcb8ab8c27159dee41

互联网大佬学历背景大调查，不要再相信“学习无用论”

https://www.zhihu.com/answer/658973076

为什么上古编程语言（比如COBOL）总喜欢把代码全部写成大写字母？

https://mp.weixin.qq.com/s/gv0X080hHtKakjZMzVaZ-w

80岁COBOL码农：“扶我起来，这个bug我会修。”

https://mp.weixin.qq.com/s/VeSBuwWMx0xd2GuPSpE0ZA

上古语言从入门到精通：COBOL教程登上GitHub热榜

https://mp.weixin.qq.com/s/XPuJJm3k8gDl17oVmtdGtA

代码回忆录：第一行Hello World，第一个弹窗广告的代码是怎么写的？

https://www.zhihu.com/answer/840708044

怎样评价《数码宝贝》第一部中的泉光子郎的编程水平？

https://mp.weixin.qq.com/s/yDaIuhjhjqL-Vtl1gwcd0A

计算机编程的历史演进：用50种编程语言写“Hello,World!”程序

https://mp.weixin.qq.com/s/Dqe5B0ooayRU79CGulq71g

重启尘封十年的代码！回到未来的人人网，如何用新技术唤醒老数据？

https://www.zhihu.com/question/50076174

为什么魂斗罗只有128KB却可以实现那么长的剧情？

https://mp.weixin.qq.com/s/_rybr3Pnmt6Rr3RWxGTCXQ

为什么有32个关卡的超级马里奥兄弟只要64KB？

https://www.w3cschool.cn/article/leijuncode

分享雷军22年前编写的代码

https://mp.weixin.qq.com/s/movz5aesYdZZZHle-hHRIw

诞生于穿孔纸带时期的语言，ALGOL 60今年60岁了

https://mp.weixin.qq.com/s/aYGcJaLwbuXzjI5z1Crsrw

LeCun自曝使用C语言23年之久，2年前才上手Python，还曾短暂尝试Lua

https://mp.weixin.qq.com/s/vBFOQjJr27AeRsqCej85iA

70年前，在苏联第一家AI LAB从事AI研究是种什么体验？

https://mp.weixin.qq.com/s/jHXri6x6a1fPISEwlm_4Eg

《红警1》源码放出，众网友GitHub怀古！4K高清“重制版”开启预售，登顶Steam畅销榜第三

https://mp.weixin.qq.com/s/L6GP0LiCQX0Z2lps3Y0ekQ

Matlab简史

https://mp.weixin.qq.com/s/7cf14CEDa-LHFvO8gyedzg

为什么老编辑器Vim这么难用，却很受欢迎？

https://mp.weixin.qq.com/s/b-34Y230B_I56Epf64hYDQ

宇宙第一IDE到底是谁？

https://mp.weixin.qq.com/s/gSW5lxCoo9JkH1JRp6hfzA

30年前未曾发行的任天堂红白机游戏，被这个团队从21张软盘中重新恢复了，还是3D的

https://mp.weixin.qq.com/s/E3_UrGoN1uSmD_4NYG-YWw

来看看比尔盖茨当年写的BASIC解释器源代码吧，你就知道泰勒级数有什么用了

https://mp.weixin.qq.com/s/RzrQpJ8M4SoY6YXhUQNWHg

你上世纪写的代码现在还work吗？挑战者：我需要一个读磁带的机器

https://www.zhihu.com/question/420656795

有哪个高手可以解读“世界黑客编程大赛第一名的作品（97年Mekka ’97 4K Intro）”?

https://mp.weixin.qq.com/s/21eCFfRZYyTstnw777-Fhg

Java的战争（Oracle vs Google）

https://mp.weixin.qq.com/s/af_MzLovqnt5JemXBQGdxg

Java的战争(后续)

https://mp.weixin.qq.com/s/oeusDoCSYiwwX61H_6wQHw

浏览器（内核）发展史

https://www.zhihu.com/question/439434803/answer/1679210108

如何评价大连车务段现在车系统瘫痪，“全力攻关一昼夜”恢复Flash运行?

https://mp.weixin.qq.com/s/YOcKv4InA1G7sdERanGZSA

《是男人就下100层》真的有隐藏剧情！

https://mp.weixin.qq.com/s/popvQv-CM7--5ByTMpeaxA

编程语言考古：曾经影响一代人的BASIC，原来还有前身

https://mp.weixin.qq.com/s/K-KIA18cCj6ANM4Sb7fEvw

50年长盛不衰，SQL为什么如此成功？

https://mp.weixin.qq.com/s/3ZszI7PupWsuTvy69BwPnw

“C语言之父”40年前搞的操作系统复活！Linux、Windows都借鉴过它（Plan 9）

https://mp.weixin.qq.com/s/ywTkMMP6ysBfByIXW3_xeQ

全世界下载量超100亿，curl怎样成为影响世界的开源项目？

https://mp.weixin.qq.com/s/lqGCGj1EuwRvg6S9Dt3yEg

PDF之父、Adobe联合创始人离世，乔布斯收购未果给了他第一桶金

https://mp.weixin.qq.com/s/x-N7n7RkrvcCXT4C7UxPSQ

Linux之父：财务自由以后，我失眠了！

https://mp.weixin.qq.com/s/wIIQQibtFR3cecOpmNenvQ

YouTube博主实测病毒之王“熊猫烧香”，当年是它太强还是杀毒软件太弱？