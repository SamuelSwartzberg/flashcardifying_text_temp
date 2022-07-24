# flexbox, grid and columns

Flex or grid containers are declared by setting display to flex/inline-flex or grid/inline-grid.
A grid (as a layout, not just in CSS) is made up of horizontal and vertical (and sometimes angular) »grid lines« that intersect to define n »grid cells« 
In a grid layout, multiple adjacent cells (in CSS, forming a rectangle) are called a grid area.
In a grid layout, the area between two adjacent grid lines is called a grid track.

The order CSS property sets the order to lay out an item in a flex or grid container. Items in a container are sorted by ascending order value and then by their source code order.

## box alignment properties

The box alignment properties in CSS are a set of 6 properties that control alignment of boxes within other boxes. 
The box alignment properties can be described along two metrics, which axis they apply to, and whose position they control.
All six box alignment properties 
Of the six box alignment properties, justify-self and justify-items have no effect in flexbox.
Theoretically, all box alignment properties besides align-self and align-items should also work to position block containers, but this is unimplemented.

justify-* adjusts things in the inline base direction (ltr in the default setup) (unless flexbox)
align-* adjusts things in the block flow direction (top to bottom in the default setup) (unless flexbox)
place-* is a shorthand for align-* justify*, if only one value is specified, it generally applies to both.
`display: grid` and `place-items: center` is a very easy way to center an item in CSS.

For flexbox, what justify-* and align-* align relative to are the main axis/cross axis, respectively.

*-content adjusts foo's content within foo. https://drafts.csswg.org/css-align/images/content-example.svg
*-self adjusts foo within foo's parent. https://drafts.csswg.org/css-align/images/self-example.svg
*-items adjusts all of foo's children within their box. https://drafts.csswg.org/css-align/images/items-example.svg

The alignment subject is the thing being aligned by the property:
the alignment subject  for *-self is the margin box of foo.
the alignment subject for *-content is defined by its layout mode/formatting context.

the alignment container is the thing within which the alignment subject is a ligned with.
the alignment container is generally the containing block container box.

the box alignment properties take three types of keywords: positional alignment, baselinge alginement, distributed alignment
type of keyword|function
positional alignment|alignment to absolute position within alignment container
baseline alignment|alignment as relationship between the baselines of multiple alignment subjects
distributed alignment|alignment as distribution of space among/between alignment subjects

positional-alignment keywords may be the simple center, start, and end, flex-start/flex-end, self-start/self-end, or left/right.
flex-start and flex-end behave like start/end.
the difference between start/end and left/right is that the former respect the inline base direction and the block flow direction, while the latter is always left/right no matter what.
The start and end keywords use the inline base direction of the alignment container, the self-start and self-end keywords use the inline base direction of the alignment subject.


baseline-alignment-keyword ::= [first|last] baseline
specifying only baseline as a  baseline-alignment-keyword computes to first baseline

A baseline-sharing group is composed of boxes that participate in baseline alignment together. 
Boxes in a baseline-sharing group are aligned to each other using their alignment baselines. 
A baseline set is a set of baselines, generally only one as long as you are not mixing writing systems.
Each line has a baseline set.
Each box potentially has a first/last baseline set which is the baseline set of the first/last line of box.
The alignment baseline is a baseline in its baseline set, generally the dominant baseline (within a shared alignment context).
Boxes have a »shared alignment context « when they are either (no mixing and matching) table cells, grid items and flex items of the same inline base axis (though not direction), or between grid items of the same block flow axis (though not direction)
A baseline-sharing group where they share an alignment context, as long as they have compatible baseline alignment preferences.
Two boxes have compatible baseline alignment preferences if they have the same block flow direction and the same baseline alignment preferences or opposite block flow direction and opposite baseline alignment preferences.
The first and last values give a box a baseline alignment preference: either “first” or “last”, respectively.

distributed-alignment-keyword ::= space-between|space-around|space-evenly|stretch
space-between|space only between elements, no space at borders|[xxx      yy      zzzz]
space-around|space on every side, space at borders is half size|[  xxx    yy    zzzz  ]
space-evenly|space on every side, every space is the same size|[   xxx   yy   zzzz   ]
stretch|no space, size is increased equally|[xxxxxxxyyyyyyyzzzzzzz]

## flexbox axes

For flexbox, if flex-direction is row or row-reverse, the main axis corresponds to the inline base direction, and the cross axis corresponds to to the block flow direction.
For flexbox, if flex-direction is column or column-reverse, the main axis corresponds to the block flow direction, and the cross axis corresponds to to the inline base direction.

## gaps

the gap, row-gap and column-gap specifiy gutters between items in a flex/multi-column/grid container.
gap is a shorthand for row-gap and column-gap, if only one value is specified, it sets them to the same value.
the three gap properties take a ‹length-percentage›
For multi-column containers, row-gap currently does nothing.
for flex containers, column-gap specifies minimum spacing between flex items, and row-gap specifies minimum spacing between flex lines if flex-direction is row or row-reverse, otherwise what column-gap and row-gap do is reversed.
For the gap, row-gap and column-gap there exist the now archaic grid-* aliases.

## grid

Fundamentally, the grid consists of two tasks: defining a grid ＆ its sizes, and placing items within that grid.

### defining and sizing a grid

In CSS, there are two kinds of ways to define the grid and its sizes, using the explicit or using the implicit grid.
grid-auto*|implicit grid
grid-template*|explicit grid

there are four grid-template properties, grid-template-columns ＆ -rows, grid-template-areas as well as the shorthand grid-template.
there are three grid-auto properties, grid-auto-column ＆ -rows and grid-flow

