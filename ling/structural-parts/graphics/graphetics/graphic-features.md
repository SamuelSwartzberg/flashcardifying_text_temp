# graphic features

## basics

### typeface & fonts

A fully-specified character (my term) is a character with values for all graphic features, thus being printable.

#### typeface

⟮typeface⟯ =syn= ⟮font family⟯. 
»⟮A typeface letterform⟯« (my term) is an alternant of ⟮＿a glyph＿⟯ with certain typeface features.
A typeface feature is a graphic feature where varying it changes the typeface letterform and thus the typeface.
A typeface is an instantiation of a glyph set ith certain typeface features.
Alternatively, a typeface is a set of typeface letterforms with the same typeface features.

#### fonts

A font letterform (my term) is  is an alternant of a typeface letterform with certain font features.
A font feature is a graphic feature where varying it changes the font letterform and thus the font.
A font is an instantiation of a typeface with certain font features.
Alternatively, a font is a set of font letterforms with the same font and typeface features.
font features {font weight, font size, slope}

### type, sort

flex-container:✫metal-movable-type.jpg✫


»⟮A type⎵countable⎵⟯ «is ⟮a block⟯ ⟮with a fully-specified character on it⟯.
»⟮A sort⟯« is a set of graphic features that produce a type.
»⟮Type⎵uncountable⎵⟯« is ⟮types collectively⟯.

## distinctive graphic features

### letter case

»⟮Letter case⟯« is the graphic fcategory of types distinguished mainly by size.
Typical values for letter case in a 2-cameral system = uppercase, lowercase
⟮uppercase grapheme⟯ =syn= ⟮captial letter⟯ =syn= ⟮majuscle⟯ 
⟮lowercase grapheme⟯ =syn= ⟮minuscle⟯  

### type anatomy

flex-container:✫type-anatomy.svg✫

Type anatomy is the set of constituent parts of glyphs.

#### descenders/ascenders

flex-container:✫descender.png✫✫long-ascenders.jpg✫


A »⟮descender/ascender⟯« is ⟮the portion of a letter⟯ which ⟮extends below the ＿baseline＿⟯/above the mean line. 
The ascender/descender line is the line which ascenders/descenders extend to.

#### super/subscript

s*script⎵wide⎵ is character(s) whose baseline is not the same as the general baseline
s*script⎵narrow⎵ is s*script⎵wide⎵ where the characters are smaller than regular text.
s*script may be subscript or superscript.
subscript is s*script where their baseline is lower.
superscript is s*script where their baseline is higher.


## font features

### weight

font weight is a sm graphic fcategory controlling the relative thickness of the characters.

#### 1k weight scale

The 1k weight scale (my term) is the scale specifying values for the graphic fcategory font weight in values between 1-1000.
The 1k weight scale may be the fixed-weight scale or the variable-weight scale.

##### fixed-weight scale

The fixed-weight scale is the 1k weight scale that allows values from 100 to 900 in steps of 50 or 100.

##### variable-weight scale

the variable-weight scale is the 1k weight scale that allows values from 1 to 1000 in steps of 1.

#### keyword values

The weight keywords are a set of keywords that are used as fvalues for the graphic fcategory weight.

##### correspondence with weight scale

table:1k weight scale|keyword values
100|thin/hairline
200|ultra/extra light
300|light
400|regular
500|medium
600|semi/demi bold
700|bold
800|ultra/extra bold
900|black

### keming ＆ letter-spacing

flex-container:✫kerning-av.jpg✫✫metal-type-kerning.png✫

Intraletter whitespace distance (my term) is a sm/ssm graphic fcategory specifying the distance of the horizontal distance between glyphs.
A intraletter whitespace distance adjustment is an adjustment of intraletter whitespace distance.

#### letter-spacing

Letter-spacing is an intraletter whitespace distance adjustment equally between all glyphs in a glyph sequence.
⟮Letter-spacing⟯ =syn= ⟮tracking⟯

#### kerning

Kerning is an intraletter whitespace distance adjustment between certain glyphs (only in a proportional/variable width typeface).
⟮＿kerning＿⟯ generally involves ⟮intruding into⟯ ⟮the box of another glyph's sort⟯. 
Original, the »⟮kern⟯« of ⟮a glyph or its sort⟯ was ⟮the part that overhangs its sort⟯. 
Default kerning (my term) is the kerning that is applied in almost all typefaces in existence to ensure nice visual distance.

