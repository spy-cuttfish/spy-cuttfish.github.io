# Hugo+gihubPages踩的坑

之前利用github pages搞博客，都是乱弄一通。上一个是fork了https://github.com/Simpleyyt/jekyll-theme-next 的内容，之后只需要向_post文件夹里提交.md格式的文章就可以了，傻瓜式操作。
昨天看到一个很喜欢的Hugo主题，于是找了教程https://shangzg.top/zh-cn/2021-09-14-hugo-github-pages-build-a-personal-blog/#%E6%9E%84%E5%BB%BA%E9%9D%99%E6%80%81%E9%A1%B5%E9%9D%A2 一步步跟着来。但过程中还是出现了一些问题，浅记一下。

## GitHub Pages 部署Build失败
提示如下
`Liquid Exception: Liquid syntax error (line 468): Variable '{{??}' was not properly terminated with regexp: /\\}\\}/ in themes/LoveIt/exampleSite/content/posts/theme-documentation-content/index.en.md`
通过查询issues，在根目录添加一个空的`.nojekyll`文件可以解决
具体也可参见https://lewky.cn/posts/hugo-4.html/#%E8%BF%9C%E7%A8%8B%E9%83%A8%E7%BD%B2%E5%88%B0github-pages%E5%90%8Ebuild%E5%A4%B1%E8%B4%A5

## 部署成功后访问usrname.github.io为404
发现遵循https://shangzg.top/zh-cn/2021-09-14-hugo-github-pages-build-a-personal-blog/#%E6%9E%84%E5%BB%BA%E9%9D%99%E6%80%81%E9%A1%B5%E9%9D%A2 时，通过`hugo -d docs`把静态页面存在了`/docs`目录下，却忘记setting 中配置GitHub Pages 的指定分支为`/docs`目录下的静态站点

