---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 24. 在“Network”中查看来自其他应用程序的网络流量
date:       2021-4-7
author:    陈诗樵
catalog: true
tags:
    - Chrome Devtools Tip
---

## 常用的抓包工具
Fiddler 小巧精悍,适合http
Burpsuite 安全测试的时候用过,很强大
wireshark  抓网卡,内容没有聚合上手难度高点

NetWork 面板很好用,用来拦截操作系统的网络流量
![os-network-proxy.gif](https://upload-images.jianshu.io/upload_images/8156292-af20e8217608951b.gif?imageMogr2/auto-orient/strip)

这里需要另外一个 工具来配合 github kdzwinel/betwixt
安装好了再设置下系统的代理就好了
# 补充
其实这个不是用Chrome DevTools去抓包啦,只是betwixt这个抓包工具,长得跟NetWork面板一样