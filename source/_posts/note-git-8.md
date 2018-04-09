---
title: 三区结构
date: 2016-03-10 22:27:30
tags:
categories:
- 学习笔记
- git
---

![三区结构](http://7xlana.com1.z0.glb.clouddn.com/myblog/git/git-operations.png)

三区结构是Git的结构:工作区--暂存区--版本库
<!--more-->


**版本库**:工作区有一个隐藏目录.git 这个不算工作区，而是Git的版本库。
**暂存区**：英文叫stage,或index。一般存放在git 目录下的index文件(.git/index)中，所以我们把暂存区时也叫作索引(index).
Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD。

![工作区-版本库](http://7xlana.com1.z0.glb.clouddn.com/git_note_2.png)


