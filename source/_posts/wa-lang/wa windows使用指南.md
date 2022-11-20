---
title:      wa-lang windows踩坑指南
date:       2022-11-20
author:     alasq
catalog: true
tags:
    - wa-lang
---
# wa-lang windows系统初体验

![](images/2022-11-19-15-49-38.png)
按照官网的执行的install，嗯安装不上，应该是被墙了？
不过翻墙后仍然报错!!

于是从gitee上下载了源代码,执行了`go install .`，报错如下

![](images/2022-11-19-15-51-50.png)

于是网上找了下国内的镜像仓库，安装成功，但是 `wa 不是内部或外部命令`
![](images/2022-11-19-15-53-20.png)

在项目目录下创建一个`wa.cmd`来执行下`go run main.go %*`,这样也能愉快的执行wa命令咯,效果如下
![](images/2022-11-19-16-02-13.png)

后来检查了下 install 的时候会在 $home/go/bin目录创建 wa.exe的,配置下这个目录的地址到path就行了,最根本的原因是系统中的 $GO_PATH没有设置对。