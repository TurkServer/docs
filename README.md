# Tutorial website and guide for the virtual lab

See a live version at https://virtuallab.github.io/

If you have any questions about building or running virtual lab experiments, please post an [issue][1]. This will help us improve documentation and general information for prospective future experimenters :) .

[1]: https://github.com/VirtualLab/virtuallab.github.io/issues

# Getting Started

This is a [Jekyll][2] site. Jekyll generates a static site from markdown and 
other content, automatically built and hosted by GitHub.
 
To work on the site locally, make sure you have [Ruby][3] installed, along 
with Jekyll and [Bundler][4]: 

[2]: https://jekyllrb.com/ 
[3]: https://www.ruby-lang.org/en/documentation/installation/
[4]: http://bundler.io/

```
gem install jekyll
gem install bundler
```

Then, check out this repo and install the dependencies:

```
git clone https://github.com/VirtualLab/virtuallab.github.io.git
cd virtuallab.github.io
bundle install 
```

Start Jekyll, which creates a development server that will update as you make
 edits:
 
```
bundle exec jekyll serve

```

Once you're done, send a [pull request][5] with your changes!

[5]: https://github.com/VirtualLab/virtuallab.github.io/pulls


# Contribution Guidelines

 
## Editing

1. Local files (using markdown:redcarpet) path: `_pages/{top-navigation-folder}/{your-page}`

2. In each file, following the Metadata setting:
```
---
layout: default    // choose page rendering template under `_layouts/`  [required]
author: kgao    // author name [optional]
date: '2015-05-05`    // writing date YYYY-MM-DD [optional]
title: Examples    // page title for rendering [required]
slug: examples    // page site slug  [required]
permalink: examples    // page site path  [required]
published: true    // content publish control  [required]
icon: fa fa-flask    // font awesome icon class string  [optional]
category: navigation    // choose the parent category, use parent's slug  [required]
order: 2    // order in current category  [required]
---

```


## Test 

1. Put all your test md under `_pages/test/`

2. Set `published:true` when test locally.

3. Set `published:false` when commit.


## Share

Please make sure always create a *Pull Request* for your changes.
So that our core team can help review and approve.