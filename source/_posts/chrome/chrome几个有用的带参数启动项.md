---
title: chrome几个有用的带参数启动项
date: 2021-09-26 08:26:39
tags: chrome
---
## 打开新页签的时候自动打开devtools
`--auto-open-devtools-for-tabs`

## 去除安全井盖,打开没有证书的https页面的时候就不会有告警
`--ignore-certificate-errors`

## 关闭安全验证,同源策略会被关闭,方便口语调试,新版本的chrome后面的用户目录也是必须设置的

`--disable-web-securty --user-data-dir=C:\chromeData`