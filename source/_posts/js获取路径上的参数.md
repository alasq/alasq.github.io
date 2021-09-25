---
title: js获取路径上的参数
date: 2021-09-25 22:19:18
tags: 代码片段
---
加入有如下请求js的路径,怎么在some.js中获取这个参数?
`base_url/path/to/some.js?username=bob`

```js
let url=new Error().stack.match(/at\s(.*)\s/)[1];
```
通过错误对象的堆栈信息,拿到报错的URL。我是真的佩服这个大神的脑洞。