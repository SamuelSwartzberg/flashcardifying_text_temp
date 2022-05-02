# microtypography

## fonts and font families

A synonym of ⟮typeface⟯ is ⟮font family⟯. 
»⟮A letterform⟯« is ⟮the shape⟯ that ⟮＿a graph＿⟯ takes in ⟮a particular ＿typeface＿⟯.
A »⟮typeface⟯« is ⟮a set of⟯ ⟮＿letterforms＿⟯ ⟮with a certain unified look⟯. 
⟮a »font«⟯ is ⟮a ＿typeface＿⟯ ⟮with certain characteristcs⟯. 
Ergo, there are ⟮many ＿fonts＿⟯ of ⟮a given ＿typeface＿.⟯ 
Properties that are ⟮varied⟯ to ⟮produce different ＿fonts＿⟯ of ⟮the same ＿typeface＿⟯ are most commonly ⟮＿weight＿⟯, ⟮size⟯, and ⟮slope⟯, though ⟮other things can also be varied⟯. 

## fonts

### weight

The »⟮weight⟯« of ⟮a particular ＿font＿⟯ is ⟮the thickness of the characters⟯ ⟮relative to their height⟯. 
⟮＿font weights⟯＿ are often given on ⟮a scale⟯ ⟮from 100 through 900⟯
The ⟮TrueType⟯ font format introduced the ⟮100-900 scale⟯ for font weights
The ⟮100-900 scale⟯ for font weights is also used in ⟮CSS⟯ and ⟮OpenType⟯, 
in the 100 to 900 scale, ⟮400⟯ is ⟮regular⟯ 
in the 100 to 900 scale, ⟮700⟯ is ⟮bold⟯ 
Originally, any font-weight ⟮in the 100 - 900 scale⟯ that was ⟮not a multiple of 100⟯ was ⟮meaningless⟯
in ⟮variable-weight fonts⟯, a ⟮font weight⟯ may be ⟮any number between 1 and 1000⟯. 

### keming ＆ letter-spacing

flex-container:✫kerning-av.jpg✫✫metal-type-kerning.png✫


⟮Letter-spacing⟯ = ⟮tracking⟯
»⟮Letter-spacing/tracking⟯« and »⟮c_;kerning⟯« are both ⟮the adjustment of⟯ ⟮the horizontal distance⟯ ⟮between glyphs⟯
»⟮Letter-spacing/tracking⟯« is the ⟮adjustment of the (horizontal) distance between glyphs⟯ ⟮for all glyphs equally⟯. 
»⟮Kerning⟯« is the ⟮adjustment of the (horizontal) distance between glyphs⟯ ⟮between two specific glyphs⟯. 
⟮＿Kerning＿⟯ is generally to ⟮achieve a similar amount of whitespace⟯ between glyphs. 
Original, the »⟮kern⟯« of ⟮a glyph or its sort⟯ was ⟮the part that overhangs its sort⟯. 
⟮＿kerning＿⟯ generally involves ⟮intruding into⟯ ⟮the box of another glyph's sort⟯. 
⟮＿Kerning＿⟯ is only relevant for ⟮proportional/variable-width⟯ fonts. 

## font families

### type, sort

flex-container:✫metal-movable-type.jpg✫


⟮»A type «(countable)⟯ is ⟮a block⟯ ⟮with a glyph on it⟯ used ⟮for printing⟯.
⟮»Type« (uncountable)⟯ is ⟮types collectively⟯.
⟮A type⟯ may thus also be called ⟮a piece/block of type⟯.
In most printing processes, ⟮type⟯ was made of ⟮metal⟯.
»⟮A sort⟯« is ⟮a type⟯ for ⟮a single character with certain characteristics (weight, size, etc.)⟯.
⟮type⟯ and ⟮sort⟯ only apply to ⟮movable type⟯.

### font size

