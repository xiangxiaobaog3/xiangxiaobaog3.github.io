---
layout: post
title: 从Emacs Doctor到ELIZA，看早期的人工智能
description: 从Emacs Doctor到Eliza，分析早期的人工智能与Lisp
keywords: Emacs,Eliza,Lisp,AI，人工智能,Mac,Terminal
category: Code
tagline: --read & think
tags : [Algorithm,Mac,terminal,Emacs,Trivia]
---
{% include JB/setup %}

在Mac中学习一些Terminal命令时尝试过Emacs Doctor，当时只知道这个可以和机器聊天小程序是集成在Emacs中的。最近发现Emac Doctor背后是一个早期的人工智能项目——ELIZA，仔细研究了一下，来头不小。

### 1.Emacs Doctor长什么样？

如下

![image](http://pic.yupoo.com/jok3r/DlYAuMoy/medish.jpg?resize=600%2C459)

### 2.如何找到她？

Emacs中输入“xdoctor”即可。Terminal中需要先输入“Emacs”，再“shift＋esc”。

### 3.这个Doctor怎么用？

找到Doctor后，输入你的问题，按两下“Return”，Doctor就会回答你的问题。

不过貌似这个精神治疗师的回答会让你更加神经。

下面是我和她的一段对话。

![image](http://pic.yupoo.com/jok3r/DlYAuZHv/medish.jpg?resize=600%2C459)

### 4.Emacs Doctor到底什么来头？

说到Emacs Doctor，就不得不说ELIZA（[维基百科-ELIZA](http://en.wikipedia.org/wiki/ELIZA)）。

Eliza是早期的一项人工智能项目，被MIT的41岁计算机科学家Joseph Weizenbaum在1964-1966年开发出来，并以萧伯纳的戏剧作品[《卖花女》](http://zh.wikipedia.org/wiki/%E8%B3%A3%E8%8A%B1%E5%A5%B3_(%E6%88%B2%E5%8A%87))（不是《茶花女》）中的主人公的名字命名（因此本文用“她”来称呼）。ELIZA的智能之处在于她能通过脚本理解简单的自然语言，并能产生类似人类的互动。而其中最著名的脚本便是模拟[罗吉斯心理治疗师](http://en.wikipedia.org/wiki/Rogerian_psychotherapy)的Doctor。GNU Emacs Doctor则是这个脚本的另一个版本。

ELIZA在1966年被发布出来以后，引起了不小的轰动，与ELIZA“聊天”的用户有时会误以为自己是在和人类，而不是和一个程序交谈。但是实际上ELIZA根本不知道自己在说什么。它只是按固定套路作答，或者用符合语法的方式将问题复述一遍。甚至有一段时间，人们认为这种思路可以做出通过图灵测试的程序。

Weizenbaum很吃惊很多用户会忽视自己面对的是一个机器，而对ELIZA敞开心扉（这种情况也叫做[ELIZA effect](http://en.wikipedia.org/wiki/ELIZA_effect)，ELIZA效应）。虽然Weizenbaum创造的ELIZA使他在人工智能领域成就斐然，但他并不认为AI能与人类的情感和智慧相比。1976年Weizenbaum出版著作《计算机的力量与人类的推理》，书中表示人工智能的滥用可能损害人类生命的价值，并对计算机和人类的关系进行了探讨。

关于这段历史，可以看看[《面对互联网：我们已经丧失了人性》](http://lz.book.sohu.com/chapter-19176-114681445.html)。查到有两部关于Joseph Weizenbaum和ELIZA的电影[《Weizenbaum. Rebel at Work.》](http://movie.mtime.com/111521/)和[《Plug & Pray》](http://movie.mtime.com/138645/)，打算有时间看一下。

Weizenbaum最早是用Lisp写的ELIZA。后来出现了很多其他语言的版本，著名的有Bernie Cosell重写的Lisp版本，Jeff Shrager的BASIC版本，还有就是GNU Emacs中的Emacs Doctor了。

另外，有一个用Perl写的改进版本的ELIZA（[Chatbox-ELIZA](http://search.cpan.org/dist/Chatbot-Eliza/)），好像只能装到UNIX内核的机器上，我尝试了下**。ELIZA体验过程及更多请看文章最后“ELIZA体验”。**

作为最早的机器智能的体现之一，ELIZA可以说是一个里程碑。不管它有多么简陋，但它是将人－人互动的感觉带到了人机互动上的第一次尝试。

总结一下，ELIZA有以下影响：

* ChatterBot：ELIZA可以说是第一个Chatterbot——聊天机器人，你现在依然可以在很多Chatterbot中发现ELIZA的影子。不得不说的是，两年前Apple的Siri发布时，ELIZA也被再次请出，用来吐槽“智能”的Siri。

* Game：这一点很容易理解，由于ELIZA具有很强的互动性，她对游戏领域的影响是深远的，特别对早期的游戏。一些角色扮演类游戏和文字游戏很大程度上借鉴了ELIZA的设计，具体看这里。2011年的游戏黑客入侵：人类革命（Deus Ex: Human Revolution）也在向ELIZA致敬。游戏中的一个伪装成记者的反派Eliza Cassan最后被主角击杀，并发现她是一个高度智能的AI。

* Smart Assistant:虽然Google Now和Siri等一些智能语音助理能完成各种任务，甚至对它们给予的输入是完全的自然语言，但是它们仍可以判断意思并给出回答。维基百科上说Siri中有个很有意思的彩蛋（前提是语言设置为en），问Siri：“Who would you vote for-Mitt Romney or Barack Obama?”,Siri回答：“I can’t vote.But if I did,I would vote for ELIZA.She knows all.”或者问Siri：“Tell me a story.”最后她会给你讲她是如何被选中给Apple工作的，然后故事中会提及ELIZA。当然你也可以向Siri问ELIZA，然后她会仔细地向你介绍。

* etc.

 Emacs Doctor源代码中这样介绍自己

	The single entry point `doctor', simulates a Rogerian analyst using phrase-production techniques similar to the classic ELIZA demonstration of pseudo-AI.
	
	
Emacs Doctor的脚本是用eLisp语言写的。在Mac中，打开emacs/24.3/Emacs.app/Contents/Resources/lisp/play ，其中的doctor.elc便是Doctor的藏身之处。

Gnu Emacs 20.2.2中Emacs Doctor源代码：[点击查看](http://www.csee.umbc.edu/courses/471/papers/emacs-doctor.shtml)

写的不好，有错误还请指正。

### Eliza体验

安装过程：

<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">$ cd Chatbot-Eliza-1.04</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">$ ls</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Chatbotdebug.cgidoctor.txtsimple</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">MANIFESTdeutschnorsksimple.cgi</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Makefile.PLdeutsch.cginorsk.cgitest.pl</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">READMEdeutsch.txtnorsk.txttwobots</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">$ perl Makefile.pl</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Checking if your kit is complete...</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Looks good</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Writing Makefile for Chatbot</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">$ make test</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">cp Chatbot/Eliza.pm blib/lib/Chatbot/Eliza.pm</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">PERL_DL_NONLAZY=1 /opt/local/bin/perl "-Iblib/lib" "-Iblib/arch" test.pl</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000; min-height: 15px;"> </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Attempting to load module...done.  </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000; min-height: 15px;"> </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">OK, looks good.</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000; min-height: 15px;"> </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;"><span style="color: #f5f5f5;">$ make install </span><span style="font-family: Menlo; font-size: 13px;"><span style="color: #ff2800;">在这需要权限才行，sudo就行了</span></span></p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Manifying blib/man3/Chatbot::Eliza.3pm</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">ERROR: Can't create '/opt/local/lib/perl5/site_perl/5.12.4/Chatbot'</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">mkdir /opt/local/lib/perl5/site_perl: Permission denied at /opt/local/lib/perl5/5.12.4/ExtUtils/Install.pm line 494</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000; min-height: 15px;"> </p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;"> at -e line 1</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">make: *** [pure_site_install] Error 13</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">$ sudo make install</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Password:</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Sorry, try again.</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Password:</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Files found in blib/arch: installing files in blib/lib into architecture dependent library tree</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Installing /opt/local/lib/perl5/site_perl/5.12.4/darwin-thread-multi-2level/.DS_Store</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Installing /opt/local/lib/perl5/site_perl/5.12.4/darwin-thread-multi-2level/auto/.DS_Store</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Installing /opt/local/lib/perl5/site_perl/5.12.4/darwin-thread-multi-2level/.DS_Store</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Installing /opt/local/lib/perl5/site_perl/5.12.4/darwin-thread-multi-2level/auto/.DS_Store</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Installing /opt/local/lib/perl5/site_perl/5.12.4/darwin-thread-multi-2level/Chatbot/Eliza.pm</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Installing /opt/local/share/perl5.12/siteman/man3/Chatbot::Eliza.3pm</p>
<p style="margin: 0px; font-size: 13px; font-family: Menlo; color: #f5f5f5; background-color: #000000;">Appending installation info to /opt/local/lib/perl5/5.12.4/darwin-thread-multi-2level/perllocal.pod</p>

这算安装好了。

然后”./simple”运行，尝试一下，本来感觉无聊的过程却发现亮点在最后。。。 感觉这个比Emacs Doctor的回答智能多了！

![image](http://pic.yupoo.com/jok3r/DlYAul52/medish.jpg?resize=600%2C450)

参考资料：

[Need A Psychiatrist? Meet Eliza](http://marcelgagne.com/content/need-psychiatrist-meet-eliza)

[Meet The Emacs Doctor](http://marcelgagne.com/content/meet-emacs-doctor)

[Wikipedia—ELIZA](http://en.wikipedia.org/wiki/ELIZA)

[Wikipedia—ELIZA Effect](http://en.wikipedia.org/wiki/ELIZA_effect)

[Wikipedia—Joseph Weizenbaum](http://en.wikipedia.org/wiki/Joseph_Weizenbaum)

[CSEE.UMBC.EDU](http://www.csee.umbc.edu/courses/471/papers/)

[面对互联网：我们已经丧失了人性](http://lz.book.sohu.com/chapter-19176-114681445.html)

###Update2014-04-12

自己写的一个C版本的Eliza，点击查看[C语言版本的Eliza与Hacker Go](http://jackiekuo.com/code/2014/04/12/recreate-eliza-and-hacker-go-with-c/)。
