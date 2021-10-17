---
title: 华为OD牛客网岗机试题困难
date: 2021-10-12 06:31:17
tags: 面试
---
面了下华为德科的岗位，居然要机考。机考要求做三道编程题。

## 聊聊华为德科
华为社招岗位都在19级以上，是华为挖人用的，都是大厂随便进的狠角色。校招的成本太高了，工资高还要培养，培养的差不多了人家就要跑路了，在没有股票的加持之下，华为的工资相对一线大厂还是较低的。外包仔的职级一般在4-12之间，最高可以达到16级，草吃的少还能跑的外包马仔是写代码的主力军，华为员工还是写PPT比较多。之前听说海思那边13级外包直接转内部岗位，反正我是没见过13级的外包仔，毕竟这么牛了还干外包的确实少见。这种写代码的都是外包仔就导致了一个问题，人员流动性特别大，外包公司对外包仔宰的也狠，最高的时候可能是46分成，你4，公司拿6，这两年好些了，华为强制要求至少55开。不知道哪个高人想到了一个妙招，华为德科，传说的中外包精英，干掉中间商挣差价，也能增加外包仔归属感，加上与华为员工同工同酬，着实提高了外包仔的福利待遇，还能转华为正编，这个饼还是挺香的。

## 面试流程
1. 牛客网机考（三道题，两简单，一难），收到邮件后7天内做完就好
2. 性格测试
3. 技术面试
4. 综面&资面

全程远程面试,HR拿到简历会要身份证号,锁定这个人,防止内部抢人。

## 摄像头？？
机考需要摄像头，笔记本积灰多年，台式机木有摄像头，拼多多一个19.9的还在路上，无聊就先把题库的困难级别的题都给它刷了吧！相对于华为内部的OJ算法题库，这些真心小Case。

## 困难级别的题目如下
![](/images/2021-10-12-07-16-49.png)

## 开刷
以下编码都是使用 `JavaScript Node`去做的,毕竟我一前端还是对js比较熟悉

### HJ18 识别有效的IP地址和掩码并进行分类统计
这个题的描述坑太多了,出问题的测试用例也看不全
```js
// DOTO
```
### HJ19 简单错误记录

```js
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

let lines=[]
rl.on('line', function (line) {
    lines.push(line)
});

rl.on('close', function (line) {
let err=[]
lines.forEach(i => {
  let [path, line] = i.split(' ');
  let name = path.split('\\').pop().slice(-16)

  let finded=err.find(itme=>itme.name==name&&itme.line==line)

    if(finded){
      finded.count++
    }else{
      err.push({name:name,line:line,count:1})
    }

  
})

err.slice(-8).forEach(item=>{
  console.log([item.name,item.line,item.count].join(' '))
})
});
```


### HJ27 查找兄弟单词

```js
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});
rl.on('line', function (line) {
    let [n,k]=line.split(' ').slice(-2)
    let bs=line.split(' ').slice(1,-2)

    let ret=bs.filter(item=>compare(item,n)).sort()
    console.log(ret.length)
    if(ret[k-1]){
          console.log( ret[k-1])
    }
 
    function compare(a,b) {
        if(a===b)return false
      return a.split('').sort().join()==b.split('').sort().join()
    }
});
```

## 我机考通过了
三道里面两道简单,一道中等难度。就没有往后面刷了！！