The »⟮font size⟯« specifies the ⟮＿body height＿⟯. 
Thus, if using ⟮movable type⟯, ⟮the ＿font size＿⟯ specifes ⟮the physical height of the ＿sort＿.⟯ 
Thus, if using ⟮digital type⟯, ⟮＿font size＿⟯ is ⟮the height that the ＿em square＿ is scaled to⟯. 
Stated differently, in ⟮digital type⟯, ⟮setting a specific ＿font size＿⟯ ⟮scales up the ＿em square＿⟯. 
⟮The ＿font size＿⟯ is called ⟮「point size」⟯ if ⟮specified in point⟯, or ⟮sometimes also if not⟯. 
»⟮em⟯« is a unit ⟮relative to⟯ ⟮the current ＿font size＿⟯.
Ergo, the ⟮＿font size＿⟯ is equal to ⟮1em (by definition)⟯.
Following the general definition of the font size, in css ⟮the em⟯ is ⟮equivalent to⟯ ⟮the current font-size.⟯ 

### units

#### ems and ens

flex-container:✫m-vs-em.svg✫


⟮the sort⟯ of ⟮uppercase Ms⟯ used to be ⟮as wide as tall (i.e. square)⟯,
⟮em⟯ is sometimes also defined as ⟮the width⟯ of an ⟮uppercase (or more rarely lowercase)⟯ ⟮M⟯.
Defining an em as ⟮the width of an uppercase m⟯ is ⟮equivalent to⟯ ⟮the usual definition⟯ since ⟮the sort of uppercase Ms used to be square.⟯
!The »⟮en⟯« is either
- !⟮half the width⟯ of ⟮an em⟯. 
- !⟮the width⟯ of ⟮an uppercase or lowercase⟯ ⟮n⟯. 
The »⟮en/em space/dash⟯« are ⟮a space and dash⟯ that are defined as ⟮one en/em⟯ ⟮wide⟯.
The ⟮en/em space⟯ and ⟮c_;en/em dash⟯ are ⟮one en/em⟯ ⟮wide⟯. 
Due to ⟮the confusion about definitions of en/ems⟯, sometimes ⟮variant definitions⟯ for ⟮en/em dashes/spaces⟯ are used. 

#### point

