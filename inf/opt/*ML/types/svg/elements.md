# elements

## basic shapes

You ⟮create basic shapes⟯ in SVG by using ⟮the SVG basic shapes⟯. 
the ⟮SVG basic shapes⟯ are a grouping of⟮, well, basic shapes⟯ 
SVG ⟮basic shapes⟯: ⟮‹circle›⟯, ⟮‹ellipse›⟯, ⟮‹line›⟯, ⟮‹polygon›⟯, ⟮‹polyline›⟯, ⟮‹path›⟯ and ⟮‹rect›⟯ 

### rect

A `‹rect›` is determined by a `x`, `y`, `width` and `height`.
A `‹rect›` may optionally have a corner radius specified with `rx`, `ry`.

### circle

A `‹circle›` is determined by `r`, `cx` and `cy` (center x center y)

### line

A `‹line›` is determined by `x1`, `y1`, `x2`, `y2`.

### polyline

A polyline/polygon is a set of connected straight lines (e.g. you might draw a star or a parallelogram or sth. with this).
A polyline/polygon is determined by a single attribute `points`
poly-points ::= ‹point› {‹point›}
point ::= ‹x›, ‹y›
The difference between a `‹polyline›` and a `‹polygon›` is that a `‹polyline›` may be left open (creating a line), while a `‹polygon›` is closed automatically.

### path

A `‹path›` is determined by a single attribute `d`
svg-path-specifier ::= ‹command›{ ‹command›}
command ::= ‹command-letter›{ ‹parameter›}
All path commands end with the coordinates of the 'current point' or the 'pen' (to follow the analogy of a plotter).

#### commands 

For command letters, an uppercase letter specifies absolute coordinates.
For command letters, a lowercase letter specifies relative coordinates from the last point.

The command letter `M/m` means 「move to」.
The command letter `M/m` takes two arguments, x y (for M) or dx dy (for m)

##### straight lines

The command letter `L/l` means 「draw line to」.
The command letter `L/l` takes two arguments, x y (for M) or dx dy (for m)
The command letters `H/h` and `V/v` are abbreviated forms of `L/l` for drawing a horizontal/vertical line.
The command letter `Z/z` means to close the path to the original node.
For `Z/z`, there is obviously no difference between the uppercase and lowercase form.

##### curves

the curve commands separate multiple coordinates with commas. (so e.g. x y, x2 y2)
The command letter `C/c` makes it draw a cubic bezier curve. 
The cubic bezier starts at the last position, and as such it takes three coordinates as parameters, the two handle/control poiints plus the ending point. 
The command letter `S/s` makes it draw a cubic bezier curve, but with the first control point mirrored from the previous one if there is one. 
The command letter `Q/q` makes it draw a quadratic bezier curve, with the first parameter describing the one control point, and the second parameter describing the end point.
The command letter `T/t` infers the control point from a previous `Q/q` or `T/t` command, thus only taking a single point argument.

https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths/shortcut_quadratic_b%C3%A9zier_with_grid.png

```
 C x1 y1, x2 y2, x y
 c dx1 dy1, dx2 dy2, dx dy
 S x2 y2, x y
 s dx2 dy2, dx dy
```

##### arcs

the arc command letter is `A/a`.
Essentially, the arc command specifies part of an elllipse.
The arc command takes seven numbers as arguments.
Because all commands must end in the end point, the svg arc command syntax is hella complicated.
For the svg arc command, the first two numbers specify the x and y radius.
For the svg arc command, the last two parameters describe its endpoint, as must be.
For the svg arc command, the third parameter descirbes the rotation of the ellipse.
However, with only these five parameters, the path could still take four possible paths: 
'above' or 'below' the line (intuitively), or the 'larger'/'smaller' section of the ellipse could be cut out.
The 4th parameter of the svg arc command selects whether to take the large arc (1) or small arc (0)
The 5th parameter of the svg arc command selects whether to take the clockwie arc (1) or counterclockwise (0)

https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths/svgarcs_xaxisrotation_with_grid_ellipses.png
https://cloud.githubusercontent.com/assets/478237/16767397/28df4988-4837-11e6-9f3b-b266d825bec1.png

## ‹text›

`the ⟮‹text›⟯` element is ⟮the only place⟯ you can ⟮have text in SVG⟯ 
In ⟮SVG⟯, ⟮text⟯ ⟮outside of a ‹text›⟯ ⟮will not be shown⟯ 
⟮‹text›⟯ can contain ⟮`‹tspan›`s⟯, which ⟮define subtext (lol) for further targeting⟯. 

### tspan

for a `‹tspan›`, `x` and `y` attributes set a new absolute position, while `dx` and `dy` specify a relative displacment.
the `rotate` attribute of tspan allows it to, well`, rotate.

### textPath

`‹textPath›`s are nested withing `‹text›`
`‹textPath›`s contain tex that they make follow a path, allowing e.g. for curved text.
`‹textPath›` refers to the relevant path's id via an href

## ‹g›

the ⟮svg⟯ ⟮‹g› element⟯ is used to ⟮group ofther elements⟯ 

## ‹use›

`‹use›` is used to instantiate elements defined elsewhere.
`‹use›` takes an href attribute, which is the id of the element to be instantiated.
Using `‹use›` promotes element reuse, thus making your SVG code more DRY.
On `‹use›`, the `x`, `y`, `width`, `height` attributes will override those of the referenced element, all others will not.

## defs

`‹defs›` in SVG is an area of your file that contains things that will not display by themselves, but can be used by other elements.
There are things that can only be defined in `‹defs›`, however you can also place any normal element in `‹defs›`, which will then not be displayed, but can be reused.
Any child of `‹defs›` must have an id attribute to be referred to from elsewhere.
`‹symbol›` works similarly to e.g. a `‹defs›` with a single `‹g›` child, in that it defines a resuable element that doesn't immediately display.
The difference between `‹symbol›` and `‹defs›` with e.g. a `‹g›` child is that `‹symbol›` can define its own viewBox and preserveAspectRatio.

### whateverUnits

the `gradientUnits/patternUnits/patternContentUnits/...` attribute controls whether the units used are relative to the document or the element.
the `gradientUnits/patternUnits/patternContentUnits/...` attribute can be `userSpaceOnUse` or `objectBoundingBox`

userSpaceOnUse|document
objectBoundingBox|element


table:attribute|default
gradientUnits|objectBoundingBox
patternUnits|objectBoundingBox
patternContentUnits|userSpaceOnUse (confusingly)
filterUnitas|objectBoundingBox

## fill types

Fill types are used to `fill` objects
Fill types are defined within the `‹defs›` section, but referenced elsewhere.
The available fill types are gradients, patterns.

### referencing

Fill types are referenced by referring to their ID within `fill`, e.g. as `url(#id)`

### gradients

In SVG, there are two types of gradients, linear and radial.
linear gradients are defined by `‹linearGradient›`, radial gradients by `‹radialGradient›`
A gradient contains n `‹stop›`s

#### stops

A `‹stop›` tells the gradient what color it should be at a certain point.
The color a `‹stop›` should be is defined by its `stop-color` attribute
At what point a `‹stop›` exists is defined by its `offset` attribute.

#### linear and radial

##### linearGradient

A `‹linearGradient›` takes four attributes `x1` `y1` `x2` `y2` to define a line along which the gradient travels (relative to the thing it's being used for)

##### radialGradient

a radial gradient's extent is defined by a point `cx`, `cy` and a radius.
However, the middle of a SVG radial gradient is actually defined by a different point, the focal point `fx`, `fy`.
f the focal point isn't given at all, it's assumed to be at the same place as the center point.

#### attributes

##### spreadMethod

any gradient can take the `spreadMethod` attribute
the `spreadMethod` attribute takes one of `pad`, `reflect`, or `repeat`.
`spreadMethod` determines what happens when the gradient reaches its end, but the object isn't filled yet.


table:spreadMethod|does
pad|continue on with the end color
repeat|restart the gradient from 0
reflect|restart the gradient, but in reverse from 100%/1

### patterns

Inside the `‹pattern›` element, you can include any of the other basic shapes, styled in whatever manner you like.

## clipping and masking

In SVG at least, the difference between clipping and masking is that clipping allows only for hard edges, while masking allows for soft edges by using transparency/grey values.
In SVG, clipping is done by using the `‹clipPath›` element, while masking is done by using the `‹mask›` element.
`‹clipPath›` and `‹mask›` are defined within `‹defs›`.
`‹clipPath›` and `‹mask›` take arbitrary child elements to define their shape.

## filters

Filters are defined by the `‹filter›` element.
Filters are specified within `‹defs›`.

### filter primitives

#### general functionality

Any filter element contains a set of filter primitives as its children.
A filter  primitive performs a single fundamental graphical operation on one or more inputs, producing a graphical result.
Filter primitives are distinct SVG elements which all start with the `‹fe` prefix. 

##### IO

Filter primitives take their input by specifying the `in` attribute.
Some filters primitives can take a second input by specifying the `in2` attribute.
The output of a filter primitive is specified by the `out` attribute.
The input of a filter primitive may be the output of a previous filter primitive or one of a set of predefined inputs.
If a filter doesn't have a `in` attribute, it's assumed to be the output of the previous filter primitive.


table:predefined inputs|does
SourceAlpha|the alpha channel of the input
SourceGraphic|the input (e.g. the image, text, etc. on which the filter is applied)

#### various filter primitives

##### feFlood

The `feFlood` filter primitive creates a rectangle filled with the color and opacity values from properties `flood-color` and `flood-opacity`.

### filter regions

The filter region is the area of the input that is affected by the filter.
Interestingly, the filter region does not have to be the same as the region occupied by the element using the filter.
The filter region is defined by the `‹filter›` element's `x`, `y`, `width`, and `height` attributes.
The default filter region (if none of the attributes are manually specified) is the bounding box of the input plus 10% on each side.
any filter primitive themselves establish a filter primitive subregion.
Filter primitive subregions are altered just as the normal filter region is (by specifying the `x`, `y`, `width`, and `height` attributes).

### applying filters

To apply a `‹filter›` to an SVG element, you refer to its ID (via url()) within the `filter` attribute of the element.
You can also apply a SVG filter to a HTML element, by using the normal `filter` property.

## markers

A marker is a type of symbol that gets attached to one or more vertices of a path, line, polyline, or polygon.

### defining markers

You create markers with `‹marker›` elements.
Markers are defined within `‹defs›`.
Markers can contain other SVG elements.
The markerWidth and markerHeight attributes define the width and height of the marker’s viewport. 
The `refX` and `refY` attributes define the reference point (i.e. the point at which its attached) of the marker relative to its viewport.
The `orient` attribute determines the angle at which the marker is attached.
The `orient` attribute takes a value of auto or an angle. 
If you specify something else than auto, the marker is rotated to the specified angle relative to the SVG viewport itself, which is generally not what you want.
The `markerUnit` attribute is similar to all other `*Unit` attributes, but instead of `objectBoundingBox` it uses `strokeWidth` to indicate it being relative.

### attaching markers

markers are attached by referring to their ID within the `marker-start`, `marker-mid`, or `marker-end` attributes.
One would think that `marker-mid` would place the marker at the midpoint of the line, but instead it's for placing markers at vertices that are not the start or end.

## images

SVG allows the embedding of images via `‹image›`.
the URL for the `‹image›` is defined by the `href` attribute.

## foreignObject

SVG allows the embedding of arbitrary other *ML content within `‹foreignObject›`.

## desc and title

`‹desc›` and `‹title›` are used to add a text description to an element.
`‹desc›` and `‹title›` are nested within the element they describe.
If an element can be described by visible text, it is recommended to reference that text with an aria-labelledby attribute rather than using the `‹title›` or `‹defs›` element.

## switch

`‹switch›` is used to conditionally render an element.
Conditions for `‹switch›` are defined by certain attributes on its direct children.
There are two possible conditions currently, the rarely used `requiredExtensions` and `systemLanguage`.
`systemLanguage` takes a comma-separated list of BCP 47 language tags.
`‹switch›` renders the first child where its conditions evaluate to true.
`‹switch›` is basically only used to localize SVG content.

## metadata

`‹metadata›` is used to store metadata about an SVG document.
The content of `‹metadata›` should be elements from other XML namespaces such as RDF, FOAF, etc..