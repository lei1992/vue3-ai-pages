# 纯AI搭建的vue3项目

# github 静态网站CI/CD

参考文档：https://juejin.cn/post/7346524071185006611?searchId=20260304115932B1397D50C22F5825CF10
详细步骤如下：

## 一、在github部署可访问的静态网站

1. 在github上创建一个仓库，将项目代码上传到仓库中。注意：仓库必须是public的，否则无法部署。
2. 在仓库的settings中找到github pages，选择master分支，点击save。刷新页面，可以看到一个链接，这个就是网站的链接。
3. 打开网站链接，发现页面是空白的，打开控制台，发现有 html 结构，原因是：会默认加载了该 github 项目下根目录的 index.html 文件。
4. 修改项目根目录下的 index.html 文件，将 `<div id="app"></div>` 改为 `<div id="app">随便加点文字</div>`。然后提交代码，等个 1、2 分钟，再刷新访问网址，就能看到最新的内容。

## 二、Github Actions 配置

可以理解为 CI、CD。可以配合上面的 Github Pages，实现提交代码，自动构建并发布的效果。

1. 更改Github Pages配置，改为Github Actions形式
   settings -> pages -> Build and deployment (source) -> deploy from a branch (选择Github Actions) -> save
2. 创建Github Actions的配置
   settings -> pages -> Build and deployment -> static html (点击configure),会帮我们生成了一个最基本的配置(.github/workflows/static.yml)，点击commit changes提交配置文件，提交后点击actions，可以看到构建的日志，至此简单的 github actions 配置完成
