---
layout: post
title: "Code On your iPhone－－Vim for iOS"
description: Vim for iOS的介绍与简单配置
keywords: editor,iOS,vim,emacs,vi
category: "Code"
tagline: --read & think
tags : [Code,Vim,iOS,App]
---

某一天，某个菜鸟coder发了一个帖子，“我是一个程序员新手，我是应该用Vi呢还是Emacs呢？”，于是乎，引发了程序员圈界一场旷日持久的战争－－[编辑器之战](http://zh.wikipedia.org/zh-cn/%E7%BC%96%E8%BE%91%E5%99%A8%E4%B9%8B%E6%88%98)。

以上纯属虚构。

有句老话说的好：“你可以把马带到水边，但是你不能强迫它使用你最钟爱的的代码编辑器。”:-P虽然我不想加入这场永无休止的Emacser和Vimer的争吵，但不得不承认的是，Vim以其快速、小巧、简单（相对Emacs）的特点为自己赢得了更高的普及率。在移动设备冲击PC生态环境的大环境下，`vi on everywhere`的口号也渗透到了iOS。软件开发商Applidium将Vim移植到了iOS平台，在[最新版本](https://itunes.apple.com/cn/app/vim/id492668168?l=en&mt=8)中，软件不光为iOS7优化了，还适配iPhone5的屏幕（真是业界良心，VLC for iOS也是他家的）。

![vimicon](http://pic.yupoo.com/jok3r/DCbN4kZg/small.jpg)

Vim for iOS基本上保留了vim所有的功能：支持编辑.vimrc，添加主题（这个感觉很不错，就是用iTunes传来传去有点麻烦），一般的插件都支持，不过大型插件支持的不是很好（就算支持，安装也是个问题）。

另外需要注意的是，因为iOS键盘没有相应的esc键，软件便将反斜杠`\`作为了esc键，感觉如果内置一个定制的键盘会好很多。

如果已经下载安装了，你就会发现Vim默认的字体小到了很难辨认的程度。这时就需要编辑.vimrc来调整字体。

输入`vi .vimrc`并将`:set guifont=Courier:h16`写入文件(将字体改为16px)。

如果想显示行号，可以接着写`set nu`。

开启语法高亮，`:syntax enable`。

关于配置vimrc，网上有大量资料，可以自行搜索，不再多说。

写完以后，在命令模式输入`:w`保存，再重新打开vim，就可以查看刚才写的配置文件的效果了。

![vimrc](http://pic.yupoo.com/jok3r/DCGpvE49/medium.jpg)

![vimhelp](http://pic.yupoo.com/jok3r/DCbNl5u0/medium.jpg)

开发商Applidium将软件的源代码放在了GitHub上，如果感兴趣，可以看看[Vim for iOS on GitHub](https://github.com/applidium/Vim)。