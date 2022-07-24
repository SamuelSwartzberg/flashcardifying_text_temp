## width, height

width and height each have corresponding min- and max- properties
power of width and height properties: min- › max- › ø
width and height and corresponding min/max values take the following values: ‹lpminmaxauto›|fit-content(‹length-percentage›)

What width and height size depends on the box-sizing property
content-box|width and height size content-box
border-box|width and height size border-box

## position

position-values ::= static|relative|absolute|fixed|sticky.
position: static is the default.
A positioned element is an element with any position but static.
A relatively positioned element is an element with position relative.
An absolutely positioned element is an element with position relative or fixed.
(only) for positioned elements, the `top`, `right`, `boottom`, `left` properties take effect
position|top, right, bottom, left offset from|takes up how much space
relative|where it would have been if it had position static|same as static
absolute|closed positioned ancestor|none
fixed|viewport or closest ancestor with tarnsform, perspective or filter set|none
sticky|nearest scrolling and block-level ancestor|same as static

top/right/bottom/left move the element away from the relevant edge, so that positive values for each have the effect of moving the element in the opposite direction
between top and bottom, top wins.
between left and right, the inline base direction wins.

position: fixed will always be visible at the same position
position: sticky will be in the flow of the document until scrolled to its offset specified by top, right, bottom, left, and then act like position: fixed

## Background

The background: property is a shorthand for ⟮background-clip⟯, ⟮background-color⟯, ⟮background-image⟯, ⟮background-origin⟯, ⟮background-position⟯, ⟮background-repeat⟯, ⟮background-size⟯ and ⟮background-attachment⟯
background-repeat may take a single value, which will specify both x and y, or two values, which apply to x and y respectively.
while single values for background-repeat generally specify both x and y, there are the single values repeat-x and repeat-y that will only repeat in the specified ways.
background-repeat takes one or two ‹repeat›s
background-color: ‹color›
background-color is rendered behind background-image
background-clip specifies where to clip the background, background-origin specifies from where the background should start, which may be the same, but often aren't
background-clip: ‹b-p-c-box-text›
background-origin: ‹b-p-c-box›
background-image: ‹image›

background-size-values: contain|cover|auto|(‹length-percentage› [‹length-percentage›])
background-size: contain/cover are similar in functionality to the object-fit values.
background-size: auto behaves similarly to object-fit: none.
giving background-size a length or percentage makes it exactly that wide if one value, or exactly that wide and high if two values.

All background properties may take a CSL to specify multiple backgrounds.


background-attachment specifies how the background interacts with scrolling (it has a bunch of keyword values that I can't remember)
background-position takes a ‹position› value to position the background.