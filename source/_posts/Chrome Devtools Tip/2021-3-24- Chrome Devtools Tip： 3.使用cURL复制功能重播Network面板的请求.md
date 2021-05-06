---
layout:     post
title:      2021-3-24 Chrome Devtools Tip： 3.使用cURL复制功能重播Network面板的请求
date:       2021-3-24
author:    陈诗樵
catalog: true
tags:
    - Chrome Devtools Tip
---

![copy-as-curl.gif](https://upload-images.jianshu.io/upload_images/8156292-2361d35d4917df7e.gif?imageMogr2/auto-orient/strip)
网络面板中显示的资源有一个上下文菜单，该菜单允许您复制为cURL，这将进入剪贴板，此时您可以将其粘贴到命令行中，必要时进行修改，然后查看响应。请求标头也包括在内。

# 补充
1. `Numbers API`给个数字，会返回这个数字相关的信息。其实有很多免费的API很有趣，可以自行收集下，比如天气的，历史上的今天，新冠疫情数据，这样我们没有自己的服务器也能做出有意思的应用。
2. Windows 系统没有`curl`命令行工具（除非自己安装），可以使用`Copy as PowerShell`进行请求重播，复制成fetch代码也不错，做接口测试的时候就省代码了
![image.png](https://upload-images.jianshu.io/upload_images/8156292-bb4bd22c59eaa1f2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 将网络回复复制到剪贴板
![copy-response.gif](https://upload-images.jianshu.io/upload_images/8156292-6eb17dca94cc97df.gif?imageMogr2/auto-orient/strip)
