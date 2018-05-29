---
title: css分离打包（ExtractTextPlugin less）
date: 2017-07-19 21:22:15
tags: webpack
---

原来的css-loader会把css文件一并打包进js中
使用
ExtractTextPlugin less
可以把css分离出来


然后使用less编译后打包成一个style.css文件，但是这个style.css文件里面，配置文件如下：
var ExtractTextPlugin = require('extract-text-webpack-plugin');
var ExtractLess = new ExtractTextPlugin('./style/style.css');
module.exports = {
    entry: {
        base: path.resolve(__dirname,'./dev/app.js'),
        vendors: ['react']
    },
    
    ...
    
    module: [
        {
            test: /\.less$/,
            loader: ExtractTextPlugin.extract("style-loader", "css-loader!less-loader")
        },
    ]
    plugins: [
        ExtractLess
    ]
}