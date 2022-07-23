# value processing

Once a user agent has parsed a document and constructed a document tree, it must assign, to every element in the flat tree, and correspondingly to every box in the formatting structure, a value to every property that applies to the target media type.

The final value of a CSS property for a given element or box is the result of a multi-step calculation:

First, all the declared values applied to an element are collected, for each property on each element. There may be zero or many declared values applied to the element.
Each property declaration applied to an element contributes a declared value for that property associated with the element.
Cascading yields the cascaded value. There is at most one cascaded value per property per element.
Defaulting yields the specified value. Every element has exactly one specified value per property.
Resolving value dependencies yields the computed value. Every element has exactly one computed value per property.
Formatting the document yields the used value. An element only has a used value for a given property if that property applies to the element.
Finally, the used value is transformed to the actual value based on constraints of the display environment. As with the used value, there may or may not be an actual value for a given property on an element.