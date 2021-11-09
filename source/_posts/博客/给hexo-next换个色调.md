---
title: 给hexo next换个色调
date: 2021-11-09 21:41:59
tags: 博客
---
next的极简风我还是挺喜欢的，但是不喜欢这个黑白主题，死气沉沉的，我想给他换个色调。

1. 首先找到喜欢的色调图片
2. https://coolors.co/ 打开调色网站
3. 修改主题配置
```yml source/_data/next.yml
custom_file_path:
  #head: source/_data/head.njk
  #header: source/_data/header.njk
  #sidebar: source/_data/sidebar.njk
  #postMeta: source/_data/post-meta.njk
  #postBodyEnd: source/_data/post-body-end.njk
  #footer: source/_data/footer.njk
  #bodyEnd: source/_data/body-end.njk
  variable: source/_data/variables.styl
  #mixin: source/_data/mixins.styl
  #style: source/_data/styles.styl  
```
4. 新建文件 `source/_data/variables.styl`
5. 下面是默认色
  ```css
  :root {
    --body-bg-color: #f5f5d5;
    --content-bg-color: #f5f5d5;
    --card-bg-color: #f5f5f5;
    --text-color: #555;
    --blockquote-color: #666;
    --link-color: #555;
    --link-hover-color: #222;
    --brand-color: #fff;
    --brand-hover-color: #fff;
    --table-row-odd-bg-color: #f9f9f9;
    --table-row-hover-bg-color: #f5f5f5;
    --menu-item-bg-color: #f5f5f5;
    --btn-default-bg: #fff;
    --btn-default-color: #555;
    --btn-default-border-color: #555;
    --btn-default-hover-bg: #222;
    --btn-default-hover-color: #fff;
    --btn-default-hover-border-color: #222;
  }
  ```
  
修改后面这个文件就行了,但是我还没想好合适的颜色  
```less source/_data/variables.styl
$body-bg-color   = #BEE7E9 
$content-bg-color   = #a1e6e9  
// $card-bg-color   = #
// $text-color   = #
// $blockquote-color   = #
// $link-color   = #
// $link-hover-color   = #e4393c
// $brand-color   = #
// $brand-hover-color   = #
// $table-row-odd-bg-color   = #
// $table-row-hover-bg-color   = #
// $menu-item-bg-color   = #
// $btn-default-bg   = #
// $btn-default-color   = #
// $btn-default-border-color   = #
// $btn-default-hover-bg   = #
// $btn-default-hover-color   = #
// $btn-default-hover-border-color   = #

```


