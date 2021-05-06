---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 34. 通过服务器增加 Server-Timing 响应头展示时间信息
date:       2021-4-7
author:    陈诗樵
catalog: true
tags:
    - Chrome Devtools Tip
---

![server-timing.gif](https://upload-images.jianshu.io/upload_images/8156292-dfe3866e1052de27.gif?imageMogr2/auto-orient/strip)
nodejs 示例代码
```js
const headers = {
    'Server-Timing': `
        lb=18; "Load Balancer",
        server-3=104; "Server #3 Startup",
        db-read=187; "Database Read",
        aws-download=317; "AWS Content Download",
        db-write=218; "Database Write",
        templating=48; "Templating plugin"
    `.replace(/\n/g, '')
};

response.writeHead(200, headers);
```
# 补充
后台这里应该有对应的中间件实现,有兴趣的老铁可以自行搜索下