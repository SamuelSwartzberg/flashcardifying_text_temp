# text appearance

The text-transform CSS property specifies how to capitalize an element's text. It can be used to make text appear in all-uppercase or all-lowercase, or with each word capitalized. It also can help improve legibility for ruby.
the color keyword sets the color of the text and text decorations and accpets a ‹color› value.

word-spacing sets the additional space between words beyond the space there by default. 
word-spacing takes a ‹length-percentage›
letter-spacing takes a ‹length› to add/subtract from the usual letter-spacing/tracking.

the quotes property sets the quotes that the open-quotes and close-quotes of content will evaluate to.
the quotes property is inherited and so doesn't have to be set on the thing with the content property
quotes takes two strings, the opening and the closing quote, it may also take two more strings, which are for when there are nested.

hyphens controls the behavior of hyphens.
none|will not hyphenate, even if manually indicated via ＆shy;
manual|only at places indicated via ＆shy;
auto|language-dependent auto-hyphenation (may not work depending on platform or language)

text-indent takes a ‹length-percentage› which specifies how much to indent the first line box.
tab-size accepts a ‹length› to specify the width of the tab character, or an ‹integer› to specify its width in multiples of the space character

text-align aligns elements within line boxes along the inline base direction.
vertical-align algins elements within line boxes along the block flow direction.
vertical-align is relative to the line box for some properties, and to the font for others.


###### font

font-family sets the font family = typeface of the text.
font-family takes a font stack.
A font stack comma-separated list of font family names or generic family names, which repesents a priority of which ones to use.
generic family names are names like serif, sans-serif, monospace, cursive...
generic family names are guaranteed to resolve to an existing font family, and thus a font stack should generallly end in one.
It is good pracktice to quote font family names that contain whitespace, digits or punctuation characters.

The font shorthand allows setting properties starting with font-, as well as line-height.1

font-variant is a shorthand property for a few low-level font features, which all start with font-variant-
font-variant-caps: small-caps/petite-caps forces small caps/petite caps for non-capital letters, font-variant-caps: all-small-caps/all-petite-caps forces small caps for any letters, capital or not.

It may seem that certain html form elements can't have their font styled ⟮because by default, these elements don't inherit font properties⟯