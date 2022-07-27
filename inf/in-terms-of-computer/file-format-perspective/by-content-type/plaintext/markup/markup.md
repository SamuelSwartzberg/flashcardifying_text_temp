##### markup

Markup files are subset of plaintext files.
Markup files are written in markup languages.
markup languages consist of normal text and specific markup, which are intermingled.

###### across languages

bold (no importance impl)|\textbf{} (though there are others)|‹b›|**text** or __text__
italic (no importance impl)|\textit{}|‹i›|*text* or _text_
emphasize (generally via italics)|\emph{}|‹em›|N/A
strongly emphasize||‹strong›|N/A
underline|\underline{}|‹u›|N/A
strikethrough foo (whithout special semantics)|different ones in packages|‹s›foo‹s›|~foo~ or ~~foo~~ (most md flavors)
hyperlink link with title title|\href{link}{title}|‹a href="link"›title‹/a›|[title](link)
hyperlink link with title link|\url{}|‹a href="link"›link‹/a›|[link](link)
block quotation of foo|quote, quotation, or verse environment|‹blockquote›‹/blockquote›|`›foo` or `› foo` (space after › is optional)
Inline quotation of foo|\enqote{foo} (package csquotes)|‹q›foo‹/q›
inline source code||‹code›|``
create a newline|\\ or \newline|‹br›| two spaces or \‹newline character›
Heading (level one) "foo"|relevant section command|‹h1›foo‹/h1›|# foo or foo\n===(number doesn't matter)
Heading (level two) "foo"|relevant section command|‹h2›foo‹/h2›|# foo or foo\n---(number doesn't matter
Heading (level three) "foo"|relevant section command|‹h3›foo‹/h3›|## foo 
Heading (level six) "foo"|relevant section command|‹h6›foo‹/h6›|##### foo 
A code block foo||‹pre›‹code›foo‹/code›‹/pre›| originally a block indented by four spaces and separated by newlines, but most flavors now have fenced code blocks, which are done like ``` or ~~~(or more)\nfoo\n``` or ~~~
a paragraph foo|\par{foo}|‹p›foo‹\p›|\n\npar\n\n (uses blank lines)
image with url/source Asuka and alt text best girl|\includegrapics{Asuka} (no alt text possible)|‹img src="Asuka" alt="best girl"›|![best girl](Reina)
horizontal line|\rule (or \hrule, but both take arguments)|‹hr›| three or more *** ___ --- 
superscript text foo|^{foo}|‹sup›foo‹/sup›
subscript text foo|_{foo}|‹sub›foo‹/sub›
indicate a variable semantically||‹var›
keyboard input||‹kbd›
sample output||‹samp›
title of a cited work||『
preformatted text that is to be presented exactly as written||‹pre›

using \url{} or \href{} requires the package hyperref in Latex
package hyperref also does autolinking to things such as the TOC

strike is similar to ‹s›, but obsolete
‹tt› used to indicate teletype text, but is now obsolete
‹big› used to indicate big text, but is now obsolete; however ‹small› still works.
‹center› used to indicate centered text but is now obsolete

most text markup languages (HTML, Latex, md) will ignore duplciate spaces.
most text markup languages (HTML, Latex, md) will transform newlines into a single space unless otherwise indicated.

In fountain, in contrast to markdown, only * and ** do italic/bold, _ is reaserved for underlined


i|italic|conventionally italic
em|italic|more important
b|bold|conventionally bold
strong|bold|super important
u|underline|has non-textual annotation of some kind
mark|yellow highlighter|highlighted ≈ area of interest
 

non-breaking space|\nonbreakspace or ~|＆nbsp;
ampersand||＆amp;
non-breaking hyphen|"~
soft hyphen|\- (only hyphtenates in indicated location) "- (allows hyphenation in other places in the word)|＆shy;＆#8203;
"=
if you want a word ⟮with a hyphen⟯ to be ⟮able to be split anywhere⟯ (using babel ngerman), use ⟮"=⟯
zero-width space||‹wbr› or ＆#8203;

hyperref|create links automatically and \href, \url commands


nested blockquotes| `››` or `› › `(space after › to begin blockquotes is optional)

Pandoc md is a superset of most other markdown flavors
Pandoc md defaults to tilde-delimited code blocks.
In pandoc md, you can specify heading identifiers to contain things such as classes, ids, etc
pandoc-md-heading ::= #{#} ‹title› [\{{‹class›|‹id›|...}\}]


RTF|Rich Text Format