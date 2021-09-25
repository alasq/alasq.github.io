---
title: webpack-dev-server代理host配置
date: 2021-09-25 21:40:14
tags: webpack
---
# 让同事可以访问本地服务
`devServer.host`配置成 `0.0.0.0`或者是本机的IP,host默认值是`localhost`,只能自己访问

# 登录的问题
访问接口需要鉴权,通过IP访问的话 huawei.com 的cookie不能携带,导致要求登录。我们可以修改本机的DNS解析`C:\Windows\System32\drivers\etc`，将`127.0.0.1`解析到 `localhost.huawei.com`  。然后通过`localhost.huawei.com`去访问本地调试地址。

# Invalid Host Header
如果页面出现这个报错，需要修改webpack配置  `devServer.disableHostCheck`为`true`

> cmd  `ipconfig`可以查看自己的ip