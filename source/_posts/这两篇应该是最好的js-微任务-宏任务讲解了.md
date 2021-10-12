---
title: 这两篇应该是最好的js 微任务 宏任务讲解了
date: 2021-10-09 08:00:07
tags: js
---
https://www.cnblogs.com/jiasm/p/9482443.html

https://jakearchibald.com/2015/tasks-microtasks-queues-and-schedules/

## 总结
- 微任务,宏任务都是一个队列
- 宏任务产生的宏任务,追加在宏任务队列尾部
- 微任务产生的微任务,追加在微任务队列尾部
- 微任务队列空了才会执行下一个宏任务,自己新产生的也会执行完
- 不同浏览器也是有差异的,chrome跟W3C是一致的

