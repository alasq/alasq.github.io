---
title: 通过符号链接的方式移动vscode插件
date: 2021-09-26 20:40:28
tags: vscode
---
## 创建目录符号链接,修改插件位置,防止C盘爆掉
1. 剪切文件夹到新的目录,不然命令行会执行失败
2. 命令行使用管理员权限
3. `mklink /D "C:\Users\{username}\.vscode" "D:\{username}\.vscode"`

> {username} 为用户名

## vscode插件中文文档
http://liik.gitee.io/vs-code-extension-doc-zh/#/