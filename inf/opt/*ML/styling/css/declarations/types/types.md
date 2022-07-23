# types

## inherited, initial, etc.

any property is inherited or not in its behavior when no value is assigned
inherited properties default to inheriting
non-inherited properties default to the initial value
some initial values are unintuitive, since we rarely see them, as they are typically overwritten by UA stylesheets
On the root element, even inherited properties recieve their initial values if not otherwise specified.
Keyword inherit/initial to force the inherited/initial value.
unset: choose between inherit and initial based on if the thing is inherited or non-inherited
The revert CSS keyword reverts the cascaded value of the property from its current value to the value the property would have had if no changes had been made by the current cascade origin to the current element.
If used by a site's own styles (the author origin), revert rolls back the property's cascaded value to the user's custom style, if one exists; otherwise, it rolls the style back to the user agent's default style.
If used in a user's custom stylesheet, or if the style was applied by the user (the user origin), revert rolls back the cascaded value to the user agent's default style.
If used within the user agent's default styles, this keyword is functionally equivalent to unset. 
The revert keyword is mainly useful to revert to the user agents default style instead of the often-useless initial value.

The all property takes one of initial|inherit|unset|revert to reset everything but direction and unicode-bidi

## Functions

CSS functional notation is a type of CSS value that can represent more complex data types or invoke special data processing or calculations.
The syntax of CSS functional notation is: ‹name›\([‹argument› {(,| ) ‹argument›}]\)

url()

The calc() CSS function creates a math context, i.e. allows calculation as one would expect. 
min(), max() and clamp() also creates math contexts.
calc-sum ::= ‹calc-product›{ (+|-) ‹calc-product›}
calc-product ::= ‹calc-value›{ * ‹calc-value›| / ‹number›}
calc-value ::= ‹mathable›|\(‹calc-sum›\)
+ and - operators must be surrounded by whitespace within CSS calc
calc ::= calc(‹calc-sum›)

The min() CSS function evaluates to the smallest (most negative) value of a specified list.
The max() CSS function evaluates to the largest (most positive) value of a specified list.
list-of-calc-sums ::= ‹calc-sum›{, ‹calc-sum›}
min ::= min(‹list-of-calc-sums›)
max ::= max(‹list-of-calc-sums›)

The clamp() CSS function clamps a value between an upper and lower bound. clamp() enables selecting a middle value within a range of values between a defined minimum and maximum. It takes three parameters: a minimum value, a preferred value, and a maximum allowed value. 
clamp ::= clamp(‹list-of-calc-sums›, ‹list-of-calc-sums›, ‹list-of-calc-sums›)

The attr() function takes the name of an attribute (of the HTML element) and resolves to its value as a string.
Currently, attr() can only usefully be used as a value for content.

## simple types

the ‹url› datatype is a css function
url ::= url(‹string›) # where string must be a valid url or path or the ID of a SVG shape

dimension ::= ‹length›|‹time›|‹frequency›|‹resolution›|‹angle›

CSS dimensions are always a number followed by a unit with no space inbetween

mathable (not an official name) ::= ‹number›|‹dimension›|‹percentage› 
resolution ::= ‹number›‹resolution-unit›
resolution-unit ::= dpi|dpcm|dppx|x
x is an alias for dppx
dppx = dots per px
In CSS, since 1 in is fixed as 96 px, 1dppx is 96 dpi.
frequency ::= ‹number›‹frequency-unit›
frequency-unit ::= Hz|kHz
angle ::= ‹number›‹angle-unit›
angle-unit ::= deg|grad|rad|turn
time ::= ‹number›‹time-unit›
time-unit :: s|ms

turn  Represents an angle in a number of turns. One full circle is 1turn

// ‹integer›, ‹number›, ‹percentage› defined elsewhere

m-b-p-c-box ::= margin-box|border-box|padding-box|content-box
b-p-c-box-text ::= border-box|padding-box|content-box|text
b-p-c-box ::= border-box|padding-box|content-box
b-c-box ::= border-box|content-box

## ‹basic-shape›

basic-shape ::= ‹inset›|‹circle›|‹ellipse›|‹polygon›|‹path›
inset ::= inset\{‹length-percentage-edges›[ round ‹border-radius›]\}
circle ::= circle\(‹size›[at ‹position›]\)
ellipse ::= ellipse\(‹size› [at ‹position›\)
path ::= path\(‹svg-path-specifier›\)