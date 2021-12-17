---
title: npm ls 报错
date: 2021-05-06 22:10:35
tags: npm
---
> "npm ls --depth 0" 报错 "cb.apply is not a function" 
我是安装nvm 切换node版本后报错的

1. `win + r` 打开运行，输入`%appdata%`
2. 删除 `npm` 和 `npm-cache` 文件夹
3. 执行`npm cache clean --force`命令

此时应该就可以了。如果还不行，就执行卸载Node.js重新安装。