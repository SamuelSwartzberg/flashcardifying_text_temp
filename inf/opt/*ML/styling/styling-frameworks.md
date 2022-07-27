# styling frameworks

»A styling framework« is a framework for front-end design.

## variable-based

### basics

#### style placeholders

A style placeholder is a placeholder of some kind that can then be filled with precise styling later.
A scale style placeholder set is a set of style placeholders that hold values of a given style scale.
^e.g. text-lg

#### style variables

A style variable is a variable holding some predefined style information
A simple style variable is a style variable that consists of a single value.
A style scale is a style variable that consists of an array of values that gets assigned to a scale style placeholder set.
A style associative array is a style variable is an associative array of style variables.
A pre-defined style placeholder/style variable is a style placeholder/style variable whose name and expected type are well-defined.

#### style object

A style object is a set of style variables.

### applied

The 1-5 scale is a scale used for various style scales that are fairly arbitrary.
A semantic color is a style variable for a color that has a semantic name (such as primary, warn)

## properties

### breakpoints

A breakpoint is a 
Pretty much all styling frameworks have chosent the concept of breakpoints to abstract over width-based media queries.
A breakpoint corresponds to a range of widths
Common breakpoint names:
Extra small|no name (default)|Tailwind, Chakra, Bootstrap
Small|sm|Tailwind, Chakra, Bootstrap
Medium|md|Tailwind, Chakra, Bootstrap
Large|lg|Tailwind, Chakra, Bootstrap
Extra large|xl|Tailwind, Chakra, Bootstrap
Extra extra large|2xl|Tailwind, Chakra
Extra extra large|xxl|Bootstrap.
For pretty much all frameworks, breakpoints select this size and up.
The reason breakpoints generally select this size and up in most frameworks is that they are mobile first.
Since breakpoints generally select this size and up, you need to overwrite breakpoints for larger sizes if you want it to only apply to one size.
Since breakpoints select this size and up, one typically writes the style for the smallest size first and then layers  styles for larger form factors on top.


## CSS

»A CSS framework« is a styling framework that does most of its things in CSS.

### individual frameworks

#### bootstrap

Bootstrap uses a 1-5 scale for `order` and spacers. 
Bootstrap's theme-colors are semantic colors.

#### layout

##### bootstrap grid system

Bootstrap pioneered the bootstrap grid system.
The bootstrap grid system consists of containers, rows, and columns.
The boostrap grid system has been adopted by other systems such as ionic.
A container (or something else) contains n rows.
A row contains 12 template columns.
Actual columns can be 12 or more template columns wide.
Having a row with elements adding up to more than 12 template columns will force wrapping.
Offsets are specified in template columns and are used to take up column space without filling it with content.
Bootstrap grid systems feature gutters both between rows and columns, which you can customize.
The bootstrap grid system is built with flexbox.
Since the bootstrap grid system is built with flexbox, you can change the behavior of the grid system by using flexbox-related utilites.

containers are mainly for adding padding.
Containers are, depending on the exact class, either 100% of the page, or 100% with some spacing left and right

###### implementation

in bootstrap, columns are specified .col-‹meas-col›
in bootstrap, a row consisting of columns with n measurement columns width is specified as .row-cols-‹meas-col›

material color representation