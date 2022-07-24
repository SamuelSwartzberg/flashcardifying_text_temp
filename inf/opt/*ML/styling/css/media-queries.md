# media queries

Media queries and feature queries have a fair amount of similarities.
Media queries are boolean assertions if the current user's environment/device/UA is a certain way.
Feature queries are boolean assertions if a browser supports a certain set of CSS properties with certain values.
A media query is either true or false for the current user's combination of environment/device/UA.
A feature query is either true or false for the current user's CSS feature set.
Media queries are built from media types, media features, and logical operators.
Media types describe the broad category of device or UA.
Media features describe a specific feature of the environment/device/UA, which can be true or false.
Media queries are most commonly used by @media at-rules, and less frequently by @import at-rules (specified after the meat and potatoes), the media attribute in HTML, and in JS by Window.matchMedia() and MediaQueryList.addListener().
A feature query consists of "feature features" (my coinage) and logical operators.

## media types

Media types

all|all devices
print|inteded for printing
screen|intended for screens
speech|intended for speech synthesizers/screen readers

Media types are specified as boolean attributes, i.e. the presence of the keyword is enough

## media features

Media features
orientation describes relationship of width and height of the viewport (not the device/screen!)
orientation is portrait if height › width and landscape if width › height
color tests for color depth per channel
resolution tests for pixel density
height tests for height of the viewport
width tests for width of the viewport
aspect-ratio tests for a certain aspect ratio
hover testss whether the user's primary input mechanism can hover
prefers-reduced-motion is used to detect if the user has requested that the system minimize the amount of non-essential motion it uses (this is often an OS-level toggle)

Media features as well as feature features are specified in a (key: value) syntax (parentheses not optional)
for feature features for (key: value), key is a property and value is a possible value.
Media features that are range features can take a min- and a max- version of that feature to specify a range of acceptable values
Level 4 media queries support a more intuitive syntax for range features using ‹, ›, = etc.
Media featurs that are range features: color, resolution, height, width, aspect-ratio

## logical ops

The logical operators that are valid within media queries are and and not (which work as expected), and the comma, which acts as an or, but cannot be nested (i.e. can only combine media queries at the top level). 
as of Level 3 media queries (changes in level 4 media queries), the not keyword can't be used to negate an individual media feature expression, only an entire media query.
feature queries supports similar logical operators to media queries, but instead of the comma, it has a normal or operator, and not can also invert parts of feature queries.
The operator only is mainly useful for preventing browsers from matching if part of the media query applies, and there is another part that they don't understand (e.g. older browsers) and thus ignore.

## atrules

An @media at-rule is a conditional which takes a media query and executes the CSS contained within if the media query is true.
Multiple @media at-rules may apply at the same time
Syntax @media ‹media-query› ‹block›

@media screen and (min-width: 900px) {
  article {
    padding: 1rem 3rem;
  }
}

A @supports at-rule is a conditional which takes a feature query

## in HTML

The media HTML attribute may be applied to ‹link›, ‹source›, or ‹style›.
The media HTML attribute indicates when to load the specific resource.

## in JS

### media queries

window.matchMedia() takes a media query and returns a MediaQueryList object, whose matches property indicates exactly that.
To react to changes in media features/types, you can register the change event on the MediaQueryList boject.