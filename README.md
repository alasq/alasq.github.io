# alasq.github.io
hexo 博客项目,建议直接fork这个仓库到自己的主仓库 `<username>.github.io`

## 需要注意的地方
1. master分支只是用来发布的,源代码分支是 source, 所有改动需要在source分支修改
2. `/source/CNAME` 没有自己注册域名需要删除
3. next主题我用的是自己fork的仓库,为了支持简书图片,就自己改了下源代码,如果想使用官方仓库,需要改`\.github\workflows\pages.yml`

```diff
--- a/.github/workflows/pages.yml
+++ b/.github/workflows/pages.yml
@@ -24,7 +24,7 @@ jobs:
       - name: Install Dependencies
         run: npm install
       - name: Install Theme
-        run: git clone https://github.com/theme-next/hexo-theme-next themes/next
+        run: git clone https://github.com/alasq/hexo-theme-next themes/next
       - name: Build
         run: npm run build
       - name: Deploy
```
