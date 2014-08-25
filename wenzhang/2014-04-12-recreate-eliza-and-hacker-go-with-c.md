---
layout: post
title: C语言版本的Eliza与Hacker Go
description: 用C语言重写Eliza。Eliza是早期的一项人工智能项目，能通过脚本理解简单的自然语言，并能产生类似人类的互动。
keywords: Eliza,C,Chatbot,Code,代码,hacker
category: Code
tagline: --read & think
tags: [Code,Emacs,C]
---
{% include JB/setup %}

去年曾用两篇博文介绍过Chatbot--Eliza，[从Emacs Doctor到ELIZA，看早期的人工智能](http://jackiekuo.com/code/2013/12/01/eliza-and-the-earliest-ai/)以及对lisp版本Eliza的简单分析[ELIZA是如何思考的——Emacs Doctor代码的简单分析](http://jackiekuo.com/code/2013/12/01/how-eliza-works/)。

不过毕竟只是是简单分析，如果亲自尝试过的话，你就会知道，在处理一些复杂语句时Eliza就不只是针对某些关键词做出冰冷死板的特定回应了。

昨天花了几个小时用C写了一个简单版本的Eliza，实现了最基本的功能——对某些关键词做出简单回应，我已经把它放在了GitHub上，以后有时间就继续改进[点击查看Eliza](https://github.com/Jing0/Eliza)。

![Eliza in c](http://pic.yupoo.com/jok3r/DG01itX7/medish.jpg)

另外，两个星期前做了一个C版本的Hacker Go（虽然现在网页版已经搁置很长时间了），[点击查看Hacker Go](https://github.com/Jing0/C_Program_Design_E4/tree/master/Hacker%20go)，[网页版Hacker Go](http://web-terminal.qiniudn.com/)。

![Hacker Go](http://pic.yupoo.com/jok3r/DG01kQRr/medish.jpg)

![Hacker Go](http://pic.yupoo.com/jok3r/DG01jQAK/medish.jpg)