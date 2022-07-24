
# animations ＆ transitions

CSS transitions allow changing between two property values to be gradual.
CSS animations allow animating between n property values arbitrarily complexly and potentially infinitely.

CSS animations and transitions share the functionality of the properties *-delay, *-duration, *-timing-function.
All properties related to CSS animations start animation-; all properties related to CSS transitions start transition-;
Within the transition/animation shorthand, the first ‹time› is interpreted in as animation/transition-duration; the second as animation/transition-delay
The four transition properties are the three also availabe for animations (transition-delay, -duration, -timing-function) plus transition-property.
the transition property is a shorthand for the four transition properties.
The 8 animation properties are the three also availabe for transitions (animation-delay, -duration, -timing-function) plus -direction, -fill-mode, -iteration-count, -name, -play-state.
For the animation shorthand, it is common to place animation-name last, to avoid conflicts with other names.

animation/transition-* accept a comma-separated list of values, where each value applies to a specific animation-name or transition-property 
animation/transition-delay: CSL of ‹time›s to specify a delay before starting the animation. negative values will start that far into the animatin/transition
animation/transition-duration: CSL of ‹time›s to specify how long the animation will take

transition-property: CSL of ‹custom-ident›s (or all) to specify which properties to transitions

animation-direction: CSL of normal|reverse|alternate|alternate-reverse:
normal|f f f f f …
reverse|b b b b b …
alternate|f b f b f …
alternate-reverse|b f b f b …

animation-fill-mode controls if the animation will apply its beginning/end styles before/after/both/not at all
animation-fill-mode gets its styles from the first/last keyframe encountered, which depends on animation-direction
none|animation styles don't apply when not executing
forwards|animation styles apply after animation is finished
backwards|animation styles apply before animation is started (only applies if there is a animation-delay)
both|animation styles apply before and after the animation

animation-iteration-count: CSL of (‹integer›|infinite)s to specify how many iterations the animation should play
animation-name: CSL of ‹custom-ident›s which represent the names of @keyframes describing the animations to apply
animation-play-state: CSL of (running|paused).

## timimg functions

animation/transition-timing-function: CSL of ‹time›s to specify how long the animation will take

easing-function ::= linear|‹cubic-bezier-easing-function›|‹step-easing-function›
cubic-bezier-easing-function ::= ‹cubic-bezier-keyword›|‹cubic-bezier-function›
cubic-bezier-keyword ::= ease|ease-in|ease-out|ease-in-out
cubic-bezier-function ::= cubic-bezier\(‹number›, ‹number›, ‹number›, ‹number›\)
step-easing-function ::= ‹step-keyword›|‹step-function›
step-keyword ::= step-start|step-end
step-function ::= steps\(‹integer›, ‹step-position›\)
step-position ::= jump-start|jump-end|jump-none|jump-both|start|end

cubic-bezier(x_p1, y_p1, x_p2, y_p2)

The step keywords or function make the animation run in discrete steps, instead of continuously

https://drafts.csswg.org/css-easing-1/step-easing-keyword-examples.svg

step-start|only show the end state
step-end|only show the start state

https://drafts.csswg.org/css-easing-1/step-easing-func-examples.svg

jump-start, start|first 'jump' happens at 0; last jump happens some time before end|ergo: 0 state will not be visible, 1 state will
jump-end, end|first 'jump' happens at some time after 0; last jump happens at end|ergo: 0 state will be visible, 1 state will not
jump-none|first 'jump' happens at some time after 0; last jump happens some time before end|ergo: 0 ＆ 1 state will both be visible
jump-both|first 'jump' happens at 0; last jump happens at 1|ergo: 0 ＆ 1 state will both not be visible

### cubic-bezier

Bezier curvers are frequently used for curves in computer graphics
A bezier curve is constructed from two or more points.
linear|2
quadratic|3
cubic|4
To construct a bezier function, one connect the points until one has only a curve between two points left.
To construct a linear bezier function, connect P0 and P1. You're done (it's a straight line).
To construct a quadratic bezier function, connect P0P1 and P1P2. Now, let a point travel on P0P1 and P1P2 from 0 to 1. connect P⎵P0P1⎵ and P⎵P1P2⎵ with a further line. Let a point travel on P⎵P0P1⎵P⎵P1P2⎵ from 0 to 1. This point describes the quadratic bezier curve.


flex-container:✫sm_ZS4fP%20(1).png✫
flex-container:✫sm_ZS4fP%20(1)%20copy.png✫✫sm_cubBezstep3.png✫

To construct a cubic bezier function, connect P0P1, P1P2, P2P3. Now, let a point travel on P0P1, P1P2 and P2P3 from 0 to 1. connect P⎵P0P1⎵ and P⎵P1P2⎵ as well as P⎵P1P2⎵ and P⎵P2P3⎵ with a further line. Let a point travel on P⎵P0P1⎵P⎵P1P2⎵ and on P⎵P1P2⎵P⎵P2P3⎵ from 0 to 1. Connect P⎵P⎵P0P1⎵P⎵P1P2⎵⎵ and P⎵P⎵P1P2⎵P⎵P2P3⎵⎵ with a further line. Let a point travel on P⎵P⎵P0P1⎵P⎵P1P2⎵⎵ P⎵P⎵P1P2⎵P⎵P2P3⎵⎵, this point describes the cubic bezier curve.

flex-container:✫sm_cubBezstep3-1.png✫✫sm__cat_acad_inf_code_css_bez60pc.png✫✫sm__cat_acad_inf_code_css_bez80pc.png✫

The CSS cubic-beziers map the dependent variable (y) to change in property, and the independent variable (x) to change in time.
For CSS, the x values of cubic-bezier must be between 0 and 1 (representing time), the y values are not limited in such a way
For the CSS cubic beziers only two points matter, the other two are fixed at (0|0) and (1|1)
For cubic-bezier(), the four parameters represent x1, y1; x2, y2

linear|✫sm_Screenshot%202020-06-02%20at%2001.59.05.png✫
ease-in-out|cubic-bezier(0.42, 0, 0.58, 1.0)|✫sm_Screenshot%202020-06-02%20at%2002.03.45.png✫
ease-in|cubic-bezier(0.42, 0, 1.0, 1.0)|✫sm_Screenshot%202020-06-02%20at%2002.02.33.png✫
ease|cubic-bezier(0.25, 0.1, 0.25, 1.0)|✫sm_Screenshot%202020-06-02%20at%2002.02.03.png✫
ease-out|cubic-bezier(0, 0, 0.58, 1.0)|✫sm_Screenshot%202020-06-02%20at%2002.03.02.png✫
