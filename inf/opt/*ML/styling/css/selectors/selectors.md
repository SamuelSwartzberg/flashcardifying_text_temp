# Selectors

A selector is a generic term that can refer to simple selector, compound selector, complex selector, or selector list.
A simple selector is a single condition on an element.
A type selector, universal selector, attribute selector, class selector, ID selector, or pseudo-class (pseudo-element is missing from the documentation, but I presume is part of this to) is a simple selector.
A compound selectior is a sequence of one or more simple selectors that are not separated, and represent a set of simultaneous conditions on a single element.
If a compound selector contains a type selector or universal selector, that must come first.
A combinatior is a condition of the relationship between two compound selectors.
A complex selector is a sequence of compound selectors separated by combinators.
A complex selector represents a set of simultaneous conditions on element which are in the relationship described by the combinatiors.
A selector list is a list of any or multiple types of selectors, separated by commas.
A selector list most often means a list of complex selectors.
A selector list is also called called selector group.

selector-list (default complex selector meaning) ::= ‹complex-selector›{,‹complex-selector›}
complex-selector ::= ‹compound-selector›{[‹combinator›]‹compound-selector›}
compound-selector ::= ‹simple-selector›{‹simple-selector›}
simple-selector ::= ‹type-selector›||‹universal-selector›||‹attribute-selector›||‹class-selector›||‹id-selector›||‹pseudo-class-selector›||‹pseudo-element-selector›