---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 26. Store as global variable 存储成全局变量
date:       2021-4-7
author:    Alasq
catalog: true
tags:
    - Chrome Devtools Tip
---

![web-animation-api.gif](https://upload-images.jianshu.io/upload_images/8156292-4e305ded9d17242a.gif?imageMogr2/auto-orient/strip)

# 补充
很多地方的右键上下文菜单上有这个`Store as global variable `这个选项
作用是在 console 面板存成全局变量,因为对象的引用类型,修改这个全局变量,其实就是改变原对象的值,很强大。
## 将DOM变成全局变量
![image.png](https://upload-images.jianshu.io/upload_images/8156292-3d900a6460dfc1fa.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
## 将事件的处理函数作为全局变量
![image.png](https://upload-images.jianshu.io/upload_images/8156292-ccf98baf8acbfbf2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
## 打断点时候的任意一个局部变量
![image.png](https://upload-images.jianshu.io/upload_images/8156292-1ee0184cd551f0b5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
## 消息的响应体预览界面
![image.png](https://upload-images.jianshu.io/upload_images/8156292-792fb8a98b463887.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 还有其他我没发现的地方
请大家评论区补充