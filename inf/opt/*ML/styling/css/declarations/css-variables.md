# css variables

Declaration: --var-name: value;
Accessing: var(--var-name)

custom properties are properties that start with -- and save their value, which then can be referred to with the var() function.
custom properties have a scope of the variable they are declared on and all children, since they particpate in the cascade.
The var() css function can be used instead of any part of a value of another property, and may even contain commas.
var ::= var\(‹custom-property-name›, ‹fallback-value›\)