# metalanguage

»⟮A metalanguage⟯« is ⟮a language⟯ used ⟮to describe another language⟯
⟮＿An object language＿⟯ is ⟮the language being described by⟯ ⟮a metalanguage⟯
»⟮Metasyntax⟯« is ⟮＿the syntax＿⟯ governing ⟮＿a meta-language＿⟯.

## metasyntactic variable

A metasyntactic variable is a placeholder that is not part of a given language, but instead used in a metalanguage way.
The most common metasyntactic variables are foo, bar, quuz...

## BNF

⟮BNF⟯ = ⟮Backus-Naur-Form⟯
»⟮BNF⟯« is ⟮＿a metasyntax＿⟯ for ⟮c_;＿a metalanguage＿⟯ whose ⟮＿object languages＿⟯ are ⟮＿context-free languages＿⟯.


table:metacharacter/construct|BNF meaning
⟮definition(right/lefthand separator)⟯|⟮::=⟯
⟮alternation/or⟯|⟮｜⟯
⟮terminal⟯ (in this case with the name something)|⟮"something"⟯ or ⟮c_;'something'⟯
⟮non-terminal⟯ (in this case with the name something)|⟮‹something›⟯
⟮concatenation⟯|⟮␣⟯

### EBNF

⟮EBNF⟯ = ⟮Extended Backus-Naur-Form⟯
»⟮EBNF⟯« is ⟮an extension⟯ (with ⟮some changes⟯) to ⟮＿BNF＿⟯
there is ⟮no one⟯ EBNF, ⟮but a bunch of dialects⟯.

#### Possible ENBF syntax conventions

table:construct|meaning
⟮[]⟯|optional
⟮{}⟯|0 or more repetions
⟮bar⟯|alternation
⟮c+;s∞;us+3:=⟯ or ⟮c+;s∞;us+2::⟯ or ⟮c+;s∞;us+1:::=⟯|⟮definition⟯
⟮;⟯ or ⟮ø⟯|⟮end of production rule⟯
⟮()⟯|⟮grouping⟯
⟮␣⟯ or ⟮,⟯ or ⟮ø⟯|⟮concatenation⟯
⟮｜｜⟯|⟮'at least one of'⟯

!In ⟮＿ENBF＿⟯ ⟮dialects⟯, usually either 
- !⟮＿the terminals＿⟯ are ⟮quoted⟯ and ⟮c-;＿the nonterminals＿⟯ are ⟮written as is⟯
- !⟮c-;＿the terminals＿⟯ are ⟮unquoted⟯ and ⟮c-;＿the nonterminals＿⟯ are ⟮indicated as ‹something›⟯
- !both ⟮c-;＿terminals＿⟯ and ⟮c_;＿nonterminals＿⟯ are ⟮explicitly indicated⟯

### ABNF

»⟮ABNF⟯« is ⟮＿a metasyntax＿⟯ based on ⟮＿BNF＿⟯, but ⟮with significant differences⟯.
⟮＿ABNF＿⟯ is standartized in ⟮an RFC⟯.
⟮＿ABNF＿⟯ is often used for ⟮IETF documents⟯.

#### grammar

in ⟮＿ABNF＿⟯, ⟮＿nonterminals＿⟯ ⟮MAY be⟯ ⟮surrounded by ‹›⟯.
in ⟮＿ABNF＿⟯, ⟮＿nonterminals＿ and ＿terminals＿⟯ are case-⟮insensitve⟯
abnf-rule ::= ⟮‹nonterminal› = ⟯⟮‹definition› ⟯⟮[; ‹comment›]⟯⟮‹CRLF›⟯

##### terminals

```
!abnf-terminal ::= ⟮"{‹characters›}"⟯|⟮‹abnf-terminal-range›⟯|⟮‹abnf-terminal-numeric›⟯
!⟮abnf-terminal-range⟯ ::= ⟮‹abnf-base-specifier›⟯⟮‹abnf-character-digits›-‹abnf-character-digits›⟯
!⟮abnf-terminal-numeric⟯ ::= ⟮‹abnf-base-specifier›⟯⟮‹abnf-character-digits›⟯⟮{.‹abnf-character-digits›}⟯ ⟮h∞;# for a list of numbers (yes, dot-separated)⟯
!⟮abnf-character-digits⟯ ::= ⟮‹digit›{‹digit›}⟯
!⟮abnf-base-specifier⟯ ::= ⟮%‹base-char›⟯
!⟮base-char⟯ ::= ⟮b|d|x⟯
```

##### constructs

table:construct|meaning
⟮‹n›*‹m›‹thing›⟯|⟮repetitions from n to m⟯
⟮‹n›‹thing›⟯|⟮repetitions of n times⟯
⟮()⟯|⟮group⟯
⟮/⟯|⟮alternation⟯
⟮=/⟯|⟮add alternatives to previous rule⟯
⟮whitespace⟯|⟮concatenation⟯
⟮[]⟯|⟮optional⟯


for ABNF ⟮repetition⟯, ⟮leaving out ‹n› or ‹m›⟯ ⟮implies 0 or infinity⟯ as per usual

#### predefined rules

⟮LWSP⟯ = 	⟮*(WSP / CRLF WSP)⟯
⟮WSP⟯ = ⟮SP / HTAB	⟯
⟮DIGIT⟯ = ⟮a digit 0 - 9⟯
⟮CRLF⟯ = ⟮CR LF⟯
⟮ALPHA⟯ = ⟮upper/lowercase ascii letter⟯
⟮VCHAR⟯ = ⟮an ascii visible char⟯