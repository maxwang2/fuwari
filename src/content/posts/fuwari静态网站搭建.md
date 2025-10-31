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

4. 一个 <a href="https://github.com/" target="_blank" rel="noopener noreferrer">Github</a> 账号：用于创建一个代码仓库存放Fuwari文件

5. 一个 <a href="https://cloudflare.com" target="_blank" rel="noopener noreferrer">Cloudflare</a> 账号：用作托管

6. <a href="https://obsidian.md/" target="_blank" rel="noopener noreferrer">Obsidian</a>：一个 md 编辑器

### 流程图

本地部署 Fuwari，编写文章 -> 推送更改到远程 Github 仓库 -> Cloudflare Pages 检测到仓库更新自动构建新的网站静态文件 -> 网站成功更改

