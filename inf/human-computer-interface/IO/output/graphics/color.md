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

#### in detail

## color model

### basics

A color model is a model of how a set of channels make up a color. 
A color space is a color model associated with how the results are to be interpreted (viewing conditions etc.) 
A gamut⎵wide/medium/narrow/color space⎵ is a complete subset of a colors that ø/are contained in something/can be produced or represented by something/can be produced or represented by a color space.

### additive/subtractive

#### basics

An additive/subtractive color model is one where colors added together produce progressively lighter/darker colors.
Light emission/absorption follows an additive/subtractive color model.
An additive/subtractive color model is mostly used for displays/printing and other places where light is emitted/absorbed.
The RGB/CMY(K) color model is the most


In the RGB color model a thingy has the three channels red, green and blue. 
In the CMY color model a thingy has the three channels cyan, magenta and yellow. 
The CMYK color model adds a channel of key (= black). 
The key channel is generally added to CMYK because black ink is cheaper, and producing black by mixing cyan, magenta and yellow is in practice quite hard. 
The CMY and RGB color models are the most common color models in use today, in part because they correspond roughly to human tricromatic color vision. 

RYB is an alternative subtractive color model still used in the arts. It can however not create black. 

Color depth is more rarely also called bit depth. 
Today, the most common color depth is 8 bit per channel. 

the common color depth of 8 bit per channel means values from 0 - 255 / 00 to ff. 
Most colors are specified by specifying the color model and then the components (e.g. RGB 0, 120, 58). 
RGB colors are also often displayed as a hex triplet, which is generally prefixed by a # character. 
In certain places, e.g. HTML/CSS, hex colors with reduplicated digits only (e.g. 663399) can be shortened to three-digit variants (e.g. 639) 


A primary color is a member of a set of colors (all defined to be primary) that can be combined in varying amounts to create a gamut of colors. 

CMY and RGB are complementary in such a way that C+R, M+G, and Y+B are all 100% (255 with an 8 bit color depth). To get one channel, the other is subtracted from 100%. 
To get the K channel from CMY: K = min(C, M, Y) 
After getting the K channel, to convert CMY to CMYK: Channel_new = Channel - K/1 - K

Hue is what we might call ＊color＊ color. 
Hue is what most languages consider primary about color, with other attributes such as light/dark/muddy/vivid/pastel attached later. 
Hue is often generated from RGB, e.g. for c+;use in HSL ＆ HSV/HSB. 
If Hue is generated from RGB for HSL/HSV, it is specified in a degree from 0 to 360 deg 


if Hue is specified in a degree measurement
degree|color
0deg/360deg|red
120deg|green
240deg|blue


Commonly, saturation ≈ chroma refers to the distance of a color from the white-gray-black spectrum. 

Lighntess attempts to model adding white/black paint to make the color white/black. 
100% lightness is white for any saturation/hue. 
50% lightness allows for fully saturated colors. 
0% lightness is black for any saturation/hue 
Value/brightness attempts to model how shining more/less light on a thing will change the color. 
100% value/brightness allows for fully saturated colors. 
0% lightness is black for any saturation/hue. 
tint|mixture of a color with white
tone|mixture of a color with gray
shade|mixture of a color with black


HSL = hue, saturation, lightness. 
HSV = hue, saturation, value is the same as HSB = hue, saturation, brightness. 
HSL and HSV/HSB are alternate color models, which are both variants of/generated from the RGB color model. 
HSL and HSV were created because they are more natural to how we as humans understand color. 
sa;While RGB and CMY are most naturally represented as cubes, sb;HSL and HSV/HSB are commonly represented as cylinders. 
Since the top and bottom of c+;a s202;HSL cylinder all approach the same color (white and black respectively), sb;HSL may also be represented as a bicone. 
Since the bottom of a HSV/HSB cylinder approaches the same color (black), sb;HSV/HSB may more naturally be represented as a cone. 
HSL and HSV/HSB both have s211:212;hue as the degree, and s209:210;saturation as the radius. 
HSL has lightness as the height. 
HSV/HSB has value/brightness as the height.  
both HSL and HSV/B have the problem that changing the saturation and to a certain extent the hue will change the percieved lightness/brightness, even when they are supposed to be independent. 

