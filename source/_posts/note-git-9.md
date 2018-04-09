---
title: 远程仓库
date: 2016-03-10 22:33:28
tags:
categories:
- 学习笔记
- git
---

![github](http://7xlana.com1.z0.glb.clouddn.com/myblog/git/EVhvhfb4btKiCtW0U%253DhD6pxXmZH2FLAcpiuP%253DQyud9oct1450744586242compressflag.jpg)

第1步：创建SSH Key。在当前目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：
$ ssh-keygen -t rsa -C "youremail@example.com"
<!--more-->
第2步：登陆GitHub，打开“Account settings”，“SSH Keys”页面：
然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：

现在，我们根据GitHub的提示，在本地的learngit仓库下运行命令：
$ git remote add origin git@github.com:onlyone/learngit.git
添加后，远程库的名字就是origin，这是Git默认的叫法，也可以改成别的，但是origin这个名字一看就知道是远程库。

本地库的所有内容推送到远程库上：
$ git push -u origin master
#### 从远程库克隆

现在，远程库已经准备好了，下一步是用命令git clone克隆一个本地库：
$ git clone git@github.com:michaelliao/gitskills.git
 
$ cd gitskills
$ ls
README.md