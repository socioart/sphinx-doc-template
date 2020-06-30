# Requirement

* python (>= 3.7)

# Initialize


    git clone https://github.com/socioart/sphinx-doc-template.git $MY_DOC_NAME
    cd $MY_DOC_NAME
    git remote remove origin
    sed -i -e s/YOUR_DOC_NAME/$MY_DOC_NAME/ setup.cfg
    pip install pipenv
    pipenv install
    pipenv shell
    sphinx-quickstart

Edit `conf.py`.

```diff
 extensions = [
+  'recommonmark',
+  'sphinx_rtd_theme',
 ]
```

```diff
-html_theme = 'alabaster'
+html_theme = 'sphinx_rtd_theme'
```

Edit `Makefie`.

```
# Add below after `help`
server: html
	echo "Listening on http://localhost:4567"
	ruby -run -e httpd -- -p 4567 _build/html
```

# Installation

    pip install pipenv
    pipenv install

# Add page

Add `pages/PAGENAME.md` and write in Markdown.
Edit `index.rst`.

```diff
 .. toctree::
    :maxdepth: 2
    :caption: Contents:

    /pages/PAGENAME
```

# Usage

    pipenv shell
    # Compile and launch server
    make server
    # Compile
    make html
    # Remove compiled files
    make clean
