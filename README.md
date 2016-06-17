# Guide to Running Online Experiments using TurkServer

This is source code. See the live version at https://turkserver.readthedocs.io/ .

If you have any questions about building or running online experiments,
please post an [issue][is]. This will help us improve documentation and general
information for prospective future experimenters. Better yet, suggest edits 
and send a [pull request][pr] (see below).

[is]: https://github.com/TurkServer/turkserver.github.io/issues
[pr]: https://github.com/TurkServer/turkserver.github.io/pulls 

# Getting Started

This is a [Sphinx][sphinx] site for [ReadTheDocs][rtd]. Sphinx generates a 
static site this content, which is automatically built and hosted by 
ReadTheDocs.
 
[sphinx]: http://www.sphinx-doc.org/en/stable/ 
[rtd]: https://docs.readthedocs.io/
[py]: https://www.python.org/downloads/

To work on the site locally, make sure you have [Python][py] installed.  
Check out this repo and install the dependencies:

```
git clone https://github.com/TurkServer/docs.git
cd docs
pip install -r requirements.txt 
```

Start the Sphinx development server on the `source` directory, which will update
 as you make edits:
 
```
sphinx-autobuild source _build_html 
```

Once you're done, send a [pull request][pr] with your changes!

# Contribution Guidelines
 
To be completed.
