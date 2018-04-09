---
title: 管理更改
date: 2016-03-10 22:18:29
tags:
categories:
- 学习笔记
- git
---
#### 管理更改
Git与其他版本控制系统相比，Git跟踪并管理的是修改，而非文件。

在git add之后修改文件不重新add的话，commit提交的是之前add的修改而不是add之后的修改。

<!--more-->
#### 撤销修改

命令git checkout -- readme.txt意思就是，把readme.txt文件在工作区的修改全部撤销，这里有两种情况：
* 一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
* 一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
总之，就是让这个文件回到最近一次git commit或git add时的状态。