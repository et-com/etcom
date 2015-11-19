# Getting Started with Jekyll 

This lesson's intent is to help you get started using Jekyll to post materials to GitHub Pages. This lesson only covers the basics and we will be using [Barry Clark's jekyll-now repo](https://github.com/barryclark/jekyll-now) to jump start our learning (and experiment). 

At the end of the lesson, I have added some information (as much as I could) about installing Ruby, Bundle, and Jekyll. However, due to time constraints we may not get to everything. 

## What is Jekyll? 

From [Jekyll](http://jekyllrb.com/docs/home/): 

```
Jekyll is a simple, blog-aware, static site generator. 
It takes a template directory containing raw text files in various formats, 
runs it through a converter (like Markdown) and our Liquid renderer, 
and spits out a complete, ready-to-publish static website suitable for 
serving with your favorite web server. 
```

What's that mean? You can use Jekyll to create a static blog for free using GitHub Pages - actually, all of GitHub Pages runs Jekyll. 

## Why use Jekyll? 

Jekyll allows you to write posts and pages in Markdown as well as other text formats (like HTML or Liquid). Which can make writing a lot easier. Also, Jekyll builds your static site, that means you don't have to worry about databases, a cms, dealing with comments - you can just write and publish.  

## Setting up Jekyll 

For this lesson, we are going to go simple. 

 1. Fork [Barry Clark's jekyll-now repo](https://github.com/barryclark/jekyll-now)
 2. In your new repo titled "jekyll-now" create a new gh-pages branch
 3. Visit http://username.github.io/jekyll-now 

#### Okay, let's stop for a second

And take a look at the [directory structure for Jekyll sites](http://jekyllrb.com/docs/structure/) and talk over what happens. 
Also, take a look at [your example](http://tomhohenstein.com/jekyll-now)
. 

## Things to think about

1) [Frontmatter is required](https://help.github.com/articles/using-jekyll-with-pages/#frontmatter-is-required) or you'll have build problems. What is frontmatter? It looks like 

```
---
layout: post
title: You're up and running!
---
```
Frontmatter is Jekyll's way of passing variables and build information. For example, the post above has the layout variable set to "post" and the title is "You're up and running!." To learn more, [check out all of Jekyll's variables](http://jekyllrb.com/docs/variables/). 

2) _config.yml is huge. This is where all of your configurations are stored. When Jekyll builds your site, it will look at the _config.yml file for options and variables.

3) Variables are super useful. You might have guess it, but I thought I should tell you anyway. An example will show you why you need to understand Jekyll's variables. 
 
 - Take a look at your _config.yml file - see the ``` name: Your Name ```? 
 - Now go open _layouts/default.html. See ``` <meta name="author" content="{{ site.name }}" ```. You guessed it, when Jekyll builds a site it replaces ``` {{ site.name }} ``` with the value in the _config.yml file for ```name: ```
 
**For more information about variables checkout [jekyll's documentation](http://jekyllrb.com/docs/variables/) and [Shopify's Liquid](https://github.com/Shopify/liquid/wiki)

4) The _layouts folder is your friend. If you want posts to look different than pages, _layouts is the place to store your templates. Let's take a closer look at how this works: 
 - Open _posts/2014-3-3-Hello-World.md. There are two frontmatter variables, layout and title (lines 1-4), as well as some content on lines 6-10. 
 - Now take a look at: _layouts/post.html. Check out ```{{ page.title}}``` on line 6 - yep, that's where the title, "You're up and running!" in this example, will be placed.  Notice ``` {{ content }} ``` on line 9? Thats where the content from _posts/2014-3-3-Hello-World.md will go. Finally, post.html has one variable in its frontmatter - layout - which is set to "default" 
 - Okay, let's go up one more level and check out the default layout. Open _layouts/default.html. On about line 43 of default.html you should see something like ``` {{ content }} ```. Thats where all your post content will go. 

**whew,** that was a lot but, hopefully, you can see how one file is put into one template, which can then be put into another template.

5) _site is where the site is put after each build. It holds all your html, css, and js files 

6) _scss is for sass, which Jekyll will convert to css. 

## Play Time 

Let's take a few minutes to explore the jekyll-now repo, ask questions, and discover what a jekyll blog looks like. Also, if you're interested check out our BU Study Group repo. 

## Setting up Jekyll locally 

The great thing about using Jekyll is that, once it is all setup, you can develop locally and then push your content to GitHub. This part is a little more technical and I haven't refined the process for prime time (so we will have to work through this together) 

### What are the prerequisites? 

 1. Ruby
 2. RubyGems
 3. Linux, Unix, or Mac OS X
 4. NodeJS (or another JavaScript runtime) 
 5. Python 2.7 (for Jekyll 2 and earlier) 

Want to know more, [read the offical documents](http://jekyllrb.com/docs/installation/)

#### Wait, What aboud Windows? 

While Windows is not officially supported (I know!) there are [instructions for getting Jekyll to work](http://jekyllrb.com/docs/windows/#installation). 

For detailed instructions, [see Julian Thilo's instructions](http://jekyll-windows.juthilo.com/). 

### Installation 

#### Mac 

These instructions are also posted at: ahttps://help.github.com/articles/using-jekyll-with-pages/a

1) Install Ruby - if you're on a Mac you probably already have Ruby installed. To check run: 
```
ruby --version
```
You'll want version 2.0.0 or higher 

2) Install Bundler 

```
gem install bundler
```

3) Install Jekyll 

 1. Create a file in your repository called ```Gemfile``` 
 2. Add the line ``` gem 'github-pages' ``` to your Gemfile. ([or see this example](https://github.com/bulib/studyGroup/blob/gh-pages/Gemfile))
 3. Run the command ``` bundle install ``` and you should ready. 

#### Windows 

 *Note:* I don't have a windows machine! 
 The directions are at: http://jekyll-windows.juthilo.com/ (and they are great!) 
 
 1) Download Ruby for Windows at: http://rubyinstaller.org/downloads/
 2) Install the Ruby Dev Kit at: http://rubyinstaller.org/downloads/ (for Ruby v2.0.0 look for ``` DevKit-mingw64 ```
 3) Follow the instructions at: http://jekyll-windows.juthilo.com/1-ruby-and-devkit/ to bind the DevKit to your Ruby installation
 4) Install the Jekyll gem ``` gem install jekyll ```
 
