---
title: 如何查看emoji表情的Unicode编码
date: 2021-10-22 19:13:48
tags: emoji
---
## 可以在下面这个网站复制粘贴emoji
https://getemoji.com/

## 👶🏻 这个除了复制粘贴怎么打印呢?

我们js中的字符串编码是`utf-8`
![](images/2021-10-22-19-19-17.png)
```js
escape('👶🏻')
// '%uD83D%uDC76%uD83C%uDFFB'

console.log('\uD83D\uDC76\uD83c\uDFFB')
//  👶🏻
```

## emoji-regex

https://www.npmjs.com/package/emoji-regex

这个仓库用来匹配字符串中的emoji表情,可以用来做富文本的图片替换