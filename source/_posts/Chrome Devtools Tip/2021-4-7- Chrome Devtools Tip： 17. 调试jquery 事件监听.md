---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 17. 调试jquery 事件监听
date:       2021-4-7
author:    陈诗樵
catalog: true
tags:
    - Chrome Devtools Tip
---

![jquery-event-listeners.gif](https://upload-images.jianshu.io/upload_images/8156292-c203c83afc13da33.gif?imageMogr2/auto-orient/strip)
jquery事件监听指向jquery的源代码，这对于调试没啥用，我们可以通过查看监听器方法的定义，找到事件处理函数