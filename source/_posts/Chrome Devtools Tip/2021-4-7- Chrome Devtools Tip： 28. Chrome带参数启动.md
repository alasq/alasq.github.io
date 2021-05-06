---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 28. Chrome带参数启动
date:       2021-4-7
author:    陈诗樵
catalog: true
tags:
    - Chrome Devtools Tip
---

![auto-open-devtools.gif](https://upload-images.jianshu.io/upload_images/8156292-cbfad927c7427d7f.gif?imageMogr2/auto-orient/strip)

`--auto-open-devtools-for-tabs` 新打开的标签页,带上devtools工具
比如新打开的页面有重定向问题,但是由于没有打开devtools会导致在Network面板看不到任何有用的信息.

# 补充
老外给的图里面是使用命令行启动，苹果机器的，在windows下可以创建快接方式，在快捷方式里带上参数即可
![image.png](https://upload-images.jianshu.io/upload_images/8156292-27dd854e848f6924.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 没生效！！
添加启动参数后,发现没生效。已经打开了一个浏览器实例导致的。关闭所有的Chrome浏览器，再通过这个快接方式打开就能生效了。

# 让Chrome支持跨域调用
本地调试小程序挺好用的,不用代理服务器
` --disable-web-security --user-data-dir=C:\MyChromeDevUserData` 高版本Chrome需要`--user-data-dir`这个参数才可以使disable-web-security生效,后面是个例子
`"C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" --disable-web-security --user-data-dir=C:\MyChromeDevUserData`

# 讨论
老铁们,还有些什么有用的启动命令可以在评论区发下
