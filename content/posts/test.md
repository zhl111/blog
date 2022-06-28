---
title: "世界，你好！"
description: "快速的描述下有关于 Hugo 建站的基本用法。"

lastmod: 2022-06-03T16:43:23+08:00
date: 2022-06-02T11:52:03+08:00

categories:
 - 博客
tags:
 - Hugo
 - 开始

url: post/hello-world.html
weight: 2
---

> “使用 `weight` 关键字置顶文章。”

[Hugo](https://gohugo.io/) 是现今世界上最快的网站建设框架，也是最流行的开源静态站点生成器之一。 凭借其惊人的速度和灵活性，Hugo 让建设网站再次变得有趣起来。

- 创建分支命令：`git branch -M main`
- 可以多建几个文件，再次检查页面
- 查看上次提交之后是否有对文件进行再次修改。`git status`
- 添加当前目录下的所有文件到暂存区：`git add .`
- 提交暂存区到本地仓库中：`git commit -m “ready to upload”`
- 创建分支命令：`git branch -M main`


<!--more-->

## 快速开始

### 发表新文章

```shell
$ hugo new hello-world.md
```

更多信息：[内容格式](https://gohugo.io/content-management/formats/)

### 启动服务

```shell
$ hugo server
```

更多信息：[Hugo 服务命令行](https://gohugo.io/commands/hugo_server/)

### 生成静态文件

```shell
$ hugo
```

更多信息：[Hugo 建站](https://gohugo.io/commands/hugo/)

### 部署到服务器

```language
$ hugo deploy
```

更多信息：[Hugo 发布](https://gohugo.io/commands/hugo_deploy/)

祝你好运，相信你会喜欢上 Hugo 建站的旅程！