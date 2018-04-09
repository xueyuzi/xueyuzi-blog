---
title: 删除文件
date: 2016-03-10 22:24:13
tags:
categories:
- 学习笔记
- git
---
你通常直接在文件管理器中把没用的文件删了，或者用rm命令删了：

现在你有两个选择，一是确实要从版本库中删除该文件，那就用命令git rm删掉，并且git commit：
$ git rm test.txt
rm 'test.txt'
$ git commit -m "remove test.txt"
现在，文件就从版本库中被删除了。
另一种情况是删错了，因为版本库里还有呢，所以可以很轻松地把误删的文件恢复到最新版本：
$ git checkout -- test.txt