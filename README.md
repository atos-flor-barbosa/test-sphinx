# Testing Sphinx

Testing Sphinx for documentation generation.

## Installation

### Windows
It can be installed using Chocolatey, or with pip.

    $ choco install sphinx
    
    $ pip install -U sphinx

### Mac
Easiest way would be using homebrew

    $ brew install sphinx-doc
## Create a new project

        mkdir project
        cd project
        sphinx-quickstart .

## Structure
Key files when using Sphinx.

        conf.py - settings and execute code
        index.rst
        Makefile

## Words: Source format

- reStructuredText - no changes needed to conf.py
- Markdown - you need to use recommonmark

## Using Markdown
To be able to add your markdown files on Sphinx, there are several requirements

    $ pip install recommonmark

And add the following lines to your configuration file (conf.py)

```python
...

# -- General configuration ---------------------------------------------------

# Add any Sphinx extension module names here, as strings. They can be
# extensions coming with Sphinx (named 'sphinx.ext.*') or your custom
# ones.
extensions = [
    'recommonmark'
]

source_suffix = {
    '.rst': 'restructuredtext',
    '.txt': 'markdown',
    '.md': 'markdown',
}

...
```

Also, if using tables, you will have to add the following in order for Sphinx to render them correctly

    $ pip install sphinx-markdown-tables

And also add this extension to your config file, having now something like this:

```python
extensions = ['recommonmark', 'sphinx_markdown_tables']
```

## Run the build
To view the html files generated each time a change occurs, follow the next command and after that, open de index.html located inside the build/html directory.

    $ make html

> Note: if you get an error saying make command was not found, you need to install it (using Windows you can download it through chocolatey)

## References
* https://www.sphinx-doc.org/en/master/index.html
* https://www.youtube.com/watch?v=0ROZRNZkPS8
* https://www.sphinx-doc.org/en/master/usage/markdown.html
* https://gist.github.com/johncrossland/9f6f54d559e9136773172aa0a429b46f
  
  
