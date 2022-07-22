# attributes

## CSS

all attributes can be set as, well, attributes.
some but not all attributes can be set via CSS.
attributes that can be set via CSS are also known as »properties«.

## viewBox

A `viewBox` attribute defines a viewport.

## width ＆ height

it seems that ⟮SVG elements⟯ will have ⟮width⟯ and ⟮height⟯ of ⟮0⟯ and thus ⟮be invisble⟯ if ⟮not otherwise specified⟯ 

## x ＆ y

In ⟮SVG⟯, you ⟮position things⟯ by ⟮specifying the x and y properties⟯ ⟮on the elements⟯. 

## stroke ＆ fill

### stroke

the stroke of a shape is the line drawn around the object
`stroke-width` defines the width of a stroke.

#### edges of lines

`stroke-linecap` defines how the stroke ends on the line

stroke-linecap="butt"|▯▯¶▮▮¶▯▯
stroke-linecap="square"|▯▯¶▯▮¶▯▯
stroke-linecap="round"|◜-¶|▮¶◟-

`stroke-linejoin` defines how a joint between two line segments behaves.

table:|imagining a top left 90° corner
stroke-linejoin="bevel"|◢
stroke-linejoin="round"|◜
stroke-linejoin="miter"|◼

#### dashes

`stroke-dasharray` determines how a stroke is dashed, if at all.
`stroke-dasharray` takes a comma-separated list of values.
for stroke-dasharray, values at an odd index indicate the length of the filled part of a dash, values at an even index indicate the unfilled part of the dash.
`stroke-dasharray` needs at least 2 values, but may take more.
`stroke-dasharray` takes the supplied pattern as a pattern to repeat.

### both

the `stroke/fill` attribute sets the color of the stroke/fill.
You can set the opacity of the stroke and fill by setting a color with transparency, or by using `stroke/fill-opacity`.
`stroke/fill` both can also apply text.

## font

Many SVG font-related properties are the same as in HTML/CSS.
However, `dominant-baseline` and not `vertical-align` is used for vertical alignment, and also for determining the baseline of the box alignment context.
