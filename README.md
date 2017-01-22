# Masters-Doctoral-Thesis-Template

A bit of information about the Masters-Doctoral-Thesis-Template
(from now on called MDT), version 2.4. This is no official guide.

## What is this template? 

MDT  is a basic skeleton for writing a thesis document or
scientific report. I predefines a few commands that some might
consider useful. 

## What do i need to know to use the template? 

You need to have a basic knowledge of LaTeX. The class is based
on the standard LaTeX class `book`.

## Options of the class

- `consistentlayout`   
The template set the pages for abstract, declaration and others
with a special formatting. This option makes the layout more
consistent

- `chapterinoneline`  
Default `book` class sets the word chapter and the current number
in one line, and the chapter title in the next line. This option
just sets the current number and the title, both in one line

- `liststotoc`, `toctotoc`  
Add entries for the list of tables, list of figures and table of
contents to the table of contents. The user has to decide how
useful it is to have an entry for the table of contents within
the table of contents. `liststotoc` also influences the
predefined environments for *List of Abbreviations*, *Physical
Constants* and  *List of Symbols* if you should decide to really
use them. You don't have to. Packages like `acro` or `glossaries`
can give you much more power.

- `nolistspacing`
Package `setspace` is used by the template, so you can set the
spacing to `singlespacing` (default), `onehalfspacing` or
`doublespacing` if you need it. Option `nolistspacing` keeps the
singlespacing in the lists and keeps them compact.

- `parskip`
The template default is the usual paragraph indentation as seen
in almost any book. If you want to separate paragraphs of text by
a blank line, use this option. In the background, package
`parskip` will be loaded. 

- `nohyperref`  
Probably one of the most important options. As a rule of thumb,
package `hyperref` should be loaded last. Use that option to
prevent the class from loading the package, giving you full
control about the time to load the package.

Options that are not handled by the class are forwarded to the
packages. `headsepline`, the language options or the spacing
options are some of them. 

## Changing chapter titles

A few commands are available to change the appearance of chapter
titles.

`\abovechapterskip` The spacing above the chapter
`\chapterbelowskip` The spacing below the chapter
`\chapterinbetweenskip` The spacing between  the chapter lines
`\chapteralign` Alignment of the chapter
`chapterfont` The font of the chapter
`chapterprefixfont` The font of the chapter prefix
`\autodot` 
`\mdtChapapp`

If you don't know how to customize the output yourself, have a
look at the support section below. 

If you need more than the given features, have a look at package
`titlesec`.

## Dealing with unnumbered chapters and sections

The template provides `addchap*{The title of your unnumbered
chapter}` to typeset unnumbered chapters. If you want an
additional entry in the table of contents, remove the asterisk.


## standard packages

Packages `inputenc` and `fontenc` are important when compiling
with pdfTeX. If you need to compile with another engine, you need
to make the according changes.

Modern package `biblatex` is used to do the bibliography. If you
need, for some reason, to use the older `natbib` package, feel
free to do so.

Package `caption` is used to define the captions of tables and
figures.

Package `geometry` is used to set the paper margins. 

Package `booktabs` is used for the example tables.

Package `scrlayer-scrpage` is used to define the headers and
footers. If you need to change them, have a look at the
KOMA-script documentation.

## I want to change the title page?

Do so. A good guide can be found in the
[LaTeX-Wikibook](https://en.wikibooks.org/wiki/LaTeX/Title_Creation)


## I want to change the predefined abstract/declaration/etc. page?

Don't bother redefining class definitions. Just do what you would
do if you would not use the class.


## Where do i get support? 

Standard location for class support is LaTeX-community.org.
Remember to give a detailed description of what is not working. 