#### monospace

Monospacing is characters occupying the same horizontal space.
A typeface may either be monospaced or proportional-width.

### font size

The »⟮font size⟯« specifies the ⟮＿body height＿⟯. 
The ⟮＿body height＿⟯ is the height of the sort (if physical) or em square (if digital)

#### units

##### em

###### em

»⟮em⟯« is a unit ⟮relative to⟯ ⟮the current ＿font size＿⟯.
Ergo, the ⟮＿font size＿⟯ is equal to ⟮1em (by definition)⟯.

###### m sort

flex-container:✫m-vs-em.svg✫


⟮the sort⟯ of ⟮uppercase Ms⟯ used to be ⟮as wide as tall (i.e. square)⟯,
Since the sort of uppercase M was square, the em arose as the width/height of an uppercase M sort.

###### em square

flex-container:✫metal-movable-type.jpg✫


The »⟮em square⟯« is ⟮an imaginary square⟯ which is 1em wide and high, allowing other font properties to be sized relative to it.

###### en

!The »⟮en⟯« is either
- !⟮half the width⟯ of ⟮an em⟯. 
- !⟮the width⟯ of ⟮an uppercase or lowercase⟯ ⟮n⟯. 

###### derived thins

An en/em space/dash is a space/dash that is 1 en/em wide

##### point

In typography, the »⟮point⟯« is ⟮the smallest⟯ ⟮unit of measure⟯, though its exact size has varied.
The point size is the font size specified in point.
»⟮A pica⟯« is ⟮12 point (whatever point you're using)⟯.

###### DTP point

⟮DeskTop Publishing point⟯ =short=> ⟮DTP point⟯
the DPT point is a quasi-standard point, defined as 1/72 inch

###### abbrevivations

table:language|abbreviation|unit
CSS|pt|DTP point
TeX|pt|slightly smaller thant the DTP point
TeX|bp|DTP point
???|p|point
CSS|pc|pica


## typeface features

### character sizing

#### lines

The »⟮baseline⟯« is ⟮the imaginary line⟯ ⟮on which most letters sit⟯.
The »⟮mean line⟯« is ⟮the imaginary line⟯ ⟮up to which most lowercase letters extend⟯.

#### sizes

»⟮Body height⟯« = ⟮＿ascender line＿ - ＿descender line＿⟯.
»⟮X-height⟯« = ⟮＿mean line＿ - ＿baseline＿⟯.
Descender depth = ＿descender line＿ - ＿baseline＿.
Ascender height = ＿ascender line＿ - ＿mean line＿
typically, ascender height > cap height.
line spacing = ＿ascender line＿ - next ＿descender line＿


#### naming details

⟮Line spacing⟯ =syn= ⟮leading⟯
⟮ascender line⟯ =syn= ⟮topline⟯
⟮x-height⟯ =syn= ⟮corpus size⟯
⟮the height of the x-height⟯ typically ⟮corresponds to the height of the x⟯, ⟮hence the name⟯. 

#### overshoot

»⟮Overshoot⟯« is when characters ⟮extend a little beyond⟯ ⟮the lines meant to constrain them⟯.
»⟮downwards overshoot⟯« is ⟮＿overshoot＿⟯ beyond the ⟮＿baseline＿⟯.
»⟮upwards overshoot⟯« is ⟮＿overshoot＿⟯ beyond the ⟮＿x-height＿ or ＿cap height＿⟯.

##### motivation

⟮＿Overshoot＿⟯ is used due to ⟮quirks with our perception⟯, where otherwise ⟮the non-overshot letters would look slightly too small⟯.
⟮＿Overshoot＿⟯ is generally used for ⟮round⟯ or ⟮c_;pointy⟯ leters.

#### average relative sizing

table:type property|size
⟮＿cap height＿⟯|⟮0.7em⟯
⟮＿x-height＿⟯|⟮0.5em⟯

### serifs

flex-container:✫serif-sans-serif.jpg✫


Serifs are a typeface-varied feature, namely these little bits sticking out of some letters.