---
layout:     post
title:      2021-3-24 Chrome Devtools Tip： 2.如何使用DevTools触发CSS伪类
date:       2021-3-24
author:    陈诗樵
catalog: true
tags:
    - Chrome Devtools Tip
---

![pseudo-trigger.gif](https://upload-images.jianshu.io/upload_images/8156292-fe137965f93360e7.gif?imageMogr2/auto-orient/strip)
可以触发元素上的[伪类](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)，以研究元素（例如，将元素悬停在元素上）如何反应。您可以右键单击“元素”面板中的节点，然后选择“强制元素状态”。或者，可以在“[样式”](https://developers.google.com/web/tools/chrome-devtools/inspect-styles)子窗格中单击“切换”元素状态图标。

当一个元素应用了某种状态时，您将在节点的开始标签左侧看到一个视觉指示器，在某些情况下，也将在关闭标签左侧（如果它们相距很远）。

我们可以触发：活动类（:active），焦点类(:focus)，悬停类(:hover)和访问过的（:visited）伪类。

# 补充
一般伪类是`:PseudoClass`,伪元素是`::PseudoElement`,虽然伪元素也能写一个冒号，但是最好区分开来