# the DOM

## the DOM

DOM|Document Object Model
The DOM is a tree data structure that acts as an interface for a XML (or XML-derived) or HTML document.
DOM vertices are `Node`s (often subclasses of `Node`).
`Node` implements the EventTarget interface, so all things inheriting from Node also do.

## APIs

Javascript offers a rich DOM parsing API called the DOM API.


table:span=2;DOM parsing libraries in other languages
beautiful soup|python


## document

The Document interface represents any web page loaded in the browser and serves as an entry point into the web page's content, which is the DOM tree.
the root Node of the DOM tree is of type Document
Nodes of type Document are known as documents
The Document interface describes the common properties and methods for any kind of document. Depending on the document's type (e.g. HTML, XML, SVG, …), a larger API is available: HTML documents, served with the "text/html" content type, also implement the HTMLDocument interface, whereas XML and SVG documents implement the XMLDocument interface.
Document's browsing context is the browsing context whose session history contains the Document.

## Node tree

A node tree is a set of nodes arranged as a tree.
A document tree is a node tree whose root is a document.
A shadow tree is a node tree whose root is a shadow root.

## Node

a node has an associated document (essentially an owner), which is known as its 'node document'

### interface

cloneNode(deep?: boolean)|returns a duplicate of the node

### NodeLists

A NodeList is similar to an Array, but doesn't have all the methods.
A NodeList is a linear collection of nodes.
NodeList has a foreach method.
NodeLists can be live or static.
A live NodeList (or similar) reflects changes in the DOM
A static NodeList (or similar) does not reflect changes in the DOM
`HTMLCollection`s are an interface similar to NodeLists, but may only contain elements, is live, and has a far less rich interface.

### types of

onion-box:
⟮Node⟯
  others...
  ⟮Element⟯
    others...
    HTMLElement
    SVGElement
  ⟮Document⟯
    HTMLDocument
    XMLDocument
  ⟮DocumentFragment⟯
  ⟮CharacterData⟯
    Text
    Comment
    CDATASection
    ProcessingInstruction

### Elements

any HTML element has a JS interface that is called HTMLSomeelementnameElement.

#### types of attribute

An IDL (Interface Description Language) is a generic language used to specified objects' interfaces apart from any specific programming language.
In XMLHTML, most attributes have two faces: the content attribute and the IDL attribute.

The content attribute is the attribute as you set it from the content (the HTML code) and you can set it or get it via element.setAttribute() or element.getAttribute(). The content attribute is always a string even when the expected value should be of a different type.

the IDL attribute may be accessed from js like element.foo.

Any content attribute is also acessiable as an IDL attribute.

#### IDL interface

element.innerHTML|content between the tags
The Element.classList is a read-only property that returns a live DOMTokenList collection of the class attributes of the element
element.requestFullscreen()  issues an asynchronous request to make the element be displayed in full-screen mode, and returns a Promise for the eventual sucess or failure of becoming fullscreen.
requestFullscreen can only be called in response to user interaction or device orientation change
Document.exitFullscreen()   exits fullscreen
element.append takes n Node or DOMStrings
element.append appends Node objects as, well, nodes
element.append appends DOMStrings as Text nodes
In contrast, Node.appendChild() can only append one Node, and does not take DOMString objects.
However, Node.appendChild() returns the appended Node.
document.createElement() takes a tagName and creates an element of that name (however, it does not yet have a place in the document tree)
document.createElement optionaly takes an options object with a single key `is`, whose value is the tag name of a custom element previously defined via customElements.define().

#### Types of elements (and their interfaces)

##### HTMLCanvasElement

The HTMLCanvasElement.toDataURL(type) method returns a data URI containing a representation of the image in the format specified by the MIME type in the type parameter.

## custom elements

## DOM traversal

document.querySelector(selector)|get first element that matches selector
document.querySelectorAll(selector)|get NodeList of elements that matches selector
qs and qsa can be called on document for a global search, or on an element for a search only on that elements children.
qsa returns a static NodeList
document.getElementBy‹whatever›() returns HTMLCollections.
document.getElementBy‹whatever› has four variants ById, ByClassName, ByTagName
Element.closest(selector)|get the closest ancestor element which matches the selector

## other interfaces ＆ classes

### DOMTokenList

The DOMTokenList interface represents a set of space-separated tokens. 

## visibilityState

visibilityState = whether the document is somehow in the background/not in a visible tab/minimized, etc.
visibilityState = visible|hidden
change of document.visibilityState fires visibilitychange