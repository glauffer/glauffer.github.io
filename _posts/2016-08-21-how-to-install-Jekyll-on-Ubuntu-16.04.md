---
layout: post
title: How to Install Jekyll on Ubuntu 16.04
subtitle: Installing Jekyll, the static site generator engine used by GitHub Pages.
---

[Jekyll](https://jekyllrb.com) is the Static Site Generator used on GitHub Pages. Here are some guidance to install this amazing tool on Ubuntu 16.04 and how to work locally on your GitHub page.

First, it is necessary to install `ruby` and `ruby-dev` (Ruby is standard on Ubuntu but ruby-dev is not):

>```bash
>$ sudo apt install -y ruby ruby-dev
>```

Then we can install Jekyll:

>```bash
>$ sudo apt install -y jekyll
>```


## Jekyll Plugins

Some websites and themes need specific plugins to work. For example, the amazing [Minimal Mistakes Theme](https://mmistakes.github.io) uses the following:

* Paginate
* sitemap
* gist
* jemoji

As Jekyll and its plugins are written in Ruby, we need to use the `gem` package manager to install those plugins. For the case of the minimal Mistakes Theme plugins, one can type on terminal:

>```bash
>sudo gem install jekyll-paginate jekyll-sitemap jekyll-gist jemoji
>```


## Work on your GitHub page locally

To generate and preview your site locally in your browser, first you have do clone your GitHub page directory to your computer and `cd` into it. Then, you can type on terminal:

>```bash
>$ jekyll serve
>```

this command will generate your website locally on your machine. You can access your local page by typing on your Internet browser the information which appeared on your terminal under the "Serve address" section. Usually it is `localhost:4000`

Any changes that you make on your files will be loaded on your local website and will be showed on your browser<sup id="a1">[1](#f1)</sup>. The only exception for this is `_config.yml` file. For any changes in this file it will be necessary to run `serve` command again.



<sub><b id="f1">1</b> Older Jekyll version needed the flag `--watch` to load changes on files. [↩](#a1)<sub>