In typography, the »⟮point⟯« is ⟮the smallest⟯ ⟮unit of measure⟯. 
⟮the exact size⟯ of ⟮the ＿point＿⟯ ⟮has varied⟯.
⟮＿point＿⟯ is often abbreviated ⟮pt⟯ or ⟮c_;just p⟯. 
»⟮A pica⟯« is ⟮12 point (whatever point you're using)⟯.

##### DTP point

⟮DTP point⟯ = ⟮DeskTop Publishing point⟯.
the ⟮＿DTP point＿⟯ ⟮came into existence⟯ ⟮with digital printing⟯.
The ⟮＿DTP point＿⟯ has become a sort of ⟮standard ＿point＿⟯.
the »⟮DTP point⟯« is defined as ⟮1/72 inch⟯.
If using ⟮the ＿DTP point＿⟯, ⟮＿a pica＿⟯ is ⟮1/6 inch⟯.

##### css

⟮CSS⟯ uses ⟮the DTP⟯ ⟮＿point＿⟯.
In ⟮CSS⟯, ⟮`pt`⟯ is the unit name for ⟮＿point＿⟯.
In ⟮CSS⟯, ⟮`pc`⟯ is the unit name for ⟮＿pica＿⟯.

##### tex

⟮TeX's⟯ ⟮bp⟯ is ⟮equivalent to the DTP point⟯.
⟮TeX's⟯ ⟮pt⟯ is ⟮very slightly smaller than the DTP point⟯. 

### type anatomy

flex-container:✫type-anatomy.svg✫✫descender.png✫✫long-ascenders.jpg✫

#### body

»⟮the body height⟯« is ⟮the distance between⟯ ⟮the ＿ascender＿ and ＿descender line＿⟯. 
The ⟮＿body height＿⟯ when talking about ⟮movable type⟯ is ⟮the height of the sort⟯. 

#### baseline, mean line

The »⟮baseline⟯« is ⟮the imaginary line⟯ ⟮on which most letters sit⟯.
The »⟮mean line⟯« is ⟮the imaginary line⟯ ⟮up to which most lowercase letters extend⟯.

#### x-height

⟮x-height⟯ = ⟮corpus size⟯
The »⟮x-height⟯« is ⟮the distance between⟯ ⟮＿baseline＿ and ＿mean line＿⟯.
⟮the height of the x-height⟯ typically ⟮corresponds to the height of the x⟯, ⟮hence the name⟯. 

#### overshoot

»⟮Overshoot⟯« is when letters ⟮extend a little⟯ ⟮above or below⟯ ⟮the lines meant to constrain them⟯.
If downwards, ⟮＿overshoot＿⟯ is extending beyond the ⟮＿baseline＿⟯.
If upwards, ⟮＿overshoot＿⟯ is extending beyond the ⟮＿x-height＿ or ＿cap height＿⟯.
⟮＿Overshoot＿⟯ is used due to ⟮quirks with our perception⟯, where otherwise ⟮the non-overshot letters would look slightly too small⟯.
⟮＿Overshoot＿⟯ is generally used for ⟮round⟯ or ⟮c_;pointy⟯ leters.

#### ascenders, descenders, line spacing

A »⟮descender⟯« is ⟮the portion of a letter⟯ which ⟮extends below the ＿baseline＿⟯. 
Letters such as ⟮lowercase y, g, and j⟯ typically have ⟮＿descenders＿⟯. 
»⟮the descender depth⟯« is the ⟮distance⟯ ⟮the ＿descender＿ reaches below the ＿baseline＿⟯ 
A »⟮ascender⟯« is ⟮the portion of a letter⟯ which ⟮extends above the ＿baseline＿⟯. 
Letters such as ⟮lowercase f, h and uppercase letters (if we want to count them⟯) typically have ⟮＿ascenders＿⟯. 
The »⟮ascender height⟯« is the ⟮distance⟯ that ⟮＿ascenders＿ reach above the ＿baseline＿⟯. 
The ⟮＿ascender height＿⟯ is generally ⟮higher than⟯ ⟮the ＿cap-height＿⟯ 
⟮ascender line⟯ = ⟮topline⟯
The »⟮ascender/descender line⟯« is ⟮the imaginary line⟯ ⟮defined by⟯ ⟮the ＿ascender height/descender depth＿⟯ 
⟮Line spacing⟯ = ⟮leading⟯
»⟮Line spacing⟯« is ⟮the distance between⟯ ⟮the ＿descender line＿⟯ and ⟮the next ＿ascender line＿⟯ 

#### super/subscript

⟮＿Subscript＿ and ＿superscipt＿⟯ text is usually ⟮smaller than⟯ regular text. 
»⟮Superscript⟯« text is text whose ⟮＿baseline＿⟯ ⟮sits somewhat above⟯ ⟮c-;the general ＿baseline＿⟯. 
»⟮Subscript⟯« text may ⟮sit at the general ＿baseline＿⟯ and ⟮just be smaller⟯ or ⟮have a ＿baseline＿⟯ ⟮somewhat below⟯ ⟮c-;the general ＿baseline＿⟯.


#### em square ＆ relative sizing

flex-container:✫metal-movable-type.jpg✫


The »⟮em square⟯« is ⟮an imaginary square⟯ ⟮around which parts of letters are sized⟯.
The ⟮＿em square＿⟯ is used in ⟮digital typography⟯.
The ⟮＿em square＿⟯ is ⟮1em⟯ ⟮wide and high⟯.
Using ⟮＿the em sqare＿⟯ allows us to ⟮give the size⟯ of ⟮any other part of the font (e.g. ascender height, x-height, cap height, etc. etc.)⟯ ⟮in em⟯.
The size relationship ⟮between parts of letters⟯ ofc. depends on ⟮the typeface⟯.

##### average relative sizing

table:type property|size
⟮cap height⟯|⟮0.7em⟯
⟮x-height⟯|⟮0.5em⟯

### font properties

#### serifs

flex-container:✫serif-sans-serif.jpg✫

Serifs are these little bits sticking out of some letters.
One major axis along which font families are distinguished is if they have serifs or not.

#### monospace

A monospaced font where all characters occupy the same horizontal space.
A font that is not monospaced is proportional-width.

### installation

⟮installing custom font families⟯ is possible on ⟮most desktop os⟯, but not on ⟮android⟯ (and ofc not on ⟮ios⟯)

<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}{{c28::}}{{c29::}}{{c30::}}{{c31::}}{{c32::}}{{c33::}}{{c34::}}{{c35::}}{{c36::}}{{c37::}}{{c38::}}{{c39::}}{{c40::}}{{c41::}}{{c42::}}{{c43::}}{{c44::}}{{c45::}}{{c46::}}{{c47::}}{{c48::}}{{c49::}}{{c50::}}{{c51::}}{{c52::}}{{c53::}}{{c54::}}{{c55::}}{{c56::}}{{c57::}}{{c58::}}{{c59::}}{{c60::}}{{c61::}}{{c62::}}{{c63::}}{{c64::}}{{c65::}}{{c66::}}{{c67::}}{{c68::}}{{c69::}}{{c70::}}{{c71::}}{{c72::}}{{c73::}}{{c74::}}{{c75::}}{{c76::}}{{c77::}}{{c78::}}{{c79::}}{{c80::}}{{c81::}}{{c82::}}{{c83::}}{{c84::}}{{c85::}}{{c86::}}{{c87::}}{{c88::}}{{c89::}}{{c90::}}{{c91::}}{{c92::}}{{c93::}}{{c94::}}{{c95::}}{{c96::}}{{c97::}}{{c98::}}{{c99::}}{{c100::}}{{c101::}}{{c102::}}{{c103::}}{{c104::}}{{c105::}}{{c106::}}{{c107::}}{{c108::}}{{c109::}}{{c110::}}{{c111::}}{{c112::}}{{c113::}}{{c114::}}{{c115::}}{{c116::}}{{c117::}}{{c118::}}{{c119::}}{{c120::}}{{c121::}}{{c122::}}{{c123::}}{{c124::}}{{c125::}}{{c126::}}{{c127::}}{{c128::}}{{c129::}}{{c130::}}{{c131::}}{{c132::}}{{c133::}}{{c134::}}{{c135::}}{{c136::}}{{c137::}}{{c138::}}{{c139::}}{{c140::}}{{c141::}}{{c142::}}{{c143::}}{{c144::}}{{c145::}}{{c146::}}{{c147::}}{{c148::}}{{c149::}}{{c150::}}{{c151::}}{{c152::}}{{c153::}}{{c154::}}{{c155::}}{{c156::}}{{c157::}}{{c158::}}{{c159::}}{{c160::}}{{c161::}}{{c162::}}{{c163::}}{{c164::}}{{c165::}}{{c166::}}{{c167::}}{{c168::}}{{c169::}}{{c170::}}{{c171::}}{{c172::}}{{c173::}}{{c174::}}{{c175::}}{{c176::}}{{c177::}}{{c178::}}{{c179::}}{{c180::}}{{c181::}}{{c182::}}{{c183::}}{{c184::}}{{c185::}}{{c186::}}{{c187::}}{{c188::}}{{c189::}}{{c190::}}{{c191::}}{{c192::}}{{c193::}}{{c194::}}{{c195::}}{{c196::}}{{c197::}}{{c198::}}{{c199::}}{{c200::}}{{c201::}}{{c202::}}{{c203::}}{{c204::}}{{c205::}}{{c206::}}{{c207::}}{{c208::}}{{c209::}}{{c210::}}{{c211::}}{{c212::}}{{c213::}}{{c214::}}{{c215::}}{{c216::}}{{c217::}}{{c218::}}{{c219::}}{{c220::}}{{c221::}}{{c222::}}{{c223::}}{{c224::}}{{c225::}}{{c226::}}{{c227::}}{{c228::}}{{c229::}}{{c230::}}{{c231::}}{{c232::}}{{c233::}}{{c234::}}{{c235::}}{{c236::}}{{c237::}}{{c238::}}{{c239::}}{{c240::}}{{c241::}}{{c242::}}{{c243::}}{{c244::}}{{c245::}}{{c246::}}{{c247::}}{{c248::}}{{c249::}}{{c250::}}</span>