---
title: netlify介绍
date: 2021-12-17 22:20:04
tags: 博客
---
# 目前博客存在的问题
github pages服务部署,国内访问很慢,github防止百度爬虫不收录

# 解决
使用netlify可以做静态网站的cdn部署

# 使用方法
1. 使用github账号登录netlify
2. 授权netlify访问需要部署的仓库与分支
---------------
3. 如果有自己的域名,在DNS解析服务器上,CNAME解析到netlify提供的域名即可


# 验证
ping 一下自己的域名,看下真实地址对不对就可以的
![](images/2021-12-17-22-27-52.png)

# netlify官网
https://www.netlify.com/