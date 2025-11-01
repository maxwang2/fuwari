---
title: fuwari静态网站搭建
published: 2025-10-31
description: 基于cf进行托管的静态fuwari搭建教学
image: ""
tags:
  - Blogging
  - Fuwari
category: Tutorial
draft: false
lang: ""
---

### 你需要准备的东西

1. 一个牛逼的脑子，支持并行运算至少两个单位以上的事件，学会和 ai 调情

2. <a href="https://git-scm.com/downloads" target="_blank" rel="noopener noreferrer">Git</a>：最牛逼的版本控制器

3. <a href="https://nodejs.org/en" target="_blank" rel="noopener noreferrer">Node.js</a>：伟大无需多言

4. 一个 <a href="https://github.com/" target="_blank" rel="noopener noreferrer">Github</a> 账号：用于创建一个代码仓库存放 Fuwari 文件

5. 一个 <a href="https://cloudflare.com" target="_blank" rel="noopener noreferrer">Cloudflare</a> 账号：用作托管

6. <a href="https://obsidian.md/" target="_blank" rel="noopener noreferrer">Obsidian</a>：一个 md 编辑器

### 流程图

本地部署 Fuwari，编写文章 -> 推送更改到远程 Github 仓库 -> Cloudflare Pages 检测到仓库更新自动构建新的网站静态文件 -> 网站成功更改

### 让我们开搞吧！

#### 1.1 本地部署Fuwari

1. Fork 仓库：<a href="https://github.com/saicaca/fuwari" target="_blank" rel="noopener noreferrer">Fuwari 仓库</a>（如果登不上去就挂梯子）

2. 然后将仓库克隆到本地：`git clone <你的仓库URL>`（必须使用 SSH，否则不能实时推送至 cf）

3. 来到你刚克隆的项目的根目录，全局安装 pnpm：`npm install -g pnpm`（如果拉取过慢，可尝试 **npmmirror** 镜像站）

4. 在项目根目录继续安装依赖：`pnpm install` 和 `pnpm add sharp`

至此，你成功在本地部署了Fuwari

#### 1.2 本地编写文章

> 强烈推荐 obsidian 编辑器

1. 首先，在项目根目录执行：`pnpm new-post <你的文章标题>`

2. 然后，检查根目录下的 `src/content/posts` 文件夹中是否多出一个 `xxx.md` 文件

3. 我们使用 Obsidian 打开这个文件，你可以看到一些基本信息，我们只需要关注几个重要的信息：

```
title: xxx
published: xxx
description: ''
image: ''
tags: []
categories: ''
draft: false
lang: ''
```

- title：标题
- published：发布时间
- description：文章描述，正常会显示在文章标题下面
- image：文章封面图
- tag：文章标签
- categories：文章分类

4. 编写好你的文章

5. 更改根目录下的 `astro.config.mjs`，在第34行更改 `site:` 为你的站点URL

至此，你已经会用 Obsidian 编写 MarkDown 语法的博客了