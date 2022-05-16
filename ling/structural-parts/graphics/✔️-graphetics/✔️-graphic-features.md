# graphic features

## basics

### typeface & fonts

»⟮c1;A fully-specified character⟯« (my term) is ⟮a character⟯ with ⟮＿values＿ for all ＿graphic features＿⟯.

#### typeface

⟮c4;typeface⟯ =syn= ⟮font family⟯. 
»⟮c6;A typeface letterform⟯« (my term) is ⟮an alternant of ＿a glyph＿⟯ with ⟮certain ＿typeface features＿⟯.
»⟮c9;A typeface feature⟯« is ⟮＿a graphic feature＿⟯ where varying it ⟮changes ＿the typeface letterform＿⟯ and thus ⟮c_;＿the typeface＿⟯.
»⟮c12;A typeface⟯« is ⟮an instantiation⟯ of ⟮c_;a glyph set⟯ with ⟮certain ＿typeface features＿⟯.
Alternatively, »⟮c15;a typeface⟯« is ⟮a set of ＿typeface letterforms＿⟯ with ⟮the same ＿typeface features＿⟯.

#### fonts

»⟮c18;A font letterform⟯« (my term) is ⟮an alternant of ＿a typeface letterform＿⟯ with ⟮certain ＿font features＿⟯.
»⟮c21;A font feature⟯« is ⟮＿a graphic feature＿⟯ where varying it ⟮changes the ＿font letterform＿⟯ and thus ⟮c_;＿the font＿⟯.
»⟮c24;A font⟯« is ⟮an instantiation⟯ of ⟮c_;＿a typeface＿⟯ with ⟮certain ＿font features＿⟯.
Alternatively, »⟮c27;a font⟯« is ⟮a set of ＿font letterforms＿⟯ with ⟮the same ＿font features＿ and ＿typeface features＿⟯.
⟮c30;＿font features＿⟯ = {⟮＿font weight＿⟯, ⟮＿font size＿⟯, ⟮＿slope＿⟯}

### type, sort

flex-container:✫metal-movable-type.jpg✫

⟮c34;type⟯ =syn= ⟮sort⟯
»⟮c36;A type⎵countable⎵/sort⟯« is ⟮a block⟯ ⟮with ＿a fully-specified character＿ on it⟯.
»⟮c39;A type block⟯« is ⟮the block⟯ of ⟮＿a type⎵countable⎵/sort＿⟯.
»⟮c42;A type/sort type⟯« is ⟮a set of ＿graphic features＿⟯ that ⟮produce ＿a type＿⟯.
»⟮c45;Type⎵uncountable⎵⟯« is ⟮types collectively⟯.

## distinctive graphic features

### letter case

»⟮c47;Letter case⟯« is ⟮＿the graphic fcategory＿⟯ distinguishing glyphs by ⟮chunkyness:⟯
Typical values for ⟮c50;＿letter case＿⟯ in a 2-cameral system = ⟮uppercase⟯, ⟮c_;lowercase⟯
⟮c52;uppercase grapheme⟯ =syn= ⟮captial letter⟯ =syn= ⟮majuscle⟯ 
⟮c55;lowercase grapheme⟯ =syn= ⟮minuscle⟯  

### descenders/ascenders

flex-container:✫descender.png✫✫long-ascenders.jpg✫


»⟮c57;A descender/ascender⟯« is ⟮the portion of a letter⟯ which ⟮extends below ＿the baseline＿⟯/⟮above ＿the mean line＿⟯. 
»⟮c61;The ascender/descender line⟯« is ⟮the line⟯ which ⟮＿ascenders/descenders＿ extend to⟯.

### super/subscript

»⟮c64;s*script⎵wide⎵⟯« is character(s) whose ⟮＿baseline＿⟯ ⟮is not the same as⟯ ⟮c_-;the general ＿baseline＿⟯
»⟮c67;s*script⎵narrow⎵⟯« is ⟮＿s*script⎵wide⎵＿⟯ where ⟮the characters are smaller than regular text⟯.
⟮c70;＿s*script＿⟯ may be ⟮＿subscript＿⟯ or ⟮c_;＿superscript＿⟯.
»⟮c72;subscript⟯« is ⟮＿s*script＿⟯ where ⟮their ＿baseline＿ is lower⟯.
»⟮c75;superscript⟯« is ⟮＿s*script＿⟯ where ⟮their ＿baseline＿ is higher⟯.


