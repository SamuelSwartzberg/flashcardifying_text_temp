# selectors themselves

## Simple selectors

### Basic types

Syntax of universal selector ::= *
the universal selector matches everything
Syntax of type selector ::= ‹name›
the type selector matches any element with the given nodename (so foo will match any ‹foo›)
Syntax of class selector ::= .‹name›
The class selector matches any element with the given class
Syntax of id selector ::= #‹name›
The id selector matches any element with the given ID
The attribute selector matches any element where a certain attribute is a certain way.
Syntax of attribute selector ::= \[‹attr›[‹operator›‹value›]\]
no operator (and no value) [‹attr›]|just elements with attribute present
= [attr=value]|attr is exactly value


Adding an i (or I) before the closing bracket causes the value to be compared case-insensitively (for characters within the ASCII range).

### Pseudo-classes

A pseudo-class indicates a state of an element
A pseudo-class is begun by a single colon

:empty| matches an element that has no child **nodes** (including text nodes)
:not(‹selector-list›) matches elements that don't match selector-list.
:not() is a pseudo-class, but has no influence on specificity
:root selects the root element
:indeterminate selects indeterminate element.
An 
input type="checkbox"|indeterminate when its indeterminate property is set to true via JS
input type="radio"|indeterminate when no radio buttons with the same name are selected
progress|indeterminate when no value attribute is present.
:placeholder-shown selects an element whose placeholder is being shown (NOT the placeholder itself)

:target|element has the same id as the fragment in the url
:fullscreen|fullscreen element

#### input pseudo-classes

a number of pseudo-classes have to do with input
:enabled/:disabled|HTML enabled attribute is specified, or specified on the parent fieldset (or not, for disabled)
:read-write/:read-only|element is not disabled and is not readonly, or has the contenteditable attribute set to true/element has none of these things
:in-range/:out-of-range|element is/is not within a specified range 
:required/:optional|elements with the "required" attribute specified/not specified
:valid/:invalid|element is valid/invalid according to properties specified in HTML
:checked|selects a toggled radio button or checkbox


#### Tree-structural pseudo-classes

Tree-structural pseudo-classes are pseudo-classes that allow selection of elements based on information in the document tree

:root  Selects the document's root element  
:empty  Selects every ‹p› element that has no children (including text nodes)  

Child-indexed pseudo-classes are tree-structural pseudo-classes that select elements based on their index among their siblings.
Child-indexed pseudo-classes end -child
For any child-indexed pseudo class there is an equivalent typed child-indexed pseudo-class that ends -of-type isntea of -child
Typed child-indexed pseudo-classes are tree-structural pseudo-classes that select elements based on their index among siblings of the same type.

:nth-child(‹nth›)  Selects every ‹p› element that is the ‹nth› child of its parent  
:nth-last-child(‹nth›)  Selects every ‹p› element that is the ‹nth› child of its parent, counting from the last child  
:first-child  Selects every ‹p› element that is the first child of its parent  
:last-child  Selects every ‹p› element that is the last child of its parent  
:only-child  Selects every ‹p› element that is the only child of its parent  

nth ::= ‹an-plus-b›|even|odd
an-plus-b ::= ‹integer›n+‹integer›

#### link-related pseudo-classes

:any-link|All links: ‹a› and ‹area› elements
:link|Selects all unvisited links  
:visited|Selects all visited links  

#### user action pseudo-classes

user action pseudo-classes are pseudo-classes that allow you to react to user action

:active|Selects the active link (when you click it/hold down the mouseclick on it)  
:hover|Selects links on mouse over  
:focus|element has the focus (accepts keyboard or mouse events, or other forms of input).
The :focus-within CSS pseudo-class matches an element if the element or any of its descendants are focused. In other words, 
The :focus-visible pseudo-class applies while an element matches the :focus pseudo-class and the UA (User Agent) determines via heuristics that the focus should be made evident on the element.

### Pseudo-elements

A pseudo-element indicates a part of a element which isn't a real element.
A pseudo-element is begun by two colons

::after, ::before
In CSS, ::before/::after creates a pseudo-element that is the first/last child of the selected element. 
content can only be usefully be used on ::after and ::before
content-values ::= normal|none|({‹content-specifier›} / ‹alt-text›)
alt-text ::= ‹string›|‹counter›
the content-specifier can be a bunch of different things
a ::before/::after pseudo-element will not display if it does not have content.

::placeholder|matches placeholder text
In HTML/CSS, ‹input› and ‹textarea› can have placeholder text in form of a placeholder attribute.
::selection|matches text currently selected/highlighted by the user via cursor/touch etc.
::selection only supports a subset of properties, mainly color, background-color and text-shadow.
::first-letter|matches the first letter of a block-level element
::first-line|matches the first line of a block-level element
::backdrop is the pseudo-element that is the size of the viewport and is rendered beneath ⟮any element that is in fullscreen⟯
::marker|the marker of a list item or a summary item

## Combinators


+
~
›


## The Grouping selector