---
title: '启动tomcat时,log出现淇℃伅'
date: 2021-09-26 21:32:50
tags: tomcat
---
`淇℃伅`其实是 `信息`的乱码显示
修改tomcat安装目录下的`config/logging.properties`文件,找到`java.util.logging.Consolehandler.encoding`,将值改成`GBK`即可解决该问题。我下载的comcat8.5默认是`UTF-8`

如果没有这个配置项就在最后直接加上
```properties config/logging.properties
java.util.logging.Consolehandler.encoding = GBK
```