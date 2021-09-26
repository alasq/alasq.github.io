---
title: 设置node最大使用内存
date: 2021-09-26 23:48:31
tags: node
---
node的最大使用内存是2G 超出会导致程序退出

下面设置的是4096M
`setx NODE_OPTIONS --max_old_space_size=4096`