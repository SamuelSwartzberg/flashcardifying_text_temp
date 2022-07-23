# length related

## offsets

generally from the top left corner.
Even when not using the ‹offset› syntax, offsets in HTML/SVG are often from the top left corner.
for ‹offset›, the first value is x and the second is y
while offset is not a official datatype, I will define it as offset ::= ‹length› ‹length›

## length

length ::= ‹number›‹length-unit›
length-percentage ::= ‹length›|‹percentage›
resolution-length-percentage ::= ‹resolution›|‹length-percentage›

lpminmaxauto ::= ‹length-percentage›|min-content|max-content|auto # this is a term I made up
terms like auto, min-content and max-content depend on the current formatting context/layout mode
an element with width/height = auto has a width/height of its automatic size
an element with width/height = min-content has a width/height of its min-content size
an element with width/height = max-content has a width/height of its max-content size
An elements lengths min-content and max-content size are equivalent to its automatic size unless otherwise specified.
When not equal to auto, in general the min-content size is the smallest size that doesn't lead to overflow which could be avoided by choosing a larger size
When not equal to auto, in general the max-content size is the size a box could assume when given infinte space, while avoiding overflow.

‹flex› consists of a ‹number› followed by the unit fr.
the fr unit represents a fraction of the leftover space in the grid container. 
flex-l-p-min-max-auto ::= ‹flex›|‹l-p-min-max-auto›

length-unit ::= ‹relative-length-unit›|‹absolute-length-unit›
relative-length-unit ::= ‹font-relative-length-unit›|‹viewport-relative-length-unit›
font-relative-length-units
`rem`|font-size of the root element
`ex`|the height of a lowercase x of the current font (rarely used)
`em`|the font-size of the element
`ch`|width of the "0" (zero)

viewport-relative-length-units
`vw`|1% of the width of the viewport*
`vmin`|1% of viewport's* smaller dimension
`vmax`|1% of viewport's* larger dimension
`vh`|1% of the height of the viewport*

absolute units in CSS may or may not refer to their real-world equivalent.
On print media and similar situations, css absolute units refer to their real-world equivalent.
For low dpi devices, absolute units are instead defined in reference to the reference pixel: 1 in = 96 px, thus `1in` may not correspond to 1 RL inch. 
For high dpi devices, px are instead defined in reference to real-world units, so that 1 in is one 1 RL in, and 1px is 1/96in, no matter how many screen pixels that would actually correspond to on the device.
absolute-length-unit ::= ‹metric-length-unit›|‹imperial-length-unit›|px
metric-length-unit ::= cm|mm|Q
imperial-length-unit ::= in|pc|pt

## ‹size›

size ::= (‹length-percentage›[ ‹length-percentage›])|size-keyword
size-keyword ::= closest-side|closest-corner|farthest-side|farthest-corner


table:size-keyword|meaning
closest-side|The gradient's ending shape meets the side of the box closest to its center (for circles) or meets both the vertical and horizontal sides closest to the center (for ellipses).
closest-corner|The gradient's ending shape is sized so that it exactly meets the closest corner of the box from its center.
farthest-side|Similar to closest-side, except the ending shape is sized to meet the side of the box farthest from its center (or vertical and horizontal sides).
farthest-corner|The default value, the gradient's ending shape is sized so that it exactly meets the farthest corner of the box from its center.

For ‹size›, specifying two ‹length-percentages› applies them to horizontal/vertical direction respectively. specifying only one makes it applly two both horizontal and vertical directions. Places that expect a ‹size› for a circle may only recieve one ‹legnth-percentages›

## position

‹position› can take two kinds of values: keywords and values.
Keywords for ‹position› are center, top, right, bottom and left.
A value for ‹postion› can be a ‹percentage› or ‹length›.
For ‹position›, specifying one value positions it exactly at that keyword (if keyword), or at value on the x axis and the y defaults to 50%.
For ‹position›, specifying two values means that the first will apply to x positioning, and the second will apply to y positioning, unless it is two keywords.
For ‹position›, a keyword followed by a value specifies the offset from the keyword.
For ‹position›, if specifying two keywords or two keywords with values each, the order doesn't matter.
The value described by ‹position› need not be inside the elements box.


flex-container:✫sm_position_value.png✫