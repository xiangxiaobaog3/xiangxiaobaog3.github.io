---
layout: post
title: .viminfo出错的解决方法
description: .viminfo出错的解决方法
keywords: Vim,viminfo,terminal
category: Code
tagline: --read & think
tags : [Linux,Mac,Vim]
---
{% include JB/setup %}

今天在terminal下打开vim时出现一行错误代码，如下：

`$ vim`

`E575: viminfo: Illegal starting char in line: lipse/artifacts.xml`

`Press ENTER or type command to continue`

**分析：**.viminfo是用户主目录下的记录用户动作的日志文件。vim每次退出都会保存一个.viminfo在用户主目录，下次启动vim时就会读取这个文件，以达到继续编辑的目的。但如果vim没有正常退出或是其他情况，.viminfo就有可能损坏，vim读取失败后就会显示相应的错误信息。

**解决方法：**一般解决.viminfo出错就是把它删掉。

在terminal进入用户主目录，输入以下命令即可。

`rm -i .viminfo`

出现E???:viminfo:等错误时也是这样解决。