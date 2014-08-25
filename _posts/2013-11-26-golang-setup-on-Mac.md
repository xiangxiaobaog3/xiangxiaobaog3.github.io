---
layout: post
title: Mac OS X下Go语言环境搭建过程及遇见的一些问题
category: Code
tagline: --read & think
tags : [Go,Mac,Brew,terminal]
---
{% include JB/setup %}

![image](http://pic.yupoo.com/jok3r/Dlb48L3V/medish.jpg?resize=200%2C120)

一直对Google的Go很好奇，最近看到Go的开发团队专门做了[Go tour](https://code.google.com/p/go-tour)来帮助开发者学习，就决定尝试下。

本来感觉一个很简单的环境搭建却出现了几个意想不到的问题，所以有必要 

## 一.安装

Go的官网上有[安装指南](http://golang.org/doc/install/)，看了下决定用brew下载安装，简单方便。

<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">$ brew install go</p>

安装后输入go可以查看一些命令的使用。

看下版本
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">$ go version</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">go version go1.1.2 darwin/amd64</p>

安装包会自动安装在 /usr/local/Cellar/go目录下。

## 二.配置

安装好后，在`/usr/local/Cellar/go/1.1.2/libexec/misc`中，可以看到有很多编辑器版本, 在其下可以自动配置不同编辑器来使用Go开发。

###配置$GOPATH和$GOROOT

输入以`go env`命令来查看环境变量

<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">$ go env</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">GOARCH="amd64"</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">GOBIN=""</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">GOCHAR="6"</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">GOEXE=""</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">GOHOSTARCH="amd64"</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">GOHOSTOS="darwin"</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">GOOS="darwin"</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">GOPATH="/Users/Jackie/gocode"</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">GORACE=""</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">GOROOT="/usr/local/Cellar/go/1.1.2/libexec"</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">GOTOOLDIR="/usr/local/Cellar/go/1.1.2/libexec/pkg/tool/darwin_amd64"</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">CC="gcc"</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">GOGCCFLAGS="-g -O2 -fPIC -m64 -pthread -fno-common"</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">CGO_ENABLED="1"</p>

`$GOROOT`是go的安装路径，配置后可直接在终端执行相关命令。注：Go 1.0之后安装包自带的Go tool会自动设置。

`$GOPATH`用来设置workspaces，即工作路径，可以设置多个。在Go  1.1之后被强制要求设置。具体见官方文档GoLang.org

关于这个`$GOPATH`,我安装时报错不断，真是让人头痛。

开始一直提示"`$GOPATH not set.`"，尝试了Stack Overflow上所有的方法，都没用，最后索性不弄了。没想到第二次打开又可以了，难道必须要重启？

后来就是在安装gotour时出现的一个问题，下面再说。

## 三.安装Gotour 

首先需要hg(Mercurial)，这是一个跨平台的分布式版本控制软件。安装后可以使用`hg`等命令。

当然，我还是用brew安装

<p><span style="color: #f5f5f5; font-family: Menlo; font-size: 13px; background-color: #000000;">$ brew install hg</span> </p>

安装成功后后输入`hg`命令会出现Mercurial的相关使用信息。

接下来需要建立$GOPATH所需要的目录，下面是官方给出的一个例子

	GOPATH=/home/user/gocode
 
    /home/user/gocode/
        src/
            foo/
                bar/               (go code in package bar)
                    x.go
                quux/              (go code in package main)
                    y.go
        bin/
            quux                   (installed command)
        pkg/
            linux_amd64/
                foo/
                    bar.a          (installed package object)
按照官方文档，这时在终端下使用

<p><span style="color: #f5f5f5; font-family: Menlo; font-size: 13px; background-color: #000000;">$ sudo go get code.google.com/p/go-tour/gotour</span> </p>

就可以安装Go tour了

如果安装中文的话地址改为

<p><span style="color: #f5f5f5; font-family: Menlo; font-size: 13px; background-color: #000000;">$ sudo go get bitbucket.org/mikespook/go-tour-zh/gotour</span></p>

*注*：中文地址我始终不能下，貌似被qiang了。

不过我安装的时候又出现了问题，

<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">abort: error: EOF occurred in violation of protocol  </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">package code.google.com/p/go-tour/gotour: exit status 255 </p>

反复尝试无果后，决定用`hg`直接手动下载

<p><span style="color: #f5f5f5; font-family: Menlo; font-size: 13px; background-color: #000000;">$ hg clone https://code.google.com/p/go-tour/</span></p>

再复制

<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">cp -r go-tour $GOPATH/src/pkg/code.google.com/p/go-tour/gotour</p>

再安装

<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">cd $GOPATH/src/pkg/code.google.com/p/go-tour/gotour</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">go install ./</p>

这时gotour就安装到`$GOPATH/bin`目录下了

![gotour](http://pic.yupoo.com/jok3r/Dlb47kTH/medish.jpg)

进入这个目录打开它就行了

<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">$ ls $GOPATH/bin</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">$ gotour</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">2013/11/26 15:48:56 Serving content from /Users/Jackie/gocode/src/code.google.com/p/go-tour</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">2013/11/26 15:48:56 A browser window should open. If not, please visit http://127.0.0.1:3999</p>

这时会自动打开浏览器，如图

![gotour](http://pic.yupoo.com/jok3r/Dlb48CVp/medish.jpg)

最后终于弄好了，不过不能每次都进这个目录再输入命令吧。

再配置一下bashrc就可以了。

<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">$ sudo vi /etc/bashrc</p>

然后在下面加上

<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">#Go tour</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">alias gotour='/Users/Jackie/gocode/bin/gotour'</p>

这样就完美了。

大功告成，赶快体验一下。

写的不好，如有错误欢迎指出。