## font features

### weight

»⟮c78;font weight⟯« is a ⟮＿sm graphic fcategory → font fcategory＿⟯ specifying ⟮the relative thickness of the characters⟯.

#### 1k weight scale

»⟮c81;The 1k weight scale⟯« (my term) is the scale specifying values for ⟮the ＿graphic fcategory＿ ＿font weight＿⟯ in ⟮values between 1-1000⟯.
⟮c84;＿The 1k weight scale＿⟯ may be ⟮＿the fixed-weight scale＿⟯ or ⟮c_;＿the variable-weight scale＿⟯.

##### fixed-weight scale

»⟮c86;The fixed-weight scale⟯« is ⟮＿the 1k weight scale＿⟯ that allows values ⟮from 100 to 900⟯ in steps of ⟮c_;50 or 100⟯.

##### variable-weight scale

»⟮c89;the variable-weight scale⟯« is ⟮＿the 1k weight scale＿⟯ that allows values ⟮from 1 to 1000⟯ in steps of ⟮c_;1⟯.

#### keyword values

»⟮c92;The weight keywords⟯« are ⟮a set of keywords⟯ that are used as ⟮＿fvalues＿⟯ for ⟮c_;＿the graphic fcategory＿ ＿font weight＿⟯.

##### correspondence with weight scale

table:1k weight scale|keyword values
⟮c95;100⟯|»⟮thin/hairline⟯«
⟮c97;200⟯|»⟮ultra/extra light⟯«
⟮c99;300⟯|»⟮light⟯«
⟮c101;400⟯|»⟮regular⟯«
⟮c103;500⟯|»⟮medium⟯«
⟮c105;600⟯|»⟮semi/demi bold⟯«
⟮c107;700⟯|»⟮bold⟯«
⟮c109;800⟯|»⟮ultra/extra bold⟯«
⟮c111;900⟯|»⟮black⟯«

### intraletter whitespace distance

flex-container:✫kerning-av.jpg✫✫metal-type-kerning.png✫


»⟮c113;Intraletter whitespace distance⟯« (my term) is ⟮＿a sm/ssm graphic fcategory＿⟯ specifying ⟮the horizontal distance⟯ ⟮between ＿glyphs＿⟯.
»⟮c117;A intraletter whitespace distance adjustment⟯« is ⟮an adjustment of ＿intraletter whitespace distance＿⟯.

#### letter-spacing

»⟮c119;Letter-spacing⟯« is ⟮＿an intraletter whitespace distance adjustment＿⟯ ⟮equally between⟯ ⟮all ＿glyphs＿ in a ＿glyph＿ sequence⟯.
⟮c123;Letter-spacing⟯ =syn= ⟮tracking⟯

#### kerning

»⟮c125;Kerning⎵general⎵⟯« is ⟮＿an intraletter whitespace distance adjustment＿⟯ ⟮between certain glyphs (only in a proportional/variable width typeface)⟯.
»⟮c128;Kerning⎵mechanical typography⎵⟯« is ⟮intruding into⟯ ⟮＿the type block＿ another glyph's ＿sort＿⟯. 
»⟮c131;A kern⎵mechanical typography⎵⟯« is ⟮the part of ＿a sort＿ that overhangs its ＿type block＿⟯. 
»⟮c133;Default/standard kerning⟯« (my term w/ some internet support) is ⟮＿the kerning＿⟯ that is ⟮applied in almost ＿all typefaces＿ in existence⟯ to ⟮ensure nice visual distance⟯.

#### monospace

»⟮c137;Monospacing⟯« is ⟮each character⟯ ⟮occupying the same horizontal space⟯.
⟮c140;＿A typeface＿⟯ may either be ⟮＿monospaced＿⟯ or ⟮c_;＿proportional-width＿⟯.

### font size

The »⟮c142;font size⟯« specifies the ⟮＿body height＿⟯. 
The ⟮c144;＿body height＿⟯ is ⟮the height⟯ of ⟮＿the sort＿⟯ (if ⟮mechanical typography⟯) or ⟮c-;＿em square＿⟯ (if ⟮digital⟯)

