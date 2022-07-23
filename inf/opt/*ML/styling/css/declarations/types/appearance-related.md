# appearance-related

## color

All css color keywords are case-insensitive.
any property ending in -color: takes a ‹color› value
color  ::= transparent|currentColor|‹color-keyword›|‹hex-color›|‹color-function›
color keywords are things such as red, darkgrey, rebeccapurple 💜, which correspond to specific RGB values.
the transparent keyword is a shortcut for rgba(0,0,0,0)
The currentColor keyword represents the value of an element's color property, or the inherited value of the color property if specified as the color property. 
color functions are a bunch of different CSS functions that take the components of a certain color model as arguments.
most css color functions have a variant that ends a and accepts a fourth alpha value.
CSS color functions: rgb/rgba, hsl/hsla
for rgb()/rgba(), the color components can be ‹percentage›s from 0% to 100%, or ‹numbers› from 0 to 255
for hsl()/hsla(), the h component is a ‹angle›, or a ‹number› between 0 and 360
for hsl()/hsla(), s and l are ‹number-or-percentages› (how they work is specified in the general color flashcard)
in css, the alpha channel takes a ‹number-or-percentage-0-1›

## shadows

The box-shadow property creates a rectangular shadow behind an element's entire box, while the drop-shadow() filter function creates a shadow that conforms to the shape (alpha channel) of the image itself.

the first two ‹lengths› of text-shadow, box-shadow and drop-shadow() take a ‹offset› (two ‹length›s), the third ‹length› specifies the blur-radius
for box-shadow, the fourth ‹length› specifies the spread-radius, for text-shadow and drop-shadow(), there is no way to specify a spread radius.
for text-shadow, box-shadow and drop-shadow(), the non-length value specifies the color.
box-shadow additionally may take the keyword inset, which specifies that the shadow should render inside the box instead of outside it.

text-shadow and box-shadow also accept a CSL of shadow specifiers for specifying multiple shadows.

To make text blurry in CSS, make it's color transparent and set a text-shadow.
