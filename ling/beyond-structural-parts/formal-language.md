# formal language

## formal languages

»⟮A formal language⟯« is a set of ⟮＿well-formed words＿⟯.
»⟮A well-formed word⟯« is ⟮＿a word＿⟯ that ⟮conforms to⟯ ⟮＿the syntax＿⟯ of ⟮＿the formal language＿⟯ ⟮of which it is a part⟯.
»⟮The syntax⟯« of ⟮＿a formal language＿⟯ is ⟮the structure⟯ of ⟮＿well-formed words＿⟯.
»⟮A word⟯« is ⟮any concatenation of tokens⟯ from ⟮＿the alphabet＿⟯ of ⟮a given ＿formal language＿⟯.
»⟮The alphabet⟯« of ⟮＿a formal language＿⟯ is ⟮a set of tokens⟯.
⟮＿The alphabet＿⟯ is indicated with ⟮Σ⟯.
⟮The syntax of a formal language⟯ is often defined by ⟮a formal grammar⟯.
»⟮A formal grammar⟯« is ⟮an algorithm for⟯ creating ⟮＿well-formed words＿⟯.

### finite and infinite

⟮＿Formal languages＿⟯ are separated by size into ⟮＿finite＿⟯ and ⟮c_;＿inifinte＿⟯ languages.
To define a ⟮＿finite formal language＿⟯, besides specifying its syntax we could ⟮just list ＿all well-formed words＿⟯.

### formal grammar

A ⟮‹whatever› grammar⟯ defines the syntax for a ⟮‹whatever› language⟯.

#### production rules

⟮＿A formal grammar＿⟯ consists of ⟮n ＿production rules＿⟯.
»⟮A production rule⟯« consists of ⟮a left-hand⟯ and ⟮c_;right-hand side⟯.

#### derivation

»⟮A derivation⟯« is ⟮an application⟯ of ⟮＿the production rules＿⟯ of ⟮＿a formal grammar＿⟯ to ⟮arrive at a ＿well-formed word＿⟯.
»⟮The start symbol⟯« is ⟮＿the nonterminal＿⟯ we ⟮start derivation from⟯.
⟮＿The start symbol＿⟯ is indicated with ⟮S⟯.
⟮＿Derivation＿⟯ involves ⟮replacing all ＿nonterminals＿⟯ ⟮until there are no ＿nonterminals＿ left⟯.
⟮＿Derivation＿⟯ is ⟮finished⟯ when ⟮we've arrived at a string with no more ＿nonterminals＿⟯.
⟮Terminals/nonterminals⟯ are technically ⟮called terminal/nonterminal symbols⟯.
⟮Nonterminals⟯ are also called ⟮syntactic variables⟯.
»⟮Nonterminals⟯« are elements that ⟮are to be replaced⟯ ⟮with the right-hand side of further ＿production rules＿⟯.
»⟮Terminals⟯« are ⟮elements from ＿the alphabet＿⟯.
⟮＿Terminals＿⟯ are written in ⟮lowercase letters⟯, ⟮c-;＿nonterminals＿⟯ are written in ⟮uppercase letters⟯.
The ⟮empty word⟯ is indicated ⟮e⟯ or ⟮c_;ε⟯.

## types of formal languages

### chomsky hierarchy

⟮＿The chomsky hierarchy＿⟯ describes a hierarchy of ⟮＿formal grammars＿⟯.


onion-box:
⟮recursively enumerable⟯
  ⟮context-sensitive⟯
    ⟮context-free⟯
      ⟮regular⟯

### regular

In the production rules of ⟮context-free⟯ and ⟮＿regular grammars＿⟯, ⟮＿the left side＿⟯ ⟮may only contain a single non-terminal⟯.
Regular grammars may be ⟮＿right-regular＿⟯ or ⟮＿left-regular＿⟯.
⟮＿Right sides＿⟯ of ⟮＿production rules＿⟯ in ⟮＿regular grammars＿⟯ may contain ⟮a single ＿terminal⟯＿, or may contain ⟮nonterminal terminal/terminal nonterminal⟯ (»⟮right/left-regular⟯«).

