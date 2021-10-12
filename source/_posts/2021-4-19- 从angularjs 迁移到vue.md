---
layout:     post
title:      2021-4-19- 从angularjs 迁移到vue 
date:       2021-4-19
author:    Alasq
catalog: true
tags:
    - 项目笔记
---

由于历史原因，项目组维护的项目有 vue  angularjs  angular 多个包。招聘成本比较高，需要统一技术栈，全部使用vue重构。
这里记录下迁移过程，希望能帮助有需要的人。
本文记录从angularjs 迁移到vue ，后续angular 迁移到vue单独成文

# 路由 ui-router To vue-router
`main.js`这部分直接重写
# 多语言处理 angular-translate To vue-i18n
## 1. 模板中的 translate 
1. 使用正则替换 `translate\s?=\s?["'](.*?)["']` `v-t="'$1'"` , 替换下面这三种格式成指令
![image.png](https://upload-images.jianshu.io/upload_images/8156292-61c2d902fa125889.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
2. 定义全局指令 `v-t`
 ```
Vue.directive('t', function (el,binding) {
    el.innerText=binding.value
  })
```
$如果有用到 filter的话就还要定义filter,我们项目没有这么用就没写 $
## 2. js中的 $translate.instant
在有注入`$translate`的地方导入 vue-i18n的实例
```js
import $translate from './i18n/' // 假设/i18n/index.js 默认导出的是vue-i18n的实例
$translate.instant=$translate.t //instant属性跟 vue-i18n的实例t是一样的
```
# \$scope 与 \$http  处理
首先将模块从这个样子
```js
module.exports=['$scope',function($scope,$http){
}]
```
改成下面这个样子
```js
export default function($scope,$http){
  return $scope
}

```
这里我写了一个通用方法`getVueOptions`处理$scope
```js
// 这些代码写在一起是为了方便查看学习,项目中肯定会抽成模块
import axios from axios;//使用axios代替$http
const instance=axios.create()
instance.default.header.common['content-type']='application/json'
// 将$scope分解成vue组件的 methods 与 data
function getVueOptions($scope) {
  const options = {
    data: {},
    methods: {}
  }
  for (const key in object) {
    if (Object.prototype.hasOwnProperty.call(object, key)) {
      const element = object[key];
      if (element instanceof Function) {
        options.methods[key] = element
      } else {
        options.data[key] = element
      }
    }
  }
  return options
}
let scope={}
const opts=getVueOptions(fn(scope,instance))
export default {
  data(){
    return {
      ...opts.data
    }
  },
  methods:{
    ...opts.methods
  }
}
```
# ng-init 处理
这个放到 `mounted()`里面调用`this.xxx`即可

# 模板中的替换
把angular组件模板`xx.html`,直接贴到vue组件的 `<template><div></div></template>`中

搜索 ` ng-` ng-前面有空格,如果是方法的话(ng-cick,ng-mouseover)就换成`@` ,属性(ng-class,ng-style)就换成`:`,指令(ng-if,ng-show,ng-model)就换成`v-`

## 属性绑定方式修改
正则模式搜索 `\s(.*?)\s?=\s?(["'])\{\{(.*?)\}\}\2` 替换成 `  :$1="$3"`
![image.png](https://upload-images.jianshu.io/upload_images/8156292-7eca4862d9bd6ee0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
# rootScope 处理
我这项目没怎么用,如果有用到就 export导出下,利用provide注入到根组件,用到的地方 inject一下
# 其他依赖注入
用类似axios的替换模式一个一个换成你vue的替代品即可,如果使用方式有差异就用正则查询全局替换就好了
## 剩下的就是体力活儿了
**组件**  **指令**  **过滤器** 一个一个的重构就好了
组件的props有些是双向绑定的,可以使用vue的 `xxx.sync` `this.$emit('update:xxx')`的写法来搞定


**下一篇 ：**《 typescript angular7 项目迁移到 vue2.x  》等我把改完再发心得
