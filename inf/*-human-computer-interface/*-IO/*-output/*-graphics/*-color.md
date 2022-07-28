# color

## components

### basics

Each pixel in a color image is made up of two or more components.
A component⎵pixel⎵ is a value that makes up part of a pixel. 
^components may also be non-scalar and thus not channels, e.g. in the case of GIF index numbers
A channel⎵pixel⎵ is a component that is a scalar value.

### in terms of the image

A channel/component⎵image⎵ is the matrix of channel/component values for the whole image.

### types

A color/alpha channel・component is a channel・component representing color/opacity.

### color depth

#### basics

Bits per pixel/component/channel is the amount of bits used for a pixel/component/channel.
bpp/bpc =short for=> bits per pixel/bits per channel
Color depth is ambiguous between bits per pixel/component/channel.
bit depth =syndef= color depth.

#### names

table:name|bpp/bpc
high color|15-16/5
true color|24/8
deep color|30/10

## color model

### basics

A color model is a n-tuple of primary channels, and their relationships.
A color space is a color model associated with how the results are to be interpreted (viewing conditions etc.) 
A gamut⎵wide/medium/narrow/color space⎵ is a complete subset of a colors that ø/are contained in something/can be produced or represented by something/can be produced or represented by a color space.
A color model graphical representation is a representation of a color model as a shape in n-dimensional space.

### primary, secondary

A primary channel is a fundamental channel of a color model.
A secondary channel is a channel created from the combination of two primary channels.
An n-ary (n>1) channel is a channel created of the combination of two adjacent n-1-ary channels.
A primary/secondary/n-ary color is a primary/secondary/n-ary channel that is a color.

### representation

A color from a color model is typically represented as an color n-tuple, or as a color hexadecimal representation.
color-n-tuple ::= &lt;color-model-name&gt;(&lt;component-value&gt;{, &lt;component-value&gt;})
color-hexadecimal-representation ::= #{&lt;component-hex-value&gt;}

### derivatives

An alpha/depth color model (my term) is a different color model with an alpha/depth channel added.
The alpha/depth color model name is the color model name + A/-D.

### types

#### additive/subtractive

##### basics

An additive/subtractive color model is one where the channels added together produce progressively lighter/darker colors.
Light emission/absorption follows an additive/subtractive color model.
An additive/subtractive color model is mostly used for displays/printing and other places where light is emitted/absorbed.

##### RGB/CMY

###### basics

The RGB/CMY(K) color model is the most common additive/subtractive color model, in part because it corresponds/is the inverse of the model that corresponds roughly to human trichromatic color vision.
The RGB/CMY color models consists of the three channels red, green, blue/cyan, magenta, yellow.

###### relationship

C+R = 1
M+G = 1
Y+B = 1

###### CMYK

The CMYK color model adds a channel of key (= black) to the CMY color model.
The key channel is generally added to CMYK because black ink is cheaper, and producing black by mixing cyan, magenta and yellow is in practice quite hard. 
K = min(C, M, Y) 
channel⎵CMYK⎵ = (channel⎵CMY⎵ - K) / (1 - K)

##### others

RYB is an alternative subtractive color model still used in the arts, which however cannot create black. 

Color depth is more rarely also called bit depth. 
Today, the most common color depth is 8 bit per channel. 

the common color depth of 8 bit per channel means values from 0 - 255 / 00 to ff. 
Most colors are specified by specifying the color model and then the components (e.g. RGB 0, 120, 58). 
RGB colors are also often displayed as a hex triplet, which is generally prefixed by a # character. 
In certain places, e.g. HTML/CSS, hex colors with reduplicated digits only (e.g. 663399) can be shortened to three-digit variants (e.g. 639) 

#### hue-based

##### hue

Hue is what most languages consider primary about color.
^so e.g. hue is the head in NP/APs describing color: light green, pastel purple.
RGB-based hue is hue generated/mapped from RGB, which is the most common scale for hue.
RGB-based hue is conceputally a circle and thus is specified in degrees.
R/G/B are 0=360/120/240deg of RGB-based hue.
Y/C/M are 60/180/300 of RGB-based hue.

Hue is often generated from RGB, e.g. for c+;use in HSL ＆ HSV/HSB. 
If Hue is generated from RGB for HSL/HSV, it is specified in a degree from 0 to 360 deg 

##### hue-based color model

flex-container:h∞;✫sm_hsl_cylinder.png✫✫sm_hsv_cylinder.png✫


flex-container:h∞;✫sm_hsl_cone.png✫✫sm_hsv_cone.png✫

###### basics

A hue-based color model is a color model that contains a hue channel.
hue represents the angular distance of a hue-based color model's color model graphical representation.

###### lightness & value

Lightness/value =symb=> L/V.
Lightness/value represents the height of the hue-based color model's color model graphical representation cylinder・bicone/cone.
Lightness/value allows for the greatest range of color at 0.5/1.
Despite the name, lightness/value are not the only things that influenced percieved brightness in hue-based color models.

####### value

Intuitively, value is how adding shining more or less light on a non-black thing will change its color.
Thus, at 0 value (no light) all colors are black.
Thus, at 1 value (max light) all colors besides black can exist.

####### lightness

Intuitively, lightness models how mixing black (0-0.5) or white (0.5-1) will change its color.
Thus at 0/1 lightness all colors are white/black.

###### saturation and chroma

Chroma is the distance of a color from being grayscale.
Chroma has different intervals (smaller than [0, 1]) depending on the lightness/value.
Saturation is chroma stretched to always be a value in the interval [0, 1]
Using chroma, a hue-based color model's color model graphical representation using lightness/value is a bicone/cone.
Using saturation, a hue-based color model's color model graphical representation is always a cylinder.
Chroma/saturation represents the radius of a hue-based color model's color model graphical representation.

###### HSL, HSV

HS/CL・HS/CV is the color model using RGB-based hue consisting of hue, saturation/chroma, lightness・value.
HS/CV is the exact same as HS/CB.

## non-model-terminology

### mixtures

A tint/tone/shade is a mixture of a color with white/gray/black.

## groupings

### color schemes

A color scheme is a subset of colors used for a specific purpose.

#### hue scheme

##### basics

A hue scheme is a set of hues used for a specific purpose, and is typically based on a color wheel.

##### types

###### basics

A n-hue hue scheme is a hue scheme consisting of n hues.
A dyadic/triadic/tetradic/... hue scheme⎵wide⎵ =syndef= 2/3/4/...-hue hue scheme.
A monochromatic/non-monochromatic hue scheme is a 1/2+-hue hue scheme.

###### non-monochromatic

An analoguous hue scheme is a non-monochromatic hue scheme consisting of an arbitrary amount of adjacent hues.
A complementary hue scheme is a 2-hue hue scheme where the hues are spaced 180deg apart.
A split-complementary hue scheme is a 3-hue hue scheme which is based on a complementary hue scheme, but one hue is split in two, with the two new hues offset by +/- some degrees (typically 30deg)
A triadic hue scheme⎵narrow⎵ is a 3-hue hue scheme where the hues are spaced 120deg apart.
A double-complementary hue scheme is a 4-hue hue scheme consisting of two complimentary hue schemes.
A square hue scheme is a 4-hue hue scheme where the hues are spaced 90deg apart.
A rectangle hue scheme is a 4-hue hue scheme where the hues are spaced 60-120-120-60deg.

### systematizations

A color systematization (my term) is a systematization of colors within or independent of color models.

#### material

The material color systematization describes colors by a combination of material hue and material weight.
A material hue is a name of a color (e.g. orange) roughly equivalent to its hue.
A material weight is a variant of a material hue roughly similar to lightness, measured on a 1k weight scale.
material-color ::= ‹material-hue›-‹material-weight›