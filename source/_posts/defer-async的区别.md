---
title: defer async的区别
date: 2021-09-25 20:57:20
tags: html
---

![图片](http://segmentfault.com/img/bVcQV0)
1. `defer` 能确保脚本加载的顺序,会在dom解析完成后执行
2. `async` 是先请求到先加载,会中断dom解析
3. ES6 Module 有 `type=module` 默认defer模式
4. `async`适合完全独立的脚本