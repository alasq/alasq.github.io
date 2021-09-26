---
title: 非vue-cli构建的项目使用 webpack-dev-server不打印代理日志
date: 2021-09-26 23:51:28
tags: webpack
---
使用 webpack-dev-server打印代理日志需要使用以下配置
```js
module.exports={
  devServer:{
    proxy:{
      "/"{
        target:'',
        logLevel:'debug'//加上这个就可以了
      }
    }
  }
}
```
