---
layout: post
title: 如何优雅地使用Vim？(趣味篇)
description: 如何优雅地使用Vim?关于Vim的有趣的用法
keywords: Vim,Sublime text,Atom,Plugin
category: Code
tagline: --read & think
tags: [Vim,Code,Trivia]
---
{% include JB/setup %}

话说2014年，刚满22岁的Vim却不断受到一些乳臭未干的小屁孩的挑战：Sublime Text以`Sexy`自称，而不满一岁的Atom，却顶着`editor for the 21st century`的荣耀光环。这些`Sexy`和`Modern`的不和谐文化，不断挑衅着Vim以及破坏Vim党派内的风气。

废话完毕！Vim强大的插件岂是黄毛小儿所能比的？下面的一些插件教你如何优雅(`echo "0000000: e8a3 85e9 80bc 0a" | xxd -r`)地使用Vim。

注：Vim插件的安装方式一般为输入`:source <plugin_name>`或是直接放到`.vim/plugin/`。

###Matrix黑客帝国

![matrix.vim](http://jackiekuo.com/images/matrix.gif)

是的，这个是模拟《矩阵革命》里经典的字符下落的效果。虽然这只能算是个屏保，不过它确实很酷。安装后，输入`:Matrix`就能看到效果。

[下载地址](http://www.vim.org/scripts/script.php?script_id=1189)

###Tetris俄罗斯方块

![teris](http://jackiekuo.com/images/tetris.gif)

这个还用过多介绍吗？在编辑器中玩史上最伟大的游戏之一，就这一点足以让Sublime Text党和Atom派一边玩儿去了。

游戏玩起来速度有点快，不过可以通过自己修改插件来调整。如何控制下落方向和变形？当然是HJKL了。输入`<Leader>te`启动(默认为`\te`)。

[下载地址](http://www.vim.org/scripts/script.php?script_id=172)

###Sudoku数独

![sudoku](http://pic.yupoo.com/jok3r/DJ6Eny3y/medish.jpg)

数独是我最喜欢的游戏了。虽然在Vim里玩起来不是太爽，但为了`优雅`，还是可以装一下的。

输入`SudokuEasy`、`SudokuMedium`、`SudokuHard`或`SudokuVeryHard`可以选择不同难度。

[下载地址](http://www.vim.org/scripts/script.php?script_id=3553)

####见下篇[如何优雅地使用Vim？(美化篇)](http://jackiekuo.com/code/2014/05/06/use-vim-the-sexy-way/)