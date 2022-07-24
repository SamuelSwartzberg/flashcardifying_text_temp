
## edges

Shorthand for edges in CSS use a consistent syntax:

1 value|specifies all sides|✫sm_1_border.png✫
2 values|1st specifies top/bottom, 2nd specifies left/right|✫sm_2_border.png✫
3 values|1st specfies top, 2nd specfies left/right, 3rd specifies|✫sm_3_border.png✫
4 values|1,2,3,4 top right bottom left (TRBL)|✫sm_4_border.png✫

Normally, instead of using the shorthand, you can also set the properties individually by using -top(-), -left(-), -bottom(-), -right(-) properties.
Things in css that take the edge shorhand and also have four individual properties to set them: border (border, border-color, border-width, border-style), margin, padding, scroll-padding, scroll-margin

typically, any edge width is specified as a ‹length-percentage›
‹length-percentage-edges› ::= ‹length-percentage› [‹length-percentage›] [‹length-percentage›] [‹length-percentage›]

### css box model

[⟮c+;s∞;Margin-box⟯ [⟮c+;s∞;Border-box⟯ [⟮c+;s∞;Padding-box⟯ [⟮c+;s∞;Content-box⟯]]]]

margin: auto can be used to center a thing horizontally, but not vertically

#### logical properties

logical properties are a set of properties that respect the block-flow-directrion or inline base direction.
logical-property ::= [margin|padding|border]-[block|inline]-[start|end]
the border logical property can be split into width, style and color as per usual.

### Border ＆ outline

border can also be seen as a shorthand for border-top, border-right...
border-width, border-style, border-color are all shorthand for edges, and can be set via the 4 properties individually.
Notably, outline is similar to border in that it is composed of -width, -style, -color, but that in contrast to border, neither it itself nor its three subproperties are shorthands for the sides, nor are there individual properties for the sides - you either set the outline on all sides, or none at all.
Outlines can be moved away from its box via outline-offset: ‹length›

#### border-image

`border-image` allows you to use an image instead of an elements regular border
`border-image` is shorthand for `-source`, `-slice`, `-width`, `-outset` and `-repeat`.
most `border-image` properties take the edge shorthand, exept for `-repeat`, which only takes up to two values, and `-source`, which only takes one at most.
none of the `border-image-whatever` has corresponding -top, -left... properties.
`border-image-source` takes the ‹image› representing the border image
`border-image-outset` takes (up to four) of ‹length› or ‹number›, where a ‹number› specifies multiples of `border-width`
`border-image-width` takes (up to four of) ‹length-percentage› or ‹number›, where a ‹number› specifies a multiple of a border-width.
`border-image-repeat` takes 1-2 repeats (working as 1-2 values would normally using the edge syntax)
`border-image-slice` governs how the image specified by is divided.
Specifically, `border-image-slice` specifies the measurements of the part of the border image taken for the corners, with the leftover being used for the sides.
`border-image-slice` takes 1-4 ‹number› or ‹percentage› plus the optional fill keyword.
for `border-image-slice`, a ‹number› without unit specifies pixels for some reason.
for `border-image-slice`, a ‹percentage› specifies a propertion of the `border-image`'s size
for `border-image-slice`, using the fill keyword specifies that the part of the image not sliced for the border (the center) should be used as a background-image for the element, but stacked above the actual `background`
If we specified `border-image-slice: 33%`, this means that all corners would take 33% of the image, leaving 33% to be stretched/repeated/whatever for the sides.
`border-image-slice` takes the full range of the edge syntax, but interprets it different than most: In general, the lengths describe the lengths of the sides of a single corner.
when top/bottom/right/left are specified with the 3/4 value syntax, that works as:
https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-slice/border-image-slice.png


border-image-slice: 10%
table:|10%|80%|10%|
10%|class=no;|class=no;|class=no;|
80%|class=no;|class=no;|class=no;|
10%|class=no;|class=no;|class=no;|


border-image-slice: 10% 30%
table:|30%|40%|30%|
10%|class=no;|class=no;|class=no;|
80%|class=no;|class=no;|class=no;|
10%|class=no;|class=no;|class=no;|
10%|class=no;|class=no;|class=no;|


border-image-slice: 20% 10% 30% 60%;
table:|60%|30%|10%|
20%|class=no;|class=no;|class=no;|
50%|class=no;|class=no;|class=no;|
30%|class=no;|class=no;|class=no;|

## lines

Line is not really an official css term.
Lines: border, column-rule, outline
text-decoration functions similar to 'lines', in that it is a shorhand for -width, -style, and -color, but 1) it's called -thickness, not -width; 2) -style only supports a subset of keywords; 3) included in the shorthand is a fourt property, text-decoration-line, which takes n of the keywords underline||overline||line-through.

Lines have following shorthand and respective subproperties:
foo: foo-width || foo-style || foo-color

where foo-width takes a ‹line-width›
line-width ::= thin|medium|thick|‹length›
where foo-style takes a ‹line-style›

line-style
hidden|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em hidden black;"> </div>
dotted|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em dotted black;"> </div>
dashed|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em dashed black;"> </div>
solid|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em solid black;"> </div>
double|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em double black;"> </div>
groove|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em groove black;"> </div>
ridge|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em ridge black;"> </div>
inset|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em inset black;"> </div>
outset|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em outset black;"> </div>

## corners

1 value|specifies all corners|✫sm_1_corner.png✫
2 values|1st specifies topleft and bottomright, 2nd specifies topright and bottomleft|✫sm_2_corner.png✫
3 values|1st specfies topleft, 2nd specfies topright and bottomleft, 3rd bottomright|✫sm_3_corner.png✫
4 values|1,2,3,4 topleft topright bottomright bottomleft|✫sm_4_corner.png✫

Normally, instead of using the shorthand, you can also set the properties individually by using -top-left(-), -top-right(-), -bottom-right(-), -bottom-left(-) properties.

things that take corners may also take two sets of corners specifiers, separated by a slash.
If a thing takes two sets of corner specifiers, the first apply in x direction and the second in y direction.

Data types that specify corners are ‹border-radius›
border-radius: ‹border-radius›