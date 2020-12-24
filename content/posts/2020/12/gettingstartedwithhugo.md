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

The easiest way to install Hugo is through Homebrew. I recommend installing Homebrew as it makes downloading apps a lot easier. 

To install Homebrew, run the following command:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
``` 
The script will explain what it will do and then pause before it does it.

To install Hugo through Homebrew run: 
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

To download the theme, you need to download the theme from Github using these commands: 
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

You will see the web server is available at [http://localhost:1313/](http://localhost:1313/). Click the link in the terminal to visit your site.

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

Below you will see my config.toml file for this site to get an idea of what you can do:
```
baseURL = "/"
languageCode = "en-us"
title = "Akhil Peddikuppa"
theme = "hugo-PaperMod"
buildDrafts = false
[params]
env = "production"
title = "Akhil Peddikuppa"
author = "Akhil Peddikuppa"
ShowReadingTime = true
ShowShareButtons = false
comments = false
defaultTheme = "auto"
disableThemeToggle = false

[fuseOpts]
isCaseSensitive = false
shouldSort = true
location = 0
distance = 1_000
threshold = 0.4
minMatchCharLength = 0
keys = [ "title", "permalink", "summary", "content" ]
  

  [params.label]
  text = "Akhil Peddikuppa"
  icon = "/favicon.ico"
  
  
[params.profileMode]
  enabled = false
  title = "Akhil Peddikuppa"
  subtitle = "High School Sophomore at the School For the Talented and Gifted"
  imageUrl = "https://www.w3schools.com/w3css/img_lights.jpg"
  imageWidth = 250
  imageHeight = 250
    [[params.profileMode.buttons]]
    name = "About Me"
    url = "about"
    

    [[params.profileMode.buttons]]
    name = "Projects"
    url = "Projects"

    [[params.profileMode.buttons]]
    name = "Resume"
    url = "Resume"

    [[params.profileMode.buttons]]
    name = "My Tech"
    url = "tech"
    [[params.profileMode.buttons]]
    name = "Posts"
    url = "posts"

  [params.homeInfoParams]
  Title = "Hi there 👋"
  Content = "My name is Akhil. I'm a High School Sophomore at the School for the Talented and Gifted in Dallas, Texas. I am interested in medicine, tech, and economics. If you would like to know more about me, you can click [this link to visit my page about me](/about/)."
  
  
  [[params.socialIcons]]
  name = "email"
  url = "mailto:akhil.peddikuppa@outlook.com"
  [[params.socialIcons]]
  name = "twitter"
  url = "https://twitter.com/bballbeast301"

  [[params.socialIcons]]
  name = "youtube"
  url = "https://www.youtube.com/channel/UCQb004LW6mQhC_ONxAIaJTw?view_as=subscriber"

  [[params.socialIcons]]
  name = "github"
  url = "https://github.com/bballbeast30"

  

  [params.cover]
  responsiveImages = true

[menu]
[[menu.main]]
identifier = "home"
name = "🏠 Home"
url = "/"
weight = 5
[[menu.main]]
identifier = "about"
name = "👨🏾‍⚕️ About Me"
url = "/about/"
weight = 10

[[menu.main]]
identifier = "projects"
name = "💼 Projects"
url = "/projects/"
weight = 20

[[menu.main]]
identifier = "posts"
name = "📌 Posts"
url = "/posts/"
weight = 30

[[menu.main]]
identifier = "resume"
name = "📃 Resume"
url = "/resume/"
weight = 25

[[menu.main]]
identifier = "search"
name = "🔍 Search"
url = "/search/"
weight = 50

[outputs]
home = [ "HTML", "RSS", "JSON" ]
```

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

Now, to build the website for deployment with your drafts simply call:
```
hugo -D
```

If you would like to build without drafts run
```
hugo
```

The outputted files will be in the `/public/` folder and you can copy those items to deploy in whatever hosting site you have.