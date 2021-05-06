---
layout:     post
title:      2021-3-24 Chrome Devtools Tip： 5.通过本地修改查看您的更改
date:       2021-3-24
author:    陈诗樵
catalog: true
tags:
    - Chrome Devtools Tip
---

![local-mods.gif](https://upload-images.jianshu.io/upload_images/8156292-d122d3505663c200.gif?imageMogr2/auto-orient/strip)

本地修改使您可以查看（通过DevTools）对某些源文件进行了哪些更改。

进行更改并保存后，右键单击“源代码”面板中的文件，然后选择“本地修改”。每个修改都将列为新的更改，并且每个修改都可以单独还原。

本地修改有助于跟踪，进行了哪些更改，何时进行了这些更改以及对哪些文件进行了更改。

您可能还对较新的[DevTools更改面板](https://umaar.com/dev-tips/137-changes-panel/)感兴趣。
# 补充
1. 一般IDE（IDEA，VSCODE）自带的diff比较工具都挺好用的，但是如果去比较两个文件夹，还是建议使用**Beyond Compare 4**
2. git 自身的diff工具如果用的不舒服,可以改成vscode呢！这个文章是写怎么设置的，其他工具设置方法类似https://blog.csdn.net/LeonBec/article/details/78989149
3. 可视化的git工具，小乌龟我用的还是很习惯的，建议下载一个。https://tortoisegit.org/
4. 真的很讨厌用命令行装B，骗骗外行还行，这里怼一下那些天天 `git add .` 提交所有文件，也不`diff`一下的菜鸡
# 思考与尝试
devtools自带的diff工具，不知道git 命令行能不能设置成这个工具，知道的小伙伴评论区见哈！