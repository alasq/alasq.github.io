---
title: 记录webpack4的两个坑
date: 2021-09-26 22:41:06
tags: webpack
---
1. mode=production 的时候会自动压缩混淆js。但是如果加上css压缩的配置后,js的会失效,需要显式声明压缩插件` new TenserJSPlugin()`

2. (file-loader extract-loader html-loader) 与 html-webpack-plugin 有冲突。这时候生成的index.html模板信息会丢失掉，只有一个片段。解决方案是在 (file-loader extract-loader html-loader) 处理html导入的时候,exclude掉index.html(不一定是这个名字,主要看模板名称)