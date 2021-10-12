---
layout:     post
title:      2021-3-24 Chrome Devtools Tip： 4.在任何网页上运行预定义的代码段
date:       2021-3-24
author:    Alasq
catalog: true
tags:
    - Chrome Devtools Tip
---

![snippets.gif](https://upload-images.jianshu.io/upload_images/8156292-3ab1f856b9a0a89b.gif?imageMogr2/auto-orient/strip)
DevTools中提供了一个名为Snippets的功能，使您可以注入可在网页上运行的JavaScript代码（与在控制台面板中重新键入JavaScript代码相比，这更方便）。尝试一下：

*   转到“来源”>“代码段”（位于左侧边栏中）
*   在摘要窗口中单击鼠标右键，然后选择“新建”。
*   输入文件名和所需的代码段
*   右键点击代码段，然后选择运行（或Ctrl / Cmd + Enter）

您还会注意到，它具有多行编辑功能，并且可以确认退出而不保存。

这是大量的DevTools片段集合：[https](https://github.com/bgrins/devtools-snippets) : [//github.com/bgrins/devtools-snippets](https://github.com/bgrins/devtools-snippets)
# 补充
代码段可以直接在 `Console`面板执行的，但是在里面不好调整格式，也没有自动完成，也不能保存。所以这种方式挺好的。

总能遇到一些本地环境不能调试的代码，直接使用代码段功能在测试环境执行我们的代码，省去了打包上环境的时间，也确保了代码的正确性。
# 思考与尝试
尝试下打断点，触发断点后，再执行代码段，不知道此时的变量作用域怎么样的呢？有兴趣的同学可以自己试试，评论区见答案。