---
title: "Hugo 极简搭建指南-成功版"
description: "first-blog"
keywords: "first,blog"

date: 2022-06-26T21:50:50+08:00
lastmod: 2022-06-26T21:50:50+08:00

categories:
 - 博客
tags:
  - IT
  - 教程

# 原文作者
# Post's origin author name
#author:
# 原文链接
# Post's origin link URL
#link:
# 图片链接，用在open graph和twitter卡片上
# Image source link that will use in open graph and twitter card
#imgs:
# 在首页展开内容
# Expand content on the home page
#expand: true
# 外部链接地址，访问时直接跳转
# It's means that will redirecting to    external links
# extlink:
# 在当前页面开启或关闭评论功能
# Switch to enabled or disabled comment plugins in this post
comment:
enable: true
# 开启文章目录功能
# Enable table of content
toc: true
# 绝对访问路径
# Absolute link for visit
# url: "first-blog.html"
# 开启文章置顶，数字越小越靠前
# Sticky post set-top in home page and the smaller nubmer will more forward.
weight: 1
---

本人纯小白一枚，完全零基础开始搭建个人网站。期间遇到各种大坑小坑无数，终于在熬过几个深夜后，搭建成功!!！

选择 Hugo 这一静态网站生成器，图的就是它的简单。所以本地 blog 搭建没有任何难度。而在部署 Github 个人页面时遇到了巨大的阻碍，第二个阻碍则是主题的部署。

<!--more-->

部署 Github 个人页面时遇到的大坑，现在总结起来有这么几个原因：
- 其一，教程作者基本都是 IT 从业者，他们随口略过的步骤，恰恰是小白无法逾越的鸿沟。
- 其二，网上教程虽说无数，但作者水平不一，要求不同，导致搭建方式也各有不同。而小白在一个教程里遇到不懂的步骤，换到另一个教程，就很容易将事情复杂化。
- 其三，时间问题。随着时间的推移，网站内容、代码的更新，使得教程无法一一对应，这对小白来说，也是无比痛苦的事情。
- 其四，有些问题是不能被 google 或 baidu 搜索到的
- 其五，个人电脑系统不同。Mac与Windows系统对应教程的差异，不利于小白一步一趋的跟随。

