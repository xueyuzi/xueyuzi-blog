---
title: html5中的file对象
date: 2018-06-11 11:42:12
tags:
---

# JS读取或利用file对象
html5提供了两个方案：FileReader和ObjectUrl。

<!--more-->
## 使用FileReader

首先需要实例化FileReader对象：

```javascript
var reader = new FileReader();
```

利用FileReader读取file对象是一个异步的过程，我们需要先为FileReader设置好load事件的callback，告知FileReader在读取到file对象的数据后应该进行什么进一步的操作：
```javascript
reader.onload = function(e) { 
    document.getElementById("image").src = e.target.result; 
}
```

上面这段代码的意思是，FileReader读取到图片的数据后，把数据（DataUrl）放到的src属性里。
最后，就是通过FileReader不同的方法，来决定读取file对象数据后用什么数据格式来存放，并实施读取：

readAsArrayBuffer(file) ：读取file对象并存放为ArrayBuffer对象（ArrayBuffer对象是什么我暂时没有搞清，应该是一种为了高效存取数据而产生的数据结构）。
readAsText(file [, 'UTF-8']) ：以一般文本模式读取file对象，值得注意的是，利用第二个参数（可选）可指定字符编码。
readAsDataURL(file) ：读取file对象并存放为data: URL格式的字符串。

## 使用ObjectURL
ObjectURL相当于文件的一个临时路径，此临时路径可随时生成、随时释放，在本地浏览器使用起来时，与普通的url无异。
以把一张本地图片显示在页面上为例：
```javascript
var img = document.createElement("img");
img.src = window.URL.createObjectURL(file);
```
此时，src形如：blob:https://dn-coding-net-production-static.qbox.me/699526e2-04fc-4ef8-9f61-6cf42693f51d.jpg?imageMogr2/auto-orient/format/jpeg/crop/!236x236a344a0

用这个src就能让浏览器从本地读取图片。
这种方案相对用FileReader生成图片的base64编码并放到的src里来说，性能有了很大的提升。
比较这两种读取File对象的方案，FileReader适合用来上传文件，而ObjectURL则适合直接在浏览器进行操作，然后操作后再把处理后的数据进行上传，例如利用canvas截图或进行图片压缩等。当然，这一切都是要考虑兼容性的。
