---
author: Cong Liu
authorLink: https://mrcongliu.com
categories:
- code
date: "2020-03-06T21:29:01+08:00"
description: Build A Website Using BlogDown
draft: false
images: []
lastmod: "2020-03-06T21:29:01+08:00"
lightgallery: true
resources:
- name: featured-image
  src: featured-image.jpg
tags:
- installation
- configuration
title: Build A Website Using BlogDown
toc:
  auto: false
weight: 1
---

Building and maintaining a personal blog has always appealed to me. Since childhood, I’ve tried different ways of keeping my ideas: writing dairy, posting on social media, and uploading them to WordPress through FTP. But none of them worked.

After working as a software developer for half a year, I feel it is a perfect time for me to try something new since my programming skills have improved dramatically, meaning that I am able to solve most problems while building a new blog.

With that in mind, I have been following [Yihui’s blog](https://yihui.org/) for quite a while and liked it. So, I decided to build something similar using the framework called **BlogDown**, which is also the foundation of his blog.

Browsing through his blog, I found some useful resources that explain how to duplicate a blog quickly.

- [BlogDown Documentation](https://bookdown.org/yihui/blogdown/)

- [An Instruction about BlogDown written by one of its core developers](https://www.apreshill.com/blog/2020-12-new-year-new-blogdown/)

To get a full understanding of how to build a website using BlogDown, I highly recommend you go through the above essays. The purpose of this essay is just to give you a quick idea about each step.

## Pre-requisites

In Alison's post, she mentioned you need to know the basics about three things:

- R,
- the RStudio IDE, and
- GitHub.

For me, I've learned R and RStudio while studying Big Data Solution Architecture. Besides, I suppose most developers should know the basic about GitHub. Therefore, I am good to go with BlogDown.

## Step 0: Set your intentions

![](00-blogdown-2021.gif)

To me, it seems unnecessary to think the reason of doing something. I am always a fun of learning by doing. But Alison made her point. It would help me in the long run if I am serious about this blog. So I took a while to figure out the 

### 1. Content & Theme

The content you are about to put on your blog determines the theme you choose. For example, if you want to write academic staff, you probably want to adopt the [Academic theme](https://academic-demo.netlify.app/) and add your resume there.

However, my intention was just writing down my ideas from time to time, and put them into different categories. So, I adopted the [LoveIt theme](https://github.com/dillonzq/LoveIt), which is super clean and simple that also supports both English and Chinese.

### 2. Topic

Because my ideas vary in many fields, it is also important to focus on a few topics. After careful consideration, I decided the five pillars of my blog (also my life :joy:) as **Code, Body, Money, Food, Book**. One advantage of using this theme is that it supports as many categories as you want. So I can also add a sixth topic just by adding two lines in the corresponding post file.

For example, in the markdown file of this post:
```markdown
categories:
- code
```

### 3. Homepage

For some, homepage should be cool and without much conent other than a simple self-introduction. For me, I just liked the default one with LoveIt them, so I won't make any changes.

## Step 1: Create repo

![](01-blogdown-2021.png)

She recommended using Netlify to both build and host your site. In this case, you can name the repository anything you want! I totally agree!