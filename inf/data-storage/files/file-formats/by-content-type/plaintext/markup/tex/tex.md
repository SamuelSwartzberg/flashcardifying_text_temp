# tex, especially latex

⟮Tex⟯ consists of ⟮tex-core⟯ and ⟮plain-tex⟯ 
⟮plain-tex⟯ is ⟮the set of macros that the tex typsetting program uses⟯; ⟮tex-core⟯ is ⟮the typesetting program (that transforms it into output⟯) 
⟮Tex⟯ and thus ⟮latex⟯ is meant for ⟮typesetting⟯ 
⟮TeX⟯ and thus ⟮LaTeX⟯ mainly work via ⟮macros⟯ 
⟮Mathjax⟯ renders ⟮a subset of latex⟯ ⟮in browsers (using js⟯) 
⟮current⟯ latex version: ⟮Latex 2e⟯ 
⟮next⟯ latex version: ⟮Latex 3⟯ 
「latex」 is properly capitalized ⟮LaTeX⟯ 
「tex」 is properly capitalized ⟮TeX⟯ 
the x in ⟮tex and latex⟯ is pronounced as ⟮a voiceless velar fricative (e.g. loch, bach⟯) 

⟮latex⟯ is ⟮a set of tex macros⟯ that is supposed to be ⟮more semantic⟯. 
texinfo is a set of macros for tex for generating hypertextual documentation

info|read texinfo files

## unsorted

\{{c1::stackrel}}{{c2::{top}{bot} }} will {{c3::render the top text above the bottom text}}
In Latex, there are a bunch of commands starting with \text (which I will call \textwhatever) that indicate different fontstyles: \textbf, \textit, \textrm (roman), \texttt (monospace), \textsc (smallcaps)
If you try to type text in a math env as-is, it will look weird, as latex is formatting it for math.
To insert text in a math environment, you can use any of \mathwhatever, \textwhatever, or just \text.
It is generally advised that you use \text or \textwhatever within math environments when you want to write text, and \mathwhatever when you want to write math that just happens to be in roman letters.
For many but not all \textwhatever font formatting commands, latex has corresponding \mathwhatever fonts (e.g. \mathrm, \math.
The \mathwhatever fonts only work within a math environment.
The \textwhatever fonts also work within a math environment.
Within a math environment, there are some differences between \mathwhatever and \texthatever: 
\mathwhatever uses the defined math font and \textwhatever uses the defined text font (which may be different)
\mathwhatever does not preserve spaces within, but \textwhatever does.
you can nest \textwhatevers but not \mathwhatevers.
some text styles only exist as \mathwhatevers, e.g. mathfrak (Fraktur), mathbb (Blackboard bold)

In math environments, besides using \textbf or \mathbf, you can bold symbols by using \boldsymbol or \pmb 'poor man's bold' (which however only works by duplicating characters 3 times slightly offset)

frac{a}{b}   fraction (bruch)||<img src="sm_JFBz6.png">
sqrt[root]{math}   square root (wurzel)
\sum_lower^upper

There are also commands for math functions that are pure text (e.g. sin, lim), which have the advantage over just typing the characters that proper formatting is guaranteed

For commands (esp. math) that take something lower, it is often indicated {{c1::_{foo}}}
For commands (esp. math) that take something upper, it is often indicated {{c1::^{foo}}}

\bar{foo}|ad a bar on top of letter
<div class='c2-f'>
What does this indicate?
</div><div class='c1-f'>
How do we indicate this in latex?
</div><br/>{{c1::x^{n}}}  <span class="divider">&lt;-&gt;</span> {{c2::x<sup>n</sup>}}<br/><div class="sub">
<div class="sub c2-f c1-b" >
for single characters {} are optional
</div>
</div>
<div class='c2-f'>
What does this command do?
</div><div class='c1-f'>
Command for this?
</div><br/>((h:2;::<img src="sm_403-4037364_6848425-integral-symbol.png">))
((h:2;::<img src="sm_1200px-Greek_uc_sigma.svg.png">)){{c1::int}}  <span class="divider">&lt;-&gt;</span> {{c2::integral}}
{{c1::sum}}  <span class="divider">&lt;-&gt;</span> {{c2::render a sum}}
<div class='c2-f'>
What does this command do?
</div><div class='c1-f'>
Command for this?
</div><br/>((h:2;::<img src="sm_uNgnp.png">)){{c1::overbrace}}  <span class="divider">&lt;-&gt;</span> {{c2::horizontal curly brace on top}}
<div class='c2-f'>
What does this command do?
</div><div class='c1-f'>
Command for this?
</div><br/>((h:2;::<img src="sm_binomial-coefficient-formula.png">)){{c1::binom}}  <span class="divider">&lt;-&gt;</span> {{c2::binomial coefficient}}

To get latex citations etc to work (when compiling), first...  pdf make (<code>pdflatex</code>)
To get latex citations etc to work, first run the pdf maker (pdflatex), then run the citation processor, then...  run the pdf maker twice
To get latex citations etc to work, first run the pdf maker, then  run the citation processor
Latex' convention of naming everything to do with citation bibliography&lt;whatever&gt; reflects what usage of the word bibliography?  the wide sense (synonym to works cited / references)
\usepackage[style=foo]{biblatex}   (biblatex) set the citation style to foo
printbibliography   (biblatex) add a works cited/references section
BibTeX is a {{c1::file format (.bib)}} as well as {{c2::a latex citation processor}}
Common packages for citation management in latex are {{c1::biblatex}} and {{c2::natbib}}
Common processors for .bib files for latex are {{c1::BibTeX}} and {{c2::biber}}
In latex, what generally glues our latex file and our citations (in the .bib file) together?  a certain (citation) processor
In latex, where do we generally save our citations?  a separate (.bib) file
The confusing thing about BibTeX being two things is that even if you do what, you still use BibTeX the file format?  use a different processor
The confusing thing about BibTeX being two things is that even if you use a different processor, you still?  use the .bib format
biblatex is <b>most commonly </b>used with what as the processing program?  biber
biblatex requires what as the processing program?  nothing in particular
natbib requires what as the processing program?  BibTeX
addbibresource   (biblatex) command to specify the location for your .bib file<div class="sub">
<div class="sub c1-b c2-f">
(well, biber does also support other formats)
<br><img src="sm_tmprbsz3kbb.jpg"><br></div>
</div>
<div class="c1-f">
What's the problem?
</div>What happens if you try to use e.g. biber with a file with file ending?  it'll not work (try to find files that don't exit)
biber foo.tex  Call biber without extension (biber foo)
if you call biber, the argument you call it with has what characteristic?  don't include file extension
<div class="c2-f">
What does this command do?
</div><div class="c1-f">
Command for this?
</div>footnote{foo}   create a footnote containing foo<div class="c2-f">
What does this command do?
</div><div class="c1-f">
Command for this?
</div><br>
cite{foo}   cite a specific work with label foo
footcite{foo}   cite a specific work with label foo in as a foot note
nocite{foo}   add a specific work with label foo into the references/works cited section without referring to it in the text
parencite{foo}   cite a specific work with label foo in parentheses
textcite{foo}   cite a specific work with label foo in-text with parenthesees areound <b>a specific part</b>
<div class="c2-f">
What does this command do?
</div><div class="c1-f">
Command for this?
</div><br>appendix   generate an appendix

