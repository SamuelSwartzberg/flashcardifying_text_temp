# attributes

## common

the `datetime` attribute specifies the date and time associated with the element
`datetime` is an attribute taken by ‹del›, ‹ins›, and ‹time›

The `cite` attribute provides an URI that points to the source of a quote or change.
The `cite` attribute can be used on ‹blockquote›, ‹q›, ‹ins›, ‹del›

The HTML autocomplete attribute lets web developers specify what if any permission the user agent has to provide automated assistance in filling out form field values, as well as guidance to the browser as to the type of information expected in the field.
The autocomplete attribute can be used on inputs that take a text-like value, textarea elements, select elements and form elements.
The Boolean disabled attribute, when present, makes the element not mutable, focusable, or even submitted (if in a form).
The disabled attribute is supported by ‹button›, ‹command›, ‹fieldset›, ‹keygen›, ‹optgroup›, ‹option›, ‹select›, ‹textarea› and ‹input›.
The value attribute specifies the value of a thing.
If the value attribute of an element is pre-filled, it generally appears as a default.

content within ‹video›/‹audio›/‹canvas› is shown as a fallback for browsers that don't support the element.

### global

Global attributes are attributes common to all HTML elements; they can be used on all elements, though they may have no effect on some elements.
Kinds of global attributes:
aria-*
the onevent event handlers
xml:lang/xml:base — these are inherited from the XHTML specifications and deprecated, but kept for compatibility purposes.

class, id
HTML Microdata properties: item* (including on ‹meta›)
translate: an enumerated attribute whether the element should be translated, e.g. by tools such as google translate.

tabindex:
The tabindex attriubte indicates if and how an element can be focused by the keyboard.
 ⟮tabindex⟯⟮=0⟯ indicates that ⟮an element can be focused⟯ (e.g. ⟮by the tab key⟯)
 ⟮tabindex⟯⟮=-1⟯ indicates that ⟮c+;an element can ⁑not ⁑be focused⟯ (e.g. by ⟮the tab key⟯)
Values of tabindex larger than 0 specify the order in which things can be tabbed, use of this is highly discouraged.
CSS inline styling with style.
part and slot for the shadow DOM.
`is` for custom elements.
nonce
lang
hidden semantically indicates that the element is not relevant at the moment.
hidden in fact just sets display to none.
draggable is an enumerated attriubte w/ "true" and "false" which indicates whether the element can be dragged using the Drag and Drop API
data-* 
dir: enumerated attriubte ltr/rtl/auto
contenteditable|makes the content editable
the title attribute is *generally* shown as a tooltip, unless the element implements title differently.

#### text editing only

spellchek and inputmode attributes that are global attributes, but only can usefully be used where text can be inputed in html.
there are three places where text can be inputed in HTML: ‹input type="text"›, ‹textarea› and anything w/ contenteditable
spellcheck: an enumerated attribute w/ "true" and "false" whether to check the spelling of the thing
inputmode: specify the kind of text input that is required, thus allowing mobile devices to show appropriate soft keyboards
inputmode is different from ‹input type="..."› in that it does not enforce any kind of validation, users *can* still input anything they want.
inputmode value|shows|equivalent ‹input› type, if extant
none|no virtual keyboard
text|default virtual keyboard
decimal|keyboard with digits and decimal separtors, perhaps a -
numeric|keyboard with digits only, perhaps a -
tel|a telephone keyboard: 0-9, *, and #|type="tel"
search|return key may be labelled search, perhaps other changes|type="search"
email|optimized for email entry, contains @ prominently|type="email"
url|optimized for url entry|type="url"

autofocus
autocapitalize: capitalization of user input
enterkeyhint: is an enumerated attribute defining what action label (or icon) to present for the enter key on virtual keyboards. 