---
layout: post
title: ELIZA是如何思考的——Emacs Doctor代码的简单分析
description: ELIZA是如何思考的——Emacs Doctor代码的简单分析
keywords: Emacs,Eliza,Lisp,AI，人工智能,Mac,Terminal
category: Code
tagline: --read & think
tags : [Algorithm,Code,Emacs,Trivia]
---
{% include JB/setup %}

`版本：Gnu Emacs 20.2.2.`

**使用的源代码:**[点击查看]( http://www.csee.umbc.edu/courses/471/papers/emacs-doctor.shtml
) 

输入以后，Doctor会首先结合句子长度和关键词来进行选择，注意，是结合。我看到有的文章说是关键词为主，其实并不是这样，比如输入“unix”，并不是直接匹配“mach”类型。

一般Doctor所作的输出都是在一个个list中选取的。比如句子长度过短而句子中又没有特定关键词，就会被定义为short，然后结果就会从“shortlst”中选取。

另外，这些list还会结合一些语气词（如*hmmm*，*well*），短语（如*feelings about*，*thoughts on*），形容词（如*vivid*，*boring*）等生成句子，来使它看起来更像是人机对话。

 Emacs Doctor把269个关键词分为26类，并归为“doctor-put-meaning”，下面是“doctor-meaning”的全部分类

`howdy`打招呼

`mach`机器／计算机

`foul`脏话

`toke`放松

`drug`药物

`loves/love` 爱

`hates/hate` 恨

`state` 状态

`desire` 渴望

`mood` 心情

`fear` 恐惧

`sexnoun` 关于性的名词

`family` 家庭

`death` 死亡

`symptoms` 症状

`alcohol` 酒精

`sexverb` 关于性的动词

`conj` 连词

`when` 时间连词

`rms` Stallman<sup>注</sup> 

`school`学校

`eliza` 这个不用解释了吧

`sports`运动

`math`数学

`zippy` 有活力

`chat` 这个只有“Chat”一个关键词
 

*注：这个有意思了，不知道“Stallman”的自己Google。*

#####事例：

<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Know Stallman？</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;"> </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Have you been a friend of Stallman?</p>
所以说，当你问About Stallman时,它会回复一个带有Stallman的句子。

请注意，“Stallman”，是大写“S”的，而在Doctor里一般情况下名字是不可能出现大写字母开头的，如问的是“Tom”，会输出“tom”。这个也算是个彩蛋吧！向自由软件致敬！

每一个“doctor-put-meaning”对应一个函数defun和一个lst（list）

#####输出过程探究

1.输入“Know unix?”

2.“unix”属于“mach”（代码：(doctor-put-meaning unix ‘mach)）

3.调用函数defun doctor-mach ()

4.函数查询machlst，并从machlst的几个句子中选取（貌似是按顺序选取的），见下面。
machlst代码：

	(make-local-variable ‘machlst)
	(setq machlst 
	‘((you have your mind on (// found) \, it seems \.)
	(you think too much about (// found) \.)
	(you should try taking your mind off of (// found)\.)
	(are you a computer hacker \?)))
测试：

<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">know unix?</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000; min-height: 15px;"> </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">You have your mind on unixs, it seems.</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;"> </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">know unix?</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000; min-height: 15px;"> </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">You think too much about unixs.</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;"> </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">know unix?</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000; min-height: 15px;"> </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">You should try taking your mind off of unixs.</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;"> </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">know unix?</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000; min-height: 15px;"> </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Are you a computer hacker?</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;"> </p>

 
这样就完成了一次和Doctor的对话。

写的不好，如有错误欢迎指正。