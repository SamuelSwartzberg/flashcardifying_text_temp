# content categories

TODO: This probably should shape and partially be integrated in my division of elements.

Most HTML elements are a member of one or more content categories — these categories group elements that share common characteristics. This is a loose grouping (it doesn't actually create a relationship among elements of these categories), but they help define and describe the categories' shared behavior and their associated rules.

Flow content
Flow content is a broad category that encompasses most elements that can go inside the ‹body› element.

Heading content is a subset of flow content that includes h1-h6, and theoretically though not relevantly the never-implemented the-spec-is-lying-about-it hgroup
Sectoning content is a subset of flow content that was supposed to be relevant for the outline algorithm that was never implemented, and so is a somewhat-irrelevant category.

Phrasing content is a subset of flow content that defines the text and the markup it contains, and can be used everywhere flow content is expected. 

Content is palpable when it's neither empty or hidden; it is content that is rendered and is substantive. Elements whose model is flow content should have at least one node which is palpable.

## embedded content

Embedded content is a subset of flow content that imports another resource or inserts content from another mark-up language or namespace into the document, and can be used everywhere flow content is expected.

embedded cotnetn cotnains the media elements video and audio, image-related elements img, picture, and svg, math, frames, canvas, object, embed plus the obsolete elements applet

‹applet› was used to embed java applets, but is now obsolete.
The ‹object› HTML element represents an external resource, which can be treated as an image, a nested browsing context, or a resource to be handled by a plugin.
The ‹param› HTML element defines parameters for an ‹object› element.
The ‹embed› HTML element embeds external content at the specified point in the document. This content is provided by an external application or other source of interactive content such as a browser plug-in.

‹math› and ‹svg› embed content in HTML from MathML and SVG respectively

## replaced elements

In CSS, a replaced element is an element whose representation is outside the scope of CSS; they're external objects whose representation is independent of the CSS formatting model.
Typical replaced elements are:
‹iframe›
‹video›
‹embed›
flex-container:‹img›

Some elements are treated as replaced elements only in specific cases:

‹option›
‹audio›
‹canvas›
‹object›
‹applet›

Objects inserted using the content property are anonymous replaced elements.

The only way CSS can style replaced elements is by controlling the positioning of the element's content within its box.
for object-* to be relevant, the box of the replaced element must be of a different size than the replaced element

The object-whatever properties target replaced elements.

object-position takes a ‹position› value, and controls where the replaced element goes in its box

object-fit|aspect-ratio|clipping/letterboxing/framing/none
cover|preserve|letterboxing
contain|preserve|clipping
fill|stretch|none
none|preserve|either clipping or framing (not resized at all)
scale-down|perserve|letterbox or framing (contain or none, whichever is smaller)

#### images

image-rendering controls how an image upscales. 
image-rendering: pixelated - image will seem to be composed of large pixels
image-rendering: crisp-edges - preserve edges
image-rendering: auto - browser-defined algorithm

#### frames

A ⟮frame⟯ is ⟮a part of a webpage⟯ which ⟮displays a different webpage (or a part thereof⟯) within. 
A ⟮frame⟯ has ⟮state⟯ ⟮independent of its parent webpage⟯. 
The ⟮two types of frames⟯ that HTML has/had are ⟮‹frame›⟯ and ⟮‹iframe›⟯ 
Both ⟮‹frame›⟯ and ⟮‹iframe›⟯ need(ed) a ⟮src⟯ to be useful. 
⟮‹frame›s⟯ would have been ⟮placed within⟯ a ⟮‹frameset›⟯. 
⟮‹frameset›⟯ would have ⟮replaced⟯ ⟮body⟯. 
A site using ⟮‹frameset›⟯ was basically ⟮made up of⟯ ⟮many different HTML documents⟯. 
A site using ⟮‹frameset›⟯  would have had the advantage tha⟮t only a part of the site (e.g. the main content, but not headers and footers⟯) would ⟮have to be fetched when navigating⟯. 
The ⟮‹noframes›⟯ was provided for browsers that ⟮did not support frames⟯. 
As of ⟮HTML5⟯, ⟮‹frame› and ‹frameset›⟯ are ⟮deprecated⟯, but ⟮iframe⟯ is not. 
⟮‹frame›s⟯ were ⟮deprecated⟯ because  ⟮their intraction with the same-origin policy could be a nightmare⟯, because ⟮copyright infringemenet was easy⟯, and because ⟮of accesibility/usability problems⟯. 
⟮iframe⟯ is short for ⟮inline frame⟯ 