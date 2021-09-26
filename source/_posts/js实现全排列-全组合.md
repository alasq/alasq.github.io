---
title: 'js实现全排列,全组合'
date: 2021-09-26 21:39:37
tags: 代码片段
---
最近刷OJ算法题库的时候,发现很多都是数学问题都使用的穷举法，于是写了获取穷举的全排列,全组合两个函数。

# 全组合
```js
/**
 * 全组合
 * @param arr  用于组合的元数据
 * @param n 取其中的n个数据用于组合
 * @returns 
 */
function getAllMix(arr, n) {
  let len = arr.length ** n //全排列的长度
  let res = Array.from({ length: len }, (item, k) => {
    // 构造都是0的空数组
    let g = Array.from({ length: n }, () => 0)
    let ret = [...g, ...k.toString(arr.length).split('')].slice(-n).map(j => arr[j])
    return ret
  })

  return res
}

getAllMix([1,2,3],2)
// 从1,2,3中获取其中两个数的所有组合
// [1, 1]
// [1, 2]
// [1, 3]
// [2, 1]
// [2, 2]
// [2, 3]
// [3, 1]
// [3, 2]
// [3, 3]
```

# 全排列
```js
/**
 * 全排列
 * @param arr 全排列的元数据
 * @returns 
 */
function getAllSort(arr) {
  let len = arr.length ** arr.length
  let res = Array.from({ length: len }, (item, k) => {
    // 构造都是0的空数组
    let g = Array.from({ length: arr.length }, () => 0)
    let ret = [...g, ...k.toString(arr.length).split('')].slice(-arr.length)
    return ret
  })
  let dd = res.filter(item => {
    item=item.map(k=>parseInt(k))
    let set = new Set(item)
    return set.size == item.length
  }).map((i) => {
    let out=[]
    i.forEach((j,k) => {
      out[k]=arr[j]
    })
    return out
  })
  return dd
}

getAllSort([1,2,3])
// 数组1,2,3的全排列
// [
//     [ 1, 2, 3 ],
//     [ 1, 3, 2 ],
//     [ 2, 1, 3 ],
//     [ 2, 3, 1 ],
//     [ 3, 1, 2 ],
//     [ 3, 2, 1 ]
// ]
```
