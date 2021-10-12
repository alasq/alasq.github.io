---
layout:     post
title:      tensorflow环境搭建
author:     Alasq
header-img: img/post-bg-re-vs-ng2.jpg
catalog: true
tags:
    - TensorFlow
---
## TensorFlow 的两个依赖
### Protocol Buffer 
结构化处理工具,比json,xml更小,解析更快
### Bazel 自动化构建工具,类似于maven
- BUILD  文件用于表示构建目标
- WORKSPACE 文件用于标记外部依赖

## 安装
三种方式安装: docker  pip 源码  
我们使用pip来安装
### 安装 Anaconda
python的发行版,除了python,还包含了很多常用的关于科学计算的库  
我参考这篇文章安装成功的 https://www.cnblogs.com/ljysy/p/10660885.html

我这里下载的是 Anaconda 版本是 Anaconda3-5.3.1-Windows-x86_64.exe 对应的 python3.7.0

1. `conda create -n tensorflow python=3.7.0` 创建了一个独立的tensorflow的工作空间,在这个空间内使用的python版本为3.7.0
2. `conda activate tensorflow` 激活这个名为tensorflow空间
3. `pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple`  在空间内配置pip的镜像源
4. `pip install tensorflow`


### Anaconda + vscode 配置
https://www.jianshu.com/p/ef1ae10ba950

### 如果提示pip的版本过低,就使用下面的命令升级pip
`pip install -i https://pypi.tuna.tsinghua.edu.cn/simple pip -U`


### code-runner 输出乱码
参考这个文章解决  https://www.cnblogs.com/zhaoshizi/p/9050768.html  

在项目下 `.vscode/settings.json` 配置python的路径以及 code-runner的执行路径,设置成全局的也行吧
```json
{
  "python.pythonPath": "F:\\ProgramData\\Anaconda3\\envs\\tensorflow",
  "code-runner.executorMap": {
    "python": "set PYTHONIOENCODING=utf8 && F:\\ProgramData\\Anaconda3\\envs\\tensorflow\\python.exe",
  },
}
```

### 验证
试下tensorflow官网的例子,能跑起来就是成功了。有时候下载测试数据集的时候会失败，多试几次就好了