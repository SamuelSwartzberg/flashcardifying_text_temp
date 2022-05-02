# macrotypography

## columns

A »⟮column⟯« is ⟮(a) vertical block(s) of content⟯ ⟮positioned on a page⟯.
⟮＿Columnns＿⟯ and ⟮c_;rows⟯ are ⟮separated by⟯ ⟮＿gutters＿⟯.
»⟮Gutters⟯« are ⟮whitespace⟯ ⟮between⟯ ⟮two rows or columns⟯.

## page

### page layout

#### spacing

##### margins

flex-container:✫margin-example.png✫


the ⟮margin⟯ is ⟮the area between⟯ ⟮the main content of a page⟯ and ⟮its edges⟯.

##### alignment ＆ indentation

flex-container:✫rags.png✫


»⟮x-aligned⟯« text is where ⟮a line⟯ w⟮ill always start⟯ at ⟮the x side (or at a certain offset)⟯
»⟮A rag⟯« is an ⟮uneven⟯ ⟮margin⟯.
⟮＿x-aligned＿⟯ text will have ⟮＿rags＿⟯ on ＿the opposite side＿.
Text being »⟮flush (with) x⟯« is when the text ⟮touches the x side⟯.
»⟮Indentation⟯« is ⟮empty space⟯ at ⟮the beginning of the line⟯ so ⟮it is no longer flush⟯
»⟮A hanging indent⟯« is one way in which a paragraph might be ⟮x-aligned⟯ but not ⟮completely flush x⟯.
Using a ⟮＿hanging indent＿⟯, ⟮the first line⟯ is ⟮flush x⟯ and ⟮c-;subsequented lines⟯ are ⟮indented⟯.
Using a ⟮＿hanging indent＿⟯ is also called »⟮flush and hang style⟯«.

»⟮Justified⟯« text is ⟮both⟯ ⟮flush left⟯ ⟮c-;and⟯ ⟮right⟯.
⟮＿Justified＿⟯ text manages to be ⟮both flush left and right⟯ by ⟮squishing and stretching letter-spacing⟯.

##### rivers

»⟮rivers⟯« are ⟮gaps of white space⟯ ⟮running across multiple lines⟯.
⟮rivers⟯ may happen due to e.g. ⟮＿justification＿⟯.

### things that may be placed on pages

#### notes

»⟮A note proper⟯« is ⟮a string⟯ placed ⟮in a different place⟯ ⟮than the place it semantically belongs to⟯.
⟮＿notes proper＿⟯ most commonly include ⟮citation information⟯ or ⟮comments of some kind⟯
⟮＿Notes proper＿⟯ are generally ⟮gathered⟯ ⟮in a section just for them⟯.
I will call ⟮the section for notes proper⟯ a »⟮note section⟯«.
A »⟮note indicator⟯« (my term) is ⟮a string⟯ or ⟮c_;symbol⟯.
The string/symbol making up ⟮＿a note indicator＿⟯ is most commonly a ⟮supercripted numeral⟯ with or without ⟮square brackets⟯
^e.g. ⎴n⎴ or ⎴[n]⎴.
A »⟮in-text note indicator⟯« (my term) is ⟮＿a note indicator＿⟯ placed ⟮＿in-text＿⟯.
A »⟮note-proper-attached note indicator⟯« (my term) is ⟮＿a note indicator＿⟯ ⟮attached to a note proper⟯.
A »⟮note indicator pair⟯« (my term) consists of ⟮＿a in-text note indicator＿⟯ and ⟮＿a note-proper-attached-note indicator＿⟯ ⟮using the same string/symbol⟯.
»⟮A note⟯« consists of ⟮＿the note proper＿⟯ plus ⟮＿a note indicator pair＿⟯.
The ⟮＿in-text note indicator＿⟯ goes ⟮after⟯ ⟮any punctuation mark⟯.
The ⟮＿note section＿⟯ may be placed ⟮at the end of the page⟯ or ⟮the end of the chapter/paper/whatever⟯.
If ⟮the note seciton is placed at the end of the page⟯, ⟮＿the notes＿⟯ are known as »⟮footnotes⟯«.
If ⟮the note seciton is placed at the end of the chapter/paper/whatever⟯, ⟮＿the notes＿⟯ are known as »⟮endnotes⟯«.

## multiple pages

### division

#### pagination

⟮pagination⟯ = ⟮paging⟯
»⟮pagination⟯« is ⟮dividing⟯ ⟮a given document⟯ ⟮c_-;into⟯ ⟮discrete pages⟯.

### relationships between pages

#### orphans and widows

flex-container:✫margins-widows.png✫


»⟮Widows/orphans⟯« refer to ⟮stranded things⟯ at ⟮the beginning/end of⟯ ⟮other things⟯. 

