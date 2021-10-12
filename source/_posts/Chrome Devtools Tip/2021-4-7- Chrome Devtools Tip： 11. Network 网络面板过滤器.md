---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 11.Network 网络面板过滤器
date:       2021-4-7
author:    Alasq
catalog: true
tags:
    - Chrome Devtools Tip
---

![is-running.gif](https://upload-images.jianshu.io/upload_images/8156292-7fbd6b075cec6c2d.gif?imageMogr2/auto-orient/strip)

# 介绍
您可以使用“is:running高级网络过滤器”查看未完成的网络请求（例如正在运行的请求）。其他一些过滤器，您可以尝试是：status-code，method，domain和更多！

# 如何使用它
在“网络面板”过滤器框中，键入is:running并重新加载页面。观察可见的“网络面板”行如何快速变化以仅显示当前正在运行的资源。

# 别的过滤器
![network-advanced-filter.gif](https://upload-images.jianshu.io/upload_images/8156292-421dbaa61601a622.gif?imageMogr2/auto-orient/strip)

# 补充
还有这些过滤器可以使用

*   domain
*   has-response-header
*   is - []（例如上图的例子）
*   larger-than
*   method
*   mime-type
*   mixed-content
*   priority
*   scheme
*   set-cookie-domain
*   set-cookie-name
*   set-cookie-value
*   resource-type
*   cookie-domain
*   cookie-name
*   cookie-path
*   cookie-value
*   status-code
*   url
# 查看网络资源依赖关系
![network-dependency.gif](https://upload-images.jianshu.io/upload_images/8156292-de7a51900ab3d6b1.gif?imageMogr2/auto-orient/strip)
点击到具体的请求，查看 initiator 面板也是可以看到的 请求的调用栈与树状依赖结构


