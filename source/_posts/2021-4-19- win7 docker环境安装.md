---
layout:     post
title:      2021-4-19- win7 docker环境安装
date:       2021-4-19
author:    陈诗樵
catalog: true
tags:
    - docker
---

1. 本人win7,先下载DockerToolBox,win10的可以下载docker desktop for windows
下载地址 https://docs.docker.com/toolbox/overview/ 
双击运行 一路下一步就好了
![image.png](https://upload-images.jianshu.io/upload_images/8156292-f83cd8976a133c8c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
2. 然后报错,手按太快,询问是否安装虚拟机的时候直接点了回车,不安装,这里要注意下
![image.png](https://upload-images.jianshu.io/upload_images/8156292-bf7c186d1f902ae6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
3. 正常安装后桌面应该出现这三个小图标,第一个是docker的命令行工具,第二个是联网查看dockerhub的镜像,第三个是虚拟机
![image.png](https://upload-images.jianshu.io/upload_images/8156292-5424787ab9e6b89d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
4. 把提前下载好的 docker2boot镜像丢到缓存里面,否则启动的时候找不到会自动下载比较慢
![image.png](https://upload-images.jianshu.io/upload_images/8156292-06cb26f3eeb4ada1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
5. 我们运行第一个Docker Quickstart Terminal ,出现下面的界面就ok了
![image.png](https://upload-images.jianshu.io/upload_images/8156292-35392cc5cc1dcd05.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)