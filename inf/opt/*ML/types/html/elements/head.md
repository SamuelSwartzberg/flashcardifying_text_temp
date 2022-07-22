
# head

The ‹head› element contains metadata about the document.
The ‹head› element can contain ‹base›, ‹meta›, ‹title›, ‹link›, ‹style›, ‹script›, ‹noscript› and ‹template›

## title

the ‹title› element defines the documents title
the ‹title› element is mainly shown in the browsers tab name / title bar, as well as search engines.
the ‹title› element can only contain text, not tags.
the ‹title› element's content should change in response to major state changes.

## base

the ‹base› element specifies the base URL for the document with its href attribute.
The ‹base› element optionally accepts a target argument to choose the browsing context links open in by default.

## basefont

The ‹basefont› element used to specify the default font (color, fontface etc.) but is now deprecated.

## meta

The ‹meta› HTML element represents metadata that cannot be represented by other HTML meta-related elements.
The ‹meta› element has four mutually exclusive modes.
‹meta› specifies the value in its content attribute, except when using `charset` or `itemprop` keys.

### http-equiv mode

the `http-equiv` attribute of `‹meta›` is there to specify certain HTTP headers within HTML itself.
When using `http-equiv`, `http-equiv` contains the header name, and `content` contains the header value.

### charset mode

`‹meta›` can be used to specify the character encoding of the page by using the `charset` attribute.

### itemprop mode

`‹meta›` may be used to set HTML microdata via the `itemprop` attribute.

### name

If the `name` attribute is set, the `‹meta›` element provides basic generic metadata.

#### various meta `name`s

author|document author
description|short blurb about website, may be used in search results

#### `name="theme-color"`

theme-color|indicates a suggested color that user agents should use to customize the display of the page or of the surrounding user interface. The content attribute contains a valid CSS ‹color›.

#### `name="viewport"`

##### function

The meta tag with name viewport is used to customize/constrain the viewport.

##### background

by defaults, narrow screen devices (e.g. mobiles) render pages in a virtual window or viewport, which is usually wider than the screen, and then shrink the rendered result down so it can all be seen at once, essentially lying about their viewport size, to make non-mobile-optimized pages not look terrible.
without width=device-width, many media queries will never apply

##### syntax

For the meta tag with name viewport, the content value has the following syntax: ‹key›=‹value›{, ‹key›=‹value›}

##### key=values

width=‹integer›|set size of the viewport to ‹integer› pixels
width=device-width|prevent browser from lying about their width
initial-scale=‹integer›|set default zoom level on page
user-scalable=("yes"|"no")|allow users to zoom or not
maximum-scale=‹integer›|set maximum zoom level
