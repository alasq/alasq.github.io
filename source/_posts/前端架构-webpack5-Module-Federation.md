---
title: 前端架构 webpack5 Module Federation
date: 2021-11-27 21:25:45
tags: [前端架构,webpack]
---

# 场景
A组: 维护一个UI组件库  
B组: 维护一个单页APP,内部有很多公共函数库,业务相关组件  
C组: 新建一个单页APP,需要用到A组的UI组件库,B组项目的公共函数库,部分业务组件

# 前端模块化的现有方案
A组将UI库发布到npm仓库,B组将公共函数库作为单独的npm包发布,业务组件拷贝一份到C组的代码库

## 问题
1. B组的改动量大
2. B组每次公共函数库的改动,需要通知到C组重新发布
3. 业务组件改动,BC两组都要进行修改

## 解决
函数库与业务组件都打成umd模块放到静态资源服务器上,C组以script标签动态引入,以AMD模块的使用方式从window作用域下使用

## 继而产生的后续问题
1. 污染window作用域下命名空间
2. 打出来的umd模块需要是完整的,包含全部依赖,体积很大
3. 随着要封装暴露的entry越来越多,打包时间越来越长

# Module Federation 模块共享解决方案

## B组项目修改webpack配置,将公共函数库,公用的业务组件使用`ModuleFederationPlugin` 插件配置成共享模块

```js B组项目webpack配置
// 假设B组的页面部署到 www.baidu.com/businessB/

const {ModuleFederationPlugin}=require("webpack").container
const config = {
   ...otherConfigs
  plugins: [
    new ModuleFederationPlugin({
      name: "appB",
      filename:"remoteEntry.js",
      exposes: {
        './util': './src/util', //需要共享的公共函数库 
        './hero-list': './src/components/hero-list',//需要共享的业务组件 英雄列表
      },
    })
  ]
}
```

## C组使用`ModuleFederationPlugin` 插件配置配置B组发布到环境上的远程模块
假设C组的页面部署到 www.baidu.com/businessC/

```js C组项目webpack配置
const config = {
   ...otherConfigs
  plugins: [
    new ModuleFederationPlugin({
      remotes: {
        appB: "appB@//www.baidu.com/businessB/remoteEntry.js"
      }
    })
  ]
}
```

```html C组的主页面
<head>
  <script src="/businessB/remoteEntry.js" defer></script>
  <script src="./main.js"></script>
</head> 
```
```js main.js
(async function(){
  let util = await import('appB/util')
})()
```

```html component.vue
<script>
export default {
  components:{
    heroList:()=>import("appB/hero-list")
  }
}
</script>
```

## 完整的 DEMO

https://stackblitz.com/github/webpack/webpack.js.org/tree/master/examples/module-federation?terminal=start&terminal=

### external-remotes-plugin 可以从window作用域下动态获取远程仓库的地址
https://www.npmjs.com/package/external-remotes-plugin

```js host config
const config = {
   ...otherConfigs
  plugins: [
    new ModuleFederationPlugin({
      name: "app1",
      remotes: {
        app2: "app2@[window.app2Url]/remoteEntry.js"
      }
    }).
    new ExternalTemplateRemotesPlugin(),
  ]
}
```

```js host main.js
window.app2Url = "//localhost:3002"; // Whatever the url/logic to determine your remote module is

import("./bootstrap");
```