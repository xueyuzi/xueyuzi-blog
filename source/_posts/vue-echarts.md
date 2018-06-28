---
title: echarts配合vue使用
date: 2017-12-24 17:22:33
tags:
---

echarts 在 echarts.init(document)的时候必须是已经dom生成完毕
<!--more-->

可以在mouted()方法中初始化echats
然后先设置初始化配置
而后吧 所有需要改变的数据 分离出来 再次设置
如果有异步需求 可以 使用async 或者then来控制 是否请求完成

![初始化echarts](http://o99hhtmyi.bkt.clouddn.com/clipboard.png)


![数据变化时echarts刷新绘图](http://o99hhtmyi.bkt.clouddn.com/clipboard%20%281%29.png)

![会变动的数据提取出来](http://o99hhtmyi.bkt.clouddn.com/clipboard%20%282%29.png)





