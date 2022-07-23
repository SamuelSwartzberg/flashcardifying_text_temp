# Props

A shorthand property is a css property that allows setting multiple other properties at once.
shorthand properties in css try to not force a specific order, where semantically possible.
If a value is not set within a shorthand property, it is set to its initial value, overriding subvalues.
Using inherit as a value of many within a shorthand property is invalid.

## property enabling

### vendor prefixes

vendor prefixes have the syntax -‹vendorname›-‹propertyname›
webkit|any webkit-based (and thus also blink-based) browser besides edge
moz|firefox
o|pre-webkit opera
ms|IE and edge

vendor prefixes were designed to allow experimenting with experimental CSS features without having to worry about future changes to the standard creating breaking changes.
The problem with vendor prefixes is that in fact, vendor-prefixed properties just got used in productio as well.
As of ~2020, the trend is away from using vendor prefixes, and instead using user-controlled experimental flags.
