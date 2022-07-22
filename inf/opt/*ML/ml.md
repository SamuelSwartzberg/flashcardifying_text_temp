# *ml

## terminology

*ML is sometimes used for any SGML/HTML/XML and any subformat.

SGML stands for Standard Generalized Markup Language.
XML is a subset of SGML.
XML|Extensible Markup language
HTML was originally based on SGML, though the relationship has sometimes been fraught.
Since XML is a subset of SGML and HTML is based on it, HTML and XML share similarities in syntax.

## general syntax

### tags

*ML »tags« are delimited by ‹...›
*ML end tags additionally feature a / to look like ‹.../›

### elements

#### basics

An *ML »element« is everything from an elements start tag to an elments end tag.
An *ML element has an »element name«.
An *ML elements start and end tag feature its name: ‹foo› ... ‹/foo›.
*ML elements are begun by a »start tag« and ended by an »end tag«, unless they are self-closing.
*ML element consist of start tag, content, and end tag.
*ML elements' »content« is either text or other elements ('child elements').
*ML content goes between the start and the end tag.

#### empty elements ＆ self-closing tags

»Empty elments« are created by (or a synonym to) self-closing tags.
Self-closing tags in *ML only consist of a start tag.
Self-closing tags must end /› in XML.
Self-closing tags may end /› or merely › in HTML.
Using a closing tag for self-closing tags is usually invalid.
Empty elements cannot have content, since there is nowhere to put it.

#### optional closing tags

Some HTML elements that are not empty (not self-closing) nevertheless may omit their end tag, said to have »optional closing tags«.
Elements with optional closing tags are distinct from empty elements (elements with self-closing tags).
While most people recommend against omitting optional closing tags, google's style guide explixitly recommends them.

#### attributes

*ML attributes are placed in the start tag.
*ML attributes have the syntax key="value".
enumerated attriubtes are attributes that take a fixed set of values.
HTML attribute values may be unquoted if they do not feature whitespace and a few reserved characters.
HTML but not other *ML languages has boolean attributes.
boolean attributes are attributes which ＊may not＊ take a value, but whose presence or absence represnets true or false.
Confusingly, some HTML attributes with boolean semantics are not boolean attributes, but instead enumerated attributes, mostly with the possible values "yes" and "no" or "true" and "false".

#### element names

*ML element names may be in any case.
in HTML, putting element names in all lower case is common.
XML element names may contain any unicode with the exception of some metacharacters.
HTML and SVG built-in element names only contain characters a-z.
HTML custom elements must start with a character a-z in lowercase, must contain at least a hyphen character, but otherwise may contain any unicode.

#### whitespace

Whitespace within tags is usually ignored, as long as its not within a tag name or attribute

### root elements

*ML documents contain exactly one root element. All other elements are contained in the root element.
The *ML root element has the same name as the relevant language (i.e. html for html, xml for xml, svg for svg)

### document prolog

The document prolog (if you use one) comes at the top of the document, before the root element.
the document prolog has parts (both optional): an XML declaration and a document type declaration.

### declaration

the ⟮XML declaration⟯ ⟮contains information about the coming xml document⟯. 
the ⟮XML declaration⟯ is ⟮optional⟯, ⟮but if it appears⟯, it must appear in ⟮the first line of the document⟯. 
the ⟮XML declaration⟯ takes ⟮three⟯ possible parameters.
Of the XML declaration parameters, `⟮version⟯` is ⟮mandatory⟯.
```
‹?xml version="1.0" encoding="UTF-8" standalone="no" ?›
```

#### !XML declaration parameters

table:`⟮version⟯`|⟮The XML version the document is using⟯
`⟮encoding⟯`|⟮The text encoding this is using, e.g. UTF-8 or Shift_JIS⟯
`⟮standalone⟯`|⟮Whether the document relies on an external source such as an external DTD⟯


### doctype

A document type declaration,is an instruction that associates a particular *ML document with a document type definition.
Document type declaration is often shortened doctype.
Document type definition is typically shortened to DTD.
A document type declaration must be the first thing in the page if HTML.
A document type declaration must be the first thing after the XML declaration if XML
The syntax of a doctype declaration is ‹!DOCTYPE somestuff›
In HTML 5, the doctype no longer actually references a DTD, but merely prevents the browser from switching into quirks mode.
