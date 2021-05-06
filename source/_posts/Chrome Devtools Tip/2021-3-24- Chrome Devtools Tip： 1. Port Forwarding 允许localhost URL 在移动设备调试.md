---
layout:     post
title:      2021-3-24 Chrome Devtools Tip： 1. Port Forwarding 允许localhost URL 在移动设备调试
date:       2021-3-24
author:    陈诗樵
catalog: true
tags:
    - Chrome Devtools Tip
---

![port-forward.gif](https://upload-images.jianshu.io/upload_images/8156292-21eac099700614e6.gif?imageMogr2/auto-orient/strip)
# 在本技巧中，您将学习如何在Android设备上转发端口。

端口转发使您可以直接在android设备上查看本地网站，即使该网站托管在自定义域中。

* Chrome浏览器从台式机拨打我的本地主机URL
* 远程调试移动本地主机页面并启用端口转发
* 刷新并观察到不需要命令行！

# 补充
1. Chrome远程调试界面的的url`chrome://inspect/#devices`
2. 记得在手机`开发者工具`上打开`启用USB调试`
3. 配置入口如下图
![port-forward配置入口](https://upload-images.jianshu.io/upload_images/8156292-033914fe5e4a3845.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4. 配置完勾选端口转发复选框
![image.png](https://upload-images.jianshu.io/upload_images/8156292-15a49c6284f73ada.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
