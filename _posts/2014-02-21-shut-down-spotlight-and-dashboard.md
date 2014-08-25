---
layout: post
title: 关闭Mac OS X的Dashboard和Spotlight
category: Mac
tagline: --read & think
tags : [Mac,Think]
---
{% include JB/setup %}

一直感觉OS X自带的Dashboard对我没有多大用处。自从用了Alfred之后，Spotlight也几乎没碰过（Spotlight占用的资源可不小）。很早以前就把这两个给关闭了，今天感觉有必要记录一下。不过如果用Onyx之类的，可以直接找到相关设置项，更方便一些。

*注：以下过程中可能需要输入系统密码*

### 关闭Dashboard

在终端中输入

`defaults write com.apple.dashboard mcx-disabled -boolean YES`

再输入

`killall Dock`

### 关闭Spotlight

1.在终端中输入

`sudo launchctl unload -w /System/Library/LaunchDaemons/com.apple.metadata.mds.plist`

禁用Spotlight服务。

2.删除菜单栏Spotlight图标（给相关文件重命名）

`cd /System/Library/CoreServices/`

`sudo mv Search.bundle/ Search2.bundle/`

`killall SystemUIServer`

### 恢复方法

1.开启Dashboard

在终端中输入

`defaults write com.apple.dashboard mcx-disabled -boolean NO`

再输入

`killall Dock`

2.开启Spotlight服务

`sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.metadata.mds.plist`

3.恢复Spotlight图标

`cd /System/Library/CoreServices/`

`sudo mv Search2.bundle/ Search.bundle/`