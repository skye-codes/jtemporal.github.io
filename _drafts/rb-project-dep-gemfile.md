---
title: 'Ruby Project Dependencies: Gemfile'
layout: post
date: 2018-01-13T08:00:00.000+00:00
image: "/images/pro_tip.png"
tags:
- english
- protip
- pro tip
- jekyll
- ruby
- gemfile
- terminal
comments: true
description: Today's pro-tip teaches you what to do when you don't have a Gemfile

---
\---

Author note: [Leia este artigo em Português](https://jtemporal.com/gemfile/).

\---

After [teaching how to get your website online](https://translate.googleusercontent.com/translate_c?depth=1&rurl=translate.google.com&sl=auto&sp=nmt4&tl=en&u=http://jtemporal.com/do-tema-ao-ar/&xid=17259,1500000,15700002,15700021,15700186,15700190,15700256,15700259,15700262,15700265,15700271,15700283&usg=ALkJrhjY8BCFOb0VuCzIEDasyaE7ldKdZA) (in Portuguese) using [Jekyll](https://jekyllrb.com). I'm going to use today's pro-tip to answer a question somebody asked me: _"My theme doesn't have a Gemfile, now what?"_

## What is a Gemfile?

Before explaining what this file is, you need to understand a little bit about Ruby projects. Usually, each project, independent of the language you are using, has a list of dependencies that are required for the said project to run. For Ruby projects, this dependency management list is made using a system known as Gemfile.

Each package/library you need install to run your project is called a _gem_. Just as Jekyll itself is a gem, you may need, for example, Jekyll plugins to do things on your site such as paginating post lists, including SEO and even automatically building an XML feed. To install and manage such plugins, we use a Gemfile.

## My theme does not have a Gemfile

In the tutorial, I used the [Fresh](http://jekyllthemes.org/themes/fresh/) theme that comes with a Gemfile ready. But what if I choose a theme without a Gemfile? How does it work?

For starters, the `bundle install` command will not work. This command asks Gemfile to install the project gems. Similarly, the `bundle exec jekyll serve` command will not work either.

Today I am going to teach you how to create a Gemfile, or live without it, to exemplify today's steps I will use the [Wall-E](https://github.com/jtemporal/Wall-E) theme (I linked my theme fork because the original just won a PR with a Gemfile hihi).

    $ git clone git@github.com:abhn/Wall-E.git
    $ cd Wall-E/

![bundle install falhando](https://i.imgur.com/Efo1e1C.png)

If you can not start the server using the bundle, the alternative is to do it using Jekyll same puree:

    $ jekyll serve

![jekyll serve falhando](https://i.imgur.com/RGYPVQu.png)This is when you begin to realize how cool it would be to have a Gemfile. If you have it, it is much easier to start running the project. To resolve this error, just do the following steps:

    $ gem install jekyll-gist
    $ jekyll serve

And access  `localhost:4000`.

One way to know which gems to install before running the server is to check the necessary gem for the theme in the `_config.yml` file in the `plugins` tag:

    plugins: [jekyll-gist]

The plugins tag lists the gems needed for that Jekyll project.

## Creating Your Gemfile

Okay, I already know how to run a project without Gemfile, and I can install gems by hand, but I don't want to be doing this, so how do I create a Gemfile?

Start by creating a file called `Gemfile` in the project root:

    $ touch Gemfile

In this file you will list all dependencies, including Jekyll himself:

    source "https://rubygems.org"
    
    gem "jekyll"
    gem "jekyll-gist"

Just do this:

    $ bundle install
    $ bundle exec jekyll serve

And keep doing the posts 😉

***

## Links

* Tutorial about [Gems, Gemfiles and Bundler](https://learn.cloudcannon.com/jekyll/gemfiles-and-the-bundler/)