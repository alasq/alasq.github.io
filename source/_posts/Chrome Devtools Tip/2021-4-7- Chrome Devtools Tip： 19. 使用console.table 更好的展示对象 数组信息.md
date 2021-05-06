---
layout:     post
title:      2021-4-7- Chrome Devtools Tip： 19. 使用console.table 更好的展示对象 数组信息
date:       2021-4-7
author:    陈诗樵
catalog: true
tags:
    - Chrome Devtools Tip
---

![console-table.gif](https://upload-images.jianshu.io/upload_images/8156292-a154534659201462.gif?imageMogr2/auto-orient/strip)

```js
var languages = [
    { name: "JavaScript", fileExtension: ".js" },
    { name: "TypeScript", fileExtension: ".ts" },
    { name: "CoffeeScript", fileExtension: ".coffee" }
];

console.table(languages);
```
## 补充
属性太多还可以传第二个参数 ,只展示要某些字段 `console.table(languages,['name']);`
# 使用console.time 诊断程序的运行时间
```js
console.time('My time #1');
console.timeLog('My time #1'); //打印计时器时间
console.timeEnd('My time #1');//打印计时器时间,并终止计时器
```
# 使用 console.timeStamp() , 可以在录制性能时间线打标记,快速定位性能问题
![console-timestamp-timeline.gif](https://upload-images.jianshu.io/upload_images/8156292-64043923a748af3c.gif?imageMogr2/auto-orient/strip)
