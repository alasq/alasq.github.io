---
title: node打包成可执行文件exe
date: 2021-09-26 08:31:09
tags:
---
## 使用pkg这个npm工具打包
1. 安装`npm i -g pkg`
2. 配置
   ```json
    {
      "bin":"main.js",
      "pkg":{
        "target":"",
        "outputPath":""
      }
    }
   ```
3. 执行 执行的时候可能会报错,因为要从GitHub下载一些依赖,需要能连上github才行

### 无法从github下载解决方案
1. 从pkg-fetch仓库的release文件中找到自己要打包的target编译版本,例如`node-v14.4.0-win-x64`,下载后修改名字,修改成`fetched-v14.4.0-win-x64`
2. 将下载的文件放到`~/.pkg-cache/v3.0`目录下,如果目录中有 `.downloading`的文件记得删除掉


## deno可以直接打包成exe,有兴趣的尝试下