!»⟮Widows/orphans⟯« may either refer to
- !stranded ⟮words⟯ at the beginning/end of ⟮c_;paragraphs⟯
- !stranded ⟮lines⟯ at the beginning/end of ⟮c_;pages⟯. 

There is ⟮no agreement⟯ on ⟮which of widows or orphans⟯ refers to the things occurring at ⟮the beginnings or ends⟯ of other things.
that is, ⟮one persons orphan⟯ is ⟮another persons widow⟯. 

### alternating pages

#### verso and recto

»⟮verso and recto⟯« refer to ⟮the sides⟯ of ⟮a page⟯
⟮recto⟯ is ⟮the front⟯ of the page
⟮verso⟯ is ⟮the back⟯ of the page. 
⟮Recto⟯ is ⟮the front of the page⟯ since ⟮you will see it first if reading the book normally⟯
⟮verso⟯ is ⟮the back of the page⟯ since ⟮you will only see it once turning the page if reading the book normally⟯. 

##### LtR pages

table:span=2;✫verso-recto.svg✫
⟮c+;s2;verso⟯|⟮c+;s1;recto⟯

##### RtL pages

table:span=2;✫recto-verso.svg✫
⟮c+;s3;recto⟯|⟮c+;s4;verso⟯

#### left and right

Pages are »⟮left and right⟯« pages depending on whether they ⟮will appear⟯ on the ⟮left or right⟯ ⟮c_-;first⟯ when r⟮eading the book in a normal direction⟯.
In ⟮all books⟯, the ⟮first page⟯ is ⟮the cover⟯.
in ⟮LtR media⟯, the ⟮second page⟯ will be ⟮a left page⟯
Since in ⟮LtR media⟯, ⟮the second page will be a left page⟯, ⟮the cover is a right page⟯
in ⟮RtL media⟯, the ⟮second page⟯ will be ⟮a right page⟯
Since in ⟮RtL media⟯, ⟮the second page will be a right page⟯, ⟮the cover is a left page⟯

##### twosided

In a book, ⟮left and right pages⟯ are ⟮not formatted identical⟯, but instead ⟮have different e.g. margins⟯ to ⟮account for binding⟯ etc.
⟮The state of left and right pages not being identical⟯ may be called »⟮two-sided⟯«.
In latex, to ⟮optimize a document for being two-sided⟯ , include ⟮`twoside`⟯ in ⟮the optional argument [] of documentclass⟯

##### start on...

In latex, to ⟮make chapters etc. always open on a left/right page⟯  include ⟮`openleft/right`⟯ in ⟮the optional argument [] of documentclass⟯

<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}{{c28::}}{{c29::}}{{c30::}}{{c31::}}{{c32::}}{{c33::}}{{c34::}}{{c35::}}{{c36::}}{{c37::}}{{c38::}}{{c39::}}{{c40::}}{{c41::}}{{c42::}}{{c43::}}{{c44::}}{{c45::}}{{c46::}}{{c47::}}{{c48::}}{{c49::}}{{c50::}}{{c51::}}{{c52::}}{{c53::}}{{c54::}}{{c55::}}{{c56::}}{{c57::}}{{c58::}}{{c59::}}{{c60::}}{{c61::}}{{c62::}}{{c63::}}{{c64::}}{{c65::}}{{c66::}}{{c67::}}{{c68::}}{{c69::}}{{c70::}}{{c71::}}{{c72::}}{{c73::}}{{c74::}}{{c75::}}{{c76::}}{{c77::}}{{c78::}}{{c79::}}{{c80::}}{{c81::}}{{c82::}}{{c83::}}{{c84::}}{{c85::}}{{c86::}}{{c87::}}{{c88::}}{{c89::}}{{c90::}}{{c91::}}{{c92::}}{{c93::}}{{c94::}}{{c95::}}{{c96::}}{{c97::}}{{c98::}}{{c99::}}{{c100::}}{{c101::}}{{c102::}}{{c103::}}{{c104::}}{{c105::}}{{c106::}}{{c107::}}{{c108::}}{{c109::}}{{c110::}}{{c111::}}{{c112::}}{{c113::}}{{c114::}}{{c115::}}{{c116::}}{{c117::}}{{c118::}}{{c119::}}{{c120::}}{{c121::}}{{c122::}}{{c123::}}{{c124::}}{{c125::}}{{c126::}}{{c127::}}{{c128::}}{{c129::}}{{c130::}}{{c131::}}{{c132::}}{{c133::}}{{c134::}}{{c135::}}{{c136::}}{{c137::}}{{c138::}}{{c139::}}{{c140::}}{{c141::}}{{c142::}}{{c143::}}{{c144::}}{{c145::}}{{c146::}}{{c147::}}{{c148::}}{{c149::}}{{c150::}}{{c151::}}{{c152::}}{{c153::}}{{c154::}}{{c155::}}{{c156::}}</span>