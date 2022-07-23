# Cascading

The cascade takes an unordered list of declared values for a given property on a given element, sorts them by their precedence as determined below, and outputs a single cascaded value.

The cascaded value is determined by their precedence, which is specified by the cascade sort order:
origin ＆ importance › context › specificity › order of appearance in source document.

## Cascade origin

The three possible cascade origins are user-agent, user, or author.
author stylesheet|applied by the website author
user stylesheet|applied by the user, e.g. via addons
user-agent stylesheet|applied by the user-agent = browser
In addition, there are two virtual cascade origins, transition declarations and animation declarations.
the weakest style in an element higher in the cascade origin hierarchy beats the strongest style in an element lower in the cascade origin hierarchy
normal declarations|author›user›user-agent
important declarations|user-agent›user›author

## important

A declaration is important if it has a !important annotation as defined by [css-syntax-3], i.e. if the last two (non-whitespace, non-comment) tokens in its value are the delimiter token ! followed by the identifier token important. All other declarations are normal (non-important).
An important declaration takes precedence over a normal declaration.

Ergo, for cascade origin plus important there is the following hierarchy:

transition declarations › Important user agent declarations › Important user declarations › Important author declarations › Animation declarations › Normal author declarations › Normal user declarations › Normal user agent declarations

## context

## Specificity

Specificity is the means by which browsers decide which CSS property values within a single source type are the most relevant to an element, based on selectors.
Specificity is tiered, with lower tiers not being able to beat higher tiers.
Each specifier on a tier gains you one point on the specificity scale.

3rd lowest|id selectors
2nd lowest|class selectors|attribute selectors|pseudo-class selectors
lowest|element selectors|pseudo-element selectors
no effect on specificity|:not(), universal selector