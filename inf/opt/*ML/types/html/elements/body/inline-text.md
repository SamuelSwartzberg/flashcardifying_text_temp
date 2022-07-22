# inline text

## abbr

The abbr HTML element represents an acronym or abbreviation.
There used to be an ‹acronym› element which was obsoleted in favor of ‹abbr›
The thing an abbr element is short for may either be explained in the text or specified in a `title` attribute.

## dfn

‹dfn› represents defining instance of a term.
the definition of a term defined by an ‹dfn› is the ancestor closest that is a ‹p›, ‹dt›/‹dd› pairing, or ‹section›.
The term ‹dfn› is defining is the value of the `title` attribute if it has one, or its text content otherwise.
If ‹dfn› has a `title`, its contents may be something else then the name of the term, e.g. an abbr or alternative term.

## del and ins 

The ‹del› HTML element represents text that has been deleted from a document.
The ‹ins› HTML element represents text that has been added to the document.
The ‹del› and ‹ins› elements are often used for purposes such as tracking changes or source code diffs.

## ruby 

ruby text/characters are small annotative glosses placed on the top or to the right of characters.
Ruby text/characters is called furigana in japanese.
In HTML, ruby text is delimited by the ‹ruby› tag
In HTML ruby annotation, the syntax is ‹ruby›lowertext‹rt›uppertext‹/rt›‹/ruby›
In HTML, one may designate fallback delimiters for the upper text. 
Ruby fallback delimiters are enclosed in ‹rp› tags, and go before and after the ‹rt› delimited uppertext.