---
title: 利用bat简化命令行脚本
date: 2021-09-26 20:49:36
tags: cmd
---
## 注册表修改
创建 `fastkey.reg` 注册表修改文件。 AutoRun后面的路径修改成自己的配置文件，这个修改是让CMD每次执行的时候去执行下这个`fastkey.bat`
```reg fastkey.reg
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Command Processor]
"AutoRun"="D:\\profile\\fastkey.bat"
```

## 创建修改 fastkey.bat 文件
这里我创建了三个命令别名
1. (单行命令)用linux shell的`ls`命令执行windows cmd的dir命令。`$*`代表把`ls`后面所有的参数带给`dir`
2. (多行命令)多行命令的话,我们可以写在批处理文件中,然后通过别名调用批处理文件
3. 端口被占用查询`netstat -ano | findstr LISTENNING | findstr 8080`,这个命令我经常用但是又记不住,所以配置了一个别名,要注意的点是管道运算符`|`需要转义成`$b`,且两边不能有空格
```bat D:\profile\fastkey.bat
@echo off
doskey ls= dir /b $*
doskey dev= call %~dp0npmdev.bat
doskey port= netstat -ano$bfindstr LISTENNING$bfindstr $*

```
4. 创建自定义批处理脚本 npmdev.bat
```bat D:\profile\npmdev.bat
npm run dev || npm start
```


## 总结
现在我可以在命令行里面
1. 输入` dev `执行 npm run dev || npm start
2. 输入 `ls` 查看当前目录
3. 输入` port 8080` 查看端口被哪个进程占用,然后`taskkill`

**发挥想象,还能用这个做更多的事情**