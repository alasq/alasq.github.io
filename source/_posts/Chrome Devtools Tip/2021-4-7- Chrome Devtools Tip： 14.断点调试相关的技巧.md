---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 14.断点调试相关的技巧
date:       2021-4-7
author:    Alasq
catalog: true
tags:
    - Chrome Devtools Tip
---

![highlight-paused-statement.gif](https://upload-images.jianshu.io/upload_images/8156292-b182b48798fc84b5.gif?imageMogr2/auto-orient/strip)
调试器暂停后，您现在可以看到正在执行的代码的确切部分。它以高亮显示较深的蓝色阴影。这在调试精简代码时很有用。

![debugger-shortcuts.gif](https://upload-images.jianshu.io/upload_images/8156292-f5fdd4026a918fda.gif?imageMogr2/auto-orient/strip)

Toggle a breakpoint while on a line: `Cmd + B` （切换当前行的断点）
Select the next call frame: Ctrl + . (下一个调用栈)
Select the previous call frame: Ctrl + , (上一个调用栈)
# 补充
动图上点击的按钮是当遇到报错的时候，自动触发断点调试。
我们可以在源代码中添加 `debugger` 设置断点
可以在source面板中文件的行号前面单击设置断点 `Cmd + B`
### 通过DOM被修改，被移除命中断点
![image.png](https://upload-images.jianshu.io/upload_images/8156292-a07045fdf96cc168.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 通过触发网络请求命中断点
![image.png](https://upload-images.jianshu.io/upload_images/8156292-f9c5980598e753fc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 断点触发后，按住Ctrl 能跳转到的地方会被高亮
![js-jump-to-destination.gif](https://upload-images.jianshu.io/upload_images/8156292-371da7a472f180de.gif?imageMogr2/auto-orient/strip)
