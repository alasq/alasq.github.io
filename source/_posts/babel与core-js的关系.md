---
title: babel与core-js
date: 2021-12-09 22:13:15
tags:  babel
---
# babel,垫片是什么?
1. babel 是用来把ES6,ESNext语法转换成ES5语法的,本身没有垫片的功能
2. 垫片就是给一些低版本的浏览器实现一些新的API,比如数组的`includes` `find`,`Promsie`等实现
3. `@babel/polifill` 这个垫片是babel官方提供的,相当于全量引入了长期支持的API,以及使用了的部分API
  ```js
  import "@babel/polyfill";
  // 等同于下面两句
  import "core-js/stable";//长期支持的
  import "regenerator-runtime/runtime";//部分使用的
  ```
4. 目前我们一般用 `@babel/preset-env`根据使用的API动态的使用垫片,项目中没用过的就不用垫了。
5. `core-js`是一个专门的垫片仓库
6. `@babel/preset-env` 的配置项 `useBuiltIns`有`entry` 与 `usage`两个选项,默认值是`false`,全量引入，体积最大。
7. `entry`需要手动在代码入口加上 `import '@babel/polyfill'`,表示按照目标兼容浏览器版本全量加载，体积小一些。
8. `usage`表示根据API按需加载，体积最小。
9. `@babel/preset-env`的配置项 `corejs:2`默认是`2.x`,如果需要使用`core-js@3`需要修改这个配置项`corejs:3`
10. babel在转换语法的时候会自动生成一些辅助函数,这些辅助函数大量重复存在
11. `core-js`的垫片会直接修改API 的原型与全局方法
12. `@babel/plugin-transform-runtime`插件会做两件事,第一辅助函数一次性引入,防止重复。第二，垫片作为闭包方法调用，防止全局污染


# 最佳实践的babel配置
`npm i @babel/core、@babel/preset-env @babel/runtime-corejs3 @babel/plugin-transform-runtime`
```js
{
  "presets": [
    [
      "@babel/preset-env",
      {
        "useBuiltIns": "usage"
      }
    ]
  ],
  "plugins": [
    [
      "@babel/plugin-transform-runtime",
      {
        "corejs": 3 // 指定 runtime-corejs 的版本，目前有 2 3 两个版本
      }
    ]
  ]
}
```
# 总结
core-js 是一个通用的垫片仓库,babel的垫片相关功能依赖core-js

http://www.ruanyifeng.com/blog/2016/01/babel.html