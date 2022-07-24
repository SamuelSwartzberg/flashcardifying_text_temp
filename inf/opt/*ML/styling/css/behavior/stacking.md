# stacking changes

Stacking contexts relate to each other in a tree.
Only certain elements or elements with certain properties. establish a stacking context.
The root element creates the root stacking context
The hierarchy of stacking context is a subset of the hierarchy of HTML elements because only certain elements create stacking contexts.
Within a stacking context, 
stacking order: z-index beats 'is a positioned element' beats order of apperance in html
stacking order of child stacking context is namespaced by the stacking order of parent stacking contexts, there is nothing a thing in a child stacking context can do to beat an aunt/uncle stacking order.
z-index may only be applied to positioned elements.
Isolation: isolate creates a new stacking context and prevents that element of being blended with mix-blend-mode.