---
title: 盘点几个js库
date: 2021-09-26 22:11:23
tags: npm
---
# p5.js
把整个浏览器当做一个画板进行创意创作的绘图库
官网: https:p5js.org

# SpriteJS
SpriteJS是一款由360奇舞团开源的跨终端 canvas/webgl绘图库,我看了下API非常友好
官网: https:gitee.com/qihoo360/SpriteJS

# Annie2x
Annie2x是一款Adobe Flash的插件,支持Flash CC 2015及以上 和 Adobe Animate全线版本。
官网： http://annie2x.com/

# flatfile 
超强的数据导入js库,可以将Excel PDF CSV 导出成廷议的符合规则的结构化数据,强大的UI界面支持,非常适合集成到大数据采集的项目
## 官网
https://flatfile.io
## 特色
1. 前端数据导入,校验,格式化
2. 无须构建CSV解析器
3. 强大的API可以将结构化数据发布到任意端点

## flatfile库的设计思路
1. 定义JSONschema用于数据自身的校验
2. 提供导入校验的钩子 用于数据行字段之间的的校验,以及数据处理能力
3. 点击导入按钮,解析Excel,将Excel列与JSONschema列进行自动映射
4. 提供映射交互页面,给用户修改自动映射的结果
5. 生成数据处理后的结果,让用户填充校验失败的字段
6. 提供导出的API 提供平台能力使用这些结构化数据

# handsontable 强大的表格,数据再多都不会卡
https://handsontable.com/

# ag-grid The Best JavaScript Grid in the World
https://www.ag-grid.com