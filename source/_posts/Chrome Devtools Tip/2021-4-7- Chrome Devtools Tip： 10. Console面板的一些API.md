---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 10.Console面板的一些API
date:       2021-4-7
author:    Alasq
catalog: true
tags:
    - Chrome Devtools Tip
---

# 快速监控JavaScript中的事件
![monitor-events.gif](https://upload-images.jianshu.io/upload_images/8156292-b7226d2fe4dede77.gif?imageMogr2/auto-orient/strip)
您可以使用命令行API方法`monitorEvents（object [，events]）`记录分发给对象的所有事件。然后将事件对象记录到控制台。当您需要提醒事件对象的可用属性时很有用。

## 一个例子
例如，直接在控制台面板中尝试以下代码：

> monitorEvents(window, 'click')  

当您在网页中单击时，现在应该看到click事件自动记录到控制台。

# 控制台获取当前选定的DOM节点的快捷方式
![dollar-zero.gif](https://upload-images.jianshu.io/upload_images/8156292-f6444ade5bf7074e.gif?imageMogr2/auto-orient/strip)

在“Element”面板中选择节点后，请在控制台面板中使用表达式`$0`进行访问。您还可以使用`$_`访问最近求值的表达式的值

# 控制台快速定位DOM位置
![reveal-in-elements.gif](https://upload-images.jianshu.io/upload_images/8156292-2d4c59000b3e4d31.gif?imageMogr2/auto-orient/strip)
