---
title: promise分步请求接口
date: 2021-09-26 23:55:42
tags: 代码片段
---
# 背景
并发请求后台接口,处理时间过长,导致服务器超载挂掉,尤其是用户刷新页面操作,需要前端限制请求并发
```js
let arr = [
  { url: 'xxx', data: {} },
  { url: 'xxx', data: {} },
  { url: 'xxx', data: {} },
  { url: 'xxx', data: {} },
  { url: 'xxx', data: {} },
  { url: 'xxx', data: {} },
  { url: 'xxx', data: {} }
]
async function SubmitMsg(datas, count) {
  while (datas.length > 0) {
    let urls = datas.splice(0, count)
    let ret = await Promise.all(urls.map(getData))
    console.log(ret);

  }
}

function getData({ url, data }) {
  return axios.post(url, data)
}

SubmitMsg(arr,2) //每次发送两个请求
```