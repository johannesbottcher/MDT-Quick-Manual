# Masters-Doctoral-Thesis-Template -- unofficial usage guide

A bit of information about the Masters-Doctoral-Thesis-Template
(from now on called MDT), version 2.4 (2016/11/22).  
 This is no official guide.

## What is this template? 

MDT is a basic skeleton for writing a thesis document or
scientific report. It predefines a few commands and environments
that some might consider useful. 

## What do I need to know to use the template? 

MDT  basically just defines the layout of the document.  You need
to have a basic knowledge<sup>1</sup> of LaTeX to write your report. MDT  is
based on the standard LaTeX class `book` and is therefore typeset
in `twoside` mode.

## MDT options

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

## Options to be passed down further

Options that are not handled by the class directly  are passed
down to the already loaded package packages (see below)

- `headsepline` is passed to package scrlayer-scrpage, it sets a
  thin line between the running header and the text of your
document. Alternatively, you can have such a line between text
and footer with `footsepline`, but the footer is empty by
default. 

- `english` or `ngerman` is passed down to package `babel`.
  `babel` takes care of proper hyphenation. The language you use
also changes predefined strings (for example *Contents* in
english and *Inhaltsverzeichnis* in german). You can use any
langauge known to babel, but might need to add strings for the
language you are using. 

- `oneside` is one of the options of standard LaTeX classes. The
  default for the book class is typesetting in `twoside` mode,
that means if you open your printed report, left and right hand
pages have ink on them.  If you want only right hand pages to
have text (so the back of every page is empty after printing),
remove the comment character.


## standard packages used by MDT

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

## Dealing with unnumbered chapters and sections

The template provides `\addchap*{The title of your unnumbered
chapter}` to typeset unnumbered chapters. If you want an
additional entry in the table of contents and properly set
headers, remove the asterisk.  The same mechanism is provided for
sections: `\addsec{Title}` adds an unnumbered section with an
according entry in the table of contents.

## I want to customize the template to my needs, what to do? 

No problem, feel free to do so. Please take a look at the license
of the class file.
*Disclaimer: Once again, basic LaTeX knowledge is needed.*

### I want to change the title page?

Do so. A good guide can be found in the
[LaTeX-Wikibook](https://en.wikibooks.org/wiki/LaTeX/Title_Creation)


### I want to change the layout of predefined abstract/declaration/etc. page?

Don't bother redefining class definitions. Just do what you would
do if you would not use the class.


## I want a different language.

Add the babel language you want to need in the global options.
You need to add some language strings yourself, for example: 

```language=latex
\providecaptionname{spanish}{\abbrevname}{Lista de Abreviaciones}
\providecaptionname{dutch}{\acknowledgementname}{Dank}
```

Strings you can change:  
`\abbrevname` (List of Abbreviations)  
`\byname` (by in the abstract)  
`\abstractname` (Abstract)  
`\acknowledgementname` (Acknowledgements)  
`\authorshipname` (Declaration of Authorship)  
`\constantsname` (Physical Constants)  
`\symbolsname` (List of Symbols)  


## I want to change how chapter titles look.

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

## Often asked questions

### Occasional blank pages appearing?

As MDT relies on `book`, it defaults to chapters starting on
right hand pages only. You can change the behavior by adding the
global option `openany`. Please also have a look at `oneside`
explained above.

### The margins of my thesis are changing back and forth.

This is normal for books which are printed that left and right
hand pages are full of content. Maybe you want a `oneside`
document? Please read about it above.

### I don't get a bibliography

You have to press the BibTeX button in your editor. After the
process finished, you need to recreate the pdf once more.

If that wasn't enough to help you create the bibliography, please
read [Bold citation key instead of citation
number](http://tex.stackexchange.com/questions/63852/question-mark-or-bold-citation-key-instead-of-citation-number).

You can use the file
[bibTest](https://github.com/johannesbottcher/MDT-Quick-Manual/blob/master/bibTest.tex)
as a working test case.  
Hint: `wombat` will always be undefined

### The title of the abstract is at the bottom and the content on
the next page

The abstract is flushed to the bottom om the page. If you don't
want that, you can use `\begin{abstract}[]` (note the empty pair
of brackets). 

Note: This will not happen with the `consistentlayout`  option.

Hint: Abstracts should be reasonably short. 

## Where do i get support? 

Standard location for template support is LaTeX-community.org.
Remember to give a detailed description (minimal working
example) of what is not working. 

## Where do i report a bug?

Standard location for template support is LaTeX-community.org.
Remember to give a detailed description (minimal working
example) of what is not working. 


----

<sup>1</sup> A bit useful material:
- [lshort – A short introduction to LaTeX](http://ctan.org/pkg/lshort)
- [LaTeX for complete novices](http://www.dickimaw-books.com/latex/novices/index.html)
- [Using LaTeX to  writ a PhD-thesis](http://www.dickimaw-books.com/latex/thesis/index.html)