主题的部署难度相对要小一些。主要是 `theme`、`baseURL` 的名称要搞对，多看说明文档。虽然还有很多不懂没搞明白的，但只要网站搭建起来，后期再慢慢调试吧。
# 1. 准备工作
- 我的电脑是windows系统，所有的软件以此为基础
- Hugo 下载安装
	- 打开 Hugo 官方 GitHub 的[**Releases**](https://github.com/gohugoio/hugo/releases)页面，选择最新的版本下载（选择`hugo_xxx_Windows-64bit.zip` 或为了便于修改主题使用 extend 版本）
	- 将压缩包内的  `hugo.exe` 文件解压至某个文件夹目录下。譬如： `D:\hugo\`
- 设置 `Hugo` 的环境变量
	- 在 `文件资源管理器` （即 `我的电脑` ）中空白处点击鼠标右键，打开属性。
	- 依次点击 `高级系统设置` -`环境变量` ，双击打开系统变量中的 `Path` 。
	- 在环境变量界面中双击空白行，添加 `D:\hugo\` ，点击确定。
	- 打开命令提示符，输入语句： `hugo version`  。以确认 Hugo 是否安装成功（如果安装成功就能看到版本号）
- Git 下载安装
	- 打开 [Git](https://git-scm.com/) 官方页面，选择相应版本。为了不增加电脑负担，我选择了 64 位的 Portable 版本，代价是使用相对复杂。
	- 启动 `git-cmd.exe` 
- [GitHub Desktop ](https://desktop.github.com/) 这个软件是因为主题名称没设置对，其他文件都上传了，唯独 `themes` 里的文件无法上传，就下了这个软件。虽然没解决问题，但解决了另一个问题：我一直以为 Github 的邮箱是另外一个，导致无数次的失败……
	- 后来发现同步本地与远端，上传网站文件很方便，适合小白。
- Sublime Text 下载安装
	- 一个轻量、简洁、高效、跨平台的编辑器。其实别的方式也可以 完成后续的步骤。

# 2. 本地blog搭建
- 创建站点
	- 切换至相应目录下，使用如下语句： `hugo new site blog` 。这将在一个叫  `blog`  的文件夹内创建一个新的 Hugo 站点。然后 hugo 会自动生成这样一个目录结构：

| 目录        | 备注                       |
| ----------- | -------------------------- |
| archetypes  | default. Md 为模板         |
| content     | 放的是你写的 markdown 文章 |
| layouts     | 网站的模板文件             |
| static      | 图片、css、js 等资源       |
| config. Toml | 网站的配置文件 

这样就建立了新的站点。但此时新站点无法启动，需要安装主题。- 主题的挑选可以到官方的 [**主题页面**](https://themes.gohugo.io/)

# 3. 配置主题
选主题花了点时间，不知道哪个主题方便易用，适合小白。而且每个主题的设置也不一样，所以就选择了有中英文说明的、经过历史验证的、简洁大方的。就是这么发现了凡梦星尘大佬建立的next主题——[Hugo's site theme.](https://github.com/elkan1788/hugo-theme-next)

- 下一步就是进入 blog 文件夹，输入命令：`cd blog`
- 在目录中执行 git init 创建一个 Git 仓库：`git init`
- 添加当前目录下的所有文件到暂存区：`git add .`
	- 不要忽略了那个小数点
- 提交暂存区到本地仓库中：`git commit -m “message”`
	- [message] 可以是一些备注信息。
- 下载主题到 themes 目录：`git submodule add -b develop https://github.com/hugo-next/hugo-theme-next.git themes/next`
- - 克隆好后，还要执行一下， `git submodule update --remote` 确认下 hugo-theme-next 目录下是有内容的。
	- Next 最新的主题似乎还没正式发布，这是一个分支？我还不太明白这些
	- Next 主题不同于默认的用 `config.toml` 来配置，而是用 `config.yml` 配置主题，据说这个更好用，我也不太懂。
		- 所以就可以删除 `config.toml` 文件了。
	- 将此目录下 `~\blog\themes\hugo-theme-next\exampleSite\`的两个文件夹` content `、` static `拷贝到` ~\blog`下
	- 将此目录下 `~\blog\themes\hugo-theme-next\archetypes\`的`default.md`文件拷贝到`~\blog\archetypes\`下

也可以直接 `git clone` 下来进行使用，但之后自己对主题进行修改后，可能会与原主题产生一些冲突，不方便版本管理与后续更新。
- 这里很重要的是主题名称问题。直接下载的主题名称与 submodule 下来的主题名称可能是不同的，设置错误是无法正常显示的。
- 打开 `config.yml` 设置网址：`baseURL: https://a.happy2008.top`、theme是：`title: 'hugo -theme-next'
	- 这里我用了自己的域名，其本来的blog网址是后面再讲。
	- **注意设置不同**：
		- 默认的 `config.toml` blog 网址设置： `baseURL = 'a. Happy2008. Top'`、theme是：`title = 'hugo -theme-next'`
# 4. blog文章创建及发布
- 使用如下命令，创建一篇文章：`hugo new posts/my-first-post.md`
- 启动Hugo本地预览服务：`hugo server -D`
- 打开 [**http://localhost:1313/**](http://localhost:1313/) ，即可看到实时预览的站点（在本地的任何修改，将即时更新）。
- 可以多建几个文件，再次检查页面
- 查看上次提交之后是否有对文件进行再次修改。`git status`
- 添加当前目录下的所有文件到暂存区：`git add .`
- 提交暂存区到本地仓库中：`git commit -m “ready to upload”`
- 创建分支命令：`git branch -M main`

# 5. 部署到 GitHub
- 打开 [ GitHub](https://github.com/yourname) 创建仓库 blog
- 添加远程版本库：`git remote add origin https://github.com/你的用户名/blog.git`
- 将本地的分支版本上传到远程并合并：`git push -u origin main`
	- 输入 github 的密码
- 用 sublime text 在 blog 目录建立文件 `. github /workflows/gh-pages.yml
	- 其实直接在 `blog` 目录下建立文件夹 `.github`，打开它再建立文件夹 `workflows`，新建文件 `gh-pages.yml`, 文件名可随意。
	- 拷贝代码，在 hugo 网站 docs→ hugo to github
	[Host on GitHub | Hugo](https://gohugo.io/hosting-and-deployment/hosting-on-github/)，完全不用任何修改。
```
name: github pages

on:
  push:
    branches:
      - main  # Set a branch to deploy
  pull_request:

jobs:
  deploy:
    runs-on: ubuntu-20.04
    steps:
      - uses: actions/checkout@v2
        with:
          submodules: true  # Fetch Hugo themes (true OR recursive)
          fetch-depth: 0    # Fetch all history for .GitInfo and .Lastmod

      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: 'latest'
          # extended: true

      - name: Build
        run: hugo --minify

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        if: github.ref == 'refs/heads/main'
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public
```
- `git add .`
- `git commit -m “deploy”`
- `git push`
	- 此时可能会出现认证的弹出框，我因邮箱写错折腾了许久。
- 查看github Actions里的`deploy`运行是否正常：![upgit_20220627_1656321977.png](https://raw.githubusercontent.com/zhl111/upgit/main/2022/06/upgit_20220627_1656321977.png)
- 将 blog 分支改为 `gs-pages` ![upgit_20220627_1656322094.png](https://raw.githubusercontent.com/zhl111/upgit/main/2022/06/upgit_20220627_1656322094.png)
- 将code处的分支改为`main` ![upgit_20220627_1656322026.png](https://raw.githubusercontent.com/zhl111/upgit/main/2022/06/upgit_20220627_1656322026.png)
- 我的 blog 网址： [https://zhl111.github.io/blog/](https://zhl111.github.io/blog/)
- 改域名：略吧…这教程不少。到此就算完成了，剩下的就是各种调试主题的时间，等主题调试完成就该安心地写点东西了……

这里还要说一句，之前的弯路走的特别的多，主要还是有很多人是把文章源文件单独放到一个仓库里，可以不公开，也方便管理。但是，他们的方法都很复杂，有的是要公钥、私钥，有的是要TOKEN设置。也遇到教程跟现在的网页不对应问题等等，我这啥也不懂的小白就被绕了进去，反反复复安装了几十遍。

我这个教程既实现了源文件仓库与发布网站仓库的分离，实现起来的过程还相当简洁，我自己还挺满意的。
## 参考链接：
- [主题设置 | NexT]( https://theme-next.js.org/docs/theme-settings/#Configuring-Menu-Items )  2022/6/27



<!--more-->