## metalanguage

»⟮A metalanguage⟯« is ⟮a language⟯ used ⟮to describe another language⟯
⟮＿An object language＿⟯ is ⟮the language being described by⟯ ⟮a metalanguage⟯
»⟮Metasyntax⟯« is ⟮＿the syntax＿⟯ governing ⟮＿a meta-language＿⟯.

### metasyntactic variable

A metasyntactic variable is a placeholder that is not part of a given language, but instead used in a metalanguage way.
The most common metasyntactic variables are foo, bar, quuz...

### BNF

⟮BNF⟯ = ⟮Backus-Naur-Form⟯
»⟮BNF⟯« is ⟮＿a metasyntax＿⟯ for ⟮c_;＿a metalanguage＿⟯ whose ⟮＿object languages＿⟯ are ⟮＿context-free languages＿⟯.


table:metacharacter/construct|BNF meaning
⟮definition(right/lefthand separator)⟯|⟮::=⟯
⟮alternation/or⟯|⟮｜⟯
⟮terminal⟯ (in this case with the name something)|⟮"something"⟯ or ⟮c_;'something'⟯
⟮non-terminal⟯ (in this case with the name something)|⟮‹something›⟯
⟮concatenation⟯|⟮␣⟯

#### EBNF

⟮EBNF⟯ = ⟮Extended Backus-Naur-Form⟯
»⟮EBNF⟯« is ⟮an extension⟯ (with ⟮some changes⟯) to ⟮＿BNF＿⟯
there is ⟮no one⟯ EBNF, ⟮but a bunch of dialects⟯.

##### Possible ENBF syntax conventions

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

#### ABNF

»⟮ABNF⟯« is ⟮＿a metasyntax＿⟯ based on ⟮＿BNF＿⟯, but ⟮with significant differences⟯.
⟮＿ABNF＿⟯ is standartized in ⟮an RFC⟯.
⟮＿ABNF＿⟯ is often used for ⟮IETF documents⟯.

##### grammar

in ⟮＿ABNF＿⟯, ⟮＿nonterminals＿⟯ ⟮MAY be⟯ ⟮surrounded by ‹›⟯.
in ⟮＿ABNF＿⟯, ⟮＿nonterminals＿ and ＿terminals＿⟯ are case-⟮insensitve⟯
abnf-rule ::= ⟮‹nonterminal› = ⟯⟮‹definition› ⟯⟮[; ‹comment›]⟯⟮‹CRLF›⟯

###### terminals

```
!abnf-terminal ::= ⟮"{‹characters›}"⟯|⟮‹abnf-terminal-range›⟯|⟮‹abnf-terminal-numeric›⟯
!⟮abnf-terminal-range⟯ ::= ⟮‹abnf-base-specifier›⟯⟮‹abnf-character-digits›-‹abnf-character-digits›⟯
!⟮abnf-terminal-numeric⟯ ::= ⟮‹abnf-base-specifier›⟯⟮‹abnf-character-digits›⟯⟮{.‹abnf-character-digits›}⟯ ⟮h∞;# for a list of numbers (yes, dot-separated)⟯
!⟮abnf-character-digits⟯ ::= ⟮‹digit›{‹digit›}⟯
!⟮abnf-base-specifier⟯ ::= ⟮%‹base-char›⟯
!⟮base-char⟯ ::= ⟮b|d|x⟯
```

###### constructs

table:construct|meaning
⟮‹n›*‹m›‹thing›⟯|⟮repetitions from n to m⟯
⟮‹n›‹thing›⟯|⟮repetitions of n times⟯
⟮()⟯|⟮group⟯
⟮/⟯|⟮alternation⟯
⟮=/⟯|⟮add alternatives to previous rule⟯
⟮whitespace⟯|⟮concatenation⟯
⟮[]⟯|⟮optional⟯


