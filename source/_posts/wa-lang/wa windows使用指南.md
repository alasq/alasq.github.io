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

后来检查了下 install 的时候会在 `$home/go/bin`目录(我的电脑是这个路径C:\Users\win7\go\bin)创建 `wa.exe`的

配置下这个目录的地址到path就行了,最根本的原因是安装前系统中的 `$GO_PATH`没有设置对。

## 总结
1. 安装前检查go有没用正确安装
2. 安装前设置好go的国内的镜像仓库
3. 安装完如果出现`wa 不是内部或外部命令`,用`Everything`全盘检索`wa.exe`文件,把所在目录配置到环境变量中