grid-template-columns ＆ -rows define how many columns/rows of which size the explicit grid wil contain.
grid-auto-columns ＆ -rows define what size columns/rows the auto placement algorithm will add.
specifying multiple values for grid-auto-columns ＆ -rows specifies a pattern which to follow.
grid-template-columns ＆ rows take the same values, which i will call ‹grid-template-values›

grid-template-rc-values ::= {[‹line-names› ](‹flex-l-p-min-max-auto-mm›|‹repeat›)}[ ‹line-names›]
grid-auto-values ::= ‹flex-l-p-min-max-auto-mm› {‹flex-l-p-min-max-auto-mm›}

minmax ::= minmax\(‹l-p-min-max-auto›|‹flex-l-p-min-max-auto›\)
The minmax() CSS function defines a size range greater than or equal to min and less than or equal to max. It is used with CSS Grids.
l-p-mm ::= ‹length-percentage›|‹minmax›
flex-l-p-min-max-auto-mm ::= ‹flex-l-p-min-max-auto›|‹minmax›
line-names-and-track-size ::= [‹line-names› ]‹flex-l-p-min-max-auto-mm›

the repeat() function repeats the pattern specified for the amount of times specified, or until something is full.
the auto-* keywords for repeat creates rows until creating more would overflow.
the auto-* keywords for repeat treat the track sizes of tracks that can shrink or grow as their maximum size, unless that maximum size is infinite/indefinite.
the difference between the auto-fill and auto-fit keywords is that auto-fit will collapse any empty repeated tracks that still exist after grid-items re placed, while auto-fill will not.

Using grid-template properties, you can assign line names to grid lines, to be used later for positioning.
If the same name is used for multiple grid lines, they will be numbered by a so-called occurrence number starting at the second one, which is separated by a space
Grid lines are numbered staring at 1

repeat ::= repeat\((‹integer›|‹auto-keyword›), {‹line-names-and-track-size›}[ ‹line-names›]\)
auto-keyword ::= auto-fill|auto-fit # my own name

line-names ::= [‹custom-ident›{ ‹custom-ident›}]

grid-template-area manually created named grid areas made up of the specified cells.
Within grid-template-areas . refers to an empty grid cell

grid-template-area-values ::= ‹grid-string›{‹grid-string›}
grid-string ::= "‹cell-specifier›{ { }‹cell-specifier›}"
cell-specifier ::= ‹string›|.{.}

grid-template-values ::= ‹grid-template-row-columns›|‹grid-template-row-coolumns-areas›
grid-template-row-columns ::= ‹grid-template-rc-values› / ‹grid-template-rc-values›
grid-template-row-coolumns-areas ::= {‹grid-string› ‹flex-l-p-min-max-auto-mm›} / ‹grid-template-rc-values›

grid-auto-flow-values ::= [row | column] [dense]
grid-auto-flow: row makes it add auto-positioned elements to rows, adding new rows as necessary (and respectively for grid-auto-flow: column)
The dense keyword for grid-auto-flow makes it use the dense algorithm, otherwise a sparse algorithm is used

dense algorithm|attempt to fill holes earlier in the grid
sparse algorithm|never backtrack to fill holes

specifying grid-lines with -start/-end that enclose a rectangle creates the relevant grid-area automatically 
specifying grid-areas creates the relevant grid lines with -start/-end automatically 

the grid css property is a shorthand for grid-template-* and grid-auto-*, 6/7 properties in total

### placing items

grid areas and grid lines
grid-area allows placing an item at a grid-area created manually or automatically, taking up that space
grid-area dots

grid-column/row-start/end take the same set of values, ‹grid-line›
grid-column/row-start/end specify the edges of an items grid area
Most basically, grid-column/row-start/end either position using an integer, or using a grid line name.
specifying an integer for grid-column/row-start/end positions it at that number gridline.
specifying an integer and span for grid-column/row-start/end positions it that many grid lines from the start (if end) or from the end (if start).
specifying an custom-ident while also specifying an integer and span for grid-column/row-start/end positions it that many grid lines from the start (if end) or from the end (if start), counting only gri lines with the custom-ident
specifying a custom-ident for grid-column/row-start/end positions it at ‹custom-ident›-start(if start)/-end(if end)
grid-line ::= auto | ‹custom-ident› | [span] [‹integer›] [‹custom-ident›] # slightly simplified
grid-row/column are shorthand for -start/-end
grid-row-values, grid-column-values ::= ‹grid-line›[ / ‹grid-line›]
grid-area basically takes two kind of values, the name of a grid area, or four specifiers for row/column start/end, specified in the order rs / cs / re / ce.

grid items may be placed in the same area, i.e. they may overlap, even completely.

## flex

flex-flow is a shorthand for flex-direction and flex-wrap
flex-wrap may take the values nowrap, wrap, wrap-reverse.
flex-direction may take the values row, row-reverse, column, column-reverse

flex is a shorthand of flex-grow flex-shrink flex-basis (in that order)
flex-grow and flex-shrink specify a factor, which specifies how fast that element should grow/shrink relative to other flex elements.
flex-basis specifies the initial size of a flex item along its main axis.

By default flex items don't shrink below their minimum content size. To change this, set the item's min-width or min-height.

## columns

The column-fill CSS property controls how an element's contents are balanced when broken into column fragmentainers (= column boxes)
auto|fill column boxes sequentially in the inline base direction, until the column box is full
balance|fill column boxes so that they have roughly the same height.

columns is a shorthand for column-count and column-width.
column-span: all transforms an element into a spanning element.
A spanning element spans all columns.

column-span specifies a maximum amount of columns
column-width specifies a minimum width of columns