for ABNF ⟮repetition⟯, ⟮leaving out ‹n› or ‹m›⟯ ⟮implies 0 or infinity⟯ as per usual

##### predefined rules

⟮LWSP⟯ = 	⟮*(WSP / CRLF WSP)⟯
⟮WSP⟯ = ⟮SP / HTAB	⟯
⟮DIGIT⟯ = ⟮a digit 0 - 9⟯
⟮CRLF⟯ = ⟮CR LF⟯
⟮ALPHA⟯ = ⟮upper/lowercase ascii letter⟯
⟮VCHAR⟯ = ⟮an ascii visible char⟯

<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}{{c28::}}{{c29::}}{{c30::}}{{c31::}}{{c32::}}{{c33::}}{{c34::}}{{c35::}}{{c36::}}{{c37::}}{{c38::}}{{c39::}}{{c40::}}{{c41::}}{{c42::}}{{c43::}}{{c44::}}{{c45::}}{{c46::}}{{c47::}}{{c48::}}{{c49::}}{{c50::}}{{c51::}}{{c52::}}{{c53::}}{{c54::}}{{c55::}}{{c56::}}{{c57::}}{{c58::}}{{c59::}}{{c60::}}{{c61::}}{{c62::}}{{c63::}}{{c64::}}{{c65::}}{{c66::}}{{c67::}}{{c68::}}{{c69::}}{{c70::}}{{c71::}}{{c72::}}{{c73::}}{{c74::}}{{c75::}}{{c76::}}{{c77::}}{{c78::}}{{c79::}}{{c80::}}{{c81::}}{{c82::}}{{c83::}}{{c84::}}{{c85::}}{{c86::}}{{c87::}}{{c88::}}{{c89::}}{{c90::}}{{c91::}}{{c92::}}{{c93::}}{{c94::}}{{c95::}}{{c96::}}{{c97::}}{{c98::}}{{c99::}}{{c100::}}{{c101::}}{{c102::}}{{c103::}}{{c104::}}{{c105::}}{{c106::}}{{c107::}}{{c108::}}{{c109::}}{{c110::}}{{c111::}}{{c112::}}{{c113::}}{{c114::}}{{c115::}}{{c116::}}{{c117::}}{{c118::}}{{c119::}}{{c120::}}{{c121::}}{{c122::}}{{c123::}}{{c124::}}{{c125::}}{{c126::}}{{c127::}}{{c128::}}{{c129::}}{{c130::}}{{c131::}}{{c132::}}{{c133::}}{{c134::}}{{c135::}}{{c136::}}{{c137::}}{{c138::}}{{c139::}}{{c140::}}{{c141::}}{{c142::}}{{c143::}}{{c144::}}{{c145::}}{{c146::}}{{c147::}}{{c148::}}{{c149::}}{{c150::}}{{c151::}}{{c152::}}{{c153::}}{{c154::}}{{c155::}}{{c156::}}{{c157::}}{{c158::}}{{c159::}}{{c160::}}{{c161::}}{{c162::}}{{c163::}}{{c164::}}{{c165::}}{{c166::}}{{c167::}}{{c168::}}{{c169::}}{{c170::}}{{c171::}}{{c172::}}{{c173::}}{{c174::}}{{c175::}}{{c176::}}{{c177::}}{{c178::}}{{c179::}}{{c180::}}{{c181::}}{{c182::}}{{c183::}}{{c184::}}{{c185::}}{{c186::}}{{c187::}}{{c188::}}{{c189::}}{{c190::}}{{c191::}}{{c192::}}{{c193::}}{{c194::}}{{c195::}}{{c196::}}{{c197::}}{{c198::}}{{c199::}}{{c200::}}{{c201::}}{{c202::}}{{c203::}}{{c204::}}{{c205::}}{{c206::}}{{c207::}}{{c208::}}{{c209::}}{{c210::}}</span>