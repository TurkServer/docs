# Tutorial website and guide for the virtual lab

See a live version at https://virtuallab.github.io/

If you have any questions about building or running virtual lab experiments, please post an [issue][1]. This will help us improve documentation and general information for prospective future experimenters :) .

[1]: https://github.com/VirtualLab/virtuallab.github.io/issues

# Local Editing 

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
jekyll serve --watch
```

Once you're done, send a [pull request][5] with your changes!

[5]: https://github.com/VirtualLab/virtuallab.github.io/pulls