flex-container:h∞;✫sm_hsl_cylinder.png✫✫sm_hsv_cylinder.png✫
flex-container:h∞;✫sm_hsl_cone.png✫✫sm_hsv_cone.png✫

For any given color model, to specify transparency, you add another channel, which is called the alpha channel.
For a color hex, you specify the alpha channel by adding another two-digit hex to the end.
‹color-model›-D is just that color model with an additional depth channel. 

RGB 3-tuple notation|color
Rgb(0, 0, 0)|✫sm_Screenshot%202020-02-25%20at%2017.42.47.png✫
Rgb(0, 0, 255)|✫sm_Screenshot%202020-02-25%20at%2017.43.44.png✫
Rgb(0, 255, 0)|✫sm_Screenshot%202020-02-25%20at%2017.43.16.png✫
Rgb(0, 255, 255)|✫sm_Screenshot%202020-02-25%20at%2017.44.39.png✫
Rgb(255, 0, 0)|✫sm_Screenshot%202020-02-25%20at%2017.42.26.png✫
Rgb(255, 0, 255)?|✫sm_Screenshot%202020-02-25%20at%2017.41.37.png✫
Rgb(255, 255, 0)|✫sm_Screenshot%202020-02-25%20at%2017.45.11.png✫
Rgb(255, 255, 255)?|✫sm_Screenshot%202020-02-25%20at%2017.41.09.png✫
#f2f12f|c+;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #f2f12f 0%, #f2f12f 100%);">
#e6281f|c+;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #e6281f 0%, #e6281f 100%);">
#e2e|c+;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #e2e 0%, #e2e 100%);">
#daefe4|c+;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #daefe4 0%, #daefe4 100%);">
#867d7e|c+;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #867d7e 0%, #867d7e 100%);">
#17F099|c+;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #17F099 0%, #17F099 100%);">
#132133|c+;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #132133 0%, #132133 100%);">


Color temperature is measured in Kelvin.
incandescent lights|~2500K
daylight|6000K+
candles|1500-2000K

### color schemes

c1,15;analogous |c+;h15:21;Two or more colors that are all next to each other on the color wheel|c+;h8:14;✫sm_paste-1533923cee269fdd130a526f947f61f8c9c1a07a.jpg✫
c2,16;complementary |c+;h15:21;Two opposite colors on the color wheel|c+;h8:14;✫sm_paste-03f4e18bda3e8ee3b4153d5f2ef646224461c7d2.jpg✫
c3,17;monochromatic |c+;h15:21;A single color|c+;h8:14;✫sm_paste-6e50d848ef05e96cfe3f0542e368e14cf6ae37b3.jpg✫
c4,18;tetradic (more specif: double complementary) |c+;h15:21;two pairs of complementary colors |c+;h8:14;✫sm_paste-76f4cf2d889e4aed755d6cc033dbeac563d0deee.jpg✫
c5,19;split complementary (is a form |c+;h15:21;A color and the colors adjacent to its complementary |c+;h8:14;✫sm_paste-da8b825ba5b95610f8a2dae2a17a63c508bec3d5.jpg✫
c6,20;tetradic (more specif. square)|c+;h15:21;Four colors equally spaced on the color wheel|c+;h8:14;✫sm_paste-fd4b5126038c4864c0345df2e6fb8f52cb12541f.jpg✫
c7,21;triadic |c+;h15:21;Three colors equally spaced on the color wheel|c+;h8:14;✫sm_paste-002328be373e9ab91dcae451d436c067fa5a2718.jpg✫


Material design pioneered describing lightness of colors on the same 100 (or sometimes 50) to 900 scale as font weights.
Describing colors on a 100 to 900 scale has been adopted by other things such as bootstrap, chakra.
color-on-weight-scale ::= ‹hue›-‹weight›