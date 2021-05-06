---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 36. 自定义时间测量API
date:       2021-4-7
author:    陈诗樵
catalog: true
tags:
    - Chrome Devtools Tip
---

Performance 面板就是以前的timeline面板。用于可视化分析代码性能。js提供了对应的API用于分析
https://developer.mozilla.org/zh-CN/docs/Web/API/User_Timing_API

![user-timing-performance.gif](https://upload-images.jianshu.io/upload_images/8156292-b83d2a537e1aeee8.gif?imageMogr2/auto-orient/strip)
您可以使用User Timing API查找缓慢的JavaScript代码。

尝试包装可能缓慢的代码，如下所示：
```js
performance.mark('costlyFunction Start') // 起始标记

costlyFunction()

performance.mark('costlyFunction End') // 终止标记

performance.measure(
    'costlyFunction', // 性能测量名称,会在时间线显示
    'costlyFunction Start',  起始标记
    'costlyFunction End' 终止标记
)
```
### 使用性能API有以下好处
- 将性能指标注入您不熟悉的应用程序中(上图的例子)
- 以编程方式读取JavaScript中记录的所有性能指标。`performance.getEntries()` `performance.getEntriesByType(entryType)`
`performance.getEntriesByName(name, entryType)`
- performance将性能捕获代码部署到最终用户，以便您可以收集实际用户指标。
- 了解真实用户监视的好处，以及它与综合监视的比较。
- 使用[Boomerang](https://github.com/SOASTA/boomerang)和Node.js之类的工具组合，从您的真实用户直接接收服务器的性能指标。
- Dev在DevTools中可视化用户计时指标，并将其与现有的火焰图相关联。
- 使用外部服务和插件可视化您的性能指标。

# 补充 
我们做性能录制的时候,系统获取资源,事件触发的时候,内部就是调用的这个API。Chrome选择暴露给我们，让我们在录制的时候，可以更快的找到我们想分析的部分，有针对性的分析我们想分析的代码段。我们还能做监控，当代码执行达不到我们预期的效率的时候，触发上报机制，上报到监控系统。

