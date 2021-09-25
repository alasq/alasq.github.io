---
title: 极致简洁的微前端框架-京东MicroApp开源了
date: 2021-09-25 21:08:03
tags: 读后感
---
原文地址 https://article.itxueyuan.com/ylqMxp

* 基于自定义元素，影子节点。web-components实现。
* 自定义元素属性不支持对象，这里重写set方法,用数据中心传递数据
```js
const dataCenter={
  people:{
    name:'Bob',
    age:18
  }
}
(function (setAttribute) {
  let setOld=setAttribute;
  document.getElementById("myPeople").setAttribute=function (attrName,attrValue) {
    setOld(attrName,attrValue);
    this.attrName=dataCenter[attrValue]
  }
})(document.getElementById("myPeople").setAttribute)

```
* 使用微前端会导致各个子项目技术栈完全不一致,各玩各的真的好吗?难道统一技术栈不是更好的选择,这样玩用人成本不是更高了么?
* 微前端本身也是有学习成本的,这种各玩各的问题定位起来更难了,想组织技术培训的话,卧槽!!!各个子项目用的技术都不一样,无形提高了沟通成本