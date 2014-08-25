---
layout: post
title: 找回OS X Mavericks中的网络实用工具
description: 找回OS X Mavericks 10.9 中隐藏的网络实用工具
keywords: terminal,utility,mac,网络实用工具
category: Code
tagline: --read & think
tags : [Linux,Mac,Vim]
---
{% include JB/setup %}

更新到Mac OS X 10.9后，很多人会发现Utilities里没有了Network Utility（网络实用工具）。

虽然它的功能完全可以在terminal中实现，但是在这里列出来打开它的方法以供需要的人参考。

用Spotlight强大的搜索功能就可以找到。如图：

![image](http://pic.yupoo.com/jok3r/DjXfPB2y/medish.jpg?resize=625%2C113)

可以看到地址为/System/Library/CoreServices/Applications

打开Finder，shift＋command＋G，粘贴地址，前往文件夹。

![image](http://pic.yupoo.com/jok3r/DjXcGIgO/medish.jpg?resize=625%2C426)

这时就可以看到程序的文件了。

然后再给它做个替身，把替身移动到/Applications里，这时就会在Launchpad中显示网络实用工具了。

![image](http://pic.yupoo.com/jok3r/DjXcHdG9/medish.jpg?resize=298%2C241)

另外，其实Mavericks是给它提供了进入方法的，不过这入口有点偏僻。

打开“系统信息”，选择“窗口”，这时就能看到被打入冷宫的网络实用工具了。

![image](http://pic.yupoo.com/jok3r/DjXcGL1T/medish.jpg?resize=355%2C127)