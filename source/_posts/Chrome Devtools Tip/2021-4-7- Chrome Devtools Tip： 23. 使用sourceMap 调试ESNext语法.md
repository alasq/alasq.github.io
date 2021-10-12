---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 23. 使用sourceMap 调试ESNext语法
date:       2021-4-7
author:    Alasq
catalog: true
tags:
    - Chrome Devtools Tip
---

现在经常使用ESNext语法书写代码,再使用babel转换成ES5,

1. 使用webpack 打包时候设置 devtool 为 source-map 即可
2. 生产环境上一般使用压缩混淆后的代码
3. 生产环境的ngnix服务器出于安全考虑,一般也不会返回source map类型的文件!!!

# 使用Sourcemap 调试时解析变量名
![resolve-variable-names.gif](https://upload-images.jianshu.io/upload_images/8156292-ede34451980feb28.gif?imageMogr2/auto-orient/strip)
调试的时候就算有sourceMap,显示的依然是被混淆的名字`a,b,c`这种,我们想看到真实的变量名称,怎么做呢?
启动 试验功能的`Resolve Variable Names`
## 补充 
我在Chrome 89 看不到这个老外说的这个试验功能,应该是已经转正了!!不需要单独启用,知道有这个东西就好了
