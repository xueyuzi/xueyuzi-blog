---
title: CentOs基础配置
date: 2016-04-13 17:12:34
tags:
categories:
- 笔记
- CentOs
---

![CentOS](http://7xlana.com1.z0.glb.clouddn.com/myblog/git/091724151.jpg)
在RHEL或者CentOS等Redhat系的Linux系统里，跟网络有关的主要设置文件如下：

/etc/host.conf         配置域名服务客户端的控制文件
/etc/hosts             完成主机名映射为IP地址的功能
/etc/resolv.conf       域名服务客户端的配置文件,用于指定域名服务器的位置
/etc/sysconfig/network 包含了主机最基本的网络信息,用于系统启动.
/etc/sysconfig/network-script/    系统启动时初始化网络的一些信息
/etc/xinetd.conf       定义了由超级进程xinetd启动的网络服务
/etc/networks          完成域名与网络地址的映射
/etc/protocols         设定了主机使用的协议以及各个协议的协议号
/etc/services          设定主机的不同端口的网络服务 
<!--more-->
### ip配置


[root]# vim /etc/sysconfig/network-scripts/ifcfg-eno167777736
HWADDR mac地址
BOOTPROTO 动态静态
IPADDR
DEFROUTE
PEERDNS
PEERROUTES
ONBOOT
IPADDR
NETMASK
GATEWAY
DNS1

[root]# service network restart
### 安装apache
[root]# yum install httpd
[root]# service httpd start
#### 安装apache 一些扩展

root@localhost ~]# yum -y install httpd-manual mod_ssl mod_perl mod_auth_mysql
### 安装MySql
 mysql          客户端程序

 mysql-server    服务端程序

 mysql-devel    开发设计的库

[root@localhost ~]# yum -y install mysql mysql-server mysql-devel
[root@localhost ~]# service mysqld start (5.0版本是mysqld)

### 安装php
安装相关模块：为了让PHP支持MySQL，我们可以安装php-mysql软件包；也可使用以下命令搜索可用的php模块

[root@localhost ~]# yum -y install php php-mysql

#### 安装php常用扩展

[root@localhost ~]# yum search php

[root@localhost ~]# yum -y install gd php-gd gd-devel php-xml php-common php-mbstring php-ldap php-pear php-xmlrpc php-imap