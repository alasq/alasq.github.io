---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 31. Blackboxing 获得更好的调试会话
date:       2021-4-7
author:    Alasq
catalog: true
tags:
    - Chrome Devtools Tip
---

![blackboxing.gif](https://upload-images.jianshu.io/upload_images/8156292-f08a9ae48aa2fb3e.gif?imageMogr2/auto-orient/strip)
比如我们自己封装了一个 log.js,里面调用了console.log()。
所有打印出来的日志都定位到这个log.js文件,这不是我们想要。我们可以把 log.js设置成 Blackboxing Script。
这样就能定位到上一个调用栈的方法上了。
# 补充
真心很实用的功能，以前不知道可以这么玩，我是在打印的位置设置断点，看调用栈，再设置断点。把断点取消掉。