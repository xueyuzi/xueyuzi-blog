---
title: git问题记录--如何从从detached HEAD状态解救出来
date: 2017-9-24 00:33:14
tags:
---

什么叫做’detached HEAD’，即现在HEAD指向的是一个没有分支名字的修订版本，“游离”于已知的所有分支之外。
<!--more-->

游离HEAD的问题就在于它没有一个具体的分支名，那我们给它命个名：git branch temp c90b1ca（将HEAD指向的commit命名为分支temp），然后切换到分支master上，执行merge命令(git merge temp)，最后push到远端。做完这一系列操作之后再次查看分支的最新修