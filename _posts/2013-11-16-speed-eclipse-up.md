---
layout: post
title: Eclipse提速记录
description: 给Eclipse加速，启动加速
keywords: eclipse,java
category: Code
tagline: --read & think
tags : [eclipse,java]
---
{% include JB/setup %}

> eclipse的启动速度一直不怎么的，Mac OS X上的好像更慢，愧对我给它的“最喜欢的IDE”称号。
> 下面是给eclipse提速的笔记。


`版本：Eclipse Standard/SDK
 Version: Kepler Service Release 1`

`原本启动时间：14S`

##### 1.优化项目：eclipse.ini（/Applications/eclipse/Eclipse.app/Contents/MacOS/eclipse.ini）

 `-vmargs`
 
 `-Xverify:none`
  
  作用： 优化Class加载 跳过对字节码的验证

  效果：启动时间－4S

#####2.优化项目：加载项（Preference→General→Startup and Shutdown）

`取消全部加载项`

效果：启动时间－1～2S

#####优化后启动时间：8～9S

最后附上我的eclipse.ini以供参考。


`-startup`

`../../../plugins/org.eclipse.equinox.launcher_1.3.0.v20130327-1440.jar`

`–launcher.library`

`../../../plugins/org.eclipse.equinox.launcher.cocoa.macosx.x86_64_1.1.200.v20130807-1835`

`-product`

`org.eclipse.epp.package.standard.product`

`–launcher.defaultAction`

`openFile`

`-showsplash`

`org.eclipse.platform`

`–launcher.XXMaxPermSize`

`256m`

`–launcher.defaultAction`

`openFile`

`–launcher.appendVmargs`

`-vmargs`

`-Dosgi.requiredJavaVersion=1.6`

`-XstartOnFirstThread`

`-Dorg.eclipse.swt.internal.carbon.smallFonts`

`-XX:MaxPermSize=256m`

`-Xms40m`

`-Xmx512m`

`-Xdock:icon=../Resources/Eclipse.icns`

`-XstartOnFirstThread`

`-Dorg.eclipse.swt.internal.carbon.smallFonts`

`-Xverify:none`