# canvas

The ‹canvas› element allows drawing graphics and animations via the canvas scripting API or the WebGL API
Sizing the canvas using CSS versus HTML

The displayed size of the canvas can be changed using CSS, but if you do this the image is scaled during rendering to fit the styled size, which can make the final graphics rendering end up being distorted.

It is better to specify your canvas dimensions by setting the width and height attributes directly on the ‹canvas› elements, either directly in the HTML or by using JavaScript.