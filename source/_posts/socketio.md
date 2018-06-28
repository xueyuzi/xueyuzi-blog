---
title: socket.io的使用
date: 2018-06-28 17:15:57
tags:
---



当你使用了socket.io模块后，socket.io会把以 /socket.io 开头的请求都给截拦了下来，其他的请求再让express处理。
<!--more-->
因此，当请求 /socket.io/socket.io.js 的时候，不用纠结于为什么你没有这个文件它也能返回内容，你只要知道这个是 socket.io 里面的文件，有什么用途即可。


默认 在没有加入房间的时候 所有的
监听都只在同一会话中生效
不会影响其他用户

广播示例代码

// 每个客户端连接的时候触发的
<!--more-->
```javascript
io.sockets.on("connection",function(socket){
    socket.join("one");
    
    socket.on("myChart",function(data){
        console.log(data.my)
        socket.broadcast.emit("message",{message:data.my})
        io.sockets.emit("news",{message:data.my}) //全局
socket.emit("news",{message:"helo"})//本会话
    });
});

```