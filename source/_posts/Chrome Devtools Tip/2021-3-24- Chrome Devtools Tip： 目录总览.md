---
layout:     post
title:      2021-3-24 Chrome Devtools Tip： 目录总览
date:       2021-3-24
author:    陈诗樵
catalog: true
tags:
    - Chrome Devtools Tip
---

# 目标读者
WEB 应用 **设计& 开发 & 测试 & 重度用户**
# 关于调试
WEB应用开发者中，设计=》开发=》测试=》BUG修复=》回归测试=》发布=》部署。Chrome Devtool 都是必须要掌握的知识。在项目中，发现很多同事写代码还行，遇到问题就解决的很慢，或者无从下手。玩转调试可以：
1. 增加开发效率
2. 快速定位问题
3. 降低沟通成本

# 阅读前
请先阅读 Google Chrome DevTools 官方文档(https://developers.google.cn/web/tools/chrome-devtools/) 

# 来源与改进
文章主要来源于（https://umaar.com/dev-tips/） ，并做以下改进
1. 汉化
2. 部分过时的gif重录
3. 加上自己的理解

# 计划
三月底完成！

# 目录
1. Port Forwarding 允许localhost URL 在移动设备调试
2. 如何使用DevTools触发CSS伪类
3. 使用cURL复制功能重播Network面板的请求
4. 在任何网页上运行预定义的代码段
5. 通过本地修改查看您的更改
6. 轻松的使用性能面板录制时间线
7. 将图片复制为base64编码data URI
8. 资源面板Source中的快捷键
9. 多光标编辑 框选
10. Console面板的一些API
11. Network 网络面板过滤器
12. Element面板
13. 通过快捷键快速切换 devtools 附着状态
14. 断点调试相关的技巧
15. 颜色拾取器增强
16. 动画调试
17. 调试jquery 事件监听
18. 隐藏网络请求报错的console.error
19. 使用console.table 更好的展示对象 数组信息
20. Element面板快速切换class查看效果
21. 降低CPU的性能与网络速度来观测性能
22. 使用 Sources 面板 Threads 调试
23. 使用sourceMap 调试ESNext语法
24. 在“Network”中查看来自其他应用程序的网络流量
25. 通过Performance面板录制,行级别查看代码耗时
26. Store as global variable 存储成全局变量
27. 利用Quick Source 快速写样式
28. Chrome带参数启动
29. 自定义Network面板的显示列，展示我们关心的响应头
30. devtools支持热更新调试Nodejs
31. Blackboxing 获得更好的调试会话
32. lighthouse 面板检查网页状态
33. `css tracker`面板查看未使用的css
34. 通过服务器增加 Server-Timing 响应头展示时间信息
35. Network 查看实际访问的IP
36. 自定义时间测量API
37. 查看帧率FPS
38. 复制完整的调用栈
39. 网页全页截图