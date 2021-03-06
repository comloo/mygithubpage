---
layout: post
title:  "How to add Jekyll to an existing website"
date:   2017-05-24 14:56:45
description: Step-by-step guide on integrating a Jekyll hosted blog to your existing website.
categories:
- blog
- jekyll
- tutorial
- website
comments: true
---

This guide was made to help those of you who are looking to start a blog, but want to incorporate it into your existing site instead of making a whole new website. For example, if you want a result where `www.your-site.com` is your existing website, and `www.your-site.com/blog` links to the homepage of a Jekyll blog, then this is the guide for you.

I know I ran into this problem, and there wasn't a guide out there that showed me how to do it in a way that didn't have Jekyll as the home page.

## Setup

If you haven't already done so, please make sure you have [Ruby] installed (version 2.1.0 or higher). Install [Jekyll] and [Bundler].

{% highlight bash %}
gem install jekyll
gem install bundler
{% endhighlight %}

## Creating a Jekyll blog

`cd` into the root directory of your website (for me it was where my `index.html` was located) and execute
{% highlight bash %}
jekyll new blog
{% endhighlight %}

This will create a folder in the directory called `blog` and Jekyll will install everything you need inside it. The name of the folder can be anything you want it to be, but it serves as the Jekyll project's name. We can now install the Gemfile. 

{% highlight bash %}
cd blog/
bundle install
{% endhighlight %}

This installs the dependencies in the Gemfile that was generated by Jekyll. You can now build your blog and view it.

{% highlight bash %}
jekyll build
jekyll serve
{% endhighlight %}

Your blog is now live at `localhost:4000`!

Of course this isn't what you want, because you want it to be a separate page on your website.

## Connecting the Jekyll blog to your website

The first thing we want is for `www.your-site.com` to be the main page, instead of the blog. 

To do this, move `_config.yml` from `blog/` to the main directory (up one level). Now if you `jekyll build` and `jekyll serve` and go to `localhost:4000`, it will now be your website instead of the blog. Furthermore, if you go to `localhost:4000/blog`, you can see the homepage for the Jekyll blog!

Wasn't that simple? :)

[Ruby]: https://www.ruby-lang.org/en/
[Jekyll]: https://jekyllrb.com/
[Bundler]: http://bundler.io/

