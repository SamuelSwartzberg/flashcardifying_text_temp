# media-related


## filters

backdrop-filter applies a filter to the area behind an element.
for backdrop-filter to apply, the element or its background must be at least partially transparent.
backdrop-filter and filter take a ‹filter-function-list›
filter-function-list ::= ‹filter-function›|‹svg-filter›{ ‹filter-function›|‹url›} # the URL is for a svg filter
a ‹filter-function› is a ‹function› that applies a filter (i.e. changes the appearance of an image)
filter-functions: 
blur(): takes a blur-radius
brightness(): ‹number-or-percentage-to-infinity›
contrast(): ‹number-or-percentage-to-infinity›
drop-shadow(): arguments are `offset-x offset-y [blur-radius] [color]`
grayscale(): ‹number-or-percentage-0-1›
hue-rotate(): takes an ‹angle› and rotates the hue by that angle
invert(): ‹number-or-percentage-0-1›
opacity(): ‹number-or-percentage-0-1›
saturate(): ‹number-or-percentage-to-infinity›
sepia(): ‹number-or-percentage-0-1›

anywhere that takes a blur-radius generally takes a ‹length› which defines the standard deviation of the gaussian function

There are a few places which accept a ‹number› or ‹percentage›. This is not an official CSS data type, but I will call this ‹number-or-percentage›.
There are a few different sets of semantics for ‹number-or-percentage›
‹number-or-percentage-to-infinity›: 0/0% is the opposite effect (complete lack of x), 1/100% is original, 2/200% is 2x the effect
‹number-or-percentage-0-1›: 0/0% is complete lack, 1/100% is complete application

## ‹repeat›

repeat|repeat as much as needed to cover the whole painting area, clipping if necessary
space|The image is repeated as much as possible without clipping. The first and last images are pinned to either side of the element, and whitespace is distributed evenly between the images. 
round|As the allowed space increases in size, the repeated images will stretch (leaving no gaps) until there is room (space left ›= half of the image width) for another one to be added. When the next image is added, all of the current ones compress to allow room. 
no-repeat|do not repeat

## ‹image›

The ‹image› CSS data type represents a two-dimensional image.
While there are many kinds of things in the spec that an ‹image› could be, currently it can only be an ‹url› or a ‹gradient›

### ‹gradient›

currently, there are three types of ‹gradient›s, ‹linear-gradient›, ‹radial-gradient›, and ‹conic-gradient›
‹linear-gradient› and ‹radial-gradient›s also exist as repeating versions, which repeat as much as necessary to fil a given area: ‹repeating-linear-gradient›, ‹repeating-radial-gradient›.
Repeating gradients have the same syntax as the non-repeating variants, but if you size the final stop too large, there will be no palce for repeating.
All gradients are specified via css functions.

linear-gradient ::= linear-gradient\(‹direction-specfier›, ‹color-stop-list›\)
direction-specifier ::= ‹angle›|‹side-or-corner›
side-or-corner ::= to [‹top-bottm›] [‹left-right›]
color-stop-list ::= ‹color-stop›{, ‹color-stop›}
color-stop ::= [‹color›] [‹length-percentage›] [‹length-percentage›]

radial-gradient ::= radial-gradient\(‹shape-specifier›, ‹color-stop-list›\)
shape-specifier ::= ‹ending-shape› ‹size› at ‹position›
ending-shape ::= circle|ellipse



conic-gradient ::= conic-gradient\(‹origin-specifier›, ‹color-stop-list-angular›\)
origin-specifier ::= [from ‹angle›] [at ‹position›]
color-stop-list ::= ‹color-stop-angle›{, ‹color-stop-angle›}
color-stop ::= [‹color›] [‹angle›] [‹angle›]

When specifying color stops, if you don't specify a color it will use the middle between the preceeding and succeeding colors
When specifying color stops, if you don't specify a ‹length-percentage›/‹angle› it will use the middle between the preceeding and succeeding stops.
Specifying two ‹length-percentage›/‹angle› on a single color stop will make the color stay the same inbetween those two stops.
