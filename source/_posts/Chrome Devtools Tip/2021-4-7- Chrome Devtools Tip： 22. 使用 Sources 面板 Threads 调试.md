---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 22. 使用 Sources 面板 Threads 调试
date:       2021-4-7
author:    Alasq
catalog: true
tags:
    - Chrome Devtools Tip
---

![debug-per-thread.gif](https://upload-images.jianshu.io/upload_images/8156292-f7e721beaffe14aa.gif?imageMogr2/auto-orient/strip)
如果您正在使用利用多个线程的JavaScript功能（例如Service Worker或Web Workers），则Sources Panel会考虑到这一点。

由于每个线程都有其自己的全局脚本上下文，因此您可以选择一个特定的线程进行调试（例如，在其上设置断点）。只需在Sources面板中打开Threads 窗格即可。您应该看到主线程以及所有可用的其他线程。

# 补充  
![image.png](https://upload-images.jianshu.io/upload_images/8156292-91bbd2172b895f2a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这个是Chrome 89的截图,web worker是直接显示在左边的可以找打对应的文件打断点。右边只是一个指示器，告诉我们断点处在哪个线程
这里还可以看到 Content Scripts 面板 ,Chrome拓展开发的时候会用到这个,他能共享DOM


在V3版本的Chrome拓展开发中 Service Worker 也替代了 background.js
Service Worker的调试 还有系统通知等等的调试可以看Application面板
![image.png](https://upload-images.jianshu.io/upload_images/8156292-77a7f279e19de948.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
