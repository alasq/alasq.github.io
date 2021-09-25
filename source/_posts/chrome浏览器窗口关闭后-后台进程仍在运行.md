---
title: 'chrome浏览器窗口关闭后,后台进程仍在运行'
date: 2021-09-25 20:52:55
tags: chrome
---

`chrome://settings/system` 里面有一个`关闭 Google Chrome 后继续运行后台应用` 默认是打开的,需要手动关闭。
如果项目中用到了sessionStorage的话,可能会影响到正常的逻辑。
![](../images/2021-09-25-20-54-05.png)