---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 12. Element面板
date:       2021-4-7
author:    陈诗樵
catalog: true
tags:
    - Chrome Devtools Tip
---

# 1. Alt + Click展开所有的子节点
![alt-click-expand-node.gif](https://upload-images.jianshu.io/upload_images/8156292-4524814cf7ea524e.gif?imageMogr2/auto-orient/strip)

# 2. 轻松修改tagName
![quick-edit-element.gif](https://upload-images.jianshu.io/upload_images/8156292-7ef233fca006f66a.gif?imageMogr2/auto-orient/strip)

# 3. 查看元素的事件侦听器

![view-event-listeners.gif](https://upload-images.jianshu.io/upload_images/8156292-731375e6190683ef.gif?imageMogr2/auto-orient/strip)
### 介绍
DevTools可以向您显示在元素上注册的JavaScript事件侦听器。例如，向click注册的处理程序.addEventListener()。

DevTools还可将您带到注册该事件的确切代码行，这在从中进行外部调试时非常有用。

###如何使用此功能
在“Element”面板中检查元素
导航到“Element”面板中的“Event Listener”窗格
浏览在任何节点上注册的事件。您可以通过在上下文菜单中选择“显示函数定义”来查看事件侦听器的源。

###  补充
有时候事件显示特别多，可以去掉 `Ancestors`复选框，只显示绑定在元素自身的事件，而非被代理的事件
### 思考
事件的冒泡与代理，事件的队列
