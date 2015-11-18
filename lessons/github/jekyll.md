# Getting Started with Jekyll 

This lesson's intent is to help you get started using Jekyll to post materials to GitHub Pages. 

## What is Jekyll? 

From [Jekyll](http://jekyllrb.com/docs/home/): 

```
Jekyll is a simple, blog-aware, static site generator. 
It takes a template directory containing raw text files in various formats, 
runs it through a converter (like Markdown) and our Liquid renderer, 
and spits out a complete, ready-to-publish static website suitable for 
serving with your favorite web server. 
```

What's that mean? You can use Jekyll to create a static blog for free using GitHub Pages. 

## Why use Jekyll? 

Jekyll allows you to write posts and pages in Markdown and other text formats - like HTML or Liquid. 
So rather than writing <p> tages and <a> tags, you can write in Markdown and let 
Jekyll do the markup. 


## What are the prerequisites? 

 1. Ruby
 2. RubyGems
 3. Linux, Unix, or Mac OS X
 4. NodeJS (or another JavaScript runtime) 
 5. Python 2.7 (for Jekyll 2 and earlier) 

Want to know more, [read the offical documents](http://jekyllrb.com/docs/installation/)

### Wait, What aboud Windows? 

While Windows is not officially supported (I know!) there are [instructions for getting Jekyll to work](http://jekyllrb.com/docs/windows/#installation). 

For detailed instructions, [see Julian Thilo's instructions](http://jekyll-windows.juthilo.com/). 

## Setting up Jekyll 

For this lesson, we are going to go simple. 

 1. Fork [Barry Clark's jekyll-now repo](https://github.com/barryclark/jekyll-now)
 2. In your new repo titled "jekyll-now" create a new gh-pages branch
 3. Visit http://username.github.io/jekyll-now 

 1. Navigate to the folder that contains your username.github.io repository 
 2. Run ``` Jekyll new username.github.io ``` *where username is your username*
 3. Move into your repository ``` cd username.github.io ``` *where username is your username*

#### Okay, let's stop for a second

And take a look at the [directory structure for Jekyll sites](http://jekyllrb.com/docs/structure/) and talk over what happens. 
Also, take a look at the [Study Group page for a real example](https://github.com/bulib/studyGroup)
. 

#### Frontmatter is required 

  [Frontmatter is required](https://help.github.com/articles/using-jekyll-with-pages/#frontmatter-is-required) or you'll have build problems.
 



## Jekyll Blog Templates 

## Let's review the file structure 


END LESSON 

## Installation 

### Mac 

These instructions are also posted at: https://help.github.com/articles/using-jekyll-with-pages/

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

### Windows 
