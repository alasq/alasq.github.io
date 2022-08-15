---
title: 无js的菜单栏收缩与折叠动画
date: 2022-08-15 22:33:37
tags: [css,html]
---
菜单栏收缩主要使用下面的样式实现
```css
nav:hover,nav:focus-within{
   transform:translateX(100%)
}
```

折叠面板动画
```css
details[open] summary ~ *{
  animation:sweep .5s ease-in-out
}
@keyframs sweep{
  0% {opcity:0;margin-left:-10px}
  100% {opcity:100;margin-left:0px}
}

```
