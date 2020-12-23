---
title: "How to Get Started with Hugo"
date: 2020-12-22
draft: false
cover:
    image: https://res.cloudinary.com/practicaldev/image/fetch/s--B35LQIoC--/c_imagga_scale,f_auto,fl_progressive,h_900,q_auto,w_1600/https://thepracticaldev.s3.amazonaws.com/i/ickb9tcxbvbumven7r32.png
weight: 3
---

This tutorial will explain the steps needed to get started with Hugo to build a static website for your blog or portfolio.
## What is Hugo?
Hugo is a free and open source static site generator used by many to create blogs or portfolio websites for themselves. I myself use Hugo for this portfolio/blog site.

## Step 1: Installation

The easiest way to install Hugo is through Homebrew.   
You can do so using the command: 
```
brew install hugo
```

## Step 2: Create a site

You can create a new site using the command:
```
hugo new site blog
```
Running this command will create a new site under the name "blog". The folder will likely generate in your main hard drive folder, so I would recommend to move the folder into one for all your Hugo sites.

## Step 3: Let's Add a Theme

The Hugo Marketplace features a numerous amounts of [themes](https://themes.gohugo.io) to use all of which are for free. In this tutorial, we will use the PaperMod theme by Aditya Telange, which I use for this site.

To download the theme, you need to download the theme from Githun using these commands: 
```
cd blog
git init
git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/hugo-PaperMod
```

Then, we need to add the theme to our config.toml file using the commands:
```
echo 'theme = "hugo-PaperMod"' >> config.toml
```
## Step 4: Add Content
To create content in the Hugo website, we can run the command:
```
hugo new posts/firstpost.md
```
This will create a new folder called "posts" in the content folder with file name "firstpost.md".

If you would not like to use command line instructions, you can simply just create a new folder under content and add a file, although I recommend using the command line as it can save a lot of time.

The new file will look a bit like:
```
---
title: "firstpost"
date: 2020-12-21T08:47:11+01:00
draft: true
---
```

The title parameter will be the title of your blog post. For this template you can add a cover image by adding:
```
cover:
    image: (insert image URL here)
```
to the post data.

## Step 5: Starting the Server
To start the Hugo server with drafts enabled use command:
```
hugo server -D
```

You will see the web server is available at [http://localhost:1313/](http://localhost:1313/). Click the link to visit your site.

## Step 6: Theme Customization

In order to customize this theme you can visit the config.toml file.

There you will see something like this:
```
baseURL = "https://example.org/"
languageCode = "en-us"
title = "My New Hugo Site"
theme = "hugo-PaperMod"
```

Here, you can change the title of your site, which depending on your theme will change different values.

I will like the docs for this specific theme [here](https://adityatelange.github.io/hugo-PaperMod/).

Another great thing about Hugo is that you see changes made render in real time on the server.

## The Final Step: Build and Deploy Your website

Prior to deploying your site, I would advise you to go into your config.toml file and change the parameter that says:
```
baseURL = "https://example.org/"
```
to
```
baseURL = "/"
```

Now, to build the website for deployment simply call:
```
hugo -D
```

The outputted files will be in the `/public/` folder and you can copy those items to deploy in whatever hosting site you have.