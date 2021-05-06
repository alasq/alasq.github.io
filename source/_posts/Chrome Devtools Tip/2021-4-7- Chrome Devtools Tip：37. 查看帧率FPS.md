---
layout:     post
title:      2021-4-7- Chrome Devtools Tip：37. 查看帧率FPS 
date:       2021-4-7
author:    陈诗樵
catalog: true
tags:
    - Chrome Devtools Tip
---

帧率是视频设备可以产生图像（或帧）的速率。 电影和游戏最熟悉它，但现在已广泛用作网站和 Web 应用程序的性能指标。
> 60 fps 的帧率被认为是实现流畅显示的目标，因此，为响应某些事件而需要同步进行的所有更新，需要在 16.7 ms (1000ms/60次=16.7ms  )内完成。

> 但是，一致性尤为重要：如果您无法提供 60 fps，则最好以更低的速率连续提供更好的帧率，并避免帧速率突然下降而导致站点假死。


![render-perf-pane.gif](https://upload-images.jianshu.io/upload_images/8156292-e47f4f9b065e1322.gif?imageMogr2/auto-orient/strip)
# 补充
新版的这个功能貌似被移除了,我以前还用过 render 面板去看元素重绘还是很方便的,有颜色做区分
如果真要看FPS,建议还是在录制一下,参考下图去查看比较方便
![image.png](https://upload-images.jianshu.io/upload_images/8156292-eb77c220b0f33ff5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
