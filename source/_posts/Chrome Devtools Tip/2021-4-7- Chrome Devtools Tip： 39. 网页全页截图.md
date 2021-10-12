---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 39. 网页全页截图
date:       2021-4-7
author:    Alasq
catalog: true
tags:
    - Chrome Devtools Tip
---

这个真心不错,以前都是装插件使用滚动截图的功能弄得
1. F12 打开
2. `ctrl shift p`打开 goto anywhere 命令栏
3. 输入 `full`找到对应的命令回车
![image.png](https://upload-images.jianshu.io/upload_images/8156292-07c9b096e0015d2d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 补充
如果觉得每次找这个命令麻烦,可以把该功能设置成快捷键
除了全页截图,还有
Capture node screenshot - 截取正在检查的节点
Capture screenshot - 只截取可视区域的页面
Capture full size screenshot - 整个页面的截图,即使没有呈现在可视区域内的
Capture area screenshot - 跟QQ截图一样,自己划定区域

# 思考
这个截图功能在做自动化测试时候非常有用,不知道 webDriver是不是用这种内置API去实现的,还是说用的c++调用操作系统能力去实现的?有知道的老铁留言讨论下