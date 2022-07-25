# layering

## blending

Blend modes (or mixing modes[1]) in digital image editing and computer graphics are used to determine how two layers are blended with each other. 
Blend modes typically use values from 0 to 1 for the channels for the math.
When describing blend modes, t denotes the top layer and b the bottom layer
In general, when channel is specified, assume it is done to each channel.
normal|use alpha compositing
multiply|channel_t * channel_b|result will be darker (since two numbers less than 1 multiplied will always be smaller)
screen|1 - (1 - channel_t) (1 - channel_b)|result will be always be lighter

## transparency ＆ opacity

The ⟮inverse of⟯ ⟮transparency⟯ is ⟮opacity⟯ 

transparency/opacity|visibility
⟮0% transparency / 100% opacity⟯|⟮completely visible⟯
⟮100% transparency / 0% opacity⟯|⟮completely invisible⟯
⟮30% transparency /70% opacity⟯|⟮70% visible⟯
⟮55% transparency /45% opacity⟯|⟮45% visible⟯