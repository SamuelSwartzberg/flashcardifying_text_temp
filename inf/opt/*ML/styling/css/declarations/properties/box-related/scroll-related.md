## scroll-snap

In a basic sense, CSS scroll snap is for snapping to specific scroll points
For scroll snap to do anything, you have to specify scroll-snap-type and scroll-snap-align.
For scroll snap, you specify scroll-snap-type on the parent and scroll-snap-align on the children.

scroll-snap-type-values ::= ‹axis› [mandatory|proximity]
axis ::= x|y|block|inline|both

the axis part of scroll-snap-type determines along which axis to snap. Here, block and inline refer to the relevant axes.
mandatory|must snap no matter what
proximity|snap only when close to scroll point.

scroll-snap-align ::= (start|end|center) [start|end|center]
when two values set first is block, second inline

While scroll-padding is set on the parent, scroll-margin is set on the child, and so allows different values for different children.

## Scrolling

overscrolling is what happens when you scroll further on something than that thing allows.
on mobile browsers and some desktop browsers, there is a form of overscrolling where the site will rubberband
when you overscroll a container, and this then starts scrolling the next-higher container, this is known as scroll chaining.
overscroll-behavior is actually a shorthand for overscroll-behavior-x and overscroll-behavior-y
overscroll-behavior: none prevents all overscrolling.
overscroll-behavior: contain will prevent scroll chaining only