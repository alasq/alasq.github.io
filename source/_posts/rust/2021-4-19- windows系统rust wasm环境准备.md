---
layout:     post
title:      2021-4-19- windows系统rust wasm环境准备 
date:       2021-4-19
author:    陈诗樵
catalog: true
tags:
    - rust
---

#  rust开发环境搭建
rustup-init 下载地址 https://www.rust-lang.org/zh-CN/tools/install
> rustup 用于管理rust的版本,类似于管理node版本的nvm

C++ 编译工具链 下载地址 https://visualstudio.microsoft.com/zh-hans/visual-cpp-build-tools/
> rust 最终还是会编译成C++ 代码的,只勾选C++工具链即可。安装需要存储空间挺大的,不要装C盘
> windows上我们选择 msvc(微软visual-cpp)工具链 

##  rustup-init 安装rust
> 这里可以使用 清华的rustup-mirror加速安装 `RUSTUP_DIST_SERVER=https://mirrors.tuna.tsinghua.edu.cn/rustup`
![环境变量设置.png](https://upload-images.jianshu.io/upload_images/8156292-0c7fe3e0af73fd14.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

rustup-init是个命令行工具，按照默认的安装设置即可

![rustup-init.png](https://upload-images.jianshu.io/upload_images/8156292-429da5106348a60e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 配置cargo镜像
参考这个文章 https://cargo.budshome.com/reference/source-replacement.html
可以配置 `CARGO_HOME` 环境变量修改cargo的目录,因为默认在   `C:\Users\{username}\.cargo`，而且后面安装东西也在这么目录，最好还是设置下吧
> 默认是从国外下载，时间就是生命

## 确认安装是否成功
`rustup --version` 能看到正确的版本号 `rustc`不报错就可以了

## 安装cargo-edit
> cargo install cargo-edit

## 安装wasm-pack
> cargo install wasm-pack