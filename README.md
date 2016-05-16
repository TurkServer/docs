# Guide to Virtual Lab Experiments

This is source code. See the live version at https://virtuallab.github.io/ .

If you have any questions about building or running virtual lab experiments,
please post an [issue][1]. This will help us improve documentation and general
information for prospective future experimenters. Better yet, suggest edits 
and send a [pull request][pr] (see below).

[1]: https://github.com/VirtualLab/virtuallab.github.io/issues
[pr]: https://github.com/VirtualLab/virtuallab.github.io/pulls 

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
bundle exec jekyll serve --watch
```

Once you're done, send a [pull request][pr] with your changes!

# Contribution Guidelines
 
## Editing files locally

1. All files are stored in `_pages/{top-navigation-folder}/{your-page}`.

2. The following metadata, at the top of each file, controls title, path, 
organization, and so on.

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

## Testing partial content 

The `published` key controls what pages display on the site. You can use this
 to push partial changes that you don't want to show up online. 

- Set `published: true` for local testing.
- Set `published: false` when committing.

The `_pages/test/` folder is an entire directory of content that you can play
 around with. You can also store uncategorized content that is not ready here. 

## Sharing your information

Please make sure always create a [pull request][pr] for your changes, so that
 we can take a look and add them to the site!
