# citations

## software

### reference management software

reference/citation/bibliographic management software is software that manages citation information


table:name|license|distingishing characteristic
JabRef|FOSS|often used for LaTeX
Citavi|Proprietary|only really used in germany
Zotero|FOSS|most common

### libraries

citations.js|node

## CSL

CSL|Citation Style Language 
CSL is a standard for describing citations.
CSL has XML, JSON, YAML realizations.
The CSL-processor is citeproc.
citation-js is a npm module and CLI for citation magic using various different formats.

## BibTeX

BibTeX is the format (La)TeX uses to describe citation information.
bibtex-entry ::= @‹type›\{‹unique-key›, ‹list-of-props›\}
list-of-props ::= ‹key› = ‹value›{, ‹key› = ‹value›}
type ::= book|article|...