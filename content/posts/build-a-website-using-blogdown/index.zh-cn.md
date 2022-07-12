---
author: Cong Liu
authorLink: https://mrcongliu.com
categories:
- code
date: "2020-03-06T21:40:32+08:00"
description: 用BlogDown搭建个人博客教程
draft: false
images: []
lastmod: "2020-03-06T21:40:32+08:00"
lightgallery: true
resources:
- name: featured-image
  src: featured-image.jpg
tags:
- blogdown
title: 用BlogDown搭建个人博客教程
toc:
  auto: false
weight: 1
---

很久之前，我就有写博客的想法。苦于编程能力有限，难寻合适的框架。从小学时期的手写日记，到大学时期的WordPress加FTP，全都以失败告终。

在加拿大工作半年以后，我如今觉得自己的代码能力略有精进。应该能够驾驭一款简单的框架（即使不能，也可用搜索引擎解决）。

一方面是这种想法愈演愈烈，另一方面仰慕 [谢益辉的博客](https://yihui.org/) 已久。研究了他使用的是**BlogDown**框架。钻研了一番，发现了两个相关的网站：

- [BlogDown 官方文档](https://bookdown.org/yihui/blogdown/)

- [BlogDown创始人之一的博客](https://www.apreshill.com/blog/2020-12-new-year-new-blogdown/)

如果你自学能力较强的话，这两个网站应该能解决你博客搭建的大部分问题。

## 前期准备

在创始人的博客里，我发现了想要掌握BlogDown的前提是你要对以下三个东西都基本了解:

- R语言
- RStudio IDE
- GitHub

至于我本人，由于在大数据项目中略有涉猎 R 和 RStudio，同时也是因为Github是程序员的好朋友。所以我完全符合这三个前提，可以直接上手了。

## 第零步: 制定大方向

![](00-blogdown-2021.gif)

我做事是属于三分钟热血型的，让我提前规划好一切是很难的一件事。我更偏爱在实践中学习。但是创始人的博客也给我了一丝启发，提前做做规划应该没什么坏处。

### 1. 选取主题

考虑一下你想写的东西是属于哪些门类吧！假如你是个学者或科研工作者，你很可能需要[学术风主题](https://academic-demo.netlify.app/)，顺便可以把简历加上去。但我可能思维天马行空，缺的是一种简介且有序的主题。多方比较后，我发现了这款主题很适合我————[LoveIt theme](https://github.com/dillonzq/LoveIt)。我也看中了它便捷的标签分类和支持切换中英文的功能。

### 2. 确定分类

虽然我的每天都有无数个新点子，但是我还是觉得有必要专注在一些特定的分类上面。目前，我觉得五个主题是个合适的数目，它们分别是**代码、健身、财富、饮食、阅读**。 这个框架还有个优点就是可以无限制添加新的分类，即使以后我想到了第六个分类，加上来也很方便。

比如，这篇文章的分类就是由以下代码实现的：
```markdown
categories:
- code
```

### 3. 主页

我也见过不少人的博客，有些人喜欢简洁风的主页，可能主页上只有一个他的头像和一句话。但我觉得那样太单调了，最好是让访客直接看见博客的内容。LoveIt 默认的主页很合我意，所以我也就懒得改了。

## 第一步: 创建Github仓库

![](01-blogdown-2021.png)

其实用[**Netlify**](https://www.netlify.com)挺方便的，它帮忙自动化部署，而且允许你随便给仓库起名字，因为后续你可以自定义域名。但你如果非要用Github Pages起名字就要小心了，因为之后生成的域名是和名字匹配的。当然，这里说的名字是Netlify和Github帮你生成的免费域名，如果你后面自己买了域名，那就无所谓了。不过Netlify的自动部署却是Github不具备的亮点。

1. 打开[GitHub](https://github.com)并创建新的仓库。

![Screenshot above: Creating a new repository in GitHub](github-new-repo.png)

2. 打开仓库的详情页面，找到并点击 **Clone or download** 按钮。

3. 选择 SSH or HTTPS， 如果你不知道啥是SSH的话就选HTTPS。这里面复制的链接记得保存好，下面要用到。

## 第二步: 创建项目

![](02-blogdown-2021.png)

这一步是为了在本地创建一个位置，用来同步本地和远程的仓库。你在本地写的博客，改的其他任何文件，都可以一键同步到Github对应的仓库。所以这一步需要你在RStudio里面创建一个项目，再把Github上刚创建的仓库下载到RStudio这个项目里面。

打开 RStudio 并创建一个新项目。
    
1. 点击 `File > New Project > Version Control > Git`.

2. 把上一步保存的链接粘贴过来。

3. 记住或者保存好你 RStudio 项目的位置。

## 第三步: 创建网站

![](03-blogdown-2021.png)

1. 安装最新版本的blogdown:

```
> if (!requireNamespace("remotes")) install.packages("remotes")
> remotes::install_github("rstudio/blogdown")
Using github PAT from envvar GITHUB_PAT
Downloading GitHub repo rstudio/blogdown@master
```

2. 调用 BlogDown，并设置主题，这里我们选取"starter-academic"，你也可以选其他的主题:

```
> library(blogdown)
> new_site(theme = "wowchemy/starter-academic")
```

3. 接下来你会在输出里面看见一堆红字，不用担心，不看也没关系。只需记得你可以试着用`blogdown::serve_site()`来本地预览网站。

    