#### units

##### em

###### em

»⟮c148;em⟯« is a unit that is ⟮the current ＿font size＿⟯.
Ergo, the ⟮c150;＿font size＿⟯ is equal to ⟮1em (by definition)⟯.

###### m sort

flex-container:✫m-vs-em.svg✫


⟮c152;＿the sort＿⟯ of ⟮uppercase Ms⟯ used to be ⟮as wide as tall (i.e. square)⟯,
Since the sort of uppercase M was square, the ⟮c155;em⟯ arose as ⟮the width/height of an uppercase M ＿sort＿⟯.

###### em square

flex-container:✫metal-movable-type.jpg✫


The »⟮c157;em square⟯« is ⟮an imaginary square⟯ which is ⟮1em wide and high⟯, allowing ⟮other graphic features to be sized relative to it⟯.

###### en

!The »⟮c161;en⟯« is either
- !⟮c162;half the width⟯ of ⟮an em⟯. 
- !⟮c164;the width⟯ of ⟮an uppercase or lowercase⟯ ⟮n⟯. 

###### derived thins

»⟮c167;An en/em space/dash⟯« is ⟮a space/dash⟯ that is ⟮1 en/em wide⟯

##### point

In typography, the »⟮c170;point⟯« is ⟮the smallest⟯ ⟮unit of measure⟯, though ⟮its exact size has varied⟯.
»⟮c174;The point size⟯« is ⟮＿the font size＿ specified in ＿point＿⟯.
»⟮c176;A pica⟯« is ⟮12 point (whatever point you're using)⟯.

###### DTP point

⟮c178;DeskTop Publishing point⟯ =short=> ⟮DTP point⟯
»⟮c180;the DPT point⟯« is a ⟮quasi-standard⟯ ⟮＿point＿⟯, defined as ⟮1/72 inch⟯

###### abbrevivations

table:language|abbreviation|unit
CSS|⟮c184;pt⟯|⟮DTP point⟯
TeX|⟮c186;pt⟯|⟮slightly smaller thant the DTP point⟯
TeX|⟮c188;bp⟯|⟮DTP point⟯
???|⟮c190;p⟯|⟮point⟯
CSS|⟮c192;pc⟯|⟮pica⟯


## typeface features

### character sizing

flex-container:✫type-anatomy.svg✫

#### lines

The »⟮c194;baseline⟯« is ⟮the imaginary line⟯ ⟮on which most letters sit⟯.
The »⟮c197;mean line⟯« is ⟮the imaginary line⟯ ⟮up to which most lowercase letters extend⟯.

#### sizes

```
»⟮c200;Body height⟯« = ⟮＿ascender line＿ - ＿descender line＿⟯
»⟮c202;X-height⟯« = ⟮＿mean line＿ - ＿baseline＿⟯
»⟮c204;Descender depth⟯« = ⟮＿descender line＿ - ＿baseline＿⟯
»⟮c206;Ascender height⟯« = ⟮＿ascender line＿ - ＿mean line＿⟯
typically, ＿ascender height＿ ⟮c208;>⟯ ＿cap height＿.
»⟮c209;line spacing⟯« = ⟮＿ascender line＿ - next ＿descender line＿⟯
```

#### naming details

⟮c211;Line spacing⟯ =syn= ⟮leading⟯
⟮c213;ascender line⟯ =syn= ⟮topline⟯
⟮c215;x-height⟯ =syn= ⟮corpus size⟯
⟮c217;＿the x-height＿⟯ typically ⟮corresponds to the height of the x⟯, ⟮hence the name⟯. 

#### overshoot

»⟮c220;Overshoot⟯« is when characters ⟮extend a little beyond⟯ ⟮the lines meant to constrain them⟯.
»⟮c223;downwards overshoot⟯« is ⟮＿overshoot＿⟯ beyond the ⟮＿baseline＿⟯.
»⟮c226;upwards overshoot⟯« is ⟮＿overshoot＿⟯ beyond the ⟮＿x-height＿ or ＿cap height＿⟯.

##### motivation

⟮c229;＿Overshoot＿⟯ is used due to ⟮quirks with our perception⟯, where otherwise ⟮the non-overshot letters would look slightly too small⟯.
⟮c232;＿Overshoot＿⟯ is generally used for ⟮round⟯ or ⟮c_;pointy⟯ leters.

#### average relative sizing

table:type property|size
⟮c234;＿cap height＿⟯|⟮0.7em⟯
⟮c236;＿x-height＿⟯|⟮0.5em⟯

### serifs

flex-container:✫serif-sans-serif.jpg✫


»⟮c238;Serifs⟯« are ⟮＿a typeface feature＿⟯, namely ⟮these little bits sticking out of some letters⟯.

<span class='cloze-dump'>{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}{{c28::}}{{c29::}}{{c30::}}{{c31::}}{{c32::}}{{c33::}}{{c34::}}{{c35::}}{{c36::}}{{c37::}}{{c38::}}{{c39::}}{{c40::}}{{c41::}}{{c42::}}{{c43::}}{{c44::}}{{c45::}}{{c46::}}{{c47::}}{{c48::}}{{c49::}}{{c50::}}{{c51::}}{{c52::}}{{c53::}}{{c54::}}{{c55::}}{{c56::}}{{c57::}}{{c58::}}{{c59::}}{{c60::}}{{c61::}}{{c62::}}{{c63::}}{{c64::}}{{c65::}}{{c66::}}{{c67::}}{{c68::}}{{c69::}}{{c70::}}{{c71::}}{{c72::}}{{c73::}}{{c74::}}{{c75::}}{{c76::}}{{c77::}}{{c78::}}{{c79::}}{{c80::}}{{c81::}}{{c82::}}{{c83::}}{{c84::}}{{c85::}}{{c86::}}{{c87::}}{{c88::}}{{c89::}}{{c90::}}{{c91::}}{{c92::}}{{c93::}}{{c94::}}{{c95::}}{{c96::}}{{c97::}}{{c98::}}{{c99::}}{{c100::}}{{c101::}}{{c102::}}{{c103::}}{{c104::}}{{c105::}}{{c106::}}{{c107::}}{{c108::}}{{c109::}}{{c110::}}{{c111::}}{{c112::}}{{c113::}}{{c114::}}{{c115::}}{{c116::}}{{c117::}}{{c118::}}{{c119::}}{{c120::}}{{c121::}}{{c122::}}{{c123::}}{{c124::}}{{c125::}}{{c126::}}{{c127::}}{{c128::}}{{c129::}}{{c130::}}{{c131::}}{{c132::}}{{c133::}}{{c134::}}{{c135::}}{{c136::}}{{c137::}}{{c138::}}{{c139::}}{{c140::}}{{c141::}}{{c142::}}{{c143::}}{{c144::}}{{c145::}}{{c146::}}{{c147::}}{{c148::}}{{c149::}}{{c150::}}{{c151::}}{{c152::}}{{c153::}}{{c154::}}{{c155::}}{{c156::}}{{c157::}}{{c158::}}{{c159::}}{{c160::}}{{c161::}}{{c162::}}{{c163::}}{{c164::}}{{c165::}}{{c166::}}{{c167::}}{{c168::}}{{c169::}}{{c170::}}{{c171::}}{{c172::}}{{c173::}}{{c174::}}{{c175::}}{{c176::}}{{c177::}}{{c178::}}{{c179::}}{{c180::}}{{c181::}}{{c182::}}{{c183::}}{{c184::}}{{c185::}}{{c186::}}{{c187::}}{{c188::}}{{c189::}}{{c190::}}{{c191::}}{{c192::}}{{c193::}}{{c194::}}{{c195::}}{{c196::}}{{c197::}}{{c198::}}{{c199::}}{{c200::}}{{c201::}}{{c202::}}{{c203::}}{{c204::}}{{c205::}}{{c206::}}{{c207::}}{{c208::}}{{c209::}}{{c210::}}{{c211::}}{{c212::}}{{c213::}}{{c214::}}{{c215::}}{{c216::}}{{c217::}}{{c218::}}{{c219::}}{{c220::}}{{c221::}}{{c222::}}{{c223::}}{{c224::}}{{c225::}}{{c226::}}{{c227::}}{{c228::}}{{c229::}}{{c230::}}{{c231::}}{{c232::}}{{c233::}}{{c234::}}{{c235::}}{{c236::}}{{c237::}}{{c238::}}{{c239::}}{{c240::}}</span>