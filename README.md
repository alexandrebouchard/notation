Latex macros for notation
=========================

Are you tired of chasing mathematical notation in published papers?

Are you tired of conflicting or inconsistent notation?

This package addresses these problems via:

- Automatic creation of hyperlink for each managed mathematical symbol to its first occurrence in the document.
- Generation of lists of symbols.
- Macros to do this with minimal effort for the author.


Usage
=====

1. Copy the file ``notation.sty`` in you latex directory.
2. See ``example.tex`` for instructions and an example.
3. To compile the example use:

```
pdflatex example.tex 
makeindex example.nlo -s nomencl.ist -o example.nls
pdflatex example.pdf 
```

To save time, you can put the script ``makenotation.sh`` in your path and just type:

```
makenotation example
```


Limitations
===========

- Does not seem to link into ``align`` environments, use ``equation``, ``\[ ... \]``, or ``eqnarray``
- Does not link into a figure caption
- If the package ``hyperref`` is already loaded with different options, you will get an error message saying you cannot load the package twice with different arguments. 

Workaround for the ``hyperref`` issue: instead of e.g.

```
\usepackage[colorlinks,citecolor=blue,urlcolor=blue,filecolor=blue,backref=page]{hyperref}
```

use:

```
\usepackage{hyperref}
\hypersetup{colorlinks,citecolor=blue,urlcolor=blue,filecolor=blue,backref=page}
```