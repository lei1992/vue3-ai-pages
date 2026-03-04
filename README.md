# 纯AI搭建的vue3项目
 
## 在github部署可访问的静态网站

1. 在github上创建一个仓库，将项目代码上传到仓库中。注意：仓库必须是public的，否则无法部署。
2. 在仓库的settings中找到github pages，选择master分支，点击save。刷新页面，可以看到一个链接，这个就是网站的链接。
3. 打开网站链接，发现页面是空白的，打开控制台，发现有 html 结构，原因是：会默认加载了该 github 项目下根目录的 index.html 文件。
4. 修改项目根目录下的 index.html 文件，将 `<div id="app"></div>` 改为 `<div id="app">随便加点文字</div>`。然后提交代码，刷新网站的链接，可以看到页面显示了。