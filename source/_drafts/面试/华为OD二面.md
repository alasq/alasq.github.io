---
title: 华为OD岗位二面
date: 2021-11-04 21:46:57
tags: 面试
---
第二轮还是技术面,与第一轮模式一样,先对话,后做题

## 基础
1. 项目经历
2. 项目担任的角色
3. 项目组给的奖励,是因为做了哪些工作才得到的认可
4. vue全家桶包含哪些东西,分别是做什么用的
5. 获取前端新技术,资讯的途径

面试官没有问技术细节，跟一面相比更注重个人的整体能力

## 笔试题如下

给定一个由小写字母组成的字符串，找出其中最长的一个不包含重复字符的字串，打印出最长字符子串长度。

**解答要求**

时间限制：1000ms, 内存限制：64MB

**示例 1**

> 输入: "abcde"  
> 输出: 5  
> 解释: 因为无重复字符的最长子串是 "abcde"，所以其长度为 5。

**示例 2**

> 输入: "aaa"  
> 输出: 1  
> 解释: 因为无重复字符的最长子串是 "a"，所以其长度为 1。

**示例 3**

> 输入: "abcaab"  
> 输出: 3  
> 解释: 因为无重复字符的最长子串是 "bca"，所以其长度为 3。

**进阶要求**

不使用 for 循环实现

------------------------------
### 使用循环解题
```js
function test(str) {
  let i = 0, start, end = str.length, len = 0;
  let chars = new Set();
  while (str[i]) {
    start = start || i
    let char = str[i]
    end = i
    if (chars.has(char)) {
      if (chars.size > len) {
        len = chars.size
      }
      i = ++start
      chars.clear()
    } else {
      chars.add(char)
    }
    i++
  }

  if (chars.size > len) {
    len = chars.size
  }
  if (!len) {
    len = str.length
  }
  console.log(len)
}

test('abcfabcde')//6
test('abcde')//5
test('abcaab')//3
test('aaa')//1

```

### 不使用循环解题??

用正则?有解法的兄弟评论区见