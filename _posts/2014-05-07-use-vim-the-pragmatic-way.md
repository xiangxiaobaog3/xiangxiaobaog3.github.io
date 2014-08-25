---
layout: post
title: 如何优雅地使用Vim？(实用篇)
description: 如何优雅地使用Vim?关于Vim的一些实用的插件
keywords: Vim,Sublime text,Atom,Plugin,实用,Vundle,,YouCompleteMe,ctrlp,usevim
category: Code
tagline: --read & think
tags: [Vim,Code,Trivia]
---
{% include JB/setup %}

####接上篇[如何优雅地使用Vim？(美化篇)](http://jackiekuo.com/code/2014/05/06/use-vim-the-sexy-way/)

下面推荐几个我自己常用的Vim插件，这些插件功能强大，非常实用，能极大地提高你的工作效率。如果你还不知道它们的存在的话，还能改变你对Vim的看法！

**每个下载页面介绍得都很详细，就不一一介绍如何安装配置了*

###1.[Vundle](https://github.com/gmarik/Vundle.vim)

基于Git的功能强大插件管理工具，有了它插件的安装、更新和卸载就不用操心了。

###2.[YouCompleteMe](https://github.com/Valloric/YouCompleteMe‎)

Google工程师开发的一个支持模糊匹配的自动补全插件，速度很快，支持C、C++、OC、Python等多种主流语言。个人感觉比ctags等同类工具要好一些。

![YouCompleteMe](http://jackiekuo.com/images/YCM.gif)

###3.[ctrlp](https://github.com/kien/ctrlp.vim)

用过Sublime Text的就知道，一个Ctrl+P快捷键(Windows)能通过输入关键词快速打开文件，连回车键都不用按。

而插件ctrlp就给Vim实现了同样的功能，而且在同类插件中它性能最好。

![ctrlp](http://jackiekuo.com/images/ctrlp.png)

###4.[Multiple Cursors](https://github.com/terryma/vim-multiple-cursors)

说到Sublime Text，第一次看到它官网上关于Ctrl+D快捷键(Windows)演示时，我就惊呆了。多光标多行同时编辑，真是太酷了！

而Multiple Cursors这个插件就能使Vim实现同样的功能！而且还支持正则表达式！

<img src="http://jackiekuo.com/images/multiple-cursors1.gif" style="width:400px; height:180px;">

<img src="http://jackiekuo.com/images/multiple-cursors2.gif" style="width:400px; height:180px;">

###One More Thing

暂时还没写完，有空再更新。

Vim的插件实在是太多了，虽然不乏精品，但也有一些质量很差的插件混杂其中。插件过多不但影响Vim的速度，而且一些插件还存在冲突，环境迁移的时候也会很麻烦。

因此，我的原则就是，尽量不装没用的插件，而且这个原则适用于所有的编辑器（范围还可以再扩大些）。不能因为一些插件功能强大就去装它，还要看自己需要不需要。支持我用的语言吗？我真的需要吗？真的需要吗？真的吗？想好这几个问题，再做决定，才能真正的用好Vim，提高效率。

最后，推荐一个一直更新Vim插件和使用技巧的网站：[usevim](http://usevim.com/)