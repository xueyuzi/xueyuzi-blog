---
title: 关于 create-react-app 支持 .babelrc配置
date: 2018-06-13 13:33:05
tags:
---

 在整合 mobx 到 CRA 创建的项目中时 遇到了一个问题

<!--more-->

> CRA 默认创建的项目中 并不支持 es7 中的 装饰器语法 [@]

以前的做法是直接 创建.babelrc 文件 配置babel 就可以解决

可是在这里 .babelrc文件并没有生效 。

这是由于 CRA 的默认配置把 babelrc 屏蔽了

> 解决方法:
在 node_modules/react-script/config/webpack.config.dev.js | webpack.config.prod.js 两个文件中找到
babelrc: false 改为 babelrc: true
之后 你会发现 .babelrc 就可以用了



```javascript
{
    test: /\.(js|jsx|mjs)$/,
    include: paths.appSrc,
    loader: require.resolve('babel-loader'),
    options: {
        // @remove-on-eject-begin
        babelrc: false,  // 这里把babelrc屏蔽了
        presets: [require.resolve('babel-preset-react-app')],
        // @remove-on-eject-end
        // This is a feature of `babel-loader` for webpack (not Babel itself).
        // It enables caching results in ./node_modules/.cache/babel-loader/
        // directory for faster rebuilds.
        cacheDirectory: true,
    },
}
```

Happy coding！