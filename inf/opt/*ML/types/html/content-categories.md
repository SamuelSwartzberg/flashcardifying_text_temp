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