---
title: 开发灵异事件之base64图片传输
date: 2021-09-09 20:11:56
tags:
---
### 事件
发出去的请求一毛一样，都包含了同一张base64格式的图片，图片显示出来是一样的。对比内容不一样。但是请求时间差距3分钟，甚至超时。接口20M大小的图片也能秒级处理。 图片来源一个是前端上传转换的base64，一个是后端把pdf文件首页转换出来的。

### 原因
后端生成的图片base64包含大量的换行符，http协议中的换行符有特殊含义，会被网关服务器解析，导致请求超时。

### 知识点
base64格式里面有大量的换行符，会严重影响传输效率