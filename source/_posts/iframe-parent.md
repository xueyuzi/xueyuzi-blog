---
title: 父元素调用iframe中的js方法
date: 2017-07-14 23:10:54
tags:
---

访问iframe里面的函数：
<!--more-->
复制代码代码如下:
```javascript
document.getElementById('commentIframe').contentWindow.hasLogined();
```

commentIframe为iframe的id.
要在 window.onload里面执行
