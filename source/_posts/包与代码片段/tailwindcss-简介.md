---
title: tailwindcss 简介
date: 2021-10-09 07:17:19
tags: css
---

[中文文档](https://www.tailwindcss.cn/)

tailwindcss 是一个原子化的样式库,提供原子化的class,一个class只对应一条css属性

### 原子化的好处
* 不用费脑子想类名了
* css文件大小可控
* css更安全不用担心样式冲突

### 原子化的缺点
html里面会有一堆类名,不过tailwindcss认为可以通过组件化来规避这个问题,所以也不是缺点

### 分层设计
样式共分为四层,使用 `@layer`可以将我们的代码放到不同的位置,用来调整样式的优先级
1. base 主要定义全局样式,字体等
2. components 定义class,比如按钮,卡片
3. utilities 定义原子化的class
4. screens 定义媒体查询的class

### 支持响应式设计
sm md lg xl 2xl 大部分基础样式提供响应式前缀
* `sm` 640px 手机
* `md` 768px 平板
* `lg` 1024px 1080P显示器
* `xl` 1280px 2K显示器  
* `2xl` 1536px 4K 显示器  
例如 `w-full` `md:w-full`

![alt](https://iknow-pic.cdn.bcebos.com/f7246b600c33874427696bc25c0fd9f9d62aa0e4?x-bce-process%3Dimage%2Fresize%2Cm_lfit%2Cw_600%2Ch_800%2Climit_1%2Fquality%2Cq_85%2Fformat%2Cf_jpg)

### 支持状态类前缀
hover focus 等,不是全部的

### 不够用
tailwindcss只提供了最常用的样式对应的class,如果这些还不够用的话,我们可以通过指令自定义

- @layer 样式放的层级 ` @layer components{...}`
- @variants 定义状态前缀 `@variants hover{...}`
- @screen 定义媒体查询 `@screen sm{...}`
- @apply 现有的类打散组合  `@apply w-full py-2 px-4`
- @reponsive 是`@variants reponsive {...}`的别名
- screen() 与 @screen 类似 `@media screen(sm){...}`
- theme() 或者主题参数 `theme('colors.blue.500')`

以上是css中的写法,tailwindcss也支持在配置文件中使用js的写法配置。具体就不赘述了。