A table in latex is created by the tabular environment.

the tabular environment has a very specific syntax.
Matrix syntax is similar to  {{c1::tabular syntax}}
The call to \begin{tabular} takes an additional argument, 
Defining {{c3::multiple columns}} within a {{c4::tabular}} argument: {{c5::*}} {{c6::{}} {{c1::amount}} {{c6::} }}{{c6::{}} {{c2::type}} {{c6::}&nbsp;}}&nbsp;<br><div class="sub">
spacing is for anki clozes, not for latex
</div>
((h:2;::<img src="sm_147px-Multicolumn.svg.png">))In comparison with normal columns, what do paragraph columns do?  wrap
\multicolumn{ num_cols }{ alignment }{ contents }
to wrap text within a table, what kind of columns should you use?  paaragraph columns
cline{&lt;start&gt;-&lt;end&gt;}   generate a partial horizontal line from start to end
multicolumn   create a collumn that is broader than one
paragraph column of width width   p{width}
tabular   a table<div class="sub">
<div class="sub c1-f">
syntax in html is what? (different from this)
</div>
<div class="sub all-b">
the table environment is used for something different
</div>
</div>
<div class="c2-f">
Latex package for?
</div><div class="c1-f">
Latex package for?
</div>
<div class="c2-f">
Environment that delimits what?
</div><div class="c1-f">
Is indicated by which environment?
</div><br>{{c1::longtable}}  <span class="divider">&lt;-&gt;</span> {{c2::allow tables to flow over page boundaries}}<br><div class="sub">
<div class="sub f">
package longtable
</div>
</div>
<div class="c2-f">
Environment that delimits what?
</div><div class="c1-f">
Is indicated by which environment?
</div>
<div class="c2-f">
Indicate what?
</div><div class="c1-f">
Are indicated how?
</div><br>((h:2;::<img src="sm_5da95a8e56e67d6b497a09183e429c5d961f7323.svg">)){{c1::matrix (and derivatives, pmatrix, bmatrix...)}}  <span class="divider">&lt;-&gt;</span> {{c2::a matrix&nbsp;}}
{{c1::the letters in front of the matrix environment (pmatrix, bmatrix...)}}  <span class="divider">&lt;-&gt;</span> {{c2::the braces surrounding a matrix}}<br><div class="sub">
<div class="sub all-b">
the table environment is used for something different
</div>
</div>

## Commands

A typical ⟮command⟯ looks ⟮c1;⟯⟮name⟯⟮{⟯⟮argument⟯⟮} ⟯ 
a ⟮command⟯'s ⟮required arguments⟯ (AKA ⟮arguments⟯) are ⟮delimited by {⟯} 
a ⟮command's⟯ ⟮optional arguments⟯ (AKA ⟮options⟯) are ⟮delimited by []⟯ 
{{c14::}} ⟮starts⟯ ⟮a command⟯ 
Generally, ⟮commands⟯ take ⟮the thing they act on⟯ ⟮as a required argument⟯. 
⟮Some commands⟯ instead ⟮apply to anything⟯ ⟮following the command⟯ ⟮until the end of environment or group⟯, these are known as being in ⟮declaration form⟯. 

