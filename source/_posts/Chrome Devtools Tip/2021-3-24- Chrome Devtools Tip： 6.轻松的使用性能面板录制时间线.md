---
layout:     post
title:      2021-3-24 Chrome Devtools Tip： 6.轻松的使用性能面板录制时间线 
date:       2021-3-24
author:    Alasq
catalog: true
tags:
    - Chrome Devtools Tip
---

![record-timeline-undocked.gif](https://upload-images.jianshu.io/upload_images/8156292-6bc177b57bdb952e.gif?imageMogr2/auto-orient/strip)
当您需要在Mac上执行时间线录制时，请尝试将DevTools停靠到一个单独的窗口中，以便将录制按钮放在需要执行操作的页面部分附近。

或者，使用快捷键Cmd + E启动和停止录制。

通过这种方式进行录制，可以使录制的内容简短而甜美，并且可以减少录制时的“杂音”，因为您无需长时间在页面上移动鼠标。
# 补充
1. 录制时间线的重点就是，缩短录制时间，仅仅录制要分析的操作，这样大大减少了分析成本。这个小技巧就是干这个的。
2. 有时候输入法的快捷键会跟我们的IDE快捷键冲突，比如 `ctrl shift f`在vscode中是聚焦到搜索面板，搜狗输入法是繁简体切换，Hotkey Commander[ [ 下载 ]](https://gitee.com/alasq/tools/raw/master/Hotkey%20Commander/hkcmdr_inst.exe)这个工具可以检测快捷键的冲突
![image.png](https://upload-images.jianshu.io/upload_images/8156292-b3ec75b5e13a6402.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
# 思考
 假如我们写一个vscode 插件，怎么尽可能的不与现有的快捷键冲突
