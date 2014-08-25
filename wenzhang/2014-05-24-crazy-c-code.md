---
layout: post
title: 我见过的最疯狂的C代码
description: 敲代码敲累了？看一些养眼的代码休息一下吧
keywords: Code,C,Crazy,Code语言
category: Code
tagline: --read & think
tags: [C,Code]
---
{% include JB/setup %}

C语言是最强大的语言之一。但是到底它的强大表现在何处？写操作系统？Too young to naive!

[Quora](http://www.quora.com/What-are-some-of-the-most-amazing-C-programs)上众多程序员分享了自己见过的最令人惊叹的C语言代码。敲代码敲累了？看一些养眼的代码休息一下吧！

##1.如何优雅地写一封信

下面是[Brian Westley aka Merlyn LeRoy](http://www.westley.org/)写的一段C程序。但如果细读起来你会发现它是Charlie和Charlotte两人之间的书信！

*注：这段代码还能编译运行！*

<script src="https://gist.github.com/Jing0/ab5a970d3fbad3b4f647.js"></script>

*Copyright (c) 1990, Landon Curt Noll & Larry Bassel. All Rights Reserved.  Permission for personal, educational or non-profit use is granted provided this this copyright and notice are included in its entirety and remains unaltered.  All other uses must receive prior permission in writing from both Landon Curt Noll and Larry Bassel.*

##2.分分钟画一幅地图

这一小段貌不惊人的代码竟然能画出印度地图！！

<script src="https://gist.github.com/Jing0/0bc215121dd382366fde.js"></script>

<script src="https://gist.github.com/Jing0/903584da1060897a7e43.js"></script>

##3.自己输出自己的代码

`main() {char q=34,n=10,*a="main() {char q=34,n=10,*a=%c%s%c;printf(a,q,a,q,n);}%c";printf(a,q,a,q,n);}
`

看着这段代码，想起了`Tupper自我指涉公式`...

##One More Thing

国际上还有个专门的比赛[IOCCC-The International Obfuscated C Code Contest](http://www.ioccc.org/index.html)，评选那些最奇怪最疯狂最有创意的C语言代码，截至去年已经举办22届了。这些代码有的是图画，有的输出一些奇怪的东西，当然，它们都能完美地运行！

程序员玩起来创意，是谁也比不过的！