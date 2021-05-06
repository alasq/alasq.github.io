---
layout:     post
title:      2021-4-19-《使用 MonoRepo 管理前端项目》读后感
date:       2021-4-19
author:    陈诗樵
catalog: true
tags:
    - 读后感
---

先阅读下这个文章《使用 MonoRepo 管理前端项目》   https://blog.csdn.net/qiwoo_weekly/article/details/112000852
文章说的是，多npm包管理是每个包对应一个git仓好,还是一个包对应一个仓库好。
先表明我的观点：**我支持multi-repo，一个包对应一个仓库**
# 文中列出的multi-repo缺陷
![image.png](https://upload-images.jianshu.io/upload_images/8156292-ab6c827fe620646d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> “如果有脚手架” 难道现在还有不用脚手架的么？？？所以这是个伪命题，哪有这么多如果

![image.png](https://upload-images.jianshu.io/upload_images/8156292-2aa4f2c3921f9ac6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 1. 硬盘问题：硬盘大的苹果本子太贵了??缺硬盘??10个项目的node_modules大概也就一部电影的大小,这又是个伪命题。
> 2. “每次有个新页面” webpack-plugin-html 不能解决?非要去创建新项目?至于说域名部署,shell脚本就可以处理了
> 3. "项目分散" vscode可以创建工作空间,工作空间可以添加项目文件夹 Ctrl+R 也是可以快速切换项目的

![image.png](https://upload-images.jianshu.io/upload_images/8156292-5c1bb9c46fd41c06.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 这个确实是问题,但是作为包的使用,调用方只关心输入与输出,而不应该关心包内部的实现细节。你在写自己的代码，还要调试被依赖的代码，这本身就是个错误的开发流程。如果A模块依赖B模块的功能，肯定需要B模块自身是稳定模块，如果处于开发中的状态，应该继续完善B模块。
# 文中提到的前后端放在一个仓库中
> 如果是小型项目是没问题的,大型项目CI/CD,lint什么的可能完全不一样,也不是很建议,要视情况而定
# 总结
MonoRepo 管理前端项目,确实有很多场景可以使用。但文中的理由都有点牵强，我认为开发过程中包会越来越多，越来越大。当项目小的时候就适合用MonoRepo 管理多个包，方便省事儿。等仓库达到一定的大小，比如50M的代码量，就要考虑分包，分库，分专人维护。一人----一包----一仓库，做到以人为本。。