The clip-path CSS property creates a clipping region that sets what part of an element should be shown.
clip-path-values ::= ([‹m-b-p-c-box›] [‹basic-shape›]) | ‹clip-source›
A clip-source is a reference to a SVG ‹clipPath› element.
THe shape-outside property sets a shape around which inline elements will flow.
shape-outside ::= ‹m-b-p-c-box›||‹basic-shape›||‹image›
if you use an image for shape-outside, it will compute it based on that images alpha channel.
scroll-behavior only influences programmatic scrolling, i.e. not done by the user manually.
scroll-behavior: smooth makes scrolling a smooth animation instead of an instant transition.

appearance is a property to change the native styling of an element, or to remove it.
appearance is often used prefixed, especially to target one of the many non-standard values for this property

user-select controls whether/how the user can select text.
user-select-values ::= none|auto|text|all

resize controls whether/how an element is resizable, which generally only works on devices with pointing devices.
resize-values ::= none|both|horizontal|vertical

opacity: ‹number-or-percentage-0-1›

overflow is a shorthand for overflow-x and overflow-y
overflow-specifier-values ::= visible|hidden|clip|scroll|auto

overflow-anchor determines if our scroll position is anchored to the scroll offset from the top (`none`) or to the current position in the content (`auto`), which is relevant when we add more content on top. 

mix-blend-mode and background-blend-mode both take a ‹blend-mode›
⟮Background-blend-mode⟯ regulates blending between (⟮a⟯) ⟮background-image⟯(⟮s⟯) as well as the ⟮background-color⟯.
⟮mix-blend-mode⟯ regulates blending between ⟮the⟯ ⟮element's⟯ ⟮content⟯, ⟮the⟯ ⟮element's⟯ ⟮parents content⟯, and ⟮the⟯ ⟮element's⟯ ⟮background⟯.
css ‹blend-modes› are the usual blend modes



##### custom counting

counter-reset and counter-increment and the css functions counter() and counters() are used to defined custom counters for counting().
counter-reset assigns a counter of name to value.
counter-reset defaults a counter to 0 if no value is specified.
counter-reset is also used initialize a counter.
counter-reset: ‹counter-name› [‹value›]{,‹counter-name› [‹value›]}
counter-increment: ‹counter-name› [‹value›]{‹counter-name› [‹value›]}
counter-increment: increments the counter by value (default 1) for each time it is encountered.
counter-reset on descendants creates a new counter, instead of assigning to the original counter.
counter-name ::= ‹custom-ident›
counter ::= ‹counter()›|‹counters()›
counter() ::= counter\(‹counter-name›[, ‹counter-style›]\)
counters() ::= counters\(‹counter-name›, ‹string› [, ‹counter-style›]\)
counter-style ::= ‹list-style-type›|‹@counter-style›
The css functions counter() and counters() takes a necessary first argument of the name of the counter. 
counters() differs from counter() in that it takes a middle argument of a string, and separates multiple instances of the counter with the given string.

```
ol {
  counter-reset: section;                /* Creates a new instance of the
                                            section counter with each ol
                                            element */
  list-style-type: none;
}

li::before {
  counter-increment: section;            /* Increments only this instance
                                            of the section counter */
  content: counters(section, ".") " ";   /* Combines the values of all instances
                                            of the section counter, separated
                                            by a period */
}
```

```
‹ol›
  ‹li›item‹/li›          ‹!-- 1     --›
  ‹li›item               ‹!-- 2     --›
    ‹ol›
      ‹li›item‹/li›      ‹!-- 2.1   --›
      ‹li›item‹/li›      ‹!-- 2.2   --›
      ‹li›item           ‹!-- 2.3   --›
        ‹ol›
          ‹li›item‹/li›  ‹!-- 2.3.1 --›
          ‹li›item‹/li›  ‹!-- 2.3.2 --›
        ‹/ol›
        ‹ol›
          ‹li›item‹/li›  ‹!-- 2.3.1 --›
          ‹li›item‹/li›  ‹!-- 2.3.2 --›
          ‹li›item‹/li›  ‹!-- 2.3.3 --›
        ‹/ol›
      ‹/li›
      ‹li›item‹/li›      ‹!-- 2.4   --›
    ‹/ol›
  ‹/li›
  ‹li›item‹/li›          ‹!-- 3     --›
  ‹li›item‹/li›          ‹!-- 4     --›
‹/ol›
‹ol›
  ‹li›item‹/li›          ‹!-- 1     --›
  ‹li›item‹/li›          ‹!-- 2     --›
‹/ol›
```

## transform

Transforms can be applied to both SVG and HTML elements.
Transforms are changes to the elements geometry.
transforms are applied via the `transform` property.
the `transform` property takes one or more space-separated transform functions.
The general types of transforms are rotate, scale, skew, translate.
Most general types of transform have 5 transform functions
`whateverX()`, `whateverY()`, `whateverZ()` take one value and transform in the specified axis.
`whatever()` takes two values and transforms in the 2d plane.
`whatever3d()` takes 3d values and transforms in 3d space.
Skew doesn't work in 3d and thus doesn't have `skewZ()` nor `skew3d()`

transformations can be united in the `matrix()` (for 2d) and `matrix3d()` (for 3d) function.

skewing distorts by a certain angle, as if you grabbed a certain corner and pulled them along a certain value.

In addition, there is one more transform funtion, `perspective()`

## tables

The empty-cells CSS property sets whether borders and backgrounds appear around ‹table› cells that have no visible content.
The border-collapse CSS property sets whether cells inside a ‹table› have shared or separate borders.
The caption-side CSS property puts the content of a table's ‹caption› on the specified side. 
The table-layout CSS property sets the algorithm used to lay out ‹table› cells, rows, and columns.
auto
By default, most browsers use an automatic table layout algorithm. The widths of the table and its cells are adjusted to fit the content.

fixed
Table and column widths are set by the widths of table and col elements or by the width of the first row of cells. Cells in subsequent rows do not affect column widths.
border-spacing is the equivalent of gap, but for tables. 
border-spacing applies only when border-collapse is separate.
visibility: collapse: For ‹table› rows, columns, column groups, and row groups, the row(s) or column(s) are hidden and the space they would have occupied is removed (as if display: none were applied to the column/row of the table). However, the size of other rows and columns is still calculated as though the cells in the collapsed row(s) or column(s) are present. 