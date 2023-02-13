---
author: Cong Liu
authorLink: https://mrcongliu.com
categories:
- code
date: "2020-03-06T21:29:01+08:00"
description: Build A Website Using BlogDown
draft: true
images: []
lastmod: "2020-03-06T21:29:01+08:00"
lightgallery: true
resources:
- name: featured-image
  src: featured-image.jpg
tags:
- blogdown
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

To me, it seems unnecessary to think the reason of doing something. I am always a fan of learning by doing. But Alison made her point. It would help me in the long run if I am serious about this blog. So I took a while to figure that out.

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

She recommended using [**Netlify**](https://www.netlify.com) to both build and host your site. In this case, you can name the repository anything you want! I totally agree! Before that, we need setup our GitHub.

1. Go to [GitHub](https://github.com) and create a new repository.

![Screenshot above: Creating a new repository in GitHub](github-new-repo.png)

2. Go to the main page of your new repository, and under the repository name, click the green **Clone or download** button.

3. Choose either SSH or HTTPS (if you don't know which, choose HTTPS). Choose by clicking on the clipboard icon to copy the remote URL for your new repository. You'll paste this text into RStudio in the next section.

## Step 2: Create project

![](02-blogdown-2021.png)

We just created the remote repository on GitHub. To make a local copy on our computer that we can actually work in, we'll clone that repository into a new RStudio project. This will allow us to sync between the two locations: your remote (the one you see on github.com) and your local desktop.

Open up RStudio to create a new project where your website's files will live.
    
1. Click `File > New Project > Version Control > Git`.

1. Paste the copied URL from the previous step.

1. Be intentional about where you tell RStudio to create this new Project on your workstation.

## Step 3: Create Site

![](03-blogdown-2021.png)

1. Install the latest version of Blogdown:

```
> if (!requireNamespace("remotes")) install.packages("remotes")
> remotes::install_github("rstudio/blogdown")
Using github PAT from envvar GITHUB_PAT
Downloading GitHub repo rstudio/blogdown@master
```

2. Import BlogDown into your RStudio and select a theme. For example, you can choose "starter-academic", or any other theme you like.

```
> library(blogdown)
> new_site(theme = "wowchemy/starter-academic")
```

3. Then a few lines of will pop up, it doesn't matter even if you can't understand them. Just keep in mind that you can preview your site by using `blogdown::serve_site()`.

## Step 4: Create content

![](04-blogdown-2021.png)

You can write either in `Markdown` or `.Rmarkdown`. But the difference between them is `.Rmarkdown` requires you to use the RStudio built-in `Knit` function to transform the file into a `Markdown` file. For example:


```
> blogdown::new_post(title = "Hi Hugo", 
                     ext = '.Rmarkdown', 
                     subdir = "post")
```

## Step 5: Publish site

![](05-blogdown-2021.png)

We will use Netlify to publish our site. Why is it so popular? Because Netlify helps us to automatically rebuild our site whenever new code is committed to Github repo.

- Go online to [Netlify](https://www.netlify.com). 

- Click on the **Sign Up** button and sign up using your existing GitHub account (no need to create another account).

- Log in, and select: `New site from Git > Continuous Deployment: GitHub`.

- From there, Netlify will allow you to select from your existing GitHub repositories. You'll pick the repo you've been working from with `blogdown`. Leave all settings as they are and select **Deploy Site**.

## Step 6: Sculpt site

![](06-blogdown-2021.png)


### Modify the configuration file

Every settings about your site is inside the file `config.yaml` under the root directory, you need to do your research and figure out how to modify it. Previewing your site is probably a good strategy.

### Customize SCSS

Feel free to add your own SCSS file into `assets/scss/custom.scss`. If you are not familiar with SCSS, here is a good [example](https://github.com/rbind/apreshill/blob/main/assets/custom.scss).

## Thanks

Now, your site is ready to go！ :smile:

Thanks for reading. If you have any questions, feel free to leave a comment down below.

Cheers!