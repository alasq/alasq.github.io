---
title: 防止xss注入
date: 2021-10-22 19:25:57
tags: web安全
---
## 谁是 OWASP ®基金会
Open Web Application Security Project

## web安全理论基础
https://cheatsheetseries.owasp.org/

## xss注入
主要是需要转义html `< > " ' &` 这5个字符
* `>` 转 `&gt;` 
* `<` 转 `&lt;` 
* `"` 转 `&quot;` 
* `'` 转 `&#39;` 
* `&` 转 `&amp;` 

## 最佳实践
直接使用雅虎的xss-filters
https://www.npmjs.com/package/xss-filters