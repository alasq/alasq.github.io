---
title: npm生成命令行脚本
date: 2021-09-26 21:15:49
tags: npm
---
1. 入口第一行 `index.js` 声明脚本执行环境是node
```js /path/index.js
#! /usr/bin/env node
```

2. `package.json#bin`对象内可以配置多个命令行。key是命令,value是文件路径
```json /package.json
{
  "bin":{
    "vue":"path/index.js",
    "名称2":"path/to/some.js"
  }
}
```
3. 使用 `npm link`全局安装这个包,就可以使用`vue xxx`命令咯
4. 或者作为本地依赖项,在srcipts里面使用
```json /package.json
  {
    "srcipts":{
      "cli":"vue xxx"
    },
    "dependencies":{
      "vue-cli":"file:./index.js"
    }
  }
```