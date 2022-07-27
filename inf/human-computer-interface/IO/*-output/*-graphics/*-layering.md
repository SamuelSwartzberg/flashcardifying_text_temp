# layering

## transparency

Opacity/transparency is how visible/invisible something is.
opacity + transparency = 1

## blending

A blend mode is an algorithm that determines how two layers are blended with each other. 

### calculation

#### general

Blend modes typically use values from 0 to 1 for the channels for the math.
When describing blend modes, t denotes the top layer and b the bottom layer

#### various

The default blend mode may be called default/normal/none and uses alpha compositing/blending.
Alpha compositing/blending determining the result of layering with transparency.
The multiply blend mode = channel⎵t⎵ * channel⎵b⎵
^result will be darker (since two numbers less than 1 multiplied will always be smaller)
The screen blend mode = 1 - (1 - channel⎵t⎵)(1 - channel⎵b⎵)
^result will be always be lighter