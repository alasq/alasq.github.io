---
title: js避坑-new Array
date: 2022-08-15 21:47:31
tags:
---
`new Array(8).map(i=>[])`这种声明二维数组的方式会报错

改成 `new Array(8).fill().map(i=>[])`即可

报错的原因是 new Array 产生的数组比较特殊 有length 但是没有内容，所以无法迭代

不过我一般用 `Array.form({length:8},i=>[])`这么初始化