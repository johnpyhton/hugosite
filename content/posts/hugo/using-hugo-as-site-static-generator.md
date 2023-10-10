---
title: "Using Hugo as Site Static Generator"
date: 2023-10-08T11:30:03+00:00
# weight: 1
aliases: ["/using-hugo-as-site-static-generator"]
tags: ["blog","hugo"]
author: "Me"
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: ""
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowCodeCopyButtons: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---

## Using Hugo as My Website SSG
There are many Site Static Generator (SSG). Why Hugo? I had use Jekyll before couple of years back. Before my decision to use Hugo, i had quick research, 
whats the difference between Hugo and Jekyll. Jekyll use Ruby and Hugo use Go language. Jekyll more popular and highly used by many compare to Hugo. But, Hugo is fast. Yes, it is. How fast? There is comparison between Jekyll and Hugo on how both generate thousands of pages from [Michael Nord Meyer](https://michaelnordmeyer.com/benchmarking-hugo-vs-jekyll-vs-github-pages-in-2023#?). And clear winner is Hugo.

I am not sure if this website will have thousands of pages, but for sure, i'd just want to test out Hugo as the SSG. I found a nice theme from [PaperMod](https://adityatelange.github.io/hugo-PaperMod/#?). Its clean, responsive, fast, SEO friendly and serve the purpose which as a journal for my Python learning journey towards my goal to master the data science.

## How to install Hugo ?
Hugo has a clear guidance how to [install Hugo](https://gohugo.io/installation/#?) on many operating system. I am using MacOS, follow this [Hugo installation guide for MacOS](https://gohugo.io/installation/macos/#?) and its working fine. What i need is just this 1 item:

- [HomeBrew](https://brew.sh/#?) is a free and open source package manager for macOS and Linux to install the **extended edition of Hugo**. 

## How to install PaperMod Hugo theme?
Next after the **Hugo** installed on your local computer, we can continue our next step which is to install the **PaperMod** hugo theme. I am following [method 1](https://github.com/adityatelange/hugo-PaperMod/wiki/Installation#?) with this pre-requisite:

- [Git](https://git-scm.com/#?) is a free and open source distributed version controls system. Use to clone the **PaperMod** hugo theme from repository.

Now, once you have Git installed on your local computer we could start installing the PaperMod theme on Hugo.
1. Create new Hugo site by running below command:

`hugo new site <name of site> -f yml` 

2. Create or install a theme:
   - Create a new theme with the command "hugo new theme <THEMENAME>"
   - Install a theme from https://themes.gohugo.io/
3. Edit hugo.toml, setting the "theme" property to the theme name.
4. Create new content with the command "hugo new content <SECTIONNAME>/<FILENAME>.<FORMAT>".
5. Start the embedded web server with the command "hugo server --buildDrafts".

2. Go to your new hugo site folder.

`cd <my hugo local folder>`

3. Lets grab the theme from github and clone into your hugo local folder inside *themes* by running this command:

`git clone https://github.com/adityatelange/hugo-PaperMod themes/PaperMod --depth=1` 

or

`gh repo clone adityatelange/hugo-PaperMod themes/PaperMod`

## Configure the PaperMod Hugo theme and Start Post
Next, once we successfully get the PaperMod theme into our local computer folder, we could start configuring and have the website run.

1. Update the **hugo.toml** config file by copying the [config.yml](https://github.com/adityatelange/hugo-PaperMod/wiki/Installation#sample-configyml#). 
> **Remember** to convert the **config.yml** into .toml format. I am using this [yaml to toml converter](https://www.convertsimple.com/convert-yaml-to-toml/#)

There are many items you could configure in **hugo.toml** file, few which i would like to highlight in below table:
|       Item        |         Value          |                Description                 |
|:-------------------|:------------------------|:--------------------------------------------|
|theme        |         PaperMod          |                The name of the theme.|
|mainSections |         posts          |   The default content folder which will display at the main sections. In this case we set to *posts*. The folder located inside *{your hugo main folder\content\ }*              |
|[[menu.main]]        |  set the identifier, name and url          | The main menus link that will display at the top bar.|

2. Start creating a new blog posts content by copying the *posts.md* from *<your hugo main folder\archtypes\>* folder into *<your hugo main folder\content\>*. 
3. Go to the *posts* folder, rename it to any filename that suit your post article title and start putting some content there.
4. Start the embeded web server with the below command 

`hugo server -D`

## Deploy Your Local Hugo Site to GitHub
Once you are happy with your local Hugo site and its content, time to push it to GitHub which provide free and fast static hosting over SSL for personal directly from a GitHub Repository via its GitHub Pages service and automating workflows and build with GitHub Actions. We are following this complete [guide](https://gohugo.io/hosting-and-deployment/hosting-on-github/#).



