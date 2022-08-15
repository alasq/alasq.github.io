---
title: js踩坑 isNaN(null)返回的是false
date: 2022-08-15 22:13:56
tags: js
---
`isNaN(null) === false` 按照方法名的字面意思  null不是一个数组,没毛病。
但是这个方法认为是一个数字，它的逻辑是先用`Number(null)`得到`0`,0是数字,所以等式成立。

`['']==false`这个也是成立的哟
- 隐式转换规则,跟字符串比都转字符串比较,跟数字比转数字,布尔值当数字`0`跟`1`看待,对象的话用`valueOf`拿值,拿到的如果不是原始值就`toString`后比较
- `[''].toString()`得到'' 右边是false