⟮The name⟯ ⟮of a command⟯ ⟮used as an environment⟯ is known as that commands ⟮environment form⟯ 
the ⟮environment form⟯ of ⟮\foo⟯ would look like {{c25::`\begin{command}...\end{command}`}} 
⟮Most (afaik) commands⟯ in ⟮declaration (\command (no args⟯)) form can also be used  ⟮in an environment form⟯ 
⟮The environment form⟯ of a command is based on ⟮its declaration form.⟯ 

### new commands

To ⟮create a new command⟯, use ⟮\newcommand⟯, which goes in ⟮the preamble⟯ 
⟮\newcommand⟯ has the syntax: ⟮\newcommand⟯⟮{‹name›⟯}⟮[‹number-of-arguments›]⟯⟮{‹latex-code-to-execute›⟯} 
Within ⟮\newcommand⟯, you ⟮refer to arguments⟯ ⟮positionally⟯ with ⟮#n⟯ 
⟮\newcommand{\euler}{\mathrm{e}⟯ makes ⟮\euler output \mathrm{e}⟯ 
```
\newcommand{\abs}[1]{\left|#1\right|}
```

## Sections

Latex ⟮sections⟯ ⟮go until⟯ ⟮the beginning of the next section⟯ 
Latex sections are declared via ⟮command. (e.g. \part⟯) 
Latex ⟮section commands⟯ take ⟮the full section title⟯ as ⟮a mandatory argument⟯ and ⟮a short title (e.g. for TOC⟯) as ⟮an optional argument⟯. 
^\subsection[shortitle]{This is the full title}
⟮Article⟯ notably does not havet the ⟮\chapter⟯ section command. 

### Latex section hierarchy

1. ⟮c+;sb;part⟯
2. ⟮c+;sb;chapter⟯
3. ⟮c+;sb,6-7;section⟯
4. ⟮c+;sb,6-7;subsection⟯
5. ⟮c+;sb,7;subsubsection⟯
6. ⟮c+;sb;paragraph⟯
7. ⟮c+;sb;subparagraph⟯

## latex groups

in Latex, ⟮groups⟯ ⟮create a scope⟯ 
`⟮\bgroup ... \egroup⟯` or ⟮`{ ... }`⟯ ⟮delimit a group⟯ 

## latex labels and refs

In latex, using ⟮\label⟯ you ⟮define a marker⟯, which ⟮you can then later reference⟯. 
the main advantages of ⟮using labels⟯ in latex instead of ⟮manually referring to the indices of the things⟯ is that ⟮they auto-update⟯ 
⟮\label⟯ takes ⟮an argument⟯ of ⟮the name of the marker.⟯ 
⟮\label⟯ goes ⟮within⟯ ⟮the thing being labeled⟯ as ⟮the first thing⟯ if ⟮there is a 'within'⟯, and ⟮after⟯ otherwise. 
It is common practice to ⟮prefix the name of the marker⟯ with a ⟮most often 3-character⟯ ⟮abbreviation⟯ of ⟮the type of the marker⟯ plus ⟮a colon⟯ 
^\label{sec:foo}

abbr|for
⟮eq⟯|⟮equation⟯
⟮sec⟯|⟮section⟯
⟮fig⟯|⟮figure⟯


In latex, you can ⟮reference markers⟯ defined with ⟮\label⟯ with ⟮\ref⟯, ⟮\pageref⟯ or ⟮\eqref⟯. 

command|refers to?|from package
⟮\ref{foo}⟯|⟮returns the index of foo⟯
⟮\pageref{foo}⟯|⟮returns the page on which foo is found⟯
⟮\eqref{foo}⟯|⟮returns the index of foo, but surrounded by parentheses⟯|⟮amsmath⟯


## Lengths

### rigid and rubber

The two types of lengths ⟮latex⟯ has are ⟮rigid lengths⟯ and ⟮rubber lengths⟯. 
a ⟮rubber length⟯ is a length that ⟮⁑can⁑ shrink or grow⟯ 
a ⟮rigid length⟯ is a length that ⟮will not shrink or grow⟯ 
Lengths in latex are ⟮rigid⟯ by ⟮default⟯ 
⟮rubber lengths⟯ can ⟮only shrink or grow⟯ by ⟮the length we specified⟯ 
⟮plus ‹length› ∨ minus ‹length›⟯ indicate ⟮a rubber length⟯ 

indicator|meaning
⟮plus ‹length›⟯|⟮length can grow by that amount⟯
⟮minus ‹length›⟯|⟮length can shrink by that amount⟯


```
 \blackbar{101pt}\hspace{100pt minus 2pt}\blackbar{101pt}}YYY
```


### creating lengths

To ⟮create a length foo⟯, you first have to ⟮declare it⟯ with ⟮\newlength{\foo⟯} and then ⟮initialize it⟯  ⟮with \setlength{\foo}{bar⟯}. 
⟮\setlength⟯ can also be used to ⟮change the value⟯ of ⟮preexisting length keywords⟯. 
If you ⟮change the value of preexisting length keywords with \setlength⟯, ⟮things that use these lengths itnernally⟯ will also change. 
⟮\parindent⟯|⟮represents length of first line in paragraph indentation⟯
⟮\parskip⟯|⟮represenets the vertical distance between paragraphs⟯



## math

### packages

the package ⟮amsmath⟯ contains ⟮a bunch more stuff related to math⟯. 
the package ⟮mathtools⟯ is ⟮a superset of⟯ ⟮amsmath⟯, and also ⟮fixes some of its bugs⟯ 
the package ⟮s9:10;⟮amssymb⟯ ⟮adds more math symbols⟯⟯; the package ⟮s7:8;⟮amsthm⟯ ⟮adds more theorem/proof related stuff⟯⟯. ⟮these both⟯ ⟮need to be separately loaded from amsmath/mathtools⟯ if desired. 

### environments

Fundamentally, ⟮math⟯ in LaTeX is always ⟮contained in its own environment.⟯ 
There are ⟮two types of math environments⟯ in ⟮LaTeX⟯, ⟮displayed (block in CSS terms⟯) and ⟮inline⟯. 
There exists ⟮a basic built-in environment⟯ for ⟮c+;both types of math environments⟯, ⟮displayed⟯ and ⟮inline⟯. 
The ⟮basic built-in version⟯ of ⟮both types of math environment⟯ has ⟮a shorthand⟯ ⟮derived from TeX⟯ which  is ⟮now deprecated⟯. 
The ⟮TeX derived⟯ ⟮shorthands⟯ for ⟮the built-in math environments⟯ involves ⟮using the $ character⟯. 
The basic built-in version of both types of math environment has a shorthand exclusive to LaTeX whose use is encouraged. 
The ⟮LaTeX-exclusive⟯ ⟮shorthands⟯ for ⟮the built-in math environments⟯ involves ⟮using escaped parentheses\bracket characters.⟯ 

environment name|TeX shorthand|LaTeX shorthand
⟮math⟯|⟮$...$⟯|⟮\​(...\​⟯)
⟮displaymath⟯|⟮$$...$$⟯|⟮\​[...\​]⟯


⟮amsmath/mathtools⟯ adds a bunch more ⟮displayed⟯ ⟮math environments⟯. 
For the ⟮amsmath/mathtools environments⟯ there are often ⟮two versions⟯, ⟮s34;one ⟮with a star⟯ and ⟮one without⟯⟯. 
⟮amsmath/mathtools environments⟯ ⟮w/o a star⟯ are ⟮numbered⟯, ⟮w/ a star⟯ they are ⟮not numbered⟯. 

environment|name|image
⟮equation/equation*⟯|⟮same as displaymath (added to have numbered version⟯)
⟮gather/gather*⟯|⟮center-align lines⟯|⟮h39;✫sm_2021-05-18--15-11-30-screenshot.png✫⟯
⟮multline/multline*⟯|⟮first line left-aligned, then all center-aligned, final line right-aligned⟯|⟮h43;✫sm_2021-05-18--15-16-19-screenshot.png✫⟯


The ⟮align/align* environment⟯ aligns ⟮parts of the equation⟯ ⟮vertically⟯ in relation to ⟮the anchor⟯, which is the ⟮c+;＆ symbol⟯ 
⟮split⟯ is ⟮the same as⟯ ⟮the align environment⟯, but ⟮within the equation environment⟯ 

the ⟮autobreak⟯ environment contained in ⟮the eponymous package⟯ ⟮auto inserts linebreaks into formulae⟯ 
In ⟮the autobreak environment⟯, ⟮any newline⟯ is treated as ⟮a possible point to break⟯ 
⟮proof⟯ provides ⟮an environments for proofs⟯ 
the ⟮cases environment⟯ renders ⟮multiple lines⟯ with ⟮an extensible left curly-brace⟯ for ⟮piecewise-defined functions⟯ 

flex-container:✫sm_CkJlF.png✫



### newtheorem

\newtheorem is used in the document preamble
⟮\newtheorem⟯ ⟮creates a new theorem envronment⟯ 
⟮\newtheorem⟯ takes ⟮two arguments, and one option⟯. 
⟮The first argument to \newtheorem⟯|⟮the name of the environment that we create by the call to \newtheorem (i.e. how we will refer to it later⟯)
⟮The second argument to \newtheorem⟯|⟮The heading that the environment that we create by the call to \newtheorem will have⟯
⟮The option of \newtheorem⟯|⟮based on what the theorem will be numbered⟯


For ⟮\newtheorem⟯, if ⟮[foo]⟯ occurs {{c11::between the two {args} }}, it is ⟮a reference to another theorem⟯ → ⟮with which it will share numbering⟯ , if it occurs {{c11::after the two {args} }}, it is ⟮a reference to a section⟯ → ⟮under which it will be numbered⟯ 

```
\newtheorem{theo}{Theorem}
...
\begin{theo}
```


## Symbols

### case-changed symbols

For arrows, if the ⟮first letter⟯ is ⟮lowercase⟯, it will render the ⟮thin arrow (→⟯), if the ⟮first letter⟯ is ⟮uppercase⟯, it will render the ⟮thick arrow (⇒⟯). 
so `⟮\right/left/up/downarrow⟯` renders ⟮a thin right arrow →⟯, and ⟮\Right/Left/Up/Downarrow⟯ renders ⟮a thick, double-line right arrow ⇒⟯. 
the four directional arrows are created by \right/left/up/downarrow
⟮\rightarrow⟯ can also be created by ⟮\to⟯ 
⟮\Rightarrow⟯ can also be created by ⟮\implies⟯ 
For greek letters, if the ⟮first letter⟯ is ⟮lowercase⟯, it will render the ⟮lowercase letter⟯, if the ⟮first letter⟯ is ⟮uppercase⟯, it will render the ⟮uppercase letter⟯. 
so ⟮\pi⟯ ⟮inserts a lowercase pi π⟯ and ⟮\Pi⟯ ⟮inserts an uppercase pi Π⟯ 

### logic symbols

symbol|command(s)|requires package
⟮∧⟯|⟮c+;s5;\land⟯ ⟮c+;s4;\wedge⟯
⟮∨⟯|⟮c+;s6;\lor⟯ ⟮c+;s3;\vee⟯
⟮¬⟯|⟮c+;s8;\lnot⟯ ⟮c+;s7;\neg⟯
⟮∴⟯|⟮\therefore⟯|amssymb

### set symbols

\supset|⊃
\supseteq|⊇
\supsetneq|⊋
\subset|⊂
\subseteq|⊆
\subsetneq|⊊
\cup|∪
\cap|∩
⟮\in⟯|⟮set membership⟯
⟮\notin⟯|⟮negation of set membership⟯
⟮c+;\ni|⟮c8;reversed set membership symbol⟯
∖|set difference/relative complement
⟮\o⟯|⟮ø⟯

### comparison operators

⟮\leq⟯|⟮≤⟯
⟮\geq⟯|⟮≥⟯
⟮\approx⟯|⟮≈⟯

### various symbols


command|symbol
⟮\LaTeX⟯|⟮insert the latexlogo⟯


\times|×


⟮\ldots⟯|⟮an ellipsis on the baseline …⟯
⟮\cdots⟯|⟮an ellipsis slightly below the midline ⋯⟯




⟮\infty⟯|⟮∞⟯
\prime|′ (the prime)
\degree|°


⟮\dots⟯ ⟮is equivalent to \ldots⟯ in ⟮vanilla latex⟯. 
If using ⟮amsmath⟯ and ⟮within math mode⟯, ⟮\dots⟯ ⟮decides between \ldots and \cdots⟯ ⟮based on context⟯ 

## language ＆ encoding

Package|Function
⟮babel⟯|⟮foreign language support⟯
⟮fontenc⟯|⟮output character encoding⟯
⟮inputenc⟯|⟮input character encoding⟯


## beginning of document

⟮Latex commands⟯ are ⟮either defined in the .cls file⟯ (and thus ⟮you can use them by default⟯) or ⟮in packages⟯. 

The ⟮first statement⟯ in a latex document must be  ⟮\documentclass⟯ 
⟮The required argument⟯ of ⟮\documentclass⟯ is ⟮the document clas⟯s 
calling {{c14::\documentclass{foo} }} ⟮loads foo.cls⟯ in the background 
⟮The optional argment⟯ of ⟮\documentclass⟯ contains ⟮global options such as font size, orientation, paper size...⟯ The part of the document between {{c11::\documentclass{...} and \begin{document}}} is ⟮the preamble⟯ ⟮\usepackage⟯ is used to ⟮import a package and thus its commands⟯. 


⟮Any \usepackage declarations⟯ must go in ⟮the preambl⟯e. 
⟮\RequirePackage⟯ is like ⟮\usepackage⟯, with the dif that it can be used ⟮before \documentclass⟯ and ⟮is really only used by people writing packages/classes⟯ 

⟮The document environment⟯ contains ⟮the entire document (anything that will be visible⟯) 
⟮after \begin{document⟯} there is often ⟮a set of commands⟯ setting ⟮metadata⟯ called ⟮the top matter/topmatter⟯ 
⟮\abstract⟯|⟮set the abstract of e.g. the paper⟯
⟮\author⟯|⟮set document author⟯
⟮\date⟯|⟮set document date⟯
⟮\title⟯|⟮set document title⟯
⟮\and⟯|⟮separating multiple authors within \author⟯


⟮\maketitle⟯ then ⟮renders top matter⟯ into ⟮the title page⟯ 




## document classes and their specific features

### beamer

The ⟮documentclass⟯ for ⟮creating presentations⟯ is ⟮beamer⟯. 
The highest-level division of ⟮beamer⟯ is ⟮the frame⟯. 
A beamer ⟮frame⟯ can be defined ⟮by command or as an environment⟯ 
⟮Frames⟯ ⟮may consist of multiple⟯ ⟮slides⟯. 
⟮\pause⟯ inserts a ⟮breakpoint⟯ into the frame, creating a ⟮first slide⟯ ⟮with all the content up to⟯ the ⟮breakpoint⟯, and a ⟮second slide⟯ ⟮which also contains the contents after⟯ the ⟮breakpoint⟯ 
⟮\frametitle{foo⟯} ⟮sets foo as the title of the frame⟯ 

l⟮atex presentations⟯ are ⟮styled⟯ via ⟮themes⟯ 
The kind of themes that latex presentations can have are ⟮presentation⟯, ⟮color⟯, ⟮font⟯, ⟮inner⟯, ⟮outer⟯ 
⟮the elements inside of a frame (enumerations, blocks, theorems, etc⟯) are styled via ⟮inner themes⟯ 
⟮the elements outside of a frame (headers, footers, etc.⟯) are styled via ⟮outer themes⟯ 
⟮Setting themes⟯ is done via ⟮the \usetheme command⟯ 

⟮Overlay specifications⟯ specify ⟮which slides⟯ to ⟮apply a command to⟯, or ⟮on which slides⟯ ⟮to show a thing⟯ 
⟮Overlay specifications⟯ are written ⟮‹some_number/list/range›⟯ 
^\item‹-2,4-5,7›
⟮\only⟯⟮‹overlay-spec›{text⟯}: ⟮only render the text⟯ ⟮on the specified slides⟯ 
⟮\uncover⟯⟮‹overlay-spec›{text⟯}: ⟮only render the text⟯ ⟮on the specified slides,⟯ but ⟮still take up space on the other slides⟯ 

flex-container:✫sm_L5.png✫


When using the ⟮beamer⟯ class, you can use ⟮modes⟯ to ⟮only do things in certain circumstances (handout, presentation, slide notes etc.⟯) 
Command to ⟮only do something in a certain mode⟯ ⟮mode⟯⟮‹⟯⟮certain_mode⟯⟮›⟯⟮{⟯⟮things to do⟯⟮} ⟯ 
Latex beamer modes
onion-box:[all [presentation [⟮c+;s1:2;beamer⟯][⟮c+;s1:2;second⟯][⟮c+;s1:2;handout⟯][⟮c+;s1:2;trans⟯]][⟮article⟯]]

⟮\institute⟯ ⟮sets document institute (e.g. TU Fak. 1⟯) (exclusive to ⟮beamer⟯) 

⟮\titlepage⟯ is ⟮functionally equivalent⟯ to ⟮\maketitle⟯, but ⟮will insert a missing frame if necessary⟯ 
⟮block⟯ is ⟮an environment⟯ representing ⟮a text box⟯ in latex ⟮beamer⟯, taking ⟮an additional argument⟯ of ⟮its title⟯ 
the ⟮columns environment⟯ allows ⟮a multicolumn setup⟯ in latex ⟮beamer⟯  
⟮within the columns environment of beamer⟯, ⟮\column{foo⟯} ⟮inserts a column of width foo⟯. 
⟮theorem⟯ is an ⟮environment⟯ that ⟮delimits a theorem⟯ ⟮(c:69;beamer⟯ only) 
flex-container:⟮h∞;✫sm_Beamerblock.png✫✫sm_Beamercolumns.png✫✫sm_Beamermaths.png✫ ⟯

### KOMAScript

⟮KOMA-script⟯ is ⟮a bundle of classes⟯ generally more ⟮versatile⟯ than ⟮builtin equivalents⟯ (if ⟮even  extant⟯). 
⟮KOMAoptions⟯ allows you to ⟮set a bunch of options⟯ ⟮of koma script classes⟯ 
variant of ⟮article class⟯ ⟮(c:18;KOMA-script⟯): ⟮scrartcl⟯ 

class for ⟮letters⟯ ⟮(c:19;KOMA-script⟯):⟮scrlttr2⟯ 
changing the scrlttr2 template can be can be done the option [] to \documentclass{scrlttr2} 
⟮Setting variables⟯ for ⟮koma script templates⟯ (but seemingly actually only used for ⟮scrlttr2⟯): ⟮setkomavar⟯{{c26::{key}{val} }} 
⟮Set the date of a scrlttr2 letter to today⟯: {{c27::\setkomavar{date}{\today}}} 
⟮Set the subject of a scrlttr2 letter to Ceterum censeo carthaginem...⟯:{{c29::\setkomavar{subject}{Ceterum censeo carthaginem...}}} 
⟮.lco⟯ files are ⟮regular .tex⟯ files, but are used as ⟮scrlttr2 templates⟯ 
The ⟮actual body of a letter⟯ using ⟮scrlttr2⟯ is indicated by ⟮the letter environment⟯. It may ⟮recieve a second argument⟯ of ⟮the target address⟯ 


headerrows=2;span=2;Within the scrlttr2 letter environment
command|effect
⟮\closing{foo}⟯|⟮set the closing line (e.g. Best wishes, ) to foo⟯
⟮\opening{foo}⟯|⟮set the opening line (e.g. Dear Mrs. Soandso, ) to foo⟯
⟮\encl{foo}⟯|⟮define things that are enclosed (attachments⟯)
⟮\ps⟯|⟮define a postscript⟯



## text formatting

⟮centering⟯ is a ⟮declaration form command⟯ that ⟮centers content⟯. 
⟮center⟯ is ⟮an environment⟯ that ⟮centers content⟯. 

### text sizes

1. tiny
2. scriptsize
3. footnotesize 
4. small 
5. normalsize
6. large
7. Large
8. LARGE
9. huge
10. Huge

## compilation

⟮pdf(la)tex⟯ ⟮compiles⟯ ⟮(la)tex to pdf⟯ 
⟮\listoffigures⟯|⟮generate a list of figures⟯
⟮\listoftables⟯|⟮generate a list of `table`s⟯
⟮\tableofcontents⟯|⟮generate a table of contents⟯


Whenever ⟮latex compiles⟯ and you ⟮have used one or more of \listoffigures, \listoftables, \tableofcontents⟯, it will ⟮emit a .lot, .lof, or .toc file⟯ respectively. 
Latex constructs the ⟮.aux⟯ and ⟮.log, .lof, or .toc⟯ files by ⟮keeping account of anything that would be relevant⟯ for those ⟮while compiling⟯. 
Latex uses ⟮the .lot, .lof, or .toc files⟯ on ⟮the next run⟯ ⟮to generate the actual listoffigures, listoftables or table of contents⟯. 
The reason ⟮latex needs to compile at least twice⟯ is so ⟮it can populate the references⟯ for things like ⟮lot, lof, toc as well as various things in .aux⟯ correctly. 
The ⟮aux⟯ file keeps track of ⟮various things relevant to latex compilation⟯. 

### logging

⟮Logging⟯ is done to ⟮.log⟯ for ⟮latex itself⟯ and ⟮.blg⟯ for ⟮bibtex/biber⟯. 

### synctex

⟮Synctex⟯ is the utility that ⟮synchronizes changes between⟯ ⟮source documents and pdf output⟯

## additional functionality

### headers and footers

⟮\pagestyle{foo⟯} sets ⟮the style⟯ of ⟮your headers and footers⟯ to ⟮the format defined by foo⟯ 
for ⟮anything more fancy⟯ with ⟮headers and footers⟯ than ⟮\pagestyle⟯ can do with ⟮builtin formats⟯, you need the package ⟮fancyhdr⟯ 
⟮\pagestyle{fancy⟯} activates a ⟮sensible default⟯ ⟮fancyhdr⟯ config 
after ⟮\pagestyle{fancy}⟯ you need ⟮\fancyhf{} ⟯ to ⟮remove the elements of the default page syle⟯ 

For more ⟮advanced header/footer config⟯ using ⟮fancyhdr⟯, use ⟮\(l/c/r)head{⟯} or ⟮\(l/c/r)foot{}⟯

⟮\(l/c/r)foot{foo}⟯|⟮insert an element foo at that position in the footer⟯
⟮\(l/c/r)head{foo}⟯|⟮insert an element foo at that position in the header⟯


to style headers and footers with ⟮fancyhdr⟯ in ⟮double-sided documents (e.g. books⟯) use ⟮\fancyhead⟯ and ⟮\fancyfoot⟯ 

### ending commands

⟮c4;⟯ and ⟮\newline⟯ both ⟮generate a linebreak (/end the current line⟯) 
⟮\​⟯ but not ⟮\newline⟯ takes an ⟮option⟯ to specify how ⟮large the vertical gap to the new line⟯ should be 
⟮par⟯ ⟮generates a paragraph break (/end the current paragraph⟯) 
⟮a blank line⟯ is the construct most often used to ⟮create a paragraph break⟯. 
⟮\newpage⟯ and ⟮\clearpage⟯ both ⟮generate a new page (/end the current page⟯) 
⟮\clearpage⟯ is like ⟮\newpage⟯, but ⟮\clearpage⟯ ⟮forces floats to go on a new page⟯, while ⟮\newpage⟯ will in multicollumn mode ⟮actually just create a new column (not necessary a new page⟯) 

### pdf metadata

the package ⟮hyperref⟯ also handles ⟮metadata⟯ via ⟮the \hypersetup command⟯. 
The ⟮hypersetup⟯ command defines ⟮pdf metadata⟯ by taking ⟮keys⟯ with ⟮the syntax of pdf‹name›, e.g. pdfauthor or pdftitle⟯ 
⟮pdfbookmark⟯ is a ⟮hyperref⟯ command that ⟮inserts a pdf ToC thingy (visible e.g. in the adobe reader sidebar⟯) 
Arguments to ⟮pdfbookmark⟯⟮[section]⟯⟮{Title} ⟯⟮{uid(of some kind, no standard)} ⟯ 
⟮hypcap⟯ is a package extending ⟮hyperref⟯ {{c13::make hyperref figure links link to the correct thing} 

### page geometry

⟮layout⟯ is a package that allows you to ⟮show the setup of the page (how much spaces is being taken up by margins etc.⟯) 
⟮geometry⟯ is a package that allows you to ⟮change page layout (margins etc.⟯) 
You can use ⟮the  geometry package⟯ to ⟮change the page layout globally⟯ by using ⟮the optional argument⟯ of ⟮the \usepackage call⟯. 
You can use ⟮\newgeometry{options⟯} to ⟮change the page layout⟯ for ⟮the following pages⟯, and 
⟮\restoregeometry⟯ to ⟮reset the page layout to the original state⟯ (both package ⟮geometry⟯) 

#### lscape

using the package ⟮lscape⟯, you can use ⟮the landscape environment⟯ to make ⟮the thing go into landscape mode⟯ 
If using ⟮pdflatex⟯, you use ⟮pdflscape⟯ instead of ⟮lscape⟯. 

### images

⟮graphicx⟯ is a package that allows us to ⟮use images/graphics⟯ in ⟮latex⟯. 
You define the ⟮root directory⟯ for where ⟮graphicx⟯ should ⟮look for images⟯ with ⟮\graphicspath{\foo⟯} 
To ⟮include an actual image⟯ with ⟮graphicx⟯, use ⟮\includgraphics{path⟯}. 
⟮Changing attributes of images⟯ included w/ graphics is done in ⟮the optional argument⟯ of ⟮\includegraphics⟯ 

### hyphenation

The ⟮hyphenation⟯ command takes a ⟮list of words⟯ as an ⟮argument⟯, which will ⟮only be hyphenated⟯ in ⟮the places indicated with dashes⟯ 
⟮hyphenat⟯ is a package to ⟮en/disable autohyphenation⟯, e.g. in ⟮words that contain hyphens or in monospaced fonts⟯ 
in general, if a word ⟮contains a non-alphabetic character⟯, ⟮latex⟯ will only ever ⟮split the word on that hyphen⟯ 

Latex|Result
⟮$-$ (or other inline math env notation⟯)|⟮a mathematical minus⟯
⟮---⟯|⟮an em-dash⟯
⟮--⟯|⟮an en-dash⟯
⟮c+;⟮c1;-{}-⟯⟯|⟮--⟯
⟮-⟯|⟮a hyphen⟯


### blockquotes

the ⟮quote⟯, ⟮quotation⟯, and ⟮verse⟯ environments all ⟮indent the material, blockquote-style⟯. They ⟮differ in⟯ ⟮what they indent additionally, if anything⟯. 
⟮quotation environment⟯|⟮indents the beginning line of a paragraph additionally⟯
⟮quote environment⟯|⟮indents nothing additonally⟯
⟮verse environment⟯|⟮indents every line of a paragraph but the first one additionally⟯



### verbatim

Package ⟮verbatim⟯ contains the ⟮verbatim⟯ and ⟮comment⟯ ⟮environments⟯.
environment|function
⟮comment⟯|⟮a block comment⟯
⟮verbatim⟯|⟮the text, exactly as you have inputted it (similar to ‹pre›⟯)


### drawing (tikz)

⟮tikz⟯ is a package for ⟮creating images⟯ based on ⟮LaTeXlike commands⟯ 
⟮TikZ⟯ is short for ⟮TikZ ist kein Zeichenprogramm⟯ 
⟮TikZ⟯ has ⟮its own pacakge/library system⟯, for which you ⟮import packages/libraries⟯ via ⟮\usetikzlibrary⟯ in ⟮the preamble⟯ 
⟮tikzpicture⟯ is the ⟮environment⟯ that ⟮delimits tikz commands to draw an image⟯ 

### resizing braces

In latex, ⟮parentheses⟯ and ⟮square brackets⟯ ⟮can just be inserted⟯, ⟮curly braces⟯ ⟮must be escaped⟯. 
⟮curly braces⟯ must ⟮be escaped even⟯ if ⟮as part of \left or \right⟯ 
^e.g. `\left\{`
⟮prefixing⟯ ⟮parentheses, square brackets or (escaped) curly brackets⟯ with ⟮\left⟯ (if ⟮opening⟯) or ⟮\right⟯ (if ⟮closing⟯) will ⟮make them resize if around something larger (e.g. a fraction⟯) 
^e.g. `$$\left[\frac{foo}{bar}\right]$$`

### links (hyperref)

### including other pdfs

⟮pdfpages⟯ is a ⟮package⟯ to ⟮include other pdfs within the latex documents⟯ 
⟮pdfpages⟯ mainly features the command ⟮\includepdf⟯ which ⟮allows include a pdf document in the latex document⟯ 
⟮\includepdf⟯ allows specifying ⟮how you want to include what⟯ in ⟮its options⟯ 
⟮to control the pages that are included⟯, \includepdf⟮[pages=foo]⟯ 

### color

the ⟮packages⟯ ⟮color⟯ and ⟮xcolor⟯ allow ⟮using various color-related commands⟯. 
⟮xcolor⟯ is ⟮an extension/superset of⟯ ⟮color⟯. 


command|effect
⟮\definecolor{name}{color_space (e.g. rbg)}{values (e.g. 0.858, 0.188, 0.478)}⟯|⟮define new colors⟯
⟮\pagecolor{color}⟯|⟮colors the background of a page in the specified way⟯
⟮\textcolor{color}{text}⟯|⟮colors the text in a specific color⟯


### misc

command|Effect
⟮\noindent⟯|⟮prevent the paragraph from being indented⟯
⟮\nolinebreak / \nobreak⟯|⟮prevent latex from breaking here⟯
⟮\textwidth, \columnwith, \linewidth⟯|⟮width of the current text (different variants for different circumstances⟯)
⟮\neg‹whatever›space (\negmedspace, \negthickspace⟯)|⟮negative space (pulls things closer together⟯)


Command|does
⟮\today⟯|⟮c+;render today's date in the format ‹month› ‹day›, ‹year›
⟮\bar{foo}⟯|⟮bar above foo⟯
⟮a' or a^{\prime}⟯|⟮render an a with a prime⟯
