# *ML

## *ML itself

*ML is sometimes used for any SGML/HTML/XML and any subformat.

SGML stands for Standard Generalized Markup Language.
XML is a subset of SGML.
XML|Extensible Markup language
HTML was originally based on SGML, though the relationship has sometimes been fraught.
Since XML is a subset of SGML and HTML is based on it, HTML and XML share similarities in syntax.

*ML <dfn>tags</dfn> are delimited by &lt;...&gt;
*ML end tags additionally feature a / to look like &lt;.../&gt;
An *ML <dfn>element</dfn> is everything from an elements start tag to an elments end tag.
An *ML element has an <dfn>element name</dfn>.
An *ML elements start and end tag feature its name: &lt;foo&gt; ... &lt;/foo&gt;.
*ML elements are begun by a <dfn>start tag</dfn> and ended by an <dfn>end tag</dfn>, unless they are self-closing.
*ML element consist of start tag, content, and end tag.
*ML elements' <dfn>content</dfn> is either text or other elements ('child elements').
*ML content goes between the start and the end tag.
<dfn>Empty elments</dfn> are created by (or a synonym to) self-closing tags.
Self-closing tags in *ML only consist of a start tag.
Self-closing tags must end /&gt; in XML.
Self-closing tags may end /&gt; or merely &gt; in HTML.
Using a closing tag for self-closing tags is usually invalid.
Empty elements cannot have content, since there is nowhere to put it.
Some HTML elements that are not empty (not self-closing) nevertheless may omit their end tag, said to have »optional closing tags«.
Elements with optional closing tags are distinct from empty elements (elements with self-closing tags).
While most people recommend against omitting optional closing tags, google's style guide explixitly recommends them.

Whitespace within tags is usually ignored, as long as its not within a tag name or attribute
an HTML element name may only 

*ML attributes are placed in the start tag.
*ML attributes have the syntax key="value".
HTML attribute values may be unquoted if they do not feature whitespace and a few reserved characters.
HTML features boolean attributes: attributes which <em>may not</em> take a value, but whose presence or absence represnets true or false.
HTML also features enumerated attriubtes: attributes that take a fixed set of values.
Confusingly, some HTML attributes with boolean semantics are not boolean attributes, but instead enumerated attributes, mostly with the possible values "yes" and "no" or "true" and "false".

*ML element names may be in any case.
in HTML, putting element names in all lower case is common.
XML element names may contain any unicode with the exception of some metacharacters.
HTML and SVG built-in element names only contain characters a-z.
HTML custom elements must start with a character a-z in lowercase, must contain at least a hyphen character, but otherwise may contain any unicode.

*ML documents contain exactly one root element. All other elements are contained in the root element.
The *ML root element has the same name as the relevant language (i.e. html for html, xml for xml, svg for svg)

The document prolog (if you use one) comes at the top of the document, before the root element. There are two parts (both optional): an XML declaration and a document type declaration.

### declaration

the ⟮c1;XML declaration⟯ ⟮c2;contains information about the coming xml document⟯. 
the ⟮c+;XML declaration⟯  is ⟮c3;optional⟯, ⟮c3;but if it appears⟯, it must appear in ⟮c4;the first line of the document⟯. 
the ⟮c+;XML declaration⟯ takes ⟮c5;three⟯ parameters:
<div class="c1-5-scr c12-18-scr">
`⟮c6;version⟯`|⟮c9;The XML version the document is using⟯
`⟮c7;encoding⟯`|⟮c+;The text encoding this is using, e.g. UTF-8 or Shift_JIS⟯
`⟮c8;standalone⟯`|⟮c+;Whether the document relies on an external source such as an external DTD⟯

</div>
<p class="c1-11-scr">Of these, `⟮c+;version⟯` is ⟮c+;mandatory⟯. It's syntax is:</p>
<div class="c1-11-scr">```
⟮c+;&lt;?xml⟯ ⟮c+;version=⟯"1.0" ⟮c+;encoding=⟯"UTF-8" ⟮c+;standalone=⟯"no" ⟮c+;?&gt;⟯
```</div>

### doctype

A document type declaration, or doctype, is an instruction that associates a particular XML or SGML document (for example, a webpage) with a document type definition (DTD).
A document type declaration must be the first thing in the page if HTML.
A document type declaration must be the first thing after the XML declaration if XML
The syntax of a doctype declaration is &lt;!DOCTYPE somestuff&gt;
In HTML 5, the doctype no longer actually references a DTD, but merely prevents the browser from switching into quirks mode.

### XML

#### PI

PI|Processing instruction
⟮c1;Begins a processing instruction⟯|⟮c2;&lt;?⟯
⟮c3;Ends a processing instruction⟯|⟮c4;?&gt;⟯


'Tag name' of the ⟮c6;processing instruction⟯ to ⟮c7;link a stylesheet to an xml document⟯ is ⟮c5;xml-stylesheet⟯ 

#### CDATA

⟮c1;CDATA⟯ is short for ⟮c2;Character data⟯) 
⟮c10;CDATA⟯ ⟮c3;tells the parser not to parse the content as XML markup⟯ 
⟮c11;CDATA⟯ allows us to ⟮c4;use characters with a special meaning in XML⟯ without ⟮c5;confusing the parser⟯, for example, ⟮sb;this would allow us to ⟮c13;include HTML within XML without a problem⟯.⟯ 
⟮c12;CDATA⟯ syntax: `⟮c6;&lt;![⟯⟮c7;CDATA⟯⟮c8;[⟯content...⟮c9;]]&gt;⟯` 

### HTML

#### General structure

An HTML document is started by the &lt;html&gt; tag and ended by the &lt;/html&gt; tag.
a &lt;html&gt; element consists of a &lt;head&gt; section and a &lt;body&gt;

#### nesting

some elements must appear as children of other elements - to violate these rules is a violation of good semantics and accessibility, and will hurt your search ranking.

#### elements

##### <head>

The &lt;head&gt; in HTML contains metadata about the document.
it can contain:
the &lt;title&gt; element, which defines the documents title
the &lt;title&gt; element is mainly shown in the browsers tab name / title bar, as well as search engines.
the &lt;title&gt; element can only contain text, not tags.
the &lt;title&gt; element's content should change in response to major state changes.

the <base> element specifies the base URL for the document with its href attribute.
The <abse> element optionally accepts a target argument to choose the browsing context links open in by default.
The <basefont> element used to specify the default font (color, fontface etc.) but is now deprecated.

###### <meta>

The <meta> HTML element represents metadata that cannot be represented by other HTML meta-related elements, like <base>, <link>, <script>, <style> or <title>.
<meta> specifies the value in its content attribute

The type of metadata provided by the <meta> element can be one of the following:

If the name attribute is set, the <meta> element provides document-level metadata, applying to the whole page.
If the http-equiv attribute is set, the <meta> element is a pragma directive, providing information equivalent to what can be given by a similarly-named HTTP header.
If the charset attribute is set, the <meta> element is a charset declaration, giving the character encoding in which the document is encoded.
If the itemprop attribute is set, the <meta> element provides user-defined metadata.

meta name
author|document author
description|short blurb about website, may be used in search results
theme-color|indicates a suggested color that user agents should use to customize the display of the page or of the surrounding user interface. The content attribute contains a valid CSS <color>.

by defaults, narrow screen devices (e.g. mobiles) render pages in a virtual window or viewport, which is usually wider than the screen, and then shrink the rendered result down so it can all be seen at once, essentially lying about their viewport size, to make non-mobile-optimized pages not look terrible.
without width=device-width, many media queries will never apply

The meta tag with name viewport is used to customize/constrain the viewport.
For the meta tag with name viewport, the content value has the following syntax: <key>=<value>{, <key>=<value>}
width=<integer>|set size of the viewport to <integer> pixels
width=device-width|prevent browser from lying about their width
initial-scale=<integer>|set default zoom level on page
user-scalable=("yes"|"no")|allow users to zoom or not
maximum-scale=<integer>|set maximum zoom level



##### various inline text

The abbr HTML element represents an acronym or abbreviation.
There used to be an <acronym> element which was obsoleted in favor of <abbr>
The thing an abbr element is short for may either be explained in the text or specified in a title attribute.
<dfn> represents defining instance of a term
The <p> element, the <dt>/<dd> pairing, or the <section> element which is the nearest ancestor of the <dfn> is considered to be the definition of the term.
If the <dfn> element has a title attribute, the value of the title attribute is considered to be the term being defined. The element must still have text within it, but that text may be an abbreviation (perhaps using <abbr>) or another form of the term.
If the <dfn> contains a single child element and does not have any text content of its own, and the child element is an <abbr> element with a title attribute itself, then the exact value of the <abbr> element's title is the term being defined.
Otherwise, the text content of the <dfn> element is the term being defined. 

##### Media

&lt;video&gt; and &lt;audio&gt; embed a video/audio media player.
Both HTMLVideoElement and HTMLAudioElement inherit from HTMLMediaElement.
The ⟮c1;HTMLMediaElement⟯ has a bunch of properties, amongs others

⟮c2;muted⟯|⟮c7;audio is muted/mute audio⟯|IDL & Content
⟮c3;paused⟯|⟮c8;is paused/pause⟯|IDL
⟮c5;loop⟯|⟮c10;will loop/loop⟯|IDL & Content
⟮c5;controls⟯|⟮c10;is showing controls/show controls⟯|IDL & Content
⟮c5;autoplay⟯|⟮c10;will autoplay/enable autoplay⟯|IDL & Content
⟮c4;ended⟯|⟮c9;Indicates whether it has finished playing⟯|IDL
⟮c6;playbackRate⟯|⟮c11;Represents the speed at which the thing is playing⟯|IDL


the HTMLMediaElement has quite a few different events
Attribute change:
paused=false -> paused=true|pause
paused=true -> paused=false|play

You may define a single source for &lt;video&gt; or &lt;audio&gt; via a src element.
You may define multiple sources for &lt;video&gt; or &lt;audio&gt; via child &lt;source&gt; elements.
&lt;track&gt; defines text tracks for media elements (&lt;video&gt; and &lt;audio&gt;)

the poster attribute for video specifies a URL for an image to be shown while the video is downloading. 
If the poster attribute for <video> isn't specified, nothing is displayed until the first frame is available, then the first frame is shown as the poster frame.

###### track

track can ba a child of video or audio
track has a default attribute to indicate that this is a default track
track has a kind attribute to indicate its purpose
track kinds: captions, chapters, descriptions, metadata, subtitles

##### images

<img> is used for including images

The picture element contains 0 - ∞ source elements and one <img> element.
The <img> child of <picture> is there to act as a fallback and to give the picture its dimensions.

###### srcset 

srcset-values ::=  <srcset-specifier>{, <srcset-specifier>}
srcset-specifier ::= <url> <integer>w
sizes-values ::= <sizes-specifier>{, <sizes-specifier>}
sizes-specifier ::= <media-query> <resolution-length-percentage>

scrset specifies a list of sources and their actual sizes, while sizes declares a set of media condition and what width the image should be in that case (width as in resolution, not width of the  box). The browser then picks the closest one, but preferring ones that are too large than too small.
If no sizes is provided, the browser chooses one of scrset based on which is closest to the viewport width (essentially just assuming that the image wlll be 100 vw)

##### source

the type (a MIME type) of a &lt;source&gt; element is specified via the type attribute, or else the browser will check the MIME type in the HTTP header.
The lists of <source>s for <picture>, <video> and <audio> represents a priority hierarchy - the browser will take the first one that matches.
Conditions that <source>s may have are the type and media attributes
&lt;source&gt; elements for audio/video take their URL in a src attribute; &lt;source&gt; elements for picture take their URL in a srcset attribute

##### Headings

&lt;h1&gt; to &lt;h6&gt; define headings.
It is an antipattern to skip heading levels between &lt;h1&gt; and &lt;h6&gt;
There may only be one &lt;h1&gt; per page, which should describe the overall purpose of the page.
Skipping heading levels between &lt;h1&gt; and &lt;h6&gt; results in bad accessibility and SEO heading levels
Based on h1 to h6 (and nothing else, sadly), the browser generates a document outline 
There was a push to generate the document outline dynamically from nested semantic containers, but this was never implemented.

##### del and ins 

The &lt;del&gt; HTML element represents text that has been deleted from a document.
The &lt;ins&gt; HTML element represents text that has been added to the document.
The &lt;del&gt; and &lt;ins&gt; elements are often used for purposes such as tracking changes or source code diffs.

##### progress and meter

A progress bar shows the progress of a task via a bar that becomes fuller as the task nears completion.
In HTML, a progress bar can be indicated by &lt;progress&gt;
In HTML, meter generally displays as a bar of varying fullness.
In HTML, meter supposedly represents a scalar value within a known range.
In HTML, progress only accepts max and value as attributes, reflecting the semantics of the completion of a task.
The min and max attributes specify the minimum/maximum value and are allowed on certain types of <input>s as well as <meter> and max also on <progress>
The low, high and optimum attributes may only be specified on <meter>
In HTML both progress and meter support a fallback text value within their tags.

##### tables

table > tbody/thead/tfoot (optional level, but if used, any tr must be within it)
tbody/thead/tfoot > tr
tr > th/td

caption  optional child of table

to make a td/th occupy multiple columns/rows, use colspan/rowspan="<integer>"
HTML tables are for tabular data, not for layout

The <colgroup> HTML element defines a group of columns within a table, e.g. for styling.
The <colgroup> is made up of <col> elements
The <col> element takes a span attribute indicating how many columns are being targeted.
The <colgroup> element must be the first child of <table> (besides <caption>, if it is present)

##### canvas

The <canvas> element allows drawing graphics and animations via the canvas scripting API or the WebGL API
Sizing the canvas using CSS versus HTML

The displayed size of the canvas can be changed using CSS, but if you do this the image is scaled during rendering to fit the styled size, which can make the final graphics rendering end up being distorted.

It is better to specify your canvas dimensions by setting the width and height attributes directly on the <canvas> elements, either directly in the HTML or by using JavaScript.

##### map

<map> defines an image map, within which <area> defines clickable areas.
<map> takes a shape attribute with the possible values circle, poly, rect.
The shape of a map with a given shape attribute is specified by the coords attribute
You refer to a map via its name attribute included in an <img> usemap attribute prefixed by #

##### links

The content between the tags should be descriptive of what the link does.

The <link> HTML element specifies relationships between the current document and an external resource. This element is most commonly used to link to stylesheets, but is also used to establish site icons (both "favicon" style icons and icons for the home screen and apps on mobile devices) among other things.

The rel attribute defines the relationship between a linked resource and the current document. Valid on <link>, <a>, <area>, and <form>, the supported values depend on the element on which the attribute is found.

rel=opener/noopener create a top-level browsing context that is/is not a auxiliary browsing context if the hyperlink would create either of those, to begin with (i.e., has an appropriatetargetattribute value).
rel=nofollow indicates that the current document's original author or publisher does not endorse the referenced document, and thus doesn't confer some of your sites reputation onto the linked sites reputation.
Comment sections may have rel=nofollow by default
rel=noreferrer: No HTTP Referer header will be included. Additionally, has the same effect as noopener.	 

###### <link>

rel="icon"|specifies an icon representing the current document
rel="stylesheet"|indicates a stylesheet for the document

If rel="icon", the sizes attribute of link specifies which sizes are applicable.
link-sizes-values ::= any|(<size-spec>{ <size-spec>})
size-spec ::= <width>(x|X)<height>

the type attribute of <link> specifies the mime type of the resource; however this is generally omitted except for rel="icon"

rel="alternate" indicates that the link is to an alternate version of your site, e.g. in a different language.
if rel="alternate" is linking to a version in a different language, it should have a hreflang of whatever BCP 47 lang code
rel="alternate" indicates a canonical URL for a page, useful if you have multiple urls for the same page and want crawlers etc. to use a specific one.

###### hyperlinks

The two elements that create hyperlinks are <area> and <a>.
use the attribute href for <area> and <a> to specify an URL of the links target.
The target attribute of <area>/<a> specifies in which browsing context to open the link.
_self|current browsing context
_blank|new window/tab
_parent|parent browsing context
_top|root node browsing context
for <form>, the target attribute represents where to display the response after submitting the form  

####### a

the download attribute of <a> Prompts the user to save the linked URL instead of navigating to it. 
the download attribute of <a> Can be used with or without a value.
the download attribute of <a> used without a value will prompt the browser to suggest a file type.
the download attribute of <a> used with a value will prompt the browser to save it with the specfied name as a prefilled suggestion.

##### forms


Form-associated content is a subset of flow content comprising elements that have a form owner, exposed by a form attribute, and can be used everywhere flow content is expected. A form owner is either the containing <form> element or the element whose id is specified in the form attribute.

<button>
<fieldset>
<input>
<keygen>
<label>
<meter>
<object>
<output>
<progress>
<select>
<textarea>

Form-associated content does not necessarily always have to be within a form.

This category contains several sub-categories:

listed
Elements that are listed in the form.elements and fieldset.elements IDL collections. Contains <button>, <fieldset>, <input>, <keygen>, <object>, <output>, <select>, and <textarea>.

labelable
Elements that can be associated with <label> elements. Contains <button>, <input>, <keygen>, <meter>, <output>, <progress>, <select>, and <textarea>.

submittable
Elements that can be used for constructing the form data set when the form is submitted. Contains <button>, <input>, <keygen>, <object>, <select>, and <textarea>.

resettable
Elements that can be affected when a form is reset. Contains <input>, <keygen>, <output>,<select>, and <textarea>.

###### form itself

A <form> element represents a form.
the method attribute of form accepts post|get|dialog.
post/get|use the POST/GET methods
// for dialog see <dialog>
The action attribute for form specifies the URL to which the form should be submitted.
Forms may not be nested.

###### fieldset

A <fieldset> is an HTML element used to group multiple inputs (and their labels)
The first child of a fieldset may be a <legend> (this is the only place it may appear), which captions its parent fieldset

###### button

The <button> HTML element represents a clickable button
the type attribute for <button> represents the default functionality
submit|submit form data to server
reset|reset form data
button|no default behavior, must manually be implemented

A button should have text content, or if not, it needs to be specified by aria-label

###### textarea

textarea represents a multiline text input field
textarea is not an empty element, and in fact the content can be used to provide a default value.

###### label

A <label> provides a caption/label for a thing, most commonly an <input>
There are two ways of associating an <input> with a label, either nest the input within the label, or set the for attribute of the label to the id of the input.
Any input should have exactly one <label>, or alternatively a non <label> referred to by aria-labelledby

###### input

specifying the value property of an input element in HTML sets its initial value.
As the state of <input>s changes, the value property in JS is updated.
The validation states of an input are contained in the ValidationState API and corresponding property./

####### types

type="color" for colors
type="hidden" does not show the control, but still submits the data.

######## radio & checkbox

A radio button is a graphical control element that allows the user to choose only one of a predefined set of mutually exclusive options. 
In HTML, a radio button is realized by <input type="radio">
In HTML, multiple radio buttons are linked by assigning them the same number.
radio and checkbox input accept the attribute checked to specfiy if they are checked


Bootstrap:

.form-check # set of radio buttons
.form-check-label   define a label for a checkbox/radio button
.form-check-input   define a checkbox/radio button

######## text

&lt;input type="text"&gt; is single-line only
There are a set of input types that act similarly text, but force a certain type of validation and change the soft keyboard/add input helpers, similar to inputmode:
time-related: date, datetime-local, month, time, week
number: number
other: email, password, tel, search, url
On any text-like input which is not time-related and not 'number' as well as on textarea, you may specify the minlength and maxlength attributes to contstrain the amount of UTF-16 code units.
On any non-time-related, non-number text-like input, you may specify the attribute `pattern`, providing a regex against which to match the input.
most text-only input fields may have the readonly attribute specfied, which shows the inital value but doesn't allow the user to modify it
the time-related and number text-like inputs plus range accept a step argument.

######## file

inputs of type file accept an attribute accept (lol) which takes a CSL of unique file type specifiers
an unique file type specfier is either a filename extension starting with a period, or a valid MIME type.
valid for the file input type only, the capture attribute defines which media—microphone, video, or camera—should be used to capture a new file for upload with file upload control in supporting scenarios.
input type file return a `FileList`, which is a linear collection of `File`s

######## image

Input type image supports the attributes <img> supports, in addition to the usual ones of input.
When clicked, input type="image" behaves like submit, but also sends the coordinates of the area being clicked.
The coordinates of an input type="image" will be submitted as <name>.x=<coord>&name.y=<coord>

######## submit

####### attributes

the boolean multiple attribute may be set on input type email/file and <select> elements.
When the multiple attribute is set for input type email, emails are separated with the comma.
Any input may have a form attribute to associate it with the id of its form owner.
The list attribute of most text-like input types plus range and color accepts an id of a <datalist>, which represents a list of predefined values.
The <datalist> HTML element contains a set of <option> to indicate a predefined value each.
For most input types, the value attribute merely indicates an initial default, for input type radio/checkbox/image, the value attribute specicifies the value that will be sent if that thing is checked
A checkbox or radio button with no value property will be sent as name=on.
Radio buttons/checkbox inputs are only sent if they are checked.
In a form, the name attribute becomes the key that the value being sent is associated with
If the name of a thing in a form is not specified, the value is not sent.
autofocus
A Boolean attribute which, if present, indicates that the input should automatically have focus when the page has finished loading (or when the <dialog> containing the element has been displayed).

##### select, option

The <select> HTML element represents a control that provides a menu of options:
The <option> HTML element is used to define an item contained in a <select>, an <optgroup>, or a <datalist> element. 
The <optgroup> HTML element creates a grouping of options within a <select> element.
to set the default option, specify the selected attribute on the option.

By default, ⟮c9;html `&lt;select&gt;`⟯s will usually ⟮c+;display as as a dropwdown⟯, and only ⟮c+;become a list box⟯ if `⟮c+;multiple⟯` (⟮c+;allowing multiple selection::purpose⟯) or `⟮c+;size⟯` (⟮c+;specifying how many items to show at once::purpose⟯) is specified</span>

##### output

The <output> HTML element is a container element into which a site or app can inject the results of a calculation or the outcome of a user action.
<output> are often used within forms, however tehy are not submitted with the form.

##### script

to include an external script, set the src attribute of the <script> element to its URL
the <noscript> tag is for displaying content if the browser does not support JS

##### Ruby 

ruby text/characters are small annotative glosses placed on the top or to the right of characters.
Ruby text/characters is called furigana in japanese.
In HTML, ruby text is delimited by the &lt;ruby&gt; tag
In HTML ruby annotation, the syntax is &lt;ruby&gt;lowertext&lt;rt&gt;uppertext&lt;/rt&gt;&lt;/ruby&gt;
In HTML, one may designate fallback delimiters for the upper text. 
Ruby fallback delimiters are enclosed in &lt;rp&gt; tags, and go before and after the &lt;rt&gt; delimited uppertext.

##### aside

An aside (there is no agreed-upon term, so I'm using the term that HTML uses) is a part of the main content thats only partially related to the main content, and often placed outside of the main flow. 
A pull quote is an aside that is a quote from the article.

##### figure

In general, figures are images/diagrams/similar with a caption.
In general, figures float (in the general sense).
In HTML, the <figure> element specifies its caption with <figcaption>

##### float

a float is across styling languages a thing that exists outside of the normal flow of text.

float places an element at one side of the container or next to another floating element, allowing text/inline elements to wrap around it.
float: left/right makes the element go to the left/right side of the container/the next float respectively.
A floating element is where the (computed) value of float is not none.
Float implies display: block, and converts it if required.
The clear CSS property sets whether an element must be moved below (cleared) floating elements that precede it. 
the clear property applies to clearing all floats if set to both, or to only clearing left/right floats if set to left or right.
If element contains only floated elements, its height will collapse to nothing.
To prevent and element containing only floated elements height collapsing to nothing, a technique called a clearfix is used.
The most common clearfix technique might be: ::after {
  content: "";
  display: block;
  clear: both;
}

In contrast to ⟮c10;CSS⟯, in ⟮c10;Latex⟯ ⟮c11;floats⟯ merely ⟮c12;move vertically and not horizontally⟯. 
If possible, latex places ⟮c13;floats⟯ ⟮c14;close to where they appear in the source text⟯. 
⟮c15;Floats⟯ are relevant for ⟮c9;things that cannot be broken over a page (images, tables⟯). 
To ⟮c16;uniquely identify⟯ ⟮c17;floats⟯ no ⟮c18;matter where they end up⟯, they are ⟮c19;numbered⟯ by latex. 
By default, ⟮c20;table⟯ and ⟮c21;figure⟯ are the two ⟮c22;environments⟯ that are ⟮c23;floats⟯. 
The ⟮c24;table environment⟯ is ⟮c25;functionally equivalent to⟯ the ⟮c26;figure environment⟯, but ⟮c27;has a separate index of numbering⟯. 

The ⟮c28;[option]⟯ for ⟮c29;table, figure⟯ says ⟮c30;where roughly you would like the table/figure to float.⟯ 
⟮c31;the option for controlling where a floating element⟯ goes consists of ⟮c32;a list⟯ of specifiers, which are ⟮c33;single chars⟯ ⟮c34;one after the other⟯ without ⟮c35;separators⟯, indicating ⟮c36;relative preference⟯ 
⟮c1;h⟯|⟮c2;place where it appeared in the source text as much asp possible⟯
⟮c3;H⟯|⟮c4;force place where it appears (basically turn it into a nonfloat⟯)
⟮c5;p⟯|⟮c6;special page for floats only⟯
⟮c7;t/b⟯|⟮c8;place at top / bottom of page (respectively⟯)


the ⟮c37;float⟯ package ⟮c40;improves⟯ ⟮c38;float handling⟯ and ⟮c40;defines⟯ ⟮c39;the float specifier H⟯ 

If you have ⟮c41;a table (tabular⟯) where you want to make sure it ⟮c42;flows well and does not cause awkward page breaks⟯, you should ⟮c43;float it (surround it in a table env) ⟯, but if ⟮c44;you care exactly where it appears in relation to the source text⟯, you should ⟮c43;not float it (not surround it in a table env⟯) 

⟮c45;\caption{foo⟯} is there to ⟮c46;add a caption foo⟯ to ⟮c47;floating environments⟯. 
⟮c48;the optional argument []⟯ to ⟮c49;\caption⟯ takes ⟮c50;a short title⟯ for use ⟮c51;in the listoftables/figures⟯ 
to ⟮c52;\label⟯ a ⟮c53;table/figure⟯, the ⟮c52;\label⟯ must go ⟮c54;directly after \caption⟯ 


##### data

<data> represents things that have a machine-readable translation
<time> represents a time/date/duration.

##### Lists

In HTML and Latex, ordered and unordered lists are surrounded with something different, but use the same list items.
Latex uses the same list items for description lists also, while HTML uses different elements for those.
by default, latex only allows the nesting of lists to a depth of four

ordered list|enumerate environment|&lt;ol>
unordered list|itemize environment|&lt;ul>
description list|description environment|&lt;dl>
list item|\item|&lt;li>
Term in a description list with title foo and description/explanation bar|\iten[foo]bar|&lt;dt>foo&lt;/dt>&lt;dd>bar&lt;/dd>

In markdown ⟮c1;Lists items⟯ are each ⟮c3;started by⟯ ⟮c2;one or more symbols⟯, while lists themselves are delimited by nothing more than any block-level item.. 
⟮c4;ordered list items⟯ are started by ⟮c5;&lt;n&gt;. (e.g. 1. or 7.⟯). 
it does not matter ⟮c6;with which digit you number list items with (e.g. even if you do `21. foo\n2. bar)`⟯&nbsp;they will ⟮c7;always start one and go from there (or whatever you then change it to via css⟯). 
⟮c8;unordered list items⟯ are started by ⟮c9;-⟯, ⟮c9;*⟯ or ⟮c9;+⟯, which can be ⟮c10;mixed and matched⟯. 

##### containers

div and span are 'pure' container without any semantics.
the difference between div and span is that div is by default block-level (display: block flow) and that span is by default inline (display: inline flow)

###### semantic containers

Some HTML elements are functionally just containers with extra semantics attached (part of semantic html)
HTML element|semantic container for
header|heading-related content
footer|footer
main|
section|generic, but semantically meaningful section
article|self-contained information which could be independently reused
aside|content only indirectly related to main content
address|contact information|may not contain heading/sectioning content
nav|navigation section

##### inline nonhtml

&lt;style> allows including CSS inline, by including it as content
&lt;script> allows including JS or other scripting languages inline, by including it as content

##### deprecated elements

<menu> was supposed to be a semantic alternative to <ul> for menus, but is now deprecated
<menuitem> was meant to be a child of <menu> if <menu> was a context menu, but is now deprecated.
<dir> was supposed to be a semantic alternative to <ul> for directories of files and folders, but is now deprecated.
<keygen> was an element to facilitate the generation of keys for data transfer, esp. with forms, but is now deprecated.
<font> was an element to style text, but is now deprecated.

#### content categories

Most HTML elements are a member of one or more content categories — these categories group elements that share common characteristics. This is a loose grouping (it doesn't actually create a relationship among elements of these categories), but they help define and describe the categories' shared behavior and their associated rules.

Flow content
Flow content is a broad category that encompasses most elements that can go inside the &lt;body> element.

Heading content is a subset of flow content that includes h1-h6, and theoretically though not relevantly the never-implemented the-spec-is-lying-about-it hgroup
Sectoning content is a subset of flow content that was supposed to be relevant for the outline algorithm that was never implemented, and so is a somewhat-irrelevant category.

Phrasing content is a subset of flow content that defines the text and the markup it contains, and can be used everywhere flow content is expected. 

Content is palpable when it's neither empty or hidden; it is content that is rendered and is substantive. Elements whose model is flow content should have at least one node which is palpable.

##### embedded content

Embedded content is a subset of flow content that imports another resource or inserts content from another mark-up language or namespace into the document, and can be used everywhere flow content is expected.

embedded cotnetn cotnains the media elements video and audio, image-related elements img, picture, and svg, math, frames, canvas, object, embed plus the obsolete elements applet

<applet> was used to embed java applets, but is now obsolete.
The <object> HTML element represents an external resource, which can be treated as an image, a nested browsing context, or a resource to be handled by a plugin.
The <param> HTML element defines parameters for an <object> element.
The <embed> HTML element embeds external content at the specified point in the document. This content is provided by an external application or other source of interactive content such as a browser plug-in.

&lt;math> and &lt;svg> embed content in HTML from MathML and SVG respectively

#### Common attributes

the `datetime` attribute specifies the date and time associated with the element
`datetime` is an attribute taken by &lt;del&gt;, &lt;ins&gt;, and &lt;time&gt;

The `cite` attribute provides an URI that points to the source of a quote or change.
The `cite` attribute can be used on &lt;blockquote&gt;, &lt;q&gt;, &lt;ins&gt;, &lt;del&gt;

The HTML autocomplete attribute lets web developers specify what if any permission the user agent has to provide automated assistance in filling out form field values, as well as guidance to the browser as to the type of information expected in the field.
The autocomplete attribute can be used on inputs that take a text-like value, textarea elements, select elements and form elements.
The Boolean disabled attribute, when present, makes the element not mutable, focusable, or even submitted (if in a form).
The disabled attribute is supported by <button>, <command>, <fieldset>, <keygen>, <optgroup>, <option>, <select>, <textarea> and <input>.
The value attribute specifies the value of a thing.
If the value attribute of an element is pre-filled, it generally appears as a default.

content within <video>/<audio>/<canvas> is shown as a fallback for browsers that don't support the element.

##### Global attributes

Global attributes are attributes common to all HTML elements; they can be used on all elements, though they may have no effect on some elements.
Kinds of global attributes:
aria-*
the onevent event handlers
xml:lang/xml:base — these are inherited from the XHTML specifications and deprecated, but kept for compatibility purposes.

class, id
HTML Microdata properties: item*
translate: an enumerated attribute whether the element should be translated, e.g. by tools such as google translate.

tabindex:
The tabindex attriubte indicates if and how an element can be focused by the keyboard.
&nbsp;⟮c1;tabindex⟯⟮c2;=0⟯ indicates that ⟮c3;an element can be focused⟯ (e.g.&nbsp;⟮c4;by the tab key⟯)
&nbsp;⟮c1;tabindex⟯⟮c2;=-1⟯ indicates that ⟮c3;an element can ⁑not&nbsp;⁑be focused⟯ (e.g. by ⟮c4;the tab key⟯)
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

###### text editing only

spellchek and inputmode attributes that are global attributes, but only can usefully be used where text can be inputed in html.
there are three places where text can be inputed in HTML: <input type="text">, <textarea> and anything w/ contenteditable
spellcheck: an enumerated attribute w/ "true" and "false" whether to check the spelling of the thing
inputmode: specify the kind of text input that is required, thus allowing mobile devices to show appropriate soft keyboards
inputmode is different from <input type="..."> in that it does not enforce any kind of validation, users *can* still input anything they want.
inputmode value|shows|equivalent <input> type, if extant
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

#### tools

##### emmet

Emmet is a syntax mainly using CSS selectors for quickly generating html
Emmet is or can be integrated into most code editors
In VSCode, to use emmet with JSX, enable it in the settings
$   running number indicator  // $
()   groups element
*x   create x amount of elements
@   change the number direction/offsett
^   go up an element
{something}   text (within the tag)

### SVG


#### attributes

it seems that ⟮c4;SVG elements⟯ will have ⟮c1;width⟯ and ⟮c1;height⟯ of ⟮c2;0⟯ and thus ⟮c3;be invisble⟯ if ⟮c5;not otherwise specified⟯ 

In ⟮c9;SVG⟯, you ⟮c10;position things⟯ by ⟮c11;specifying the x and y properties⟯ ⟮c12;on the elements⟯. 

#### elements

##### Basic shapes

You ⟮c9;create basic shapes⟯ in SVG by using ⟮c10;the SVG basic shapes⟯. 
the ⟮c1;SVG basic shapes⟯ are a grouping of⟮c11;, well, basic shapes⟯ 
SVG ⟮c12;basic shapes⟯: ⟮c2;&lt;circle&gt;⟯, ⟮c3;&lt;ellipse&gt;⟯, ⟮c4;&lt;line&gt;⟯, ⟮c5;&lt;polygon&gt;⟯, ⟮c6;&lt;polyline&gt;⟯, ⟮c7;&lt;path&gt;⟯ and ⟮c8;&lt;rect&gt;⟯ 

##### <text>

`the ⟮c1;&lt;text&gt;⟯` element is ⟮c2;the only place⟯ you can ⟮c3;have text in SVG⟯ 
In ⟮c7;SVG⟯, ⟮c8;text⟯ ⟮c9;outside of a &lt;text&gt;⟯ ⟮c4;will not be shown⟯ 
⟮c10;&lt;text&gt;⟯ can contain ⟮c5;`&lt;tspan&gt;`s⟯, which ⟮c6;define subtext (lol) for further targeting⟯. 

##### <g>

the ⟮c3;svg⟯ ⟮c1;&lt;g&gt; element⟯ is used to ⟮c2;group ofther elements⟯ 

### JSX

⟮c+;JSX⟯ is ⟮c+;HTML⟯-like syntax to be used in ⟮c+;JS⟯
⟮c+;any values⟯ embedded in JSX are ⟮c+;auto-escaped⟯, and thus provide ⟮c+;a degree of safety against XSS attacks⟯
You can put ⟮c+;any valid JS expression⟯ within ⟮c+;curly braces⟯ in ⟮c+;JSX⟯
⟮c+;JSX⟯ use ⟮c+;camel case⟯ for ⟮c+;HTML attribute names⟯ (including ⟮c+;events⟯) (which would normally use ⟮c+;kebap-case⟯)
In JSX, ⟮c+;self-closing tags⟯ must be closed with ⟮c+;/&gt;⟯, however ⟮c+;every react component may⟯ be ⟮c+;self-closing⟯
⟮c3;JSX⟯ is either said to be short for ⟮c2;JavaScript Syntax Extension⟯ or ⟮c1;JavaScript XML⟯
Using JSX, you generally assign events via the on&lt;Event&gt; handlers, but pass a function (instead of calling a function) , and wrap it in curly braces

#### style props

style props is using react props to change the style of a component
style props are not enabled by default, but are used extensively in various react styling frameworks
style props mostly are named as the css properties are (subject to the camelcaseification/abbreviation described elsewhere)
style props also offer some abbreviated values:
linear/radial-gradient() -> linear/radial()
to top, to top right, ... -> to-t, to-tr...
using style props, we can also define 'states'. (not called that, this is my term)
style props 'states' could be pseudo-classes, aria states or custom chakra 'states'
style props 'states' take a leading underscore, and the actual style prop declarations go within an object within the state.
e.g. _hover={{ fontWeight: 'semibold' }}
⟮h∞;<img src="sm_2021-09-17--19-05-46-screenshot.jpg">⟯
⟮c1;chakra⟯ provides some ⟮c2;predefined shadows⟯ as style props with ⟮c3;boxShadow⟯⟮c4;="name"⟯

the sx prop is an escape hatch to CSS when style props are not enough.
the sx prop takes an object whose keys can be CSS or the style prop superset.
sx={{ filter: 'blur(8px)' }}
use-cases for the sx prop are css variables, css properties for which there are no style props, nested selectors and custom media queries.

#### (Bootstrap) components via JSX

react-bootstrap implements boostrap components as react/JSX components
for react-bootstrap, components must be individually imported via react-bootstrap/ComponentName
ergo, components named via class names become <ComponentName>
parts of components become <ComponentName.Part>
properties that were implemented as key-value classes in Bootstrap become normal key="value" porps
react-bootstrap specifically, theme-color becomes `variant` (prob inspired by other react libraries)

## environment ≈ Web APIs

### browsing contexts

A browsing context is the environment in which a browser displays a Document. 
A browsing context may be a tab or a window as well as a frame (iframe/frame)

A browsing context has a corresponding WindowProxy object.
A WindowProxy object wraps the currently-being-viewed Window object.
A WindowProxy objects [[Window]] represents the wrapped window.
the Window WindowProxy is currently wrapping is called the active window, the document associated with that window the active document.
When the browsing context is navigated, the Window wrapped by the WindowProxy object changes.

A browsing context has an opener browsing context, representing the browsing context from which it was opened (subject to noopener etc.)

Certain elements (for example, iframe elements) can instantiate further browsing contexts. These elements are called browsing context containers.
a browsing context container (essentially an iframe) has a nested browsing context
a nested browsing context has a `container` which is its browsing context container.
a nested browsing context's container document, which is its containers node document.


Browsing contexts may relate to each other in a tree w/ parents and children.
A top-level browsing context has no parent browsign context.

Each browsing context has a session history.
A session history is a list of Document objects.
The documents that make up a session history are those that the browsing context has presented, is presenting, or will present. 


It is possible to create new browsing contexts that are related to a top-level browsing context without being nested through an element. Such browsing contexts are called auxiliary browsing contexts. Auxiliary browsing contexts are always top-level browsing contexts.

An auxiliary browsing context has an opener browsing context, which is the browsing context from which the auxiliary browsing context was created, and it has a furthest ancestor browsing context, which is the top-level browsing context of the opener browsing context when the auxiliary browsing context was created.
The opener attribute of Window returns the WindowProxy object of the opener broswing context, if extant/available.

#### secure contexts

Things that can only be used in secure contexts: Notifications
A document is in a secure context if it is the active document of a secure top-level browsing context (i.e.a document within a theoretically secure iframe browsing context is not secure if it's top-level browsing context is not also secure)
a resource is secure 

### the DOM

#### the DOM

DOM|Document Object Model
The DOM is a tree data structure that acts as an interface for a XML (or XML-derived) or HTML document.
DOM vertices are `Node`s (often subclasses of `Node`).
`Node` implements the EventTarget interface, so all things inheriting from Node also do.

#### APIs

Javascript offers a rich DOM parsing API called the DOM API.


table:span=2;DOM parsing libraries in other languages
beautiful soup|python


#### document

The Document interface represents any web page loaded in the browser and serves as an entry point into the web page's content, which is the DOM tree.
the root Node of the DOM tree is of type Document
Nodes of type Document are known as documents
The Document interface describes the common properties and methods for any kind of document. Depending on the document's type (e.g. HTML, XML, SVG, …), a larger API is available: HTML documents, served with the "text/html" content type, also implement the HTMLDocument interface, whereas XML and SVG documents implement the XMLDocument interface.
Document's browsing context is the browsing context whose session history contains the Document.

#### Node tree

A node tree is a set of nodes arranged as a tree.
A document tree is a node tree whose root is a document.
A shadow tree is a node tree whose root is a shadow root.

#### Node

a node has an associated document (essentially an owner), which is known as its 'node document'

##### interface

cloneNode(deep?: boolean)|returns a duplicate of the node

##### NodeLists

A NodeList is similar to an Array, but doesn't have all the methods.
A NodeList is a linear collection of nodes.
NodeList has a foreach method.
NodeLists can be live or static.
A live NodeList (or similar) reflects changes in the DOM
A static NodeList (or similar) does not reflect changes in the DOM
`HTMLCollection`s are an interface similar to NodeLists, but may only contain elements, is live, and has a far less rich interface.

##### types of


    <tr>
      <th colspan="5">⟮c9;Node⟯
others...|

            <tr>
              <th colspan="3">⟮c12;Element⟯
others...|<span class="c10-cloze c12-scr">HTMLElement</span>|<span class="c11-cloze c12-scr">SVGElement</span>

      |

            <tr>
              <th colspan="2">⟮c8;Document⟯
<span class="c6-cloze c8-scr">HTMLDocument</span>|<span class="c7-cloze c8-scr">XMLDocument</span>

      |<table>⟮c5;DocumentFragment⟯
</tbody></table>|
<tr>
            <th colspan="3">⟮c1;CharacterData⟯
<span class="c2-cloze c1-scr">Text</span>|<span class="c3-cloze c1-scr">Comment</span>|<span class="c4-cloze c1-scr">ProcessingInstruction</span>

        </tbody></table>


##### Elements

any HTML element has a JS interface that is called HTMLSomeelementnameElement.

###### types of attribute

An IDL (Interface Description Language) is a generic language used to specified objects' interfaces apart from any specific programming language.
In XMLHTML, most attributes have two faces: the content attribute and the IDL attribute.

The content attribute is the attribute as you set it from the content (the HTML code) and you can set it or get it via element.setAttribute() or element.getAttribute(). The content attribute is always a string even when the expected value should be of a different type.

the IDL attribute may be accessed from js like element.foo.

Any content attribute is also acessiable as an IDL attribute.

###### IDL interface

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

###### Types of elements (and their interfaces)

####### HTMLCanvasElement

The HTMLCanvasElement.toDataURL(type) method returns a data URI containing a representation of the image in the format specified by the MIME type in the type parameter.

#### custom elements

#### DOM traversal

document.querySelector(selector)|get first element that matches selector
document.querySelectorAll(selector)|get NodeList of elements that matches selector
qs and qsa can be called on document for a global search, or on an element for a search only on that elements children.
qsa returns a static NodeList
document.getElementBy<whatever>() returns HTMLCollections.
document.getElementBy<whatever> has four variants ById, ByClassName, ByTagName
Element.closest(selector)|get the closest ancestor element which matches the selector

#### other interfaces & classes

##### DOMTokenList

The DOMTokenList interface represents a set of space-separated tokens. 

#### visibilityState

visibilityState = whether the document is somehow in the background/not in a visible tab/minimized, etc.
visibilityState = visible|hidden
change of document.visibilityState fires visibilitychange

### window

The Window interface represents a window containing a Document (however, the window is not persistent, but changes during navigation as well. the browsing context is the persistent thing)
A global variable, window, representing the window in which the script is running, is exposed to JavaScript code.
A Window has an associated `Document`.
You can get the document associated with a window by window.document.
The `Document` associated with a window only changes during navigation.
Each Window has an associated `Navigator`.

#### bars

the Window object has a few properties representing certain UI elements (all bars), all represented by a BarProp object with the single attribute 'visible'
BarProps: locationbar, personalbar, menubar, crollbars, statusbar, toolbar

#### Web Storage API

the Web Storage API is made up of sessionStorage and localStorage.
sessionStorage and localStorage both implement the Storage inteface.
getItem(name)
setItem(name,value)
removeItem(name)
clear()

sessionStorage lasts for a session, localStorage lasts until cleared.
localStorage is larger than sessionStorage.

#### notifications

Notification.requestPermission() is a promise, which if fulfilled means we have recieved permission to send notifications.
Browsers increasingly don't even allow us to ask for notification permissione exept in response to user action.
After gaining permission, we can create notifications with the Notification() constructor.
the ⟮c3;Notification() constructor⟯ takes two arguments, the ⟮c1;title of the notification⟯ and an ⟮c2;object of options⟯
the options object for the notification constructor as a bunch of properties that precisely configure the notification.
.close()|closes the notification manually
Notification objects can have the events click, close, error and show (when the notification is shown) triggered on them.

#### Intersection Observer API

The Intersection Observer API provides a way to asynchronously observe changes in the intersection of a target element with other elements or the viewport.

#### intervals

⟮c1;window⟯.​setTimeout(function, delay, args);

#### misc

window.getComputedStyle(<element>) gets a read-only CSSStyleDeclaration.

### navigator

Instances of Navigator represent the identity and state of the user agent (the client).

#### Geolocation API

the Geolocation API is used for location hadnling in the browser.
you get an object of Geolocation from navigator.geolocation
inteface Geolocation {
  getCurrentPosition(success: function, error?: function, options?: PositionOptions): void;
  watchPosition(success: function, error?: function, options?: PositionOptions): Id;
  clearWatch(Id): void;
}
interface GeolocationPosition {
  coords: GeolocationCoordiantes;
  timestamp: DOMTimeStamp;
}

### events

#### EventTarget

The EventTarget interface is implemented by objects that can receive events and may have listeners for them.

#### event handler registration

event handler registration can be done via the content and IDL attribute on<event> or EventTarget.addEventListener()
the on<event> attribute takes a function to call.
on<event> doesn't work on non-`Elements`
addEventListener allows for registration of more than one event handler for the same event on the same EventTarget.
on<event> usage is not recommended, as it will overwrite other event handlers registered on the same element.
event handlers get an `Event` as an argument.

to work, we must pass removeEventListener the event as well as the ⁑exact same function object⁑

#### event capturing

in the capturing phase, the browser goes from the root element up to the target downwards
in the target phase, the browser triggers any event handlers on the target itself
in the bubbling phase, the browser goes from the the target up to root element upwardswards
capturing phase > target phase > bubbling phase
capturing/bubbling event handlers trigger during the capturing/bubbling phase respectively, and both on the target phase
Event.bubbles prevents bubbling

#### Event

Event.target returns a reference to the thing on which the Event was dispatched.
Event.currentTarget / this returns a reference to the thing on which the Event is being handled.

##### defaults

calling Event.preventDefault() or returning false from an on<event> handler prevents the default
touchstart, touchmove (FF, Chrome, Edge) have passive: true by default
tell the browser that you won't call preventDefault()   3rd option of addEventListener {passive: true}
Event.defaultPrevent|was a default prevented?

#### patterns

⟮c1;event delegation⟯ is ⟮c3;handling events⟯ (that are ⟮c4;similar somehow⟯) on ⟮c2;a common ancestor⟯
Event delegation only works due to event bubbling

#### node

node handles events in the module `event`, where everything that can have events implements `EventEmitter`.

##### EventEmitter methods

on|add event handler
off/removeListener|remove an event handler
once|add one-time event handler
emit|trigger an event
removeAllListeners|remove all listeners from event emitter

### Web Speech API

Web Speech API: text to speech/speech to text

### Web Audio API

### PWA

PWA|Progressive Web App
PWAs should work to some extent even when ⟮c1;there is no internet⟯
⟮h∞;<img src="SpStAtUk8Zp5iwi9yqKP.jpg">⟯ the ⟮c1;screenshots⟯ property of a web app manifest allows for ⟮c2;previewing images of the web app when installing⟯
for a PWA to be installable, you need to have the web app manifest (with required fields filled in), and a service worker (chromium only) (also an icon and HTTPS, but these are kinda obviosu)

#### service workers

⟮c1;Service Workers⟯ are a type of ⟮c2;Web Worker⟯
The main problem ⟮c1;service workers⟯ are solving is handling ⟮c2;loss of connectivity⟯
The ⟮c2;service worker's⟯ ⟮c1;lifecycle⟯ is separate from ⟮c3;your webpage's⟯

The first step in a service workers lifetime is navigator.serviceWorker.register(path-to-service-worker.js), which returns a promise
The service worker's scope ( which fetch events it reacts to) is determined by the directory the script implementing it is in 
e.g. /sw.js has the scope of everything in the project, while /example/sw.js has the scope of everything in /example.
The service worker adds event listeners like so: self.addEventListener...
⟮c1;Workbox⟯ is a library that ⟮c2;bakes in a set of best practices⟯ and ⟮c3;removes the boilerplate⟯ every developer writes when working with ⟮c4;service workers⟯.

### wasm

wasm = web assembly
WebAssembly is a low-level assembly-like language with near-native performance.
Most big compiled languages can compile to web-assembly.
In essence, WebAssembly runs in a low-level virtual machine
A WebAssembly binary is called a module
A wasm Module itself is stateless, and uses a Memory and Table for state. 
Together, a wasm module + memory + table are an Instance
a wasm Table is a typed array of references (e.g. to functions) 
a wasm Memory is a linear array of bytes used for storage
wasm page size = 64k
wasm memory can only be grown by a multiple of the page size
wasm memory cannot be shrunk
By default, as of 2021, the wasm interface only accepts numbers (and pointers) as types

wasm modules|.wasm
wasm textual representation|.wat

wasm-bindgen for rust generates glue and polyfills things so that we can use a bunch of types of features that we couldn't otherwise.
wasm-pack is a tool for helping integrating rust wasm with your webdev workflow.
AssemblyScript is a TypeScript-based programming language that is compiled to WebAssembly.


## CSS

CSS = Cascading Style Sheet

S ::= {<statement>}
statement ::= <ruleset>|<at-rule>
ruleset ::= <selector-list><declaration-block>
rulesets are less properly but more commonly called rules
selector-group ::= <selector>{,<selector>}
declaration-block ::= \{<declaration-list>\}
declaration-list ::= {<declaration>}
declaration :: <property>:<value>; // Technically, the ; is not a part of the declaration, since it only separates and does not terminate declarations. Therefore you can leave out the final semicolon of a declaration block, though this is generally not advised. This would overcomplicate the ENBF, so here this note.

at-rule ::= @<identifier> <prelude>[\{<block>\}]
At rules that have the optional block are known as nested at-rules.
the block that an at-rule may take is explicitly specified by the spec not to be the same as the declaration block of a ruleset, and therefore not at all subject to the same syntax. Nested at-rules may however *choose to* follow the same syntax as a declaration block.
nested at-rules whose block is a declaration block: @counter-style, @font-face
nested at-rules whose block is a declaration block, but also supports other at-rules within: @page
nested at-rules whose block is not a declaration block: @keyframes, @media, @supports.
A nested statement is a statement that can be used inside a conditional group rule.
A conditional group rules is a CSS at-rule that associates a condition with a group of other CSS rules.
The commmon conditional group at rules are @media and @supports.


flex-container:<img src="sm_tmpyk7c4jes.png">

style as a HTML attribute takes n declarations

### Selectors

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

selector-list (default complex selector meaning) ::= <complex-selector>{,<complex-selector>}
complex-selector ::= <compound-selector>{[<combinator>]<compound-selector>}
compound-selector ::= <simple-selector>{<simple-selector>}
simple-selector ::= <type-selector>||<universal-selector>||<attribute-selector>||<class-selector>||<id-selector>||<pseudo-class-selector>||<pseudo-element-selector>

#### Selectors

##### Simple selectors



###### Basic types

Syntax of universal selector ::= *
the universal selector matches everything
Syntax of type selector ::= <name>
the type selector matches any element with the given nodename (so foo will match any <foo>)
Syntax of class selector ::= .<name>
The class selector matches any element with the given class
Syntax of id selector ::= #<name>
The id selector matches any element with the given ID
The attribute selector matches any element where a certain attribute is a certain way.
Syntax of attribute selector ::= \[<attr>[<operator><alue>]\]
no operator (and no value) [<attr>]|just elements with attribute present
= [attr=value]|attr is exactly value


Adding an i (or I) before the closing bracket causes the value to be compared case-insensitively (for characters within the ASCII range).

###### Pseudo-classes

A pseudo-class indicates a state of an element
A pseudo-class is begun by a single colon

:empty| matches an element that has no child **nodes** (including text nodes)
:not(<selector-list>) matches elements that don't match selector-list.
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

####### input pseudo-classes

a number of pseudo-classes have to do with input
:enabled/:disabled|HTML enabled attribute is specified, or specified on the parent fieldset (or not, for disabled)
:read-write/:read-only|element is not disabled and is not readonly, or has the contenteditable attribute set to true/element has none of these things
:in-range/:out-of-range|element is/is not within a specified range 
:required/:optional|elements with the "required" attribute specified/not specified
:valid/:invalid|element is valid/invalid according to properties specified in HTML
:checked|selects a toggled radio button or checkbox


####### Tree-structural pseudo-classes

Tree-structural pseudo-classes are pseudo-classes that allow selection of elements based on information in the document tree

:root  Selects the document's root element  
:empty  Selects every &lt;p&gt; element that has no children (including text nodes)  

Child-indexed pseudo-classes are tree-structural pseudo-classes that select elements based on their index among their siblings.
Child-indexed pseudo-classes end -child
For any child-indexed pseudo class there is an equivalent typed child-indexed pseudo-class that ends -of-type isntea of -child
Typed child-indexed pseudo-classes are tree-structural pseudo-classes that select elements based on their index among siblings of the same type.

:nth-child(<nth>)  Selects every &lt;p&gt; element that is the <nth> child of its parent  
:nth-last-child(<nth>)  Selects every &lt;p&gt; element that is the <nth> child of its parent, counting from the last child  
:first-child  Selects every &lt;p&gt; element that is the first child of its parent  
:last-child  Selects every &lt;p&gt; element that is the last child of its parent  
:only-child  Selects every &lt;p&gt; element that is the only child of its parent  

nth ::= <an-plus-b>|even|odd
an-plus-b ::= <integer>n+<integer>

####### link-related pseudo-classes

:any-link|All links: <a> and <area> elements
:link|Selects all unvisited links  
:visited|Selects all visited links  

####### user action pseudo-classes

user action pseudo-classes are pseudo-classes that allow you to react to user action

:active|Selects the active link (when you click it/hold down the mouseclick on it)  
:hover|Selects links on mouse over  
:focus|element has the focus (accepts keyboard or mouse events, or other forms of input).
The :focus-within CSS pseudo-class matches an element if the element or any of its descendants are focused. In other words, 
The :focus-visible pseudo-class applies while an element matches the :focus pseudo-class and the UA (User Agent) determines via heuristics that the focus should be made evident on the element.

###### Pseudo-elements

A pseudo-element indicates a part of a element which isn't a real element.
A pseudo-element is begun by two colons

::after, ::before
In CSS, ::before/::after creates a pseudo-element that is the first/last child of the selected element. 
content can only be usefully be used on ::after and ::before
content-values ::= normal|none|({<content-specifier>} / <alt-text>)
alt-text ::= <string>|<counter>
the content-specifier can be a bunch of different things
a ::before/::after pseudo-element will not display if it does not have content.

::placeholder|matches placeholder text
In HTML/CSS, <input> and <textarea> can have placeholder text in form of a placeholder attribute.
::selection|matches text currently selected/highlighted by the user via cursor/touch etc.
::selection only supports a subset of properties, mainly color, background-color and text-shadow.
::first-letter|matches the first letter of a block-level element
::first-line|matches the first line of a block-level element
::backdrop is the pseudo-element that is the size of the viewport and is rendered beneath ⟮c1;any element that is in fullscreen⟯


##### Combinators


+
~
>


##### The Grouping selector

#### value processing

Once a user agent has parsed a document and constructed a document tree, it must assign, to every element in the flat tree, and correspondingly to every box in the formatting structure, a value to every property that applies to the target media type.

The final value of a CSS property for a given element or box is the result of a multi-step calculation:

First, all the declared values applied to an element are collected, for each property on each element. There may be zero or many declared values applied to the element.
Each property declaration applied to an element contributes a declared value for that property associated with the element.
Cascading yields the cascaded value. There is at most one cascaded value per property per element.
Defaulting yields the specified value. Every element has exactly one specified value per property.
Resolving value dependencies yields the computed value. Every element has exactly one computed value per property.
Formatting the document yields the used value. An element only has a used value for a given property if that property applies to the element.
Finally, the used value is transformed to the actual value based on constraints of the display environment. As with the used value, there may or may not be an actual value for a given property on an element.

#### Cascading

The cascade takes an unordered list of declared values for a given property on a given element, sorts them by their precedence as determined below, and outputs a single cascaded value.

The cascaded value is determined by their precedence, which is specified by the cascade sort order:
origin & importance > context > specificity > order of appearance in source document.

##### Cascade origin

The three possible cascade origins are user-agent, user, or author.
author stylesheet|applied by the website author
user stylesheet|applied by the user, e.g. via addons
user-agent stylesheet|applied by the user-agent = browser
In addition, there are two virtual cascade origins, transition declarations and animation declarations.
the weakest style in an element higher in the cascade origin hierarchy beats the strongest style in an element lower in the cascade origin hierarchy
normal declarations|author>user>user-agent
important declarations|user-agent>user>author

##### important

A declaration is important if it has a !important annotation as defined by [css-syntax-3], i.e. if the last two (non-whitespace, non-comment) tokens in its value are the delimiter token ! followed by the identifier token important. All other declarations are normal (non-important).
An important declaration takes precedence over a normal declaration.

Ergo, for cascade origin plus important there is the following hierarchy:

transition declarations > Important user agent declarations > Important user declarations > Important author declarations > Animation declarations > Normal author declarations > Normal user declarations > Normal user agent declarations

##### context

##### Specificity

Specificity is the means by which browsers decide which CSS property values within a single source type are the most relevant to an element, based on selectors.
Specificity is tiered, with lower tiers not being able to beat higher tiers.
Each specifier on a tier gains you one point on the specificity scale.

3rd lowest|id selectors
2nd lowest|class selectors|attribute selectors|pseudo-class selectors
lowest|element selectors|pseudo-element selectors
no effect on specificity|:not(), universal selector

### Declarations

#### Properites and Values

##### inherited, initial, etc.

any property is inherited or not in its behavior when no value is assigned
inherited properties default to inheriting
non-inherited properties default to the initial value
some initial values are unintuitive, since we rarely see them, as they are typically overwritten by UA stylesheets
On the root element, even inherited properties recieve their initial values if not otherwise specified.
Keyword inherit/initial to force the inherited/initial value.
unset: choose between inherit and initial based on if the thing is inherited or non-inherited
The revert CSS keyword reverts the cascaded value of the property from its current value to the value the property would have had if no changes had been made by the current cascade origin to the current element.
If used by a site's own styles (the author origin), revert rolls back the property's cascaded value to the user's custom style, if one exists; otherwise, it rolls the style back to the user agent's default style.
If used in a user's custom stylesheet, or if the style was applied by the user (the user origin), revert rolls back the cascaded value to the user agent's default style.
If used within the user agent's default styles, this keyword is functionally equivalent to unset. 
The revert keyword is mainly useful to revert to the user agents default style instead of the often-useless initial value.

The all property takes one of initial|inherit|unset|revert to reset everything but direction and unicode-bidi

##### css variables

Declaration: --var-name: value;
Accessing: var(--var-name)

##### vendor prefixes

vendor prefixes have the syntax -<vendorname>-<propertyname>
webkit|any webkit-based (and thus also blink-based) browser besides edge
moz|firefox
o|pre-webkit opera
ms|IE and edge

vendor prefixes were designed to allow experimenting with experimental CSS features without having to worry about future changes to the standard creating breaking changes.
The problem with vendor prefixes is that in fact, vendor-prefixed properties just got used in productio as well.
As of ~2020, the trend is away from using vendor prefixes, and instead using user-controlled experimental flags.

##### Props

A shorthand property is a css property that allows setting multiple other properties at once.
shorthand properties in css try to not force a specific order, where semantically possible.
If a value is not set within a shorthand property, it is set to its initial value, overriding subvalues.
Using inherit as a value of many within a shorthand property is invalid.

###### position

position-values ::= static|relative|absolute|fixed|sticky.
position: static is the default.
A positioned element is an element with any position but static.
A relatively positioned element is an element with position relative.
An absolutely positioned element is an element with position relative or fixed.
(only) for positioned elements, the `top`, `right`, `boottom`, `left` properties take effect
position|top, right, bottom, left offset from|takes up how much space
relative|where it would have been if it had position static|same as static
absolute|closed positioned ancestor|none
fixed|viewport or closest ancestor with tarnsform, perspective or filter set|none
sticky|nearest scrolling and block-level ancestor|same as static

top/right/bottom/left move the element away from the relevant edge, so that positive values for each have the effect of moving the element in the opposite direction
between top and bottom, top wins.
between left and right, the inline base direction wins.

position: fixed will always be visible at the same position
position: sticky will be in the flow of the document until scrolled to its offset specified by top, right, bottom, left, and then act like position: fixed

###### Cursor

`cursor` sets how the cursor looks when mousing over (generally irrelevant for touchscreens).
`cursor` value syntax {<url> <x> <y>,} <keyword>
When specifying an url() for cursor, the x and y values specify the offset in px of the hotspot of the cursor
`cursor: none` hides the cursor.
`cursor: default` shows the platform-default cursor.
Other <keyword>s for `cursor` (non-exhaustive, as there are ~40) are wait, crosshair, not-allowed, zoom, copy, grab.

###### Caret

The caret-color CSS property sets the color of the insertion caret, the visible marker where the next character typed will be inserted. 

###### scroll-snap

In a basic sense, CSS scroll snap is for snapping to specific scroll points
For scroll snap to do anything, you have to specify scroll-snap-type and scroll-snap-align.
For scroll snap, you specify scroll-snap-type on the parent and scroll-snap-align on the children.

scroll-snap-type-values ::= <axis> [mandatory|proximity]
axis ::= x|y|block|inline|both

the axis part of scroll-snap-type determines along which axis to snap. Here, block and inline refer to the relevant axes.
mandatory|must snap no matter what
proximity|snap only when close to scroll point.

scroll-snap-align ::= (start|end|center) [start|end|center]
when two values set first is block, second inline

While scroll-padding is set on the parent, scroll-margin is set on the child, and so allows different values for different children.

###### word-break, overflow-wrap

###### width, height

width and height each have corresponding min- and max- properties
power of width and height properties: min- > max- > ø
width and height and corresponding min/max values take the following values: <lpminmaxauto>|fit-content(<length-percentage>)

What width and height size depends on the box-sizing property
content-box|width and height size content-box
border-box|width and height size border-box

###### flexbox, grid and columns

Flex or grid containers are declared by setting display to flex/inline-flex or grid/inline-grid.
A grid (as a layout, not just in CSS) is made up of horizontal and vertical (and sometimes angular) <dfn>grid lines</dfn> that intersect to define n <dfn>grid cells</dfn> 
In a grid layout, multiple adjacent cells (in CSS, forming a rectangle) are called a grid area.
In a grid layout, the area between two adjacent grid lines is called a grid track.

The order CSS property sets the order to lay out an item in a flex or grid container. Items in a container are sorted by ascending order value and then by their source code order.

####### box alignment properties

The box alignment properties in CSS are a set of 6 properties that control alignment of boxes within other boxes. 
The box alignment properties can be described along two metrics, which axis they apply to, and whose position they control.
All six box alignment properties 
Of the six box alignment properties, justify-self and justify-items have no effect in flexbox.
Theoretically, all box alignment properties besides align-self and align-items should also work to position block containers, but this is unimplemented.

justify-* adjusts things in the inline base direction (ltr in the default setup) (unless flexbox)
align-* adjusts things in the block flow direction (top to bottom in the default setup) (unless flexbox)
place-* is a shorthand for align-* justify*, if only one value is specified, it generally applies to both.

For flexbox, what justify-* and align-* align relative to are the main axis/cross axis, respectively.

*-content adjusts foo's content within foo. https://drafts.csswg.org/css-align/images/content-example.svg
*-self adjusts foo within foo's parent. https://drafts.csswg.org/css-align/images/self-example.svg
*-items adjusts all of foo's children within their box. https://drafts.csswg.org/css-align/images/items-example.svg

The alignment subject is the thing being aligned by the property:
the alignment subject  for *-self is the margin box of foo.
the alignment subject for *-content is defined by its layout mode/formatting context.

the alignment container is the thing within which the alignment subject is a ligned with.
the alignment container is generally the containing block container box.

the box alignment properties take three types of keywords: positional alignment, baselinge alginement, distributed alignment
type of keyword|function
positional alignment|alignment to absolute position within alignment container
baseline alignment|alignment as relationship between the baselines of multiple alignment subjects
distributed alignment|alignment as distribution of space among/between alignment subjects

positional-alignment keywords may be the simple center, start, and end, flex-start/flex-end, self-start/self-end, or left/right.
flex-start and flex-end behave like start/end.
the difference between start/end and left/right is that the former respect the inline base direction and the block flow direction, while the latter is always left/right no matter what.
The start and end keywords use the inline base direction of the alignment container, the self-start and self-end keywords use the inline base direction of the alignment subject.


baseline-alignment-keyword ::= [first|last] baseline
specifying only baseline as a  baseline-alignment-keyword computes to first baseline

A baseline-sharing group is composed of boxes that participate in baseline alignment together. 
Boxes in a baseline-sharing group are aligned to each other using their alignment baselines. 
A baseline set is a set of baselines, generally only one as long as you are not mixing writing systems.
Each line has a baseline set.
Each box potentially has a first/last baseline set which is the baseline set of the first/last line of box.
The alignment baseline is a baseline in its baseline set, generally the dominant baseline (within a shared alignment context).
Boxes have a <dfn>shared alignment context </dfn> when they are either (no mixing and matching) table cells, grid items and flex items of the same inline base axis (though not direction), or between grid items of the same block flow axis (though not direction)
A baseline-sharing group where they share an alignment context, as long as they have compatible baseline alignment preferences.
Two boxes have compatible baseline alignment preferences if they have the same block flow direction and the same baseline alignment preferences or opposite block flow direction and opposite baseline alignment preferences.
The first and last values give a box a baseline alignment preference: either “first” or “last”, respectively.

distributed-alignment-keyword ::= space-between|space-around|space-evenly|stretch
space-between|space only between elements, no space at borders|[xxx      yy      zzzz]
space-around|space on every side, space at borders is half size|[  xxx    yy    zzzz  ]
space-evenly|space on every side, every space is the same size|[   xxx   yy   zzzz   ]
stretch|no space, size is increased equally|[xxxxxxxyyyyyyyzzzzzzz]

####### flexbox axes

For flexbox, if flex-direction is row or row-reverse, the main axis corresponds to the inline base direction, and the cross axis corresponds to to the block flow direction.
For flexbox, if flex-direction is column or column-reverse, the main axis corresponds to the block flow direction, and the cross axis corresponds to to the inline base direction.

####### gaps

the gap, row-gap and column-gap specifiy gutters between items in a flex/multi-column/grid container.
gap is a shorthand for row-gap and column-gap, if only one value is specified, it sets them to the same value.
the three gap properties take a <length-percentage>
For multi-column containers, row-gap currently does nothing.
for flex containers, column-gap specifies minimum spacing between flex items, and row-gap specifies minimum spacing between flex lines if flex-direction is row or row-reverse, otherwise what column-gap and row-gap do is reversed.
For the gap, row-gap and column-gap there exist the now archaic grid-* aliases.

####### grid

Fundamentally, the grid consists of two tasks: defining a grid & its sizes, and placing items within that grid.

######## defining and sizing a grid

In CSS, there are two kinds of ways to define the grid and its sizes, using the explicit or using the implicit grid.
grid-auto*|implicit grid
grid-template*|explicit grid

there are four grid-template properties, grid-template-columns & -rows, grid-template-areas as well as the shorthand grid-template.
there are three grid-auto properties, grid-auto-column & -rows and grid-flow

grid-template-columns & -rows define how many columns/rows of which size the explicit grid wil contain.
grid-auto-columns & -rows define what size columns/rows the auto placement algorithm will add.
specifying multiple values for grid-auto-columns & -rows specifies a pattern which to follow.
grid-template-columns & rows take the same values, which i will call <grid-template-values>

grid-template-rc-values ::= {[<line-names> ](<flex-l-p-min-max-auto-mm>|<repeat>)}[ <line-names>]
grid-auto-values ::= <flex-l-p-min-max-auto-mm> {<flex-l-p-min-max-auto-mm>}

minmax ::= minmax\(<l-p-min-max-auto>|<flex-l-p-min-max-auto>\)
The minmax() CSS function defines a size range greater than or equal to min and less than or equal to max. It is used with CSS Grids.
l-p-mm ::= <length-percentage>|<minmax>
flex-l-p-min-max-auto-mm ::= <flex-l-p-min-max-auto>|<minmax>
line-names-and-track-size ::= [<line-names> ]<flex-l-p-min-max-auto-mm>

the repeat() function repeats the pattern specified for the amount of times specified, or until something is full.
the auto-* keywords for repeat creates rows until creating more would overflow.
the auto-* keywords for repeat treat the track sizes of tracks that can shrink or grow as their maximum size, unless that maximum size is infinite/indefinite.
the difference between the auto-fill and auto-fit keywords is that auto-fit will collapse any empty repeated tracks that still exist after grid-items re placed, while auto-fill will not.

Using grid-template properties, you can assign line names to grid lines, to be used later for positioning.
If the same name is used for multiple grid lines, they will be numbered by a so-called occurrence number starting at the second one, which is separated by a space
Grid lines are numbered staring at 1

repeat ::= repeat\((<integer>|<auto-keyword>), {<line-names-and-track-size>}[ <line-names>]\)
auto-keyword ::= auto-fill|auto-fit # my own name

line-names ::= [<custom-ident>{ <custom-ident>}]

grid-template-area manually created named grid areas made up of the specified cells.
Within grid-template-areas . refers to an empty grid cell

grid-template-area-values ::= <grid-string>{<grid-string>}
grid-string ::= "<cell-specifier>{ { }<cell-specifier>}"
cell-specifier ::= <string>|.{.}

grid-template-values ::= <grid-template-row-columns>|<grid-template-row-coolumns-areas>
grid-template-row-columns ::= <grid-template-rc-values> / <grid-template-rc-values>
grid-template-row-coolumns-areas ::= {<grid-string> <flex-l-p-min-max-auto-mm>} / <grid-template-rc-values>

grid-auto-flow-values ::= [row | column] [dense]
grid-auto-flow: row makes it add auto-positioned elements to rows, adding new rows as necessary (and respectively for grid-auto-flow: column)
The dense keyword for grid-auto-flow makes it use the dense algorithm, otherwise a sparse algorithm is used

dense algorithm|attempt to fill holes earlier in the grid
sparse algorithm|never backtrack to fill holes

specifying grid-lines with -start/-end that enclose a rectangle creates the relevant grid-area automatically 
specifying grid-areas creates the relevant grid lines with -start/-end automatically 

the grid css property is a shorthand for grid-template-* and grid-auto-*, 6/7 properties in total

######## placing items

grid areas and grid lines
grid-area allows placing an item at a grid-area created manually or automatically, taking up that space
grid-area dots

grid-column/row-start/end take the same set of values, <grid-line>
grid-column/row-start/end specify the edges of an items grid area
Most basically, grid-column/row-start/end either position using an integer, or using a grid line name.
specifying an integer for grid-column/row-start/end positions it at that number gridline.
specifying an integer and span for grid-column/row-start/end positions it that many grid lines from the start (if end) or from the end (if start).
specifying an custom-ident while also specifying an integer and span for grid-column/row-start/end positions it that many grid lines from the start (if end) or from the end (if start), counting only gri lines with the custom-ident
specifying a custom-ident for grid-column/row-start/end positions it at <custom-ident>-start(if start)/-end(if end)
grid-line ::= auto | <custom-ident> | [span] [<integer>] [<custom-ident>] # slightly simplified
grid-row/column are shorthand for -start/-end
grid-row-values, grid-column-values ::= <grid-line>[ / <grid-line>]
grid-area basically takes two kind of values, the name of a grid area, or four specifiers for row/column start/end, specified in the order rs / cs / re / ce.

grid items may be placed in the same area, i.e. they may overlap, even completely.

####### flex

flex-flow is a shorthand for flex-direction and flex-wrap
flex-wrap may take the values nowrap, wrap, wrap-reverse.
flex-direction may take the values row, row-reverse, column, column-reverse

flex is a shorthand of flex-grow flex-shrink flex-basis (in that order)
flex-grow and flex-shrink specify a factor, which specifies how fast that element should grow/shrink relative to other flex elements.
flex-basis specifies the initial size of a flex item along its main axis.

By default flex items don't shrink below their minimum content size. To change this, set the item's min-width or min-height.

####### columns

The column-fill CSS property controls how an element's contents are balanced when broken into column fragmentainers (= column boxes)
auto|fill column boxes sequentially in the inline base direction, until the column box is full
balance|fill column boxes so that they have roughly the same height.

columns is a shorthand for column-count and column-width.
column-span: all transforms an element into a spanning element.
A spanning element spans all columns.

column-span specifies a maximum amount of columns
column-width specifies a minimum width of columns

###### Pointer-events

pointer-events: ⟮c1;none⟯ makes a thing completely ininteractable with a mouse.

###### Text

The text-transform CSS property specifies how to capitalize an element's text. It can be used to make text appear in all-uppercase or all-lowercase, or with each word capitalized. It also can help improve legibility for ruby.
the color keyword sets the color of the text and text decorations and accpets a <color> value.

word-spacing sets the additional space between words beyond the space there by default. 
word-spacing takes a <length-percentage>
letter-spacing takes a <length> to add/subtract from the usual letter-spacing/tracking.

the quotes property sets the quotes that the open-quotes and close-quotes of content will evaluate to.
the quotes property is inherited and so doesn't have to be set on the thing with the content property
quotes takes two strings, the opening and the closing quote, it may also take two more strings, which are for when there are nested.

hyphens controls the behavior of hyphens.
none|will not hyphenate, even if manually indicated via &shy;
manual|only at places indicated via &shy;
auto|language-dependent auto-hyphenation (may not work depending on platform or language)

text-indent takes a <length-percentage> which specifies how much to indent the first line box.
tab-size accepts a <length> to specify the width of the tab character, or an <integer> to specify its width in multiples of the space character

text-align aligns elements within line boxes along the inline base direction.
vertical-align algins elements within line boxes along the block flow direction.
vertical-align is relative to the line box for some properties, and to the font for others.


####### font

font-family sets the font family = typeface of the text.
font-family takes a font stack.
A font stack comma-separated list of font family names or generic family names, which repesents a priority of which ones to use.
generic family names are names like serif, sans-serif, monospace, cursive...
generic family names are guaranteed to resolve to an existing font family, and thus a font stack should generallly end in one.
It is good pracktice to quote font family names that contain whitespace, digits or punctuation characters.

The font shorthand allows setting properties starting with font-, as well as line-height.1

font-variant is a shorthand property for a few low-level font features, which all start with font-variant-
font-variant-caps: small-caps/petite-caps forces small caps/petite caps for non-capital letters, font-variant-caps: all-small-caps/all-petite-caps forces small caps for any letters, capital or not.

It may seem that certain html form elements can't have their font styled ⟮c1;because by default, these elements don't inherit font properties⟯

###### white-space

The white-space CSS property sets how white space inside an element is handled.
&nbsp;|New lines|Spaces and tabs|Text wrapping
⟮c1;s1-5;normal⟯|⟮c6;s6-20;Collapse⟯|⟮c7;s6-20;Collapse⟯|⟮c8;s6-20;Wrap⟯
⟮c2;s1-5;pre⟯|⟮c9;s6-20;Preserve⟯|⟮c10;s6-20;Preserve⟯|⟮c11;s6-20;No wrap⟯
⟮c3;s1-5;nowrap⟯|⟮c12;s6-20;Collapse⟯|⟮c13;s6-20;Collapse⟯|⟮c14;s6-20;No wrap⟯
⟮c4;s1-5;pre-wrap⟯|⟮c15;s6-20;Preserve⟯|⟮c16;s6-20;Preserve⟯|⟮c17;s6-20;Wrap⟯
⟮c5;s1-5;pre-line⟯|⟮c18;s6-20;Preserve⟯|⟮c19;s6-20;Collapse⟯|⟮c20;s6-20;Wrap⟯


###### Scrolling

overscrolling is what happens when you scroll further on something than that thing allows.
on mobile browsers and some desktop browsers, there is a form of overscrolling where the site will rubberband
when you overscroll a container, and this then starts scrolling the next-higher container, this is known as scroll chaining.
overscroll-behavior is actually a shorthand for overscroll-behavior-x and overscroll-behavior-y
overscroll-behavior: none prevents all overscrolling.
overscroll-behavior: contain will prevent scroll chaining only

###### Background

The background: property is a shorthand for ⟮c1;background-clip⟯, ⟮c2;background-color⟯, ⟮c3;background-image⟯, ⟮c4;background-origin⟯, ⟮c5;background-position⟯, ⟮c6;background-repeat⟯, ⟮c7;background-size⟯ and ⟮c8;background-attachment⟯
background-repeat may take a single value, which will specify both x and y, or two values, which apply to x and y respectively.
while single values for background-repeat generally specify both x and y, there are the single values repeat-x and repeat-y that will only repeat in the specified ways.
repeat|repeat as much as needed to cover the whole painting area, clipping if necessary
space|The image is repeated as much as possible without clipping. The first and last images are pinned to either side of the element, and whitespace is distributed evenly between the images. 
round|As the allowed space increases in size, the repeated images will stretch (leaving no gaps) until there is room (space left >= half of the image width) for another one to be added. When the next image is added, all of the current ones compress to allow room. 
no-repeat|do not repeat
background-color: <color>
background-color is rendered behind background-image
background-clip specifies where to clip the background, background-origin specifies from where the background should start, which may be the same, but often aren't
background-clip: <b-p-c-box-text>
background-origin: <b-p-c-box>
background-image: <image>

background-size-values: contain|cover|auto|(<length-percentage> [<length-percentage>])
background-size: contain/cover are similar in functionality to the object-fit values.
background-size: auto behaves similarly to object-fit: none.
giving background-size a length or percentage makes it exactly that wide if one value, or exactly that wide and high if two values.

All background properties may take a CSL to specify multiple backgrounds.


background-attachment specifies how the background interacts with scrolling (it has a bunch of keyword values that I can't remember)
background-position takes a <position> value to position the background.

###### edges

Things in css that take the edge shorhand and also have four individual properties to set them: border (border, border-color, border-width, border-style), margin, padding, scroll-padding, scroll-margin
Shorthand for edges in CSS use a consistent syntax:

1 value|specifies all sides|<img src="sm_1_border.png">
2 values|1st specifies top/bottom, 2nd specifies left/right|<img src="sm_2_border.png">
3 values|1st specfies top, 2nd specfies left/right, 3rd specifies|<img src="sm_3_border.png">
4 values|1,2,3,4 top right bottom left (TRBL)|<img src="sm_4_border.png">

Normally, instead of using the shorthand, you can also set the properties individually by using -top(-), -left(-), -bottom(-), -right(-) properties.

typically, any edge width is specified as a <length-percentage>
<length-percentage-edges> ::= <length-percentage> [<length-percentage>] [<length-percentage>] [<length-percentage>]

####### css box model

[⟮c1;s∞;Margin-box⟯ [⟮c2;s∞;Border-box⟯ [⟮c3;s∞;Padding-box⟯ [⟮c4;s∞;Content-box⟯]]]]

margin: auto can be used to center a thing horizontally, but not vertically

####### Border & outline

border can also be seen as a shorthand for border-top, border-right...
border-width, border-style, border-color are all shorthand for edges, and can be set via the 4 properties individually.
Notably, outline is similar to border in that it is composed of -width, -style, -color, but that in contrast to border, neither it itself nor its three subproperties are shorthands for the sides, nor are there individual properties for the sides - you either set the outline on all sides, or none at all.
Outlines can be moved away from its box via outline-offset: <length>

###### lines

Line is not really an official css term.
Lines: border, column-rule, outline
text-decoration functions similar to 'lines', in that it is a shorhand for -width, -style, and -color, but 1) it's called -thickness, not -width; 2) -style only supports a subset of keywords; 3) included in the shorthand is a fourt property, text-decoration-line, which takes n of the keywords underline||overline||line-through.

Lines have following shorthand and respective subproperties:
foo: foo-width || foo-style || foo-color

where foo-width takes a <line-width>
line-width ::= thin|medium|thick|<length>
where foo-style takes a <line-style>

line-style
hidden|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em hidden black;">&nbsp;</div>
dotted|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em dotted black;">&nbsp;</div>
dashed|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em dashed black;">&nbsp;</div>
solid|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em solid black;">&nbsp;</div>
double|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em double black;">&nbsp;</div>
groove|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em groove black;">&nbsp;</div>
ridge|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em ridge black;">&nbsp;</div>
inset|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em inset black;">&nbsp;</div>
outset|<div style="width: 10ch; height: 0.5em; border-bottom: 0.2em outset black;">&nbsp;</div>

###### Corners

1 value|specifies all corners|<img src="sm_1_corner.png">
2 values|1st specifies topleft and bottomright, 2nd specifies topright and bottomleft|<img src="sm_2_corner.png">
3 values|1st specfies topleft, 2nd specfies topright and bottomleft, 3rd bottomright|<img src="sm_3_corner.png">
4 values|1,2,3,4 topleft topright bottomright bottomleft|<img src="sm_4_corner.png">

Normally, instead of using the shorthand, you can also set the properties individually by using -top-left(-), -top-right(-), -bottom-right(-), -bottom-left(-) properties.

things that take corners may also take two sets of corners specifiers, separated by a slash.
If a thing takes two sets of corner specifiers, the first apply in x direction and the second in y direction.

Data types that specify corners are <border-radius>
border-radius: <border-radius>

###### Custom Counting

counter-reset and counter-increment and the css functions counter() and counters() are used to defined custom counters for counting().
counter-reset assigns a counter of name to value.
counter-reset defaults a counter to 0 if no value is specified.
counter-reset is also used initialize a counter.
counter-reset: <counter-name> [<value>]{,<counter-name> [<value>]}
counter-increment: <counter-name> [<value>]{<counter-name> [<value>]}
counter-increment: increments the counter by value (default 1) for each time it is encountered.
counter-reset on descendants creates a new counter, instead of assigning to the original counter.
counter-name ::= <custom-ident>
counter ::= <counter()>|<counters()>
counter() ::= counter\(<counter-name>[, <counter-style>]\)
counters() ::= counters\(<counter-name>, <string> [, <counter-style>]\)
counter-style ::= <list-style-type>|<@counter-style>
The css functions counter() and counters() takes a necessary first argument of the name of the counter. 
counters() differs from counter() in that it takes a middle argument of a string, and separates multiple instances of the counter with the given string.

```
ol {
  counter-reset: section;                /* Creates a new instance of the
                                            section counter with each ol
                                            element */
  list-style-type: none;
}

li::before {
  counter-increment: section;            /* Increments only this instance
                                            of the section counter */
  content: counters(section, ".") " ";   /* Combines the values of all instances
                                            of the section counter, separated
                                            by a period */
}
```

```
&#x3C;ol&#x3E;
  &#x3C;li&#x3E;item&#x3C;/li&#x3E;          &#x3C;!-- 1     --&#x3E;
  &#x3C;li&#x3E;item               &#x3C;!-- 2     --&#x3E;
    &#x3C;ol&#x3E;
      &#x3C;li&#x3E;item&#x3C;/li&#x3E;      &#x3C;!-- 2.1   --&#x3E;
      &#x3C;li&#x3E;item&#x3C;/li&#x3E;      &#x3C;!-- 2.2   --&#x3E;
      &#x3C;li&#x3E;item           &#x3C;!-- 2.3   --&#x3E;
        &#x3C;ol&#x3E;
          &#x3C;li&#x3E;item&#x3C;/li&#x3E;  &#x3C;!-- 2.3.1 --&#x3E;
          &#x3C;li&#x3E;item&#x3C;/li&#x3E;  &#x3C;!-- 2.3.2 --&#x3E;
        &#x3C;/ol&#x3E;
        &#x3C;ol&#x3E;
          &#x3C;li&#x3E;item&#x3C;/li&#x3E;  &#x3C;!-- 2.3.1 --&#x3E;
          &#x3C;li&#x3E;item&#x3C;/li&#x3E;  &#x3C;!-- 2.3.2 --&#x3E;
          &#x3C;li&#x3E;item&#x3C;/li&#x3E;  &#x3C;!-- 2.3.3 --&#x3E;
        &#x3C;/ol&#x3E;
      &#x3C;/li&#x3E;
      &#x3C;li&#x3E;item&#x3C;/li&#x3E;      &#x3C;!-- 2.4   --&#x3E;
    &#x3C;/ol&#x3E;
  &#x3C;/li&#x3E;
  &#x3C;li&#x3E;item&#x3C;/li&#x3E;          &#x3C;!-- 3     --&#x3E;
  &#x3C;li&#x3E;item&#x3C;/li&#x3E;          &#x3C;!-- 4     --&#x3E;
&#x3C;/ol&#x3E;
&#x3C;ol&#x3E;
  &#x3C;li&#x3E;item&#x3C;/li&#x3E;          &#x3C;!-- 1     --&#x3E;
  &#x3C;li&#x3E;item&#x3C;/li&#x3E;          &#x3C;!-- 2     --&#x3E;
&#x3C;/ol&#x3E;
```

###### animations & transitions

CSS transitions allow changing between two property values to be gradual.
CSS animations allow animating between n property values arbitrarily complexly and potentially infinitely.

CSS animations and transitions share the functionality of the properties *-delay, *-duration, *-timing-function.
All properties related to CSS animations start animation-; all properties related to CSS transitions start transition-;
Within the transition/animation shorthand, the first <time> is interpreted in as animation/transition-duration; the second as animation/transition-delay
The four transition properties are the three also availabe for animations (transition-delay, -duration, -timing-function) plus transition-property.
the transition property is a shorthand for the four transition properties.
The 8 animation properties are the three also availabe for transitions (animation-delay, -duration, -timing-function) plus -direction, -fill-mode, -iteration-count, -name, -play-state.
For the animation shorthand, it is common to place animation-name last, to avoid conflicts with other names.

animation/transition-* accept a comma-separated list of values, where each value applies to a specific animation-name or transition-property 
animation/transition-delay: CSL of <time>s to specify a delay before starting the animation. negative values will start that far into the animatin/transition
animation/transition-duration: CSL of <time>s to specify how long the animation will take

transition-property: CSL of <custom-ident>s (or all) to specify which properties to transitions

animation-direction: CSL of normal|reverse|alternate|alternate-reverse:
normal|f f f f f …
reverse|b b b b b …
alternate|f b f b f …
alternate-reverse|b f b f b …

animation-fill-mode controls if the animation will apply its beginning/end styles before/after/both/not at all
animation-fill-mode gets its styles from the first/last keyframe encountered, which depends on animation-direction
none|animation styles don't apply when not executing
forwards|animation styles apply after animation is finished
backwards|animation styles apply before animation is started (only applies if there is a animation-delay)
both|animation styles apply before and after the animation

animation-iteration-count: CSL of (<integer>|infinite)s to specify how many iterations the animation should play
animation-name: CSL of <custom-ident>s which represent the names of @keyframes describing the animations to apply
animation-play-state: CSL of (running|paused).

####### timimg functions

animation/transition-timing-function: CSL of <time>s to specify how long the animation will take

easing-function ::= linear|<cubic-bezier-easing-function>|<step-easing-function>
cubic-bezier-easing-function ::= <cubic-bezier-keyword>|<cubic-bezier-function>
cubic-bezier-keyword ::= ease|ease-in|ease-out|ease-in-out
cubic-bezier-function ::= cubic-bezier\(<number>, <number>, <number>, <number>\)
step-easing-function ::= <step-keyword>|<step-function>
step-keyword ::= step-start|step-end
step-function ::= steps\(<integer>, <step-position>\)
step-position ::= jump-start|jump-end|jump-none|jump-both|start|end

cubic-bezier(x_p1, y_p1, x_p2, y_p2)

The step keywords or function make the animation run in discrete steps, instead of continuously

https://drafts.csswg.org/css-easing-1/step-easing-keyword-examples.svg

step-start|only show the end state
step-end|only show the start state

https://drafts.csswg.org/css-easing-1/step-easing-func-examples.svg

jump-start, start|first 'jump' happens at 0; last jump happens some time before end|ergo: 0 state will not be visible, 1 state will
jump-end, end|first 'jump' happens at some time after 0; last jump happens at end|ergo: 0 state will be visible, 1 state will not
jump-none|first 'jump' happens at some time after 0; last jump happens some time before end|ergo: 0 & 1 state will both be visible
jump-both|first 'jump' happens at 0; last jump happens at 1|ergo: 0 & 1 state will both not be visible

######## cubic-bezier

Bezier curvers are frequently used for curves in computer graphics
A bezier curve is constructed from two or more points.
linear|2
quadratic|3
cubic|4
To construct a bezier function, one connect the points until one has only a curve between two points left.
To construct a linear bezier function, connect P0 and P1. You're done (it's a straight line).
To construct a quadratic bezier function, connect P0P1 and P1P2. Now, let a point travel on P0P1 and P1P2 from 0 to 1. connect P<sub>P0P1</sub> and P<sub>P1P2</sub> with a further line. Let a point travel on P<sub>P0P1</sub>P<sub>P1P2</sub> from 0 to 1. This point describes the quadratic bezier curve.


flex-container:<img src="sm_ZS4fP%20(1).png">
<img src="sm_ZS4fP%20(1)%20copy.png"><img src="sm_cubBezstep3.png">

To construct a cubic bezier function, connect P0P1, P1P2, P2P3. Now, let a point travel on P0P1, P1P2 and P2P3 from 0 to 1. connect P<sub>P0P1</sub> and P<sub>P1P2</sub> as well as P<sub>P1P2</sub> and P<sub>P2P3</sub> with a further line. Let a point travel on P<sub>P0P1</sub>P<sub>P1P2</sub> and on P<sub>P1P2</sub>P<sub>P2P3</sub> from 0 to 1. Connect P<sub>P<sub>P0P1</sub>P<sub>P1P2</sub></sub> and P<sub>P<sub>P1P2</sub>P<sub>P2P3</sub></sub> with a further line. Let a point travel on P<sub>P<sub>P0P1</sub>P<sub>P1P2</sub></sub> P<sub>P<sub>P1P2</sub>P<sub>P2P3</sub></sub>, this point describes the cubic bezier curve.

<img src="sm_cubBezstep3-1.png"><img src="sm__cat_acad_inf_code_css_bez60pc.png"><img src="sm__cat_acad_inf_code_css_bez80pc.png">

The CSS cubic-beziers map the dependent variable (y) to change in property, and the independent variable (x) to change in time.
For CSS, the x values of cubic-bezier must be between 0 and 1 (representing time), the y values are not limited in such a way
For the CSS cubic beziers only two points matter, the other two are fixed at (0|0) and (1|1)
For cubic-bezier(), the four parameters represent x1, y1; x2, y2

linear|<img src="sm_Screenshot%202020-06-02%20at%2001.59.05.png">
ease-in-out|cubic-bezier(0.42, 0, 0.58, 1.0)|<img src="sm_Screenshot%202020-06-02%20at%2002.03.45.png">
ease-in|cubic-bezier(0.42, 0, 1.0, 1.0)|<img src="sm_Screenshot%202020-06-02%20at%2002.02.33.png">
ease|cubic-bezier(0.25, 0.1, 0.25, 1.0)|<img src="sm_Screenshot%202020-06-02%20at%2002.02.03.png">
ease-out|cubic-bezier(0, 0, 0.58, 1.0)|<img src="sm_Screenshot%202020-06-02%20at%2002.03.02.png">

###### tables

The empty-cells CSS property sets whether borders and backgrounds appear around <table> cells that have no visible content.
The border-collapse CSS property sets whether cells inside a <table> have shared or separate borders.
The caption-side CSS property puts the content of a table's <caption> on the specified side. 
The table-layout CSS property sets the algorithm used to lay out <table> cells, rows, and columns.
auto
By default, most browsers use an automatic table layout algorithm. The widths of the table and its cells are adjusted to fit the content.

fixed
Table and column widths are set by the widths of table and col elements or by the width of the first row of cells. Cells in subsequent rows do not affect column widths.
border-spacing is the equivalent of gap, but for tables. 
border-spacing applies only when border-collapse is separate.
visibility: collapse: For <table> rows, columns, column groups, and row groups, the row(s) or column(s) are hidden and the space they would have occupied is removed (as if display: none were applied to the column/row of the table). However, the size of other rows and columns is still calculated as though the cells in the collapsed row(s) or column(s) are present. 

###### misc

The clip-path CSS property creates a clipping region that sets what part of an element should be shown.
clip-path-values ::= [<m-b-p-c-box>] [<basic-shape>]
THe shape-outside property sets a shape around which inline elements will flow.
shape-outside ::= <<m-b-p-c-box>||<basic-shape>||<image>
if you use an image for shape-outside, it will compute it based on that images alpha channel.
scroll-behavior only influences programmatic scrolling, i.e. not done by the user manually.
scroll-behavior: smooth makes scrolling a smooth animation instead of an instant transition.

appearance is a property to change the native styling of an element, or to remove it.
appearance is often used prefixed, especially to target one of the many non-standard values for this property

user-select controls whether/how the user can select text.
user-select-values ::= none|auto|text|all

resize controls whether/how an element is resizable, which generally only works on devices with pointing devices.
resize-values ::= none|both|horizontal|vertical

opacity: <number-or-percentage-0-1>

overflow is a shorthand for overflow-x and overflow-y
overflow-specifier-values ::= visible|hidden|clip|scroll|auto

overflow-anchor determines if our scroll position is anchored to the scroll offset from the top (`none`) or to the current position in the content (`auto`), which is relevant when we add more content on top. 

mix-blend-mode and background-blend-mode both take a <blend-mode>
⟮c4;Background-blend-mode⟯ regulates blending between (⟮c3;a⟯) ⟮c1;background-image⟯(⟮c3;s⟯) as well as the ⟮c2;background-color⟯.
⟮c2;mix-blend-mode⟯ regulates blending between ⟮c1;the⟯ ⟮c1;element's⟯ ⟮c3;content⟯, ⟮c1;the⟯ ⟮c1;element's⟯ ⟮c4;parents content⟯, and ⟮c1;the⟯ ⟮c1;element's⟯ ⟮c5;background⟯.
css <blend-modes> are the usual blend modes

##### Values

###### Functions

CSS functional notation is a type of CSS value that can represent more complex data types or invoke special data processing or calculations.
The syntax of CSS functional notation is: <name>\([<argument> {(,| ) <argument>}]\)

url()

The calc() CSS function creates a math context, i.e. allows calculation as one would expect. 
min(), max() and clamp() also creates math contexts.
calc-sum ::= <calc-product>{ (+|-) <calc-product>}
calc-product ::= <calc-value>{ * <calc-value>| / <number>}
calc-value ::= <mathable>|\(<calc-sum>\)
+ and - operators must be surrounded by whitespace within CSS calc
calc ::= calc(<calc-sum>)

The min() CSS function evaluates to the smallest (most negative) value of a specified list.
The max() CSS function evaluates to the largest (most positive) value of a specified list.
list-of-calc-sums ::= <calc-sum>{, <calc-sum>}
min ::= min(<list-of-calc-sums>)
max ::= max(<list-of-calc-sums>)

The clamp() CSS function clamps a value between an upper and lower bound. clamp() enables selecting a middle value within a range of values between a defined minimum and maximum. It takes three parameters: a minimum value, a preferred value, and a maximum allowed value. 
clamp ::= clamp(<list-of-calc-sums>, <list-of-calc-sums>, <list-of-calc-sums>)

The attr() function takes the name of an attribute (of the HTML element) and resolves to its value as a string.
Currently, attr() can only usefully be used as a value for content.

###### variables

custom properties are properties that start with -- and save their value, which then can be referred to with the var() function.
custom properties have a scope of the variable they are declared on and all children, since they particpate in the cascade.
The var() css function can be used instead of any part of a value of another property, and may even contain commas.
var ::= var\(<custom-property-name>, <fallback-value>\)

###### offsets

generally from the top left corner.
Even when not using the <offset> syntax, offsets in HTML/SVG are often from the top left corner.
for <offset>, the first value is x and the second is y
while offset is not a official datatype, I will define it as offset ::= <length> <length>

####### position

<position> can take two kinds of values: keywords and values.
Keywords for <position> are center, top, right, bottom and left.
A value for <postion> can be a <percentage> or <length>.
For <position>, specifying one value positions it exactly at that keyword (if keyword), or at value on the x axis and the y defaults to 50%.
For <position>, specifying two values means that the first will apply to x positioning, and the second will apply to y positioning, unless it is two keywords.
For <position>, a keyword followed by a value specifies the offset from the keyword.
For <position>, if specifying two keywords or two keywords with values each, the order doesn't matter.
The value described by <position> need not be inside the elements box.


flex-container:<img src="sm_position_value.png">

###### <image>

The <image> CSS data type represents a two-dimensional image.
While there are many kinds of things in the spec that an <image> could be, currently it can only be an <url> or a <gradient>

####### <gradient>

currently, there are three types of <gradient>s, <linear-gradient>, <radial-gradient>, and <conic-gradient>
<linear-gradient> and <radial-gradient>s also exist as repeating versions, which repeat as much as necessary to fil a given area: <repeating-linear-gradient>, <repeating-radial-gradient>.
Repeating gradients have the same syntax as the non-repeating variants, but if you size the final stop too large, there will be no palce for repeating.
All gradients are specified via css functions.

linear-gradient ::= linear-gradient\(<direction-specfier>, <color-stop-list>\)
direction-specifier ::= <angle>|<side-or-corner>
side-or-corner ::= to [<top-bottm>] [<left-right>]
color-stop-list ::= <color-stop>{, <color-stop>}
color-stop ::= [<color>] [<length-percentage>] [<length-percentage>]

radial-gradient ::= radial-gradient\(<shape-specifier>, <color-stop-list>\)
shape-specifier ::= <ending-shape> <size> at <position>
ending-shape ::= circle|ellipse



conic-gradient ::= conic-gradient\(<origin-specifier>, <color-stop-list-angular>\)
origin-specifier ::= [from <angle>] [at <position>]
color-stop-list ::= <color-stop-angle>{, <color-stop-angle>}
color-stop ::= [<color>] [<angle>] [<angle>]

When specifying color stops, if you don't specify a color it will use the middle between the preceeding and succeeding colors
When specifying color stops, if you don't specify a <length-percentage>/<angle> it will use the middle between the preceeding and succeeding stops.
Specifying two <length-percentage>/<angle> on a single color stop will make the color stay the same inbetween those two stops.

###### <size>

size ::= (<length-percentage>[ <length-percentage>])|size-keyword
size-keyword ::= closest-side|closest-corner|farthest-side|farthest-corner
closest-side	The gradient's ending shape meets the side of the box closest to its center (for circles) or meets both the vertical and horizontal sides closest to the center (for ellipses).
closest-corner	The gradient's ending shape is sized so that it exactly meets the closest corner of the box from its center.
farthest-side	Similar to closest-side, except the ending shape is sized to meet the side of the box farthest from its center (or vertical and horizontal sides).
farthest-corner	The default value, the gradient's ending shape is sized so that it exactly meets the farthest corner of the box from its center.

For <size>, specifying two <length-percentages> applies them to horizontal/vertical direction respectively. specifying only one makes it applly two both horizontal and vertical directions. Places that expect a <size> for a circle may only recieve one <legnth-percentages>

###### <basic-shape>

basic-shape ::= <inset>|<circle>|<ellipse>|<polygon>|<path>
inset ::= inset\{<length-percentage-edges>[ round <border-radius>]\}
circle ::= circle\(<size>[at <position>]\)
ellipse ::= ellipse\(<size> [at <position>\)

###### color

All css color keywords are case-insensitive.
any property ending in -color: takes a <color> value
color  ::= transparent|currentColor|<color-keyword>|<hex-color>|<color-function>
color keywords are things such as red, darkgrey, rebeccapurple 💜, which correspond to specific RGB values.
the transparent keyword is a shortcut for rgba(0,0,0,0)
The currentColor keyword represents the value of an element's color property, or the inherited value of the color property if specified as the color property. 
color functions are a bunch of different CSS functions that take the components of a certain color model as arguments.
most css color functions have a variant that ends a and accepts a fourth alpha value.
CSS color functions: rgb/rgba, hsl/hsla
for rgb()/rgba(), the color components can be <percentage>s from 0% to 100%, or <numbers> from 0 to 255
for hsl()/hsla(), the h component is a <angle>, or a <number> between 0 and 360
for hsl()/hsla(), s and l are <number-or-percentages> (how they work is specified in the general color flashcard)
in css, the alpha channel takes a <number-or-percentage-0-1>

###### simple types

the <url> datatype is a css function
url ::= url(<string>) # where string must be a valid url or path or the ID of a SVG shape

dimension ::= <length>|<time>|<frequency>|<resolution>|<angle>

CSS dimensions are always a number followed by a unit with no space inbetween

mathable (not an official name) ::= <number>|<dimension>|<percentage> 
resolution ::= <number><resolution-unit>
resolution-unit ::= dpi|dpcm|dppx|x
x is an alias for dppx
dppx = dots per px
In CSS, since 1 in is fixed as 96 px, 1dppx is 96 dpi.
frequency ::= <number><frequency-unit>
frequency-unit ::= Hz|kHz
angle ::= <number><angle-unit>
angle-unit ::= deg|grad|rad|turn
time ::= <number><time-unit>
time-unit :: s|ms

turn  Represents an angle in a number of turns. One full circle is 1turn

// <integer>, <number>, <percentage> defined elsewhere

m-b-p-c-box ::= margin-box|border-box|padding-box|content-box
b-p-c-box-text ::= border-box|padding-box|content-box|text
b-p-c-box ::= border-box|padding-box|content-box
b-c-box ::= border-box|content-box

###### length

length ::= <number><length-unit>
length-percentage ::= <length>|<percentage>
resolution-length-percentage ::= <resolution>|<length-percentage>

lpminmaxauto ::= <length-percentage>|min-content|max-content|auto # this is a term I made up
terms like auto, min-content and max-content depend on the current formatting context/layout mode
an element with width/height = auto has a width/height of its automatic size
an element with width/height = min-content has a width/height of its min-content size
an element with width/height = max-content has a width/height of its max-content size
An elements lengths min-content and max-content size are equivalent to its automatic size unless otherwise specified.
When not equal to auto, in general the min-content size is the smallest size that doesn't lead to overflow which could be avoided by choosing a larger size
When not equal to auto, in general the max-content size is the size a box could assume when given infinte space, while avoiding overflow.

<flex> consists of a <number> followed by the unit fr.
the fr unit represents a fraction of the leftover space in the grid container. 
flex-l-p-min-max-auto ::= <flex>|<l-p-min-max-auto>

length-unit ::= <relative-length-unit>|<absolute-length-unit>
relative-length-unit ::= <font-relative-length-unit>|<viewport-relative-length-unit>
font-relative-length-units
`rem`|font-size of the root element
`ex`|the height of a lowercase x of the current font (rarely used)
`em`|the font-size of the element
`ch`|width of the "0" (zero)

viewport-relative-length-units
`vw`|1% of the width of the viewport*
`vmin`|1% of viewport's* smaller dimension
`vmax`|1% of viewport's* larger dimension
`vh`|1% of the height of the viewport*

absolute units in CSS may or may not refer to their real-world equivalent.
On print media and similar situations, css absolute units refer to their real-world equivalent.
For low dpi devices, absolute units are instead defined in reference to the reference pixel: 1 in = 96 px, thus `1in` may not correspond to 1 RL inch. 
For high dpi devices, px are instead defined in reference to real-world units, so that 1 in is one 1 RL in, and 1px is 1/96in, no matter how many screen pixels that would actually correspond to on the device.
absolute-length-unit ::= <metric-length-unit>|<imperial-length-unit>|px
metric-length-unit ::= cm|mm|Q
imperial-length-unit ::= in|pc|pt

###### filters

backdrop-filter applies a filter to the area behind an element.
for backdrop-filter to apply, the element or its background must be at least partially transparent.
backdrop-filter and filter take a <filter-function-list>
filter-function-list ::= <filter-function>|<svg-filter>{ <filter-function>|<url>} # the URL is for a svg filter
a <filter-function> is a <function> that applies a filter (i.e. changes the appearance of an image)
filter-functions: 
blur(): takes a blur-radius
brightness(): <number-or-percentage-to-infinity>
contrast(): <number-or-percentage-to-infinity>
drop-shadow(): arguments are `offset-x offset-y [blur-radius] [color]`
grayscale(): <number-or-percentage-0-1>
hue-rotate(): takes an <angle> and rotates the hue by that angle
invert(): <number-or-percentage-0-1>
opacity(): <number-or-percentage-0-1>
saturate(): <number-or-percentage-to-infinity>
sepia(): <number-or-percentage-0-1>

anywhere that takes a blur-radius generally takes a <length> which defines the standard deviation of the gaussian function

There are a few places which accept a <number> or <percentage>. This is not an official CSS data type, but I will call this <number-or-percentage>.
There are a few different sets of semantics for <number-or-percentage>
<number-or-percentage-to-infinity>: 0/0% is the opposite effect (complete lack of x), 1/100% is original, 2/200% is 2x the effect
<number-or-percentage-0-1>: 0/0% is complete lack, 1/100% is complete application

###### shadows

The box-shadow property creates a rectangular shadow behind an element's entire box, while the drop-shadow() filter function creates a shadow that conforms to the shape (alpha channel) of the image itself.

the first two <lengths> of text-shadow, box-shadow and drop-shadow() take a <offset> (two <length>s), the third <length> specifies the blur-radius
for box-shadow, the fourth <length> specifies the spread-radius, for text-shadow and drop-shadow(), there is no way to specify a spread radius.
for text-shadow, box-shadow and drop-shadow(), the non-length value specifies the color.
box-shadow additionally may take the keyword inset, which specifies that the shadow should render inside the box instead of outside it.

text-shadow and box-shadow also accept a CSL of shadow specifiers for specifying multiple shadows.

### at-rules

#### nested at-rules

##### @font-face

@font-face defines a font face for use within the document.
@font-face takes at least a font-family: foo, which is the name we will use to refer to it, and a src, which provides the file for the font itself.
@font-faces src syntax: (<font-face-name>|<url> [format(<string>)]) {<url> [format(<string>)]}
font-face-name: local(<string>) # where the string is the name of a locally-installed font.
calls to local() for @font-faces src should go first since if it finds the font locally, it does not have to load it fron the URL.
for @font-faces src, the first call to local() or url() that is usable will be used.
For the @font-face src call, the format() function takes a string specifying the format of the font, where the font will only be loaded if the browser supports that format.
for @font-face, since you're specifying fonts and not font-families, for different font-weights and font-styles, you must specify multiple @font-face declarations, and within those, specify which font-weight or font-style this is specifying. Only fonts actually used will be loaded. This does not apply to variable fonts.

unicode-range: some-range will only load the font if the document uses the font for at least one character within the range

##### @keyframes

Keyframes at-rule syntax: @keyframes <keyframes-name> \{ <keyframe-block-list> \}
<keyframes-name> ::= <custom-ident>|<string>
<keyframe-block-list> ::= {<keyframe-block>}
<keyframe-block> ::= <keyframe-selector-list><declaration-block>
<keyframes-selector-list>  ::= <keyframe-selector>{,<keyframe-selector>}
<keyframe-selector> ::= from|to|<percentage>

from is an alias of 0% and to is an alias of 100%
Properties that aren't specified in every keyframe are interpolated if possible — properties that can't be interpolated are dropped from the animation.

if you mark something with !important in a keyframe,&nbsp;⟮c1;That value will be ignored⟯ (since !important can't be used in keyframes)
if you don't provide a from/0% andor a to/100% it will ⟮c1;Animate to/from the elements existing styles⟯
If you specify multiple @keyframes with the same name, ⟮c1;The last one encountered will be used⟯

##### @page

@page syntax: @page <page-selector-list>\{<page-body>\}
page-selector-list ::= <page-pseudo-class>{, <page-pseudo-class>} #maybe it's not a comma? I couldn't find any documentation this
page-pseudo-class ::= :first|:blank|:left|:right
page-body :: <page-declaration>;|<margin-at-rule>
currently supported properties for the page declaration are margins, orphans, widows and break
margin-at-rule = @<margin-at-rule-name><declaration-block>

flex-container:<img src="page_margin_at_rules.png">

##### @counter-style

@counter-style produces values of type <@counter-style>
@namespace is an at-rule that defines XML namespaces to be used in a CSS style sheet.

#### non-nested at-rules

@charset "<charset>"; declares the charset, though this is often unnecessary if UTF-8 is desired, as the browser will assume UTF-8 if no charset decaration is present.
@charset must be the first statement in the document if present.

### elements

#### replaced elements

In CSS, a replaced element is an element whose representation is outside the scope of CSS; they're external objects whose representation is independent of the CSS formatting model.
Typical replaced elements are:
<iframe>
<video>
<embed>
<img>

Some elements are treated as replaced elements only in specific cases:

<option>
<audio>
<canvas>
<object>
<applet>

Objects inserted using the content property are anonymous replaced elements.

The only way CSS can style replaced elements is by controlling the positioning of the element's content within its box.
for object-* to be relevant, the box of the replaced element must be of a different size than the replaced element

The object-whatever properties target replaced elements.

object-position takes a <position> value, and controls where the replaced element goes in its box

object-fit|aspect-ratio|clipping/letterboxing/framing/none
cover|preserve|letterboxing
contain|preserve|clipping
fill|stretch|none
none|preserve|either clipping or framing (not resized at all)
scale-down|perserve|letterbox or framing (contain or none, whichever is smaller)

##### images

image-rendering controls how an image upscales. 
image-rendering: pixelated - image will seem to be composed of large pixels
image-rendering: crisp-edges - preserve edges
image-rendering: auto - browser-defined algorithm

##### frames

A ⟮c1;frame⟯ is ⟮c2;a part of a webpage⟯ which ⟮c3;displays a different webpage (or a part thereof⟯) within. 
A ⟮c4;frame⟯ has ⟮c5;state⟯ ⟮c6;independent of its parent webpage⟯. 
The ⟮c7;two types of frames⟯ that HTML has/had are ⟮c8;&lt;frame&gt;⟯ and ⟮c9;&lt;iframe&gt;⟯ 
Both ⟮c10;&lt;frame&gt;⟯ and ⟮c10;&lt;iframe&gt;⟯ need(ed) a ⟮c11;src⟯ to be useful. 
⟮c12;&lt;frame&gt;s⟯ would have been ⟮c13;placed within⟯ a ⟮c14;&lt;frameset&gt;⟯. 
⟮c15;&lt;frameset&gt;⟯ would have ⟮c16;replaced⟯ ⟮c17;body⟯. 
A site using ⟮c18;&lt;frameset&gt;⟯ was basically ⟮c19;made up of⟯ ⟮c20;many different HTML documents⟯. 
A site using ⟮c21;&lt;frameset&gt;⟯  would have had the advantage tha⟮c22;t only a part of the site (e.g. the main content, but not headers and footers⟯) would ⟮c23;have to be fetched when navigating⟯. 
The ⟮c24;&lt;noframes&gt;⟯ was provided for browsers that ⟮c25;did not support frames⟯. 
As of ⟮c28;HTML5⟯, ⟮c26;&lt;frame&gt; and &lt;frameset&gt;⟯ are ⟮c27;deprecated⟯, but ⟮c26;iframe⟯ is not. 
⟮c29;&lt;frame&gt;s⟯ were ⟮c32;deprecated⟯ because&nbsp; ⟮c30;their intraction with the same-origin policy could be a nightmare⟯, because ⟮c31;copyright infringemenet was easy⟯, and because ⟮c33;of accesibility/usability problems⟯. 
⟮c34;iframe⟯ is short for ⟮c35;inline frame⟯ 


### stacking changes

Stacking contexts relate to each other in a tree.
Only certain elements or elements with certain properties. establish a stacking context.
The root element creates the root stacking context
The hierarchy of stacking context is a subset of the hierarchy of HTML elements because only certain elements create stacking contexts.
Within a stacking context, 
stacking order: z-index beats 'is a positioned element' beats order of apperance in html
stacking order of child stacking context is namespaced by the stacking order of parent stacking contexts, there is nothing a thing in a child stacking context can do to beat an aunt/uncle stacking order.
z-index may only be applied to positioned elements.
Isolation: isolate creates a new stacking context and prevents that element of being blended with mix-blend-mode.

### flow

CSS takes as its input a tree of elements and text nodes, most commonly a pared-down DOM.
CSS converts the DOM to a flattened element tree, which is the same but has shadow trees merged back in.
CSS takes the flattened element tree and converts it to an intermediary structure, the box tree.
To create the box tree, CSS first gets the computed value for each CSS property for each element. Then CSS generates zero or more boxes for each element as specified by that elements display property.
Typically, CSS generates one box per element, the principal box.
Typically, CSS generates one text run per contiguous sequence of sibling text nodes in the DOM tree.
CSS may generate more than one box for an element, or none at all.
For example, display: list-item generates a principal block box and a child marker box.
A block box is a block-level box that is also a block container.
A block may be short for block-level box, block container box, or both combined (ergo a block box in that case)
A box is assigned the same styles as its generating element, unless otherwise indicated.
In constructing the box tree, boxes generated by an element are descendants of the principal box of any ancestor elements.
In the general case, the direct parent box of an element’s principal box is the principal box of its parent element; however, there are some exceptions.
An anonymous box is one not associated with any element.
Unlike element-generated boxes, whose styles inherit strictly through the element tree, anonymous boxes (which only exist in the box tree) inherit through their box tree parentage.
CSS outputs its output onto a canvas, which may be your screen, a piece of paper, an audio stream or something else.
Content that extends outside of a boxes edges or would do so is known as overflow

#### display

The display property controls two distinct-things: the outer and the inner display type.
The outer display type of an element controls how it will praticipate in normal flow.
The inner display type of an element controls the layout of the children.
There is a two-value syntax for display describing the outer and inner display type separately, but it isn't well supported yet.
The two-value syntax for display is <display-outside> <display-inside>
In absence of the two-value syntax for display, most keywords control both the outer and the inner display type.
The possible values for <display-outside> are the ways an element can participate in normal flow.
There are two ways an element can participate in normal flow, block and inline.
Some values for display do not set the outer or inner display type, instead they set a role within a complex layout model.
The values for display that don't set the outer or inner display type, but instead their role within a complex layout have the type <display-internal>.
The complex layout models that have display properties for their parts are table and ruby.
the values with type <display-internal> are ruby-* and table-*

legacy-1-value property|equivalent
inline-block|inline flow-root
inline-table|inline table
inline-flex|inline flex
inline-grid|inline grid

Everything in CSS is within a certain formatting context.
The best way of thinking of formatting contexts is as mini-layouts
Most <display-inside> values establish a new formatting context, besides flow, which may not.
The purpose of <display-inside> is to set new formatting contexts, unless we're using flow for compat.
<display-inside>|establishes formatting context
flow-root|block formatting context
table|table formatting context
ruby|ruby formatting context
grid|grid formatting context
flex|flex formatting context

I think layout mode is a rough synonym for formatting context, but can't find a source either way

there is such a thing as a multi-column formatting context, but it is not established by a <display-inside> value, 
instead any element with with column-width or colum-count not as auto establishes a multi-column container.
Any fragmentainer created by the multicolumn fragmentation context is called a column box

Elements establishing an x formatting context (except perhaps block formatting context) are called an x container. 
Ergo the thing that has display:flex/inline-flex/grid/inline-grid is called flex/grid container.
A block container either contains only inline-level or only block-level boxes.
A block container containing only inline-level boxes creates an inline formatting context
A block container containing only inline elements and thus creating an inline formatting context also generates a root inline box to wrap all its inline content.
A block container must establish a block formatting context if its parent formatting context is not a block formatting context.
For grid and flex, children of the grid/flex container are called grid/flex items.

If only the <display-inside> value is set, the <display-outside> value will default to block.

the value flow for <display-inside> makes the element participate in normal/flow layout as normal.
if only <display-outside> is specified, <display-inside> will be set to flow for compatibility;

display: list-item may be either a <display-outside> or a <display-inside> value.
display: list-item may be combined with block/inline for <display-outside> and flow/flow-root for <display-inside>

Elements within a block-formatting context are layed out according to normal flow.
Normal flow may also be called flow layout.
a block-formatting context, by establishing a new flow layout, has interesting effects.
- they contain floats 
the <html> element establishes a new block-formatting context.
Block-formatting contexts are created explicitly with the <display-inside> value of flow-root.
Block-formatting contexts are also created by a bunch of other properties, including but possibly not limited to:
floating elements
flex and grid items.
elements with...
column-span: all
contain: layout|content|strict
overflow: anything but vissible
display: table-cell
absolutely positioned elements

a block-level element is an element with <display-outside> block
a inline-level element is an element with <display-outside> inline
Normal flow has two basic parameters: the <dfn>inline (base) direction</dfn> and the <dfn>block (flow) direction</dfn>.
The inline base direction defines how content is ordered inline.
The block flow direction defines how blocks are added.
Generally, the inline base direction and block flow direction are perpendicular to one another.
writing-mode determines the block flow direction
any value for writing mode has the syntax (vertical|horizontal)-(lr|rl|tb).
The default value for writing-mode is horizontal-tb.
The direction property as well as HTM:s dir attribute controls the inline base direction (either rtl or ltr)
By default, block-level elements are 100% width of the inline base direction axis.
block-level elements can have their height and width set manually, while inline-level elements
both inline-level andblock-level elements can have all their margins, borders and paddings set. however inline-level elements will only move other elements on the the inline base direction axis (i.e. not vertically for horizontal-tb).

flex-container:<img src="sm_inline_margins.png">
Since inline-level elements don't have block flow direction margins, they can't suffer from margine collapsing.
inline-level elements and text runs are handled via an inline formatting context using line boxes.
Whenever the browser encounters inline elements wiwthin a block container, it creates a new root inline box which establishes an inline formatting context.
CSS fragments inline-level elements into a stack of fragmentainers called line boxes, which are inserted into the root inline box.
the browser will fill a line box in the inline base direction with inline-level elements or text until it is full.
Once a line box is full, the browser will create a second line box, etc.
A line box is as tall as its tallest content.
If the browser encounters a block-level element while creating line boxes, it stops the line box, closes the root inline box and thus the inline formatting context, puts the block-level element on a line of itself, and then creates a new root inline box with new line boxes etc. if there's more inline-level elements/text to be handled.
line-height sets the minimum height of a line box.
line-height may be specified as a <length-percentage> or as a <number>, which is a multiple of the current font-size
If we set the line height of multiple things in the same line box to different values, they may overflow into each others boxes.

flex-container:<img src="sm_line_height_overflow.png">
The dominant baseline is the one that is used to align inline text, and may be automatically determined or manually specified with the as-yet unimplemented dominant-baseline

if writing-mode is vertical-??, the text-orientation property controls the rotation of the glyphs.
mixed|rotate vertical scripts (e.g. japanese), but not non-vertical scripts (e.g. latin letters)
upright|rotate all scripts
sideways|don't rotate any scripts (not well supported atm)

Margin collapsing is the phenomenon where vertical margins of adjacent block-level elements merge to the longest common distance.

Text overflowing a block container in inline base direction can be made to show an ellipsis by using text-overflow: ellipsis.

display may also take a value of type <display-box>, which controls whether an element generates boxes at all.
display-box ::= contents|none
contents|The element itself does not generate any boxes, but its children and pseudo-elements still generate boxes and text runs as normal. 
none|this element and any of its descendants do not generate boxes or text runs

To hide a box without influencing which boxes it generates (and thus also still taking up the space), use visibility: hidden

##### display-internal

behave as ...|<display-internal> value
tbody|table-row-group
thead|table-header-group
tfoot|table-footer-group
tr|table-row
td|table-cell
colgroup|table-column-group
col|table-column
caption|table-caption

#### fragmented flow

CSS paged media and containers consist of a fragmentation flow.
Inline flow is actually also fragemnted flow.
A fragmented flow is made up of n fragmentainers.
When breakable content would overflow a fragmentainer in the block dimension, it breaks into the next container in its fragmentation context instead.
A fragmentainer establishes its own block-formatting context.
A fragmentation context is a series of fragmentainers.
A fragmentainer contains a portion of or all of a fragmented flow.
In normal flow, a box may only consist of one box fragment.
In fragmented flow, a box may consist of one or more box fragments.
A (box) fragment is the part of a box that is in a given fragmentainer.
Each box fragment has its own share of the box's padding, border, and margin. 

##### Orphans and Widows

orphans and widows are two twin properties in CSS that apply only to pages or columns.
Both orphans and widows take an <integer>
orphans says how many lines of a block container must appear at the bottom of a page/column if it is broken over two pages/columns
widows says how many lines of a block container must appear at the top of a page/column if it is broken over two pages/columns

##### Break

The break-before/break-after/break-inside properties apply to pages and collumns.
The break-before/after/inside says how to break before/after/within a block-level element
break-before/after/inside take a keyword called avoid which prevents breaking within (if possible).
The avoid keyword for break-* is available as avoid-page and avoid-column to only apply to these, repsectively.
break-before/after but not inside  take a keyword called page or column which forces breaking before/after/within the respective thing (if possible).
break-before/after but not inside take the keywords left/right to force breaking before/after if the thing is a page that is a left/right page
break-before/after/inside default to auto, which means a break is allowed but not mandatory.
A break created by break-before and break-after is called a forced break.

### media queries

Media queries and feature queries have a fair amount of similarities.
Media queries are boolean assertions if the current user's environment/device/UA is a certain way.
Feature queries are boolean assertions if a browser supports a certain set of CSS properties with certain values.
A media query is either true or false for the current user's combination of environment/device/UA.
A feature query is either true or false for the current user's CSS feature set.
Media queries are built from media types, media features, and logical operators.
Media types describe the broad category of device or UA.
Media features describe a specific feature of the environment/device/UA, which can be true or false.
Media queries are most commonly used by @media at-rules, and less frequently by @import at-rules (specified after the meat and potatoes), the media attribute in HTML, and in JS by Window.matchMedia() and MediaQueryList.addListener().
A feature query consists of "feature features" (my coinage) and logical operators.

#### media types

Media types

all|all devices
print|inteded for printing
screen|intended for screens
speech|intended for speech synthesizers/screen readers

Media types are specified as boolean attributes, i.e. the presence of the keyword is enough

#### media features

Media features
orientation describes relationship of width and height of the viewport (not the device/screen!)
orientation is portrait if height &gt; width and landscape if width &gt; height
color tests for color depth per channel
resolution tests for pixel density
height tests for height of the viewport
width tests for width of the viewport
aspect-ratio tests for a certain aspect ratio
hover testss whether the user's primary input mechanism can hover
prefers-reduced-motion is used to detect if the user has requested that the system minimize the amount of non-essential motion it uses (this is often an OS-level toggle)

Media features as well as feature features are specified in a (key: value) syntax (parentheses not optional)
for feature features for (key: value), key is a property and value is a possible value.
Media features that are range features can take a min- and a max- version of that feature to specify a range of acceptable values
Level 4 media queries support a more intuitive syntax for range features using &lt;, &gt;, = etc.
Media featurs that are range features: color, resolution, height, width, aspect-ratio

#### logical ops

The logical operators that are valid within media queries are and and not (which work as expected), and the comma, which acts as an or, but cannot be nested (i.e. can only combine media queries at the top level). 
as of Level 3 media queries (changes in level 4 media queries), the not keyword can't be used to negate an individual media feature expression, only an entire media query.
feature queries supports similar logical operators to media queries, but instead of the comma, it has a normal or operator, and not can also invert parts of feature queries.
The operator only is mainly useful for preventing browsers from matching if part of the media query applies, and there is another part that they don't understand (e.g. older browsers) and thus ignore.

#### atrules

An @media at-rule is a conditional which takes a media query and executes the CSS contained within if the media query is true.
Multiple @media at-rules may apply at the same time
Syntax @media &lt;media-query&gt; &lt;block&gt;

@media screen and (min-width: 900px) {
  article {
    padding: 1rem 3rem;
  }
}

A @supports at-rule is a conditional which takes a feature query

#### in HTML

The media HTML attribute may be applied to <link>, <source>, or <style>.
The media HTML attribute indicates when to load the specific resource.

#### in JS

##### media queries

window.matchMedia() takes a media query and returns a MediaQueryList object, whose matches property indicates exactly that.
To react to changes in media features/types, you can register the change event on the MediaQueryList boject.

##### CSSStyleDeclaration

The CSSStyleDeclaration interface is an object that represents a CSS declaration block.

### related technologies

#### features

##### web typography

In most modern ＿styling frameworks＿ and generally in web design native fonts are now used.
The rise in using native fonts is in part attributable to the rise of more high-quality system fonts.

##### system UI themes

the ⟮c1;System UI Theme Specification⟯ is a ⟮c2;reasonably widely⟯ adopted spec for ⟮c3;a style object⟯ that stores things for ⟮c4;design systems⟯, especially ⟮c5;scales⟯
at the heart of the ⟮c1;System UI Theme Specification⟯ are ⟮c2;scales⟯ - 
scales are ⟮c3;arrays⟯ or ⟮c3;objects⟯ of ⟮c4;predefined sets of values⟯, for things such as ⟮c5;font sizes⟯, ⟮c5;colors⟯, etc.
According to the ⟮c1;System UI Theme Specification⟯, the ⟮c4;CSS properties⟯ that accept ⟮c2;only a small, finite number⟯ of valid CSS values ⟮c3;should not be included as a scale object⟯.
According to the ⟮c1;System UI Theme Specification⟯, a ⟮c2;key⟯ defining a ⟮c2;scale⟯ should be called the ⟮c3;same thing as the css property⟯, except ⟮c4;plural⟯ (except for the weirdly-named `⟮c4;space⟯`) and ⟮c5;camelCase⟯, unless there are ⟮c6;multiple css properties it might be used for⟯
```
// example fontSizes scale as an array
fontSizes: [
  12, 14, 16, 20, 24, 32 
]
// example colors object
colors: {
  blue: '#07c',
  green: '#0fa',
}
// example nested colors object
colors: {
  blue: '#07c',
  blues: [
    '#004170',
    '#006fbe',
    '#2d8fd5',
    '#5aa7de',
  ]
}
```
scales|CSS Properties
`space`| `margin`, `margin-top`, `margin-right`, `margin-bottom`, `margin-left`, `padding`, `padding-top`, `padding-right`, `padding-bottom`, `padding-left`, `grid-gap`, `grid-column-gap`, `grid-row-gap`
`fontSizes`|`font-size`
`colors`| `color`, `background-color`, `border-color`
`fonts`|`font-family`
`fontWeights`|`font-weight`
`lineHeights`|`line-height`
`letterSpacings`|`letter-spacing`
`sizes`| `width`, `height`, `min-width`, `max-width`, `min-height`, `max-height`
`borders`| `border`, `border-top`, `border-right`, `border-bottom`, `border-left`
`borderWidths`|`border-width`
`borderStyles`|`border-style`
`radii`|`border-radius`
`shadows`|`box-shadow`, `text-shadow`
`zIndices`|`z-index`
`transitions`|`transition`


##### nested rules

In SCSS/Sass and other CSS preprocessors, to achieve ⟮c2;nested selectors⟯, you can ⟮c3;nest entire rules⟯. 
```
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }

  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }
}
```

In ⟮c4;nested rules⟯'s selectors, ⟮c5;&amp;⟯ refers to ⟮c6;the parent selector⟯. 
In nested rules's selectors, ⟮c7;&amp;⟯ is useful if ⟮c8;you want to combine selectors in complex ways⟯ 
In ⟮c9;nested rules⟯'s selectors, ⟮c10;@at-root⟯ ⟮c11;goes back up to the nesting tree.⟯ 

```
.parent {
  .child {
    ⟮c1;&amp; div &amp; &amp; &gt; a⟯ {}
  }
}
```
compiles to `⟮c12;.parent .child div .parent .child .parent .child &gt; a {⟯}`

```
.grand-parent {
  .parent {
    @at-root .child {}
  }
}
```
compiles to `⟮c13;.child {}⟯`

```
.button {
  &amp;:visited { }
  &amp;:hover { }
  &amp;:active { }
}
``` compiles to `⟮c14;.button:visited { } .button:hover { } .button:active { } ⟯`

```
.btn {
  &amp;-primary {}
  &amp;-secondary {}
}
``` compiles to `⟮c15;.btn-primary {} .btn-secondary {} ⟯`

##### colors

###### theme-color

some styling frameworks (e.g. bootstrap) use a system of semantic names for colors such as primary, secondary, success, danger, warning, info, light, dark...
In bootstrap the system of semantic colors is called theme-colors.

###### color schemes

Material design pioneered describing lightness of colors on the same 100 (or sometimes 50) to 900 scale as font weights.
Describing colors on a 100 to 900 scale has been adopted by other things such as bootstrap, chakra.
color-on-weight-scale ::= <hue>-<weight>

##### misc scales

Many CSS frameworks, e.g. bootstrap have adopted a scale from 1-5 where 3 is a middle value for things that require an arbitrary scale.
Things that fall on the 1-5 scale in bootstrap are `order`, spacers.

##### components

Pretty much any styling framework features pre-existing components and/or allows the creation of custom components.

###### variants

Many style frameworks have lg and sm version of some components.

##### layout

###### bootstrap grid system

Bootstrap pioneered the bootstrap grid system.
The bootstrap grid system consists of containers, rows, and columns.
The boostrap grid system has been adopted by other systems such as ionic.
A container (or something else) contains n rows.
A row contains 12 template columns.
Actual columns can be 12 or more template columns wide.
Having a row with elements adding up to more than 12 template columns will force wrapping.
Offsets are specified in template columns and are used to take up column space without filling it with content.
Bootstrap grid systems feature gutters both between rows and columns, which you can customize.
The bootstrap grid system is built with flexbox.
Since the bootstrap grid system is built with flexbox, you can change the behavior of the grid system by using flexbox-related utilites.

containers are mainly for adding padding.
Containers are, depending on the exact class, either 100% of the page, or 100% with some spacing left and right

####### implementation

in bootstrap, columns are specified .col-<meas-col>
in bootstrap, a row consisting of columns with n measurement columns width is specified as .row-cols-<meas-col>

##### breakpoint

Pretty much all styling frameworks have chosent the concept of breakpoints to abstract over width-based media queries.
A breakpoint corresponds to a range of widths
Common breakpoint names:
Extra small|no name (default)|Tailwind, Chakra, Bootstrap
Small|sm|Tailwind, Chakra, Bootstrap
Medium|md|Tailwind, Chakra, Bootstrap
Large|lg|Tailwind, Chakra, Bootstrap
Extra large|xl|Tailwind, Chakra, Bootstrap
Extra extra large|2xl|Tailwind, Chakra
Extra extra large|xxl|Bootstrap.
For pretty much all frameworks, breakpoints select this size and up.
The reason breakpoints generally select this size and up in most frameworks is that they are mobile first.
Since breakpoints generally select this size and up, you need to overwrite breakpoints for larger sizes if you want it to only apply to one size.
Since breakpoints select this size and up, one typically writes the style for the smallest size first and then layers  styles for larger form factors on top.

##### z-indices

Z-index in bootstrap and perhaps in other frameworks exists on two scales: ⟮c+;within elements, for states (for :hover, :active, :focus) ⟯, to prevent e.g. overlapping borders and ⟮c+;for overlay components (modals, tooltips, etc.)⟯

situation|values
within elements|0-3
overlay components|1000-1080

##### abbreviation

styling frameworks tend to abbreviate things, especially CSS properties/values where possible.
However, not every CSS property/value is abbrevaited in each styling framework.
In styling frameworks property names often become a list of the first chars separated by hyphems when shortened.
E.g. something like `margin-end` would become `me`.
In react/style props based frameworks, CSS properties become camelCased unless abbreviated to chars only.
e.g. margin-top -> marginTop / mt


###### things that are pretty much always abbreviated in every system

margin|m
padding|p
width|w
height|h
background|bg
gutters|g
top/bottom/left/right/start/end|t/b/l/r/s/e
top & bottom / left & right|y/x
no character|all four sides

##### active/disabled

Many styling frameworks, e.g. bootstrap, may take an active/disabled class (or whatever) to indicate that something is currently active/cannot be interfaced with.

##### theming

#### CSS frameworking

Most CSS frameworks apply most things via CSS classes.
The most basic style of class most CSS frameworks use is .<key>-<value>.

##### conditional classes

There are two philosophies as regards adding conditions to CSS framework classes, colon-based and infixing.
colon-based|<condition>:<key>[-<value>]|Tailwind
infixing|<key>-<condition>-<value>|Bootstrap

`&lt;img class="w-16 md:w-32 lg:w-48" src="..."&gt;`
Breakpoints might be the most common condition for CSS conditional classes.

##### types of classes


###### utility classes

Utility classes are common feature of css frameworks.
Utility classes change one specific aspect of a thing (background, font size, padding, etc.)
Utility classes either apply CSS classes more or less directly (e.g. `bg-white`), or offer light syntactic sugar for CSS to apply somewhat more semantic classes (e.g. `text-xl`, `font-medium`)
Systems that feature utility classes generally strongly recommend using them instead of custom css.

###### helpers

Helper classes in CSS frameworks are classes that achieve a single effect, albeit one that doesn't correspond neatly to a CSS property/aspect of an element (ergo not components).s

####### spacer

Spacers are a special type of utility in some styling frameworks.
Spacers apply margin or padding to one or more sides.
In bootstrap, spacers controlled by $spacer.

###### components

In CSS frameworks, typically a class .<component-name> defines a component.
In CSS frameworks, typically parts of components are indicated by .<component-name>-<part>

##### implementation

Many CSS frameworks, amongst others bootstrap, are implemented by generating them from Sass (or other CSS preprocessors).
Since they are generated from Sass, to change functionality of Bootstrap or other CSS frameworks, change the Sass code.
For CSS frameworks, to change the Sass, import the code and then override whatever you want to change, then merge it back in, e.g. with map-merge.
Specifically, in bootstrap, utilities are stored in a $utilities assoc arr stored in a _utilities.scss.
Specifically, in bootstrap, the $utility assoc arr has each utility name as a key, and then a further assoc array with keys property, values.

#### CSS reset

A CSS reset is a piece of CSS to reset browser's default styling.


#### CSS processing

a CSS preprocessor is a transpiler from a language that is not css (though typically a superset) to css.

##### PostCSS

PostCSS is a CSS processor (CSS -> CSS), that does nothing by default, but can be hooked into by JS plugins.
Autoprefixer is a tool to add vendor prefixes to CSS properties automatically, implemented as a PostCSS plugin.

##### SCSS/Sass

⟮c3;Sass⟯ is a ⟮c4;CSS preprocessor⟯ that works with the two syntaxes ⟮c1;Sass (the syntax)⟯ and ⟮c2;SCSS⟯
⟮c3;SCSS/Sass⟯'s ⟮c4;scripting language⟯ which ⟮c4;is its syntax superset⟯ is called ⟮c5;SassScript⟯. 
Sass syntax that is indented rather than curly-braced   Sass
Sass syntax that is a CSS superset   SCSS (Sassy CSS)

While ⟮c1;CSS⟯ will ⟮c3;recover⟯ if ⟮c4;an error is found⟯, ⟮c2;SCSS⟯ will ⟮c3;throw an error and refuse to compile⟯ 

###### @extend and placeholder classes

`⟮c1;@extend⟯` is the keyword ⟮c2;for inheriting styles of other selectors⟯. 
In common language ⟮c3;`@extend foo`⟯ is saying ⟮c4;you want something to have the same declarations as foo⟯. 
Internally, ⟮c5;`@extend`⟯&nbsp;works ⟮c6;on selectors (instead of copying declarations⟯) 
A SCSS/Sass ⟮c7;placeholder selector⟯ has the syntax ⟮c8;`%foo`⟯. 
You put SCSS/Sass ⟮c9;placeholder selector⟯ where ⟮c10;selectors⟯ would go. 
An SCSS/sass ⟮c11;placeholder selector⟯ itself is a ⟮c12;selector⟯ that ⟮c13;doesn't select anything⟯. 
An SCSS/sass ⟮c14;placeholder selector⟯ is designed to be ⟮c15;`@extend`ed⟯. 
```
%toolbelt {
  box-sizing: border-box;
  border-top: 1px rgba(#000, .12) solid;
  padding: 16px 0;
  width: 100%;

  &amp;:hover { border: 2px rgba(#000, .5) solid; }
}

.action-buttons {
  @extend %toolbelt;
  color: #4285f4;
}

.reset-buttons {
  @extend %toolbelt;
  color: #cddc39;
}
```

###### mixins

⟮c1;@mixin⟯ at its most simple defines ⟮c2;a set of styles that can be reused⟯. 
⟮c3;@include⟯ ⟮c4;copies the styles⟯ defined by ⟮c5;@mixin⟯ ⟮c6;into the current block⟯. 
⟮c7;@mixin⟯ can take ⟮c8;arguments⟯, both ⟮c9;sassscript⟯ and ⟮c10;a block of css⟯. 
⟮c11;@mixins⟯ and ⟮c11;@include⟯ have ⟮c12;functionally the same syntax⟯ as ⟮c13;declaring⟯ and ⟮c13;calling a function⟯ in other languages 
± though using the @mixin and @include keywords, as SCSS/Sass also has @function ±<br>
⟮c14;@content⟯ refers to ⟮c15;a passed-in css block⟯ in @⟮c16;mixin⟯. 

```
@mixin button() {
    ...
    @content;
}

.alert {
    @include button {
        color: #F00;
    }
}
```
```
@mixin replace-text($image, $x: 50%, $y: 50%) {
  text-indent: -99999em;
  overflow: hidden;
  text-align: left;

  background: {
    image: $image;
    repeat: no-repeat;
    position: $x $y;
  }
}

.mail-icon {
  @include replace-text(url("/images/mail.svg"), 0);
}
```


#### CSS naming schemes

BEM = Block Element Modifier
BEM is a CSS naming convention
BEM uses kebap-case in naming individual things.
BEM requires all our selectors to only use BEM classes and nothing else, with the possible exception of generated HTML we have no control over.
in BEM, a block is a logically and functionally independent page component.
in BEM, a block is the equivalent of a component in Web Components.
BEM Blocks can be nested inside any other blocks.
BEM Blocks can be moved or reused, as they are independent of their surroundings.
in BEM, an element is a constituent part of a block that can't be used outside of it.
in BEM, an element without a block has no meaning.
in BEM, a modifier defines the appearance and/or behavior of a block or element
BEM Entities = {block, element, modifier}
in BEM, a mix is having multiple BEM entities on a single node
bem-name ::= <block-name>[__<elememt-name>][_<modifier-name>[_<modifier-value>]]
the modifier-value of BEM can be dropped if it's just a boolean value
BEM names are set in classes
It is important to keep in mind that a BEM entity is not a part of the name, rather one BEM name always refers to one entity, even if it includes the names of other entitites.

#### types of frameworks

»Styling frameworks« are frameworks for front-end design.
»CSS frameworks« are styling frameworks that do most of their thing in CSS.

##### bootstrap

Bootstrap has been the most common CSS-first framework in the 2010s and going into the 2020s
next to its own technologies, bootstrap may require popper
By default, bootstrap only uses margin-bottom.

##### chakra

⟮c3;Chakra⟯ provides a sensible ⟮c2;default⟯ theme inspired by ⟮c1;Tailwind CSS⟯

###### components

##### tailwind

⟮c3;Tailwind CSS⟯'s main idea is ⟮c1;using preexisting CSS classes⟯ for styling, instead of ⟮c2;switching to CSS⟯ 
⟮c6;Tailwind config⟯ is done in the ⟮c4;tailwind.config.js⟯ file, which works similarly to ⟮c5;the webpack config file⟯ 
<h2>
  Using ⟮c7;Tailwind CSS⟯, code might look like this:
</h2>
((c:8;h:8;::```lang=html;
&lt;div class="p-6 max-w-sm mx-auto bg-white rounded-xl shadow-md flex items-center space-x-4"&gt;
  &lt;div class="flex-shrink-0"&gt;
    &lt;img class="h-12 w-12" src="/img/logo.svg" alt="ChitChat Logo"&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div class="text-xl font-medium text-black"&gt;ChitChat&lt;/div&gt;
    &lt;p class="text-gray-500"&gt;You have a new message!&lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
```))

# data

open data is data available to everyone freely.
linked data is data that is interlinked usefully.

## data models

A data model is a model that provides structure to data, and to their properties, how they relate amongst each other, and how they relate to RL.
A database is an organized collection of data.
Any database implements a data model.

A DBMS (database management system) is the software used to manage a database.

A (data)(base) query language is a language used to query data in databases/information systems.

Structured data is a data model used for describing web pages.
Structured data is used by search engines to provide more rich results.
Schema.org is a set of schemas for structured data.

⟮c+;CRUD⟯ is short for ⟮c+;create⟯, ⟮c+;read⟯, ⟮c+;update⟯, and ⟮c+;delete⟯, the four operations that ⟮c+;persistent storage⟯ pretty much always has.

### general considerations

A schema is a format that describes/constrains/validates data/data structures

### relational data model

#### relational data model itself

https://upload.wikimedia.org/wikipedia/commons/7/7c/Relational_database_terms.svg

in a relational data model, a tuple is an ordered set (lol) of attribute values
in a relational data model, a relation is made up of a heading and body.
in a relational data model, a heading is a set of attributes.
The number of attributes constituting a heading is called the degree, which term also applies to tuples and relations. 
in a relational data model, a body is a set of n-tuples of the length of the degree of the heading.
The heading of the relation is also the heading of each of its tuples.
in a relational data model, an attribute is an ordered pair of attribute name and type.
relation|table
tuple making up the body|collection of rows
n-tuple|row
attribute|column

a relational database is a database with a relational data model.
In a relationnship database each n-tuple/row has its own unique key known as the primary key.
A foreign key is a column used in a relational database to link tables/relations by referencing a primary key of a row in a different relation/table.
A child table uses a foreign key to reference a primary key in the parent table. (parent ← child)
Foreign keys can be used for one-to-one or one-to-many relationships

SQL is a language used to manage relational databases.
SQL, despite its name, consists of a data query language, data definition language, data control langauge, and data manipulation language.

#### tabular data

A table is an accepted visual representation of a relation.
TODO revise in light of above info
tsv|tab-separated values
csv|comma-separated values

⟮c5;A table⟯ (e.g. in ⟮c5;database or spreadsheet⟯ contexts) is ⟮c6;a collection/sequence/whatever of⟯ ⟮c7;records⟯. 
⟮c8;A record⟯ is ⟮c9;a collection/sequence/whatever of⟯ ⟮c10;fields⟯, which ⟮c10;each contain an item of data⟯. 
A ⟮c11;record⟯ is ⟮c12;more or less kinda⟯ synonymous to ⟮c13;row⟯. 
⟮c14;Field⟯ is ⟮c15;sometimes used⟯ as a synonym for ⟮c16;column⟯, though following ⟮c17;the above differentiation⟯, this is of course ⟮c17;incorrect⟯. 
⟮c18;csv⟯ and ⟮c19;tsv⟯ both store ⟮c20;tables/tabular data⟯. 
⟮c21;csv/tsv⟯ separate ⟮c22;records⟯ via ⟮c23;newlines (generally CRLF⟯) 
The ⟮c24;first line⟯ of ⟮c25;csv/tsv⟯ may be ⟮c26;a header⟯. 
⟮c27;the csv/tsv header⟯ should have ⟮c28;as many fields⟯ ⟮c29;as the other records in the documents⟯. 

name|separates fields how
⟮c1;csv⟯|⟮c2;with commas⟯, sometimes also ⟮c30;arbitrary different characters⟯
⟮c3;tsv⟯|⟮c4;with tags⟯

Neither ⟮c30;csv⟯ nor ⟮c30;tsv⟯ are ⟮c31;fully standardized⟯, or rather ⟮c32;the specs aren't always followed⟯. 
In ⟮c33;csv/tsv⟯, ⟮c34;wrapping a field in double quotes⟯ commonly allows ⟮c35;the field separator to be included in the field⟯. 
If in csv/tsv ⟮c36;a field is wrapped in double quotes to allow the field separator to be included in the fields⟯, ⟮c37;double qoutes⟯ are then excaped by ⟮c38;double double quotes⟯. 
⟮c39;Trailing newlines⟯ at the ⟮c40;end of documents⟯ are ⟮c41;optional⟯ for ⟮c42;csv/tsv⟯, ⟮c43;field separators⟯ at ⟮c44;the end of the line⟯ will ⟮c45;create empty fields⟯. 

tidy-viewer is a FOSS rust-based csv viewer 
-s <char>|delimiters

### non-relational data models

A NoSQL database is really a misnomer, it refers to a non-relational database

#### graph data models

A graph data model is one that organizes entities and their relationships as a graph.
A graph database is a database that uses a graph data model.

##### RDF

RDF = resource description framework
RDF is a technology meant to realize the semantic web.
RDF implements a graph data model.
semantic triple = RDF triple 
semantic/rdf triple is sometimes shortened triple
a semantic triple is the atomic data unit in the RDF data model
a semantic triple has the three roles subject, predicate object
a semantic triple encodes the three roles subject predicate object as a directed graph, with the subject and object being nodes, and the relationship as an edge.
A named graph is a set of triples named by an URI

In rdf, a node can be a IRI, literal, or blank node

an RDF semantic triple indicating that art knows bob using the FOAF ontology might look like ex:art foaf:knows ex:bob

###### sparql

SPARQL = SPARQL Protocol and RDF Query Language
SPARQL is proounced sparkle
SPARQL is an RDF query language

###### JSON-LD

JSON-LD is an implementation of RDF
JSON-LD is included via a script tag 
Of the structured data formats, google prefers JSON-LD.

##### Other implementations of structured data

RDFa Lite is a minimal subset of RDFa that can be directly included in HTML.
Microdata is a format to include metadata, including but not limited to RDF data, directly included in HTML.

##### OWL

OWL short for web ontology langauge
OWL, RDFS and SHACL are ontology languages for RDF

##### applications

FOAF = friend of a friend
FOAF is an ontology for people, their properties and their relations using RDF/OWL 

###### open graph

The Open Graph protocol enables any web page to become a rich object in a social graph.
open graph is based on RDFa.
Open graph metadata is specified within meta tags.
There are four required properties for open graph, which are og:image, og:title, og:type and og:url.
The property of the open graph metadata is specified within the property property, and the value of the open graph metadata is specified within the content property.

#### document data model

a document database implements a document datamodel.
MongoDB is the most well known document database.
IndexedDB = Indexed Database API.
IndexedDB is a document database for client-side storage.
Most document databases are based on a variant of JSON.

## semantics

### semantic web

The semantic web is sometimes known as web 3.0
The goal of the samntic web is to make internet data machine readable
A semantic query is a data query on the semantic web.
the social graph is a graph that represents social relationship between entities.
the open graph allows web pages to become objects in a social graph

A hyperlink is a reference to data which the user can follow by interacting with it.
Hypertext is text connected by hyperlinks.
Hypermedia is media connected by hyperlinks.

A ontology languages is a language that describes an ontology. 

### folksonomy

⟮c1;Folksonomy⟯ is a system where ⟮c2;users⟯ apply ⟮c3;public tags⟯ to items, thus over time generating a sort of ⟮c4;taxonomy⟯. 
Two types of ⟮c5;folksonomies⟯ are ⟮c6;broad⟯, where ⟮c7;multiple users can apply the same tag⟯, thus ⟮c7;showing which tags are the most popular⟯, and ⟮c6;narrow⟯, where ⟮c7;the same tag can only be applied once⟯ 

booru: image site with foksonomical tags
boorus: generally look similar to Danbooru, the original
sexual content: rating:s(afe), rating:q(uestionable), rating:e(xplicit)
Other boorus for anime pictures: danbooru(.donmai.us), zerochan, gelbooru, anime-pictures, safebooru (either safebooru.org or safebooru.donmai.us), rule34.paheal.net

flex-container:<img src="sm_2021-10-19--03-12-32-screenshot.jpg"><img src="sm_2021-10-19--03-11-46-screenshot.jpg"><img src="sm_2021-10-19--03-10-58-screenshot.jpg">

## extracting information

⟮c1;A hash function⟯ ⟮c3;maps⟯ ⟮c2;data of arbitrary size⟯ ⟮c3;to⟯ ⟮c4;fixed size-values⟯ ⟮c5;deterministically⟯. 
⟮c6;The result of a hash function⟯ is generally called ⟮c7;a hash⟯. 
At it's most general, a fingerprint is an unique combination of features that uniquely identify something.
A fingerprinting algorithm reduces a data item to a much shorter unique identifier, often also called a fingerprint.
Often, hashing algorithms are used as fingerprinting algorithms.
A ⟮c2;checksum⟯ is a ⟮c1;small amount of data⟯, derived by applying ⟮c3;a suitable algorithm⟯ the relevant data, used to ⟮c4;check whether errors have occurred⟯, e.g. in ⟮c5;transmission⟯, ⟮c5;storage⟯ or ⟮c5;data entry⟯.
Depending on its design goals, a good c⟮c3;hecksum⟯ algorithm usually outputs ⟮c1;a significantly different value⟯, even ⟮c2;for small changes made to the input⟯. 
A check digit is one or more digits or characters (but generally a small amount) used as a checksum.

# HCI

HCI = Human Computer Interaction/Interfaces
The set of ways a human can interact with a computer   Interaction styles
WYSIWYG   What you see is what you get
the problem with the term 'intuitive' in HCI is that to a certain extent, everything is learned.

## IO

Input devices are devices that move/transform data from  ⟮c1;the world ≈ the user to the computer⟯
Output devices are devices that move/transform data from ⟮c1;the computer to the world ≈ the user⟯
The most important input devices are probably mouse and keyboard, less common ones are gamepads, motion tracking devices, microphones, cameras, etc.
Examples of output devices are screens, speakers, etc.
A pointing device is an input device that allows a user to input spatial information.
Examples of pointing devices are mice, trackpads, trackballs, pointing sticks aka trackpoints.
Pointing devices are governed by fitts law
Fitts law says that the time required to rapidly move move to a target area, e.g. by a pointing device, is a function of the ratio between the distance to the target and teh widht of the target.

### input

#### modes

A mode is a state which is explictly entered and exited where the same input will produce different results than if it wasn't in that state.
A quasimode is like a mode, but the state is only maintained as long as an action is performed.
Keyboard keys that maintain a quasimode are shift, alt, control, option....
Modes are prone to mode errors.
A mode error occurs when a user tries to do an action only appropriate for a different mode and gets an undesired response.
mode errors occur because the user lacks understanding between the difference in modes, has not (yet) recieved the indication of a mode switch, or is confused/has forgotten about the active mode.
Focus stealing is a mode error that happens when a program unexpectedly has focus, and the user attempts actions for the other program.

#### text

##### local variants

Keyboards are often identified based on ⟮c1;their first few keys on the top letter row⟯
QUERTY|en
QWERTZ|de
AZERTY|fr

Between english and german keyboards, the only difference in actual letters in that z and y are flipped.

strg   ctrl

##### modes

Lock keys are keys that enter/exit a mode.
Lock keys: {caps lock, shift lock, num lock, insert}
The insert key is a lock key that switches between insert and overtype mode.
in the 2020s, insert mode is common, overtype is barely used.
In overtype mode, typing replaces characters to the right
In insert mode, typing moves the characters in the right further to the right.

The cursor is reasonably wide   overtype mode
The cursor is reasonably narrow   insert mode (the kind of thing that the ins key changes)

caps lock|makes all latin characters generate uppercase characters but not alternate characters
shift lock|acts as shift was continuously pressed, that is, generates both uppercase and alternate characters respectively

On ⟮c13;windows⟯ under ⟮c14;certain keyboard layouts⟯, ⟮h14;e.g. ⟮c15;AZERTY and QWERTZ⟯,⟯ the ⟮c16;caps lock key⟯ ⟮c17;acts as shift lock⟯, ⟮hb;however not on ⟮c18;mac⟯, and ⟮c19;there is no setting to make it so⟯, making ⟮c20;any solution requiring scripting via Hammerspoon or Karabiner⟯.⟯ 
Many operating systems support ⟮c21;typing 'normal' characters⟯ by ⟮c22;pressing shift⟯ when in ⟮c23;capslock / shiftlock mode⟯⟮hb;, however, not ⟮c24;mac⟯⟯. 

##### types of keys

###### modifier keys

modifier keys are keys that maintain a quasimode.
modifier keys that are found on any hardware keyboard as of 2020 are shift, ctrl, alt/option/altgr, win/cmd/linux equivalent.
On small layout keyboards, the additional modifier key function is often present.
the function key is often abbreviated fn.
Windows and linux treat ctrl as their primary modifier key, while mac treats cmd as the primary modifier keys.
Originally, super, meta and hyper keys were all dedicated modifier keys present on some keyboards.
today, different linux distros treat meta or super as their equivalent to cmd/windows.
today, since hyper keys are not really present anywhere, hyper key refers to a fictional modifier key created by simulating an insane number of modifier keys at the same time by pressing a different non-modifier key (often e.g. capslock)f

####### alt/option

alt gr = alt graph
alt gr was originally for producing box drawing characters.
Despite having similar names, alt and alt gr generally share no functionality.
alt gr produces a quasimode for alternative characters similar to shift. 
US keyboards typically have two normal alt keys.
European/international keyboards typcially have one alt and one alt gr key.
The mac option key has functionality of both the alt and alt gr keys: it can be used as a key in key command like alt, but can also produce additional characters like alt gr.
Due to historical reasons, emacs used to use the meta key as a modifier, but later switched to alt. However, it kept the label 'M' for this modifier key.

###### delete/backspace

Delete key|Delete characters forwards (to the right)
Backspace key|Delete characters backwards (to the left)

###### navigation keys 

navigation keys are keys that move the viewport or the cursor.

####### pgupdown home end

The ⟮c6;end, home and pgup/pgdown⟯ keys ⟮c7;move the cursor⟯ when ⟮c8;text-editing⟯, ⟮c7;and the view⟯ when ⟮c8;not⟯.
  span=2;Text-editing context
Key|Action
⟮c16;Home key⟯|⟮c17;Move the cursor to beginning of line⟯
⟮c18;End key⟯|⟮c19;Move the cursor to end of line⟯
⟮c20;Pg Up / Pg down⟯|⟮c21;Go up/down a page⟯

  span=2;Non-text-editing context
Key|Action
⟮c22;Home key⟯|⟮c23;Go to beginning of document⟯
⟮c24;End key⟯|⟮c25;Go to end of document⟯
⟮c26;Pg Up / Pg down⟯|⟮c27;Go up/down a page⟯


The ⟮c9;function key⟯ is used to ⟮c10;simulate home/end/pgup/pgdown⟯ via ⟮c11;the arrow keys⟯ on ⟮c12;smaller formfactors⟯. 

  span=2;Laptops and other small form factors
Is simulated by|Key combination
⟮c28;Home key/End key⟯|⟮c29;fn left/right arrow⟯
⟮c30;Pg Up / Pg down⟯|⟮c31;fn + up/down arrow⟯


on ⟮c13;macOS⟯ ⟮c14;home, end, pgup, pgdown⟯ only ever ⟮c15;move the view.⟯</p>

mac, instead of home, end, pgup, pgdown
Key|does
⟮c32;cmd + left/right⟯|⟮c33;moves the cursor to the beginning/end of the line⟯
⟮c34;cmd + up/down⟯|⟮c35;oves the cursor to the beginning/end of the document⟯


####### navigation key combinations

Platform specific
Key|does
⟮c36;alt + left/right⟯|⟮c37;go to beginning/end of word (mac⟯)
⟮c38;ctrl + up/down⟯|⟮c39;go to beginning/end of word (win/linux⟯)
⟮c40;alt + backspace/delete⟯|⟮c41;delete to beginning/end of word (mac⟯)
⟮c42;ctrl + backspace/delete⟯|⟮c43;delete to beginning/end of word (win/linux⟯)
⟮c44;cmd + backspace⟯|⟮c45;delete to beginning of line (mac⟯)


##### key combinations & actions

A keyboard shortcut some key input that performs an action different from its literal value.
A key combination is the pressing of a key and one or more modifier keys to perform an action
A key chord are two or more key combinations or key presses sequentially to perform an action.
e.g. cmd k then m to select the document language in VSCode

###### keyboard shortcuts

####### basic OS

Action|Shortcut
⟮c1;Close tab/window⟯|⟮c2;⟦⌘⟧ ⟦w⟧⟯
⟮c3;New tab⟯|⟮c4;⟦⌘⟧ ⟦t⟧⟯
⟮c5;Quit app⟯|⟮c6;⟦⌘⟧ ⟦q⟧⟯
⟮c7;Restore tab (editor in VS code⟯)|⟮c8;⟦⌘⟧ ⟦⇧⟧ ⟦t⟧⟯


####### edit history
⟮c1;undo⟯|⟮c2;⟦⌘⟧ ⟦z⟧⟯
⟮c3;redo⟯|⟮c4;⟦⌘⟧ ⟦⇧⟧ ⟦z⟧⟯


####### browser shortcuts

Action|Shortcut
⟮c1;Switch to tab n⟯|⟮c2;⟦⌘⟧ ⟦n⟧⟯
⟮c3;Focus address bar⟯|⟮c4;⟦⌘⟧⟦L⟧⟯
⟮c5;open link in new tab⟯|⟮c6;⟦⌘⟧ ⟦click⟧⟯
⟮c7;download link target⟯|⟮c8;⟦⌥⟧ ⟦click⟧⟯

####### search 

Action|Shortcut
⟮c1;Find in project/ other larger scope⟯|⟮c2;⟦⌘⟧ ⟦⇧⟧ ⟦F⟧⟯
⟮c3;Find next⟯|⟮c4;⟦⌘⟧ ⟦g⟧⟯
⟮c5;Find previous⟯|⟮c6;⟦⌘⟧ ⟦⇧⟧ ⟦g⟧⟯
⟮c7;Open search in window/smaller scope⟯|⟮c8;⟦⌘⟧ ⟦F⟧⟯
⟮c9;Open search in project/other large scope/advanced search⟯|⟮c10;⟦⌘⟧ ⟦⇧⟧ ⟦F⟧⟯


####### form navigation
⟮c1;⟦tab⟧⟯|⟮c2;field forward⟯
⟮c3;⟦⇧⟧ ⟦tab⟧⟯|⟮c4;field back⟯



####### weird mac

Action|Shortcut
⟮c1;Get info on item⟯|⟮c2;⟦⌘⟧ ⟦i⟧⟯
⟮c3;Preferences⟯|⟮c4;⟦⌘⟧ ⟦,⟧⟯
⟮c5;Switch focus between windows of the same program⟯|⟮c6;⟦⌘⟧ ⟦`⟧⟯
⟮c8;Show hidden files⟯|⟮c7;⟦⌘⟧ ⟦⇧⟧ ⟦.⟧⟯
⟮c9;rename current item⟯|⟮c10;{{c2::⟦enter⟧}⟯
⟮c11;Minimize (not windows)⟯|⟮c12;⟦⌘⟧ ⟦m⟧⟯
⟮c11;Minimize (windows)⟯|⟮c12;⟦⊞⟧ ⟦↓⟧⟯
⟮c13;Fullscreen⟯|⟮c14;⟦⌘⟧ ⟦⌃⟧ ⟦f⟧⟯
⟮c1;⟦⌥⟧ ⟦space⟧⟯|⟮c2;non-breaking space (on keyboard⟯)
⟮c1;del key⟯|⟮c2;⟦fn⟧ ⟦⌫⟧⟯


<br>  span=2;macOs Dialogs
Action|Shortcut
⟮c1;cancel⟯|⟮c2;⟦esc⟧⟯
⟮c3;don't save⟯|⟮c4;⟦⌘⟧ ⟦⌫⟧⟯


  span=2;Magnifying glass
Action|Shortcut
⟮c1;toggle⟯|⟮c2;⟦⌘⟧<kbd class="key modifier alt"></kbd>⟦8⟧⟯
⟮c3;zoom out⟯|⟮c4;⟦⌘⟧<kbd class="key modifier alt"></kbd> ⟦-⟧⟯
⟮c5;zoom in⟯|⟮c6;⟦⌘⟧<kbd class="key modifier alt"></kbd> ⟦0⟧⟯


####### Anki

Action|Shortcut
⟮c1;Add new card⟯|⟮c2;⟦⌘⟧ ⟦n⟧⟯
⟮c3;Bury card⟯|⟮c4;⟦⌘⟧ ⟦-⟧⟯
⟮c5;Bury note⟯|⟮c6;⟦⌥⟧ ⟦-⟧⟯
⟮c7;Edit html⟯|⟮c8;⟦⌘⟧ ⟦⇧⟧ ⟦x⟧⟯
⟮c9;Mark note (both browser and reviewer),<br> mark parent element w/ textmarker (browser, custom⟯)|⟮c10;⟦⌥⟧ ⟦k⟧⟯
⟮c11;Show deck options menu⟯|⟮c12;⟦⌘⟧ ⟦⇧⟧ ⟦,⟧⟯
⟮c13;Study⟯|⟮c14;⟦L⟧⟯
⟮c15;Subscript⟯|⟮c16;⟦⌘⟧ ⟦⇧⟧ ⟦⌥⟧ ⟦2⟧⟯
⟮c17;Superscript⟯|⟮c18;⟦⌥⟧ ⟦⌘⟧ ⟦2⟧⟯
⟮c19;Suspend card⟯|⟮c20;⟦⌘⟧ ⟦j⟧⟯
⟮c21;Suspend note⟯|⟮c22;⟦⌥⟧ ⟦j⟧⟯
⟮c23;add tag⟯|⟮c24;⟦⌘⟧ ⟦t⟧⟯
⟮c25;remove tag⟯|⟮c26;⟦⌘⟧ ⟦⇧⟧ ⟦t⟧⟯
⟮c27;reposition⟯|⟮c28;⟦⌘⟧ ⟦y⟧⟯
⟮c29;reschedule⟯|⟮c30;⟦⌘⟧ ⟦⇧⟧ ⟦y⟧⟯
⟮c31;add cloze (don't increment number⟯)|⟮c32;⟦⌘⟧ ⟦⇧⟧ ⟦⌥⟧ ⟦c⟧⟯
⟮c33;add cloze (increment number⟯)|⟮c34;⟦⌘⟧ ⟦⇧⟧ ⟦c⟧⟯
⟮c35;submit something/new line⟯|⟮c36;⟦⌘⟧ ⟦enter⟧⟯
⟮c38;Browse screen⟯|⟮c37;⟦B⟧⟯
⟮c39;X⟯|⟮c40;Deck home screen⟯


####### file-related
⟮c1;Export⟯|⟮c2;⟦⇧⟧⟦⌘⟧ ⟦E⟧⟯
⟮c3;Import⟯|⟮c4;⟦⌘⟧ ⟦⇧⟧ ⟦i⟧⟯
⟮c5;Save as⟯|⟮c6;⟦⌘⟧ ⟦⇧⟧ ⟦s⟧⟯
⟮c7;Save⟯|⟮c8;⟦⌘⟧ ⟦s⟧⟯
⟮c9;New thingy⟯|⟮c10;⟦⌘⟧ <div class="key" style="grid-area: 2/5">n</div>⟯
⟮c11;New alternative thing (window, folder, etc.⟯)|⟮c12;⟦⌘⟧ ⟦⇧⟧ ⟦n⟧⟯
⟮c13;Open⟯|⟮c14;⟦⌘⟧ ⟦o⟧⟯
⟮c15;Duplicate current item⟯|⟮c16;⟦⌘⟧ ⟦⇧⟧ ⟦D⟧⟯
⟮c17;Print⟯|⟮c18;⟦⌘⟧ ⟦p⟧<br><div class="sub"></div>⟯
⟮c19;delete thingy (if file, move to bin⟯)|⟮c20;⟦⌘⟧ ⟦⌫⟧⟯


####### view
⟮c1;Reset zoom level (most often⟯)|⟮c2;⟦⌘⟧ ⟦0⟧⟯
⟮c3;Zoom out⟯|⟮c4;⟦⌘⟧ ⟦-⟧⟯
⟮c5;Zoom in⟯|⟮c6;⟦⌘⟧ ⟦=⟧⟯


####### text editing 

Shortcut|Action
⟮c1;Paste as plain text⟯|⟮c2;⟦⌘⟧ ⟦⇧⟧ ⟦v⟧⟯
⟮c3;Select all⟯|⟮c4;⟦⌘⟧ ⟦a⟧⟯
⟮c5;copy⟯|⟮c6;⟦⌘⟧ ⟦c⟧⟯
⟮c7;cut⟯|⟮c8;⟦⌘⟧ ⟦x⟧⟯
⟮c9;paste⟯|⟮c10;⟦⌘⟧ ⟦v⟧⟯
⟮c1;⟦⌃⟧ ⟦L⟧⟯|⟮c2;Insert hyperlink⟯
⟮c3;⟦⌘⟧ ⟦b⟧⟯|⟮c4;Bold text⟯
⟮c5;⟦⌘⟧ ⟦i⟧⟯|⟮c6;Italic text⟯
⟮c7;⟦⌘⟧ ⟦u⟧⟯|⟮c8;underlined text⟯
⟮c9;⟦⇧⟧ ⟦tab⟧⟯|⟮c10;unindent⟯
⟮c11;⟦tab⟧⟯|⟮c12;Indent⟯



######## video

Shortcut|Action
⟮c1;,⟯|⟮c2;one frame back⟯
⟮c3;.⟯|⟮c4;one frame forwards⟯
⟮c5; ⟦f⟧⟯|⟮c6;go fullscreen⟯
⟮c7;esc⟯|⟮c8;Exit fullscreen⟯
⟮c9;space⟯|⟮c10;pause⟯


######## discord


        Shortcut
      |Action
⟮c1;⟦⌘⟧ ⟦⇧⟧ ⟦D⟧⟯|⟮c2;Toggle deafen⟯
⟮c3;⟦⌘⟧ ⟦⇧⟧ ⟦U⟧⟯|⟮c4;Upload file⟯
⟮c5;⟦⌘⟧ ⟦⌥⟧ ⟦↑/↓⟧⟯|⟮c6;Navigate between servers⟯
⟮c7;⟦⌥⟧ ⟦↑/↓⟧⟯|⟮c8;navigate between channels (incl private messages⟯)
⟮c9;⟦⌘⟧ ⟦K⟧⟯|⟮c10;toggle quickswitcher⟯
⟮c11;⟦⌃⟧ ⟦Ä⟧⟯|⟮c12;start/accept call⟯
⟮c13;⟦e⟧⟯|⟮c14;edit message⟯
⟮c15;⟦r⟧⟯|⟮c16;reply⟯
⟮c17;⟦esc⟧⟯|⟮c18;decline incoming call⟯
⟮c19;⟦⌘⟧ ⟦⇧⟧ ⟦M⟧⟯|⟮c20;toggle mute⟯


######## vector editor

Keyboard shortcut|action|programs
⟮c1;S⟯|⟮c2;Select tool⟯|⟮c3;Inkscape, SVG-Edit⟯
⟮c4;G⟯|⟮c5;group/ungroup⟯|⟮c6;SVG-Edit⟯
⟮c7;W⟯|⟮c8;Wireframe mode⟯|⟮c9;SVG-Edit⟯
⟮c10;A⟯|⟮c11;Select everything⟯|⟮c12;SVG-Edit⟯
⟮c13;D⟯|⟮c14;Duplicate⟯|⟮c15;SVG-Edit⟯
⟮c16;alt-drag⟯|⟮c17;drag a duplicated shape (duplicate and then move⟯)|⟮c18;SVG-Edit⟯
⟮c19;cmd-drag⟯|⟮c20;drag a duplicated shape (duplicate and then move⟯)|⟮c21;Affinity designer⟯
⟮c22;tap spacebar while dragging⟯|⟮c23;drop a duplicate of the current shape at position⟯|⟮c24;Inkscape⟯
⟮c25;shift+click⟯|⟮c26;select multiple objects⟯|⟮c27;Inkscape, SVG-Edit, Affinity Designer⟯
⟮c28;F⟯|⟮c29;center canvas in frame⟯|⟮c30;SVG-Edit⟯


######## navigatable

Force/Hard Reload|⟦⌘⟧ ⟦⇧⟧ ⟦r⟧
Reload|⟦⌘⟧ ⟦r⟧

######## zoomable

Zoom in|⟦⌘⟧ ⟦+⟧

##### caret

cursor can be text or mouse
mouse cursor = pointer
text cursor = caret

Some editors feature multi-cursors, which is where you can create multiple text cursors, which will perfom the edito at all places where there is a cursor.
add text cursor above/below|⟦⇧⟧ ⟦⌥⟧ ⟦↑/↓⟧
add/remove text cursor at mouse cursor location|⟦⌥⟧ ⟦click⟧
add text cursors to all occurences of current selection|⟦⌘⟧ ⟦⇧⟧ ⟦l⟧
add text cursor to nex occurrence of selection|⟦⌘⟧ ⟦d⟧

If in VSCode you have ⟮c1;as many text cursors⟯ as ⟮c2;the thing you want to paste has lines⟯, it will auto paste it there.

##### autocomplete

<dfn>⟮c1;Autocomplete/word completion⟯</dfn> is a feature where ⟮c2;an application predicts the rest of something the user is typing⟯.  
<dfn>⟮c3;Autocomplete/word completion⟯</dfn> on ⟮c4;smartphone keyboards⟯ is called <dfn>⟮c5;predictive text⟯</dfn>, ⟮sb;this used to refer to ⟮c6;the prediction of typing on numeric keypads (e.g. T9⟯⟯) 
<dfn>⟮c7;Autocomplete/word completion⟯</dfn> ⟮c8;in a command-line interface⟯ is called <dfn>⟮c9;command-line⟯</dfn> or <dfn>⟮c9;tab⟯ ⟮c9;completion⟯</dfn>, ⟮sb;which generally uses ⟮c10;the tab key (whence the name⟯).⟯ 
<dfn>⟮c11;Autocomplete/word completion⟯</dfn> in ⟮c12;code editors⟯ is also known as <dfn>⟮c13;code completion⟯</dfn>. Examples include ⟮sb;⟮c14;VS &amp; VS Code⟯'s ⟮c15;IntelliSense⟯, and ⟮c16;AI (modfied GPT-3⟯)-powered ⟮c17;GitHub Copilot⟯.⟯ 

### Natural Language Processing

NLP = Natural Language Processing
tts = text to speech
Text to speech AKA Speech synthesis
Speech to text AKA Speech recognition

TTS

say|mac
espeak|nix

## shells

flex-container:<img src="sm_Midnight_Commander_(2005)_en.png"><img rc="sm_1024px-Vim-(logiciel)-console.jpg">


A shell is a wrapper around the OS that acts as an interface between it and humans.
Types of shells: graphical, command-based
Shell is often but kinda incorrectly used as a synonym to command-based shell
A TUI is a user interface that uses Text to render, but accept input like GUIs, and like GUIs they consume a fixed part of the screen.
NUIs are (mostly theoretical/hypothesized) intefaces that are claimed to be natural to use in some way.

UI|User interface
NUI|natural user inteface
GUI|graphical user interface
TUI|Text-based user interface
CLI|Command-line interface

### CLI

A command-line shell/interface is a type of shell (in the wide sense, it is decidedly not a type of shell in the sense of the interpreter such as bash, csh) where actions are accomplished by entering commands.
The shell living within the terminal is interacted with via a CLI, but so does e.g. vim, or various cheat consoles in games.

#### syntax

There seem to be roughly two kinds of CLIs, ones that do most of their stuff via --arguments, and ones that do most of their stuff with a sentence-like syntax.
CLIs that have a sentence-like syntax have (after the command that indicates this is what we're interfacing with, perhaps roughly equivalent to a vocative) a syntax consisting of &lt;verb(s)&gt; and &lt;object(s)&gt;
The most common forms a sentence-like cli syntax takes on is either a &lt;addressee&gt; &lt;object&gt; &lt;verb&gt; {&lt;objects&gt;} syntax or a &lt;addressee&gt; &lt;verb&gt; &lt;object&gt; {&lt;objects&gt;} syntax
topic-object-verb-object CLIs
gh|github|gh issue view 12
nmcli|NetworkManager|nmcli con add type ethernet ...
⟮c1;⟯

### GUI

A graphical shell/grapical user interface is a type of shell (in the wide sense) that allows accomplishing commands via interaction through visual elements.

WIMP = Windows, icons, menus, pointer

#### core concepts

⟮ha;<img src="sm_220px-Webdesign_Viewport_Window_Screen.svg.png">⟯
The viewport is the area (often rectangular) of a given thing that is currenty visible

#### theming

⟮h∞;<img src="sm_paste-7ba77efd4dacf391cf06da1c6828a7e27ddeb96e.jpg">⟯
A ⟮c1;s2;theme⟯ or ⟮c2;s1;skin⟯ (some people differentiate, but the differences don't seem consistent) is ⟮c3;a set of visual pattern(s) (colors, icons, fonts, etc.) that determines the look and feel of a GUI⟯. ⟮hb;It may also refer to ⟮c4;the set of files that define a theme/skin.⟯⟯ 
lxappearace is a gtk theme switcher

#### appearance

##### skeuomorphs and skeuomorphicism

A skeuomorph is a design inspired by a original design which retains elements from the original element that are no longer necessary in the new design, e.g. because it is funcionally different or in a new medium.
Skeuomorphicism is a UI design approach that uses skeuomorphs that imitate real-life objects (though that would no longer be necessary on a digital devices).

#### widgeting toolkits

#### elements

A UI element that enters a mode that blocks interaction with the main program and only allows interaction with the UI element, while it is visible is called modal, else it is modeless.

##### menu

A menu contains a lists of options or commands, one or more of which can be chosen or executed.

###### text-based 

A text-based menu is a type of menu that contains only text entries, most commonly as a list of one or more collumns.

####### searchable 

Many text-based menus are searchable by a type of fuzzy search.
dmenu and its successor rofi as well as choose on mac are shell filters that act as a text-based fuzzily searchable menu.
rofi can similate dmenu with the -dmenu argument
dmenu/rofi/choose create a menu entry for each item in stdin, where newline is treated as the delimiter by default
dmenu/rofi/choose output the selected item to stdout

######## command palette / quick open menu

⟮h∞;<img src="Screenshot%202021-12-09%20at%2003.12.09.png">⟯
A command palette is a text-based fuzzily searchable menu containing most things one can do in a program.
A quick open menu is a text-based fuzzily searchable menu containing navigation items.
Often (VSCode, Devltools) a command palette is merely a mode of a quick open menu, enterable or exitable by adding/removing >
A ⟮c19;Command Palette⟯ often also shows ⟮c20;the direct keyboard shortcuts⟯. 
A ⟮c21;Command Palette⟯ generally appears as ⟮c22;a modal⟯ floating in ⟮c23;the upper center⟯ of the window. 
Following ⟮c24;Sublime text and VSCode⟯, ⟮c25;many applications have adapted⟯ ⟮c26;the Command Palette⟯. 
vscodes command palette/quick open menu features modes that search and only navigate once enter is pressed, and modes (called go to) that navigate immediately when typing

Shortcut to open command palette|Platform
⟮c11;⟦⌘⟧ ⟦⇧⟧ P⟯|⟮c12;VSCode, Chrome Devtools⟯
⟮c13;⟦⌘⟧ (⟦⌥⟧) K⟯|⟮c14;GitHub⟯


⟮c35;Quick open menus⟯ are often entered via ⟮c36;⟦⌘⟧ ⟦P⟧.⟯ 


    <tr><th colspan="2">Possible prefixes in Quick Open menus
⟮c1;@somestring⟯|⟮c2;go to symbol somestring⟯
⟮c3;:somenumber⟯|⟮c4;go to line somenumber⟯
⟮c5;?⟯|⟮c6;show suggestions what you can do with quick open⟯
⟮c7;&gt;⟯|⟮c8;enter command palette mode⟯


####### context menu

⟮h∞;<img src="Menu_key_screen.jpg">⟯⟮h∞;<img src="Context_menu_windows.png">⟯⟮h∞;<img src="Context_Menu_on_OS_X_10.9.png">⟯
A context menu is a menu of actions for wherever the focus is, most commonly summoned by right-clicking.

###### ambiguous

####### task switcher

A task/app(lication) switcher is a menu that allos switching between open programs or windows.
A task switcher that allows switching between windows is more properly a window switcher.
windows|alt+tab|windows
mac|cmd+tab|applications

####### hamburger 

flex-container:<img src="hamburger-menu-definition.png">

A hamburger menu is a menu triggered by a hamburger button.
A hamburger menu generally comes out from the side, contains a a list of navigation options, and covers between 70% - 100% of the screen
A hamburger button is a three-line icon that contains 
A hamburger menu most often refers to the menu you get when you click a hamburger button but also may refer to the button itself, or the whole package

##### bar

A bar is a long-ish rectangle found at the edge of an UI element.

###### title bar

A title bar is a horizontal bar that is typically located at the top of a window and contains the name of the application andor document/window, as well as the title bar buttons.
the title bar buttons are most typically minimize, maximise and close.
In most GUIs, you can move the window by grabbing the title bar and dragging.
In most GUIs, you can expand the window to fill the screen by double-clicking the title bar.

###### status bar

flex-container:⟮h∞;<img src="sb-paint.png">⟯⟮h∞;<img src="460px-Emacs_statusline.png">⟯⟮h∞;<img src="Gedit_3.11.92.png">⟯⟮h∞;<img src="StatusBar_Light.png">⟯⟮h∞;<img src="lGPcKx09nzIAFtAjFbQ_6FoXc3hnT7y0oMOGVNI8tbFWziGJQdUAgar1TBMmIGP_2Sj0gvLJonpoydv5UyTrOl_WJnrDz45RPMkSM7s=w1064-v0.png">⟯

On ⟮c1;desktop⟯, a ⟮c2;status bar⟯ is a ⟮c3;horizontal⟯ ⟮c4;bar⟯ generally at ⟮c5;the bottom of a window⟯. 
A ⟮c15;status bar⟯ on desktop displays ⟮c6;various kinds of information⟯, often used when ⟮c7;editing documents ((n)vi(m), vscode, various office programs, etc.⟯). 
On ⟮c8;mobile⟯, a ⟮c9;status bar⟯ is a ⟮c10;horizontal⟯ ⟮c11;bar⟯ at ⟮c12;the top of the screeen⟯. 
A ⟮c16;status bar⟯ on mobile contains ⟮c13;notification⟯ and ⟮c13;system⟯ ⟮c13;icons⟯ ⟮hb;(such as ⟮c14;power, networks, time⟯⟯) 

###### taskbar

flex-container:⟮h∞;uh11-12;<img src="Windows_XP_task_grouping_(Luna).png">⟯⟮h∞;<img src="Windows_10_Taskbar.PNG">⟯⟮h∞;<img src="1024px-MacOS_Sierra_dock.png">⟯⟮h∞;<img src="1024px-Plasma_5.20_Taskbar.png">⟯

⟮c12;The above⟯ are all examples of ⟮c11;taskbars⟯. 
A ⟮c1;taskbar⟯ is a GUI element that typically shows ⟮c2;which programs are open⟯, and allows ⟮c3;pinning programs or other things for quick access⟯. 
A taskbar generally positioned ⟮c4;as a strip along the edge of a screen⟯. 
A taskbar, aside from programs may also have a ⟮c5;notification section⟯, ⟮c6;a search box⟯, ⟮c7;various tools⟯, etc. 
Despite being called '⟮c8;Dock⟯', it's just ⟮c9;macOs⟯'s version of a ⟮c10;taskbar⟯ 

###### navigation bar

<img src="8f922968919629.5b6dba4c75e8b.png"><img src="Dahsboard+Sidebar+Menu.webp"><img src="rm0fIeRuMarYY8xM5bLwss_ISqewjbPE0j-WOpx99ZflAdj6WFUK18kjeXGW2Ir4d1lVLDH_TgFYA1B0l0UIO2WK6iE8dktiZnEBohs=w1064-v0.png"><img src="NavigationBar_Standard.png">
A navigation bar/menu/navbar is a bar/strip, generally placed at any edge of the window, that contains links/shortcuts for navigation through a thing (program, app, website, whatever)
On iOS specifically, a navigation bar appears at the top of the screen, often containing a back button on the left, and a few controls on the right, sometimes a title in the middle
On android specifically, a navigation bar is the bar at the bottom of the screen that generally houses the three navigation controls: back, home, and overview.

###### activity bar (vscode)

flex-container:⟮h∞;<img src="sm_toggle_side_bar.gif">⟯

VS Code's ⟮c11;activity bar⟯ is a ⟮c12;nav(igation) bar⟯ containing ⟮sb;⟮c13;5 (by default) icons⟯ that ⟮c14;trigger sidebars⟯⟯. 

flex-container:⟮h∞;uh1-10;<img src="sm_paste-67a9ccb8984cb6d1d1332e6409cafa085bda1529.jpg">⟯

nth icon in activity bar|Purpose
⟮c1;1st icon⟯|⟮c2;FIile explorer⟯
⟮c3;2nd icon⟯|⟮c4;Search⟯
⟮c5;3rd icon⟯|⟮c6;Source Control⟯
⟮c7;4th icon⟯|⟮c8;Run View⟯
⟮c9;5th icon⟯|⟮c10;Extensions View⟯

⟮c15;Extensions⟯ can ⟮c16;populate all of VS Code's bars⟯ with ⟮c17;more content⟯ 

##### breadcrumbs


flex-container:<img src="sm_2021-06-26--14-46-16-screenshot.png">
A breadcrumb trail is a series of separated breadcrumbs, each representing a distict navigational item organized into a logical sequence.
A breadcrumb trail most commonly represents a hierarchical structure.
Each breadcrumb is usually a minimal element containing text only.
In bootstrap, breadcrumbs are created by .breadcrumb > .breadcrumb-item*n

##### sidebars

flex-container:⟮h∞;<img src="440eb7ec02550be3045c969dc02dc7f2.png">⟯⟮h∞;<img src="162vsE7VWrMgBdBTF8MCKXw.jpeg">⟯⟮h∞;<img src="ditch-sidebar-2016-2-fox.jpg">⟯⟮h∞;<img src="ditch-sidebar-2016-4-washington.jpg">⟯⟮h∞;<img src="sidebars.png">⟯
A ⟮c1;sidebar⟯ is an UI element that is displayed ⟮c2;to the side of⟯ ⟮c3;the main content⟯ or ⟮c4;of the screen⟯. ⟮hb;Sidebars may be ⟮c5;navigation bars⟯, contain ⟮c6;tools⟯ or contain ⟮c7;further content⟯. ⟮hb;Sidebars are generally ⟮c8;reasonably wide (i.e. not just icons).⟯⟯⟯ 

##### disclosure widgets

A disclosure widget has a collapsed state where it only shows a heading, and an expanded state which shows the heading and more content contained within.
With a disclosure widget, the content contained within is shown if the heading is interacted with.
With a disclosure widget, the heading often indicates that it can be expanded/shrunken either via ▼/▲ or via +/-
In html, a disclosure widget is defined via a details element.
In html, the header of a disclosure widget is defined by a summary element.
An accordion is a set of multiple disclosure widgets.
Most commonly, disclosure widgets start out in their collapsed state by default.
In html, you can force a disclosure widget to start in its open state by specifying the boolean attribute open.
<img src="disc.png"><img src="kfw-disclosure.jpg">⟮h2;<img src="sm_FAQ-Content-Style-Accordion.gif">⟯

##### containers

A lightbox is a box/container that displays images/videos by filling the screen and dimming out the rest of the page/UI.

###### drawer

A drawer is a container at one edge that is show-hidable.
A drawer typically takes up most of the screen when opened on a mobile device.
A drawer uses a shadow dims the rest of the UI when expanded, seemingly appearing in front of it.
Often, the menu a hamburger button triggers is a drawer.
drawers on android can typically also be opened with a swiping gesture.

###### windows

####### dialog box

A dialog box is a small window that appears in front of the main window due to some event or action and requires some sort of response.
An alert box is a dialog box which contains important information and only accepts the response of ;close'.
A modal dialog box is often just called a modal.
zenity   create GUI (GTK) dialog boxes
dialog   create TUI dialog boxes

The dialog element rerpesents a dialog box container semantically.
The dialog element has a boolean attribute open representing whether the dialog should be shown or not.
<form> elements can close a dialog if they have the attribute method="dialog". When such a form is submitted, the dialog closes with its returnValue property set to the value of the button that was used to submit the form.

##### tooltips & popovers

flex-container:⟮h∞;<img src="sm_13gJ2VKho0yW4vEovAMtrjg.jpg">⟯⟮ha;<img src="sm_220px-Mobile_URL_tooltip.png">⟯]]][[[⟮ha;<img src="sm_1sGOKl17J48qhDRMx-foqOw.gif">⟯⟮ha;<img src="sm_2021-06-24--02-37-46-screenshot.png">⟯
⟮c2;Tooltips⟯ and ⟮c2;popovers⟯ are similar in that ⟮c3;they both appear close to the thing that triggered them⟯. 
A ⟮c4;tooltip⟯ is an element/component ⟮c6;with extra text⟯ which ⟮c7;appears⟯ when ⟮c1;when hovering over something⟯ 
A ⟮c5;popover⟯ is a element/component that usually ⟮c8;appears⟯ when ⟮c9;interacting with something⟯ ⟮c10;directly adjacent to that thing⟯. it ⟮c11;is a modal (creates a mode⟯). 
⟮c12;Popper⟯ is a ⟮c13;JS⟯ library for ⟮c14;tooltips⟯/⟮c14;popovers⟯. 

##### list box

⟮h∞;<img src="1-final-listbox-matrix">⟯⟮h∞;<img src="List_example.PNG">⟯⟮h∞;<img src="ctrl-list-boxes-image1.png">⟯
A listbox (or list box) is a UI element that contains a list of values within a box, of which the user can select one or more (depending on the box)

##### corners

###### hot corners

⟮c1;hot corners⟯ are a feature of ⟮c2;mac⟯ and some ⟮c3;DEs on linux⟯ where ⟮c4;moving your mouse into a corner⟯ will ⟮c5;perform a certain action⟯ 

##### dropdown list/menu

⟮h∞;<img src="1y2NriILZC8ujowKW4TWb2Q.png">⟯⟮h∞;<img src="dropdown-example.jpg">⟯⟮h∞;<img src="3-final-sidebyside-dropdowns">⟯
dropdown is short for dropdown list/menu
A dropwdown is a UI element that consists of ⟮c3;a box⟯ and ⟮c3;a downward arrow⟯ that ⟮c4;one can interact with⟯ to ⟮c5;show a list of options⟯, ⟮c6;exactly one of which⟯ can be ⟮c7;selected⟯. Often, larger ones will ⟮c8;scroll⟯.

##### buttons

###### app shortcuts

App shortcuts is the webdev name for the set of actions that are shown e.g. when you long press on a launcher icon on android

###### FAB

flex-container:⟮ha;<img src="sm_fab.jpg">⟯⟮ha;<img src="sm_paste-ea1a89438b76845b5487f1dddea6f955ef559d50.png">⟯
A ⟮c1;FAB⟯ ⟮(c:2;floating action button⟯) is ⟮c3;a button⟯ that ⟮c4;is always visible⟯ and contains ⟮c5;the primary action for the application/view⟯. 
A ⟮c6;FAB⟯ is typically located ⟮c7;in the bottom right⟯, is fairly ⟮c8;large⟯ and ⟮c9;round⟯. 
A ⟮c10;FAB⟯ may ⟮c11;contain more actions⟯ when ⟮c12;pressed⟯. 

##### icons

###### icon fonts

Icon fonts map unicode characters from the private use areas to vectors/images
Icon fonts are most often applied via css classes.
the most common icon font is font awesome.

###### icon packs

An icon pack is a set of aesthetically united icons.
octicons|icons used on github
bootstrap-icons|Icons by/for bootstrap

#### actions

##### window snapping

Window snapping is making windows take up an exact area of the screen (most commonly halves, thirds, corners)
Window snapping is most commonly performed by dragging them to edges/corners, via keyboard shortcuts or other buttons/automatic dialogs.
Windows has had window snapping as of windows 7.
Mac requires custom programs sto achieve window snapping, e.g. Spectacle (now deprecated) or Rectangle

#### platforms

<svg data-qb-2-tld="reactnative.dev" data-qb-domain="reactnative.dev" data-qb-url="https://reactnative.dev/docs/assets/diagram_ios-android-views.svg" viewBox="0 0 1221 828" xmlns="http://www.w3.org/2000/svg"><defs><style>.cls-16{fill:#99d5e7}.cls-3{fill:#d5e2f5}.cls-5{fill:#e9e8e8;mix-blend-mode:multiply}.cls-6{fill:#f29dc4}.cls-29,.cls-7{fill:#fff}.cls-17,.cls-20{font-family:-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'}.cls-10,.cls-12,.cls-17{font-size:28px}.cls-10{fill:#134484}.cls-10,.cls-12{font-family:source-code-pro,Menlo,Monaco,Consolas,Courier New,monospace}.cls-11,.cls-13,.cls-18,.cls-25{fill:none;stroke-miterlimit:10}.cls-11{stroke:#134484}.cls-11,.cls-13{stroke-width:3px}.cls-12,.cls-27{fill:#374d9c}.cls-13{stroke:#374d9c}.cls-14{fill:#71c9e4}.cls-15{fill:#09a5d3}.cls-18{stroke:#99d5e7}.cls-18,.cls-25{stroke-width:2px}.cls-19{fill:#0069ac}.cls-20{font-size:32px}.cls-23{fill:#1f2129}.cls-24{fill:#97aad8}.cls-25{stroke:#d5e2f5}.cls-26{fill:#5971b5}.cls-29{opacity:.7}</style></defs><g style="isolation:isolate"><g data-name="Layer 3" id="Layer_3"><g id="Example"><path d="M347 474h797v354H347z" fill="#99d5e7" opacity=".5"></path><path class="cls-3" d="M44 0h794v354H44z"></path><path d="M309 277h575v245H309z" fill="#e9e8e8"></path><path class="cls-5" d="M309 277h575v245H309z"></path><path class="cls-5" d="M309 277h575v245H309z"></path><path class="cls-6" d="M309 277h575v245H309z"></path><path class="cls-7" d="M369 325.5h452v135H369z"></path><g id="Pouncival"><path d="M527.84 388.44s-13.09 4-18.12 27.17c0 0-5.6-3.18-18.19-2.46-.64 0-1.27.07-1.86.13l-.57.05-.92.1c-.53.05-1.05.1-1.61.17a22.35 22.35 0 00-6.86 2c-5-23.15-18.11-27.17-18.11-27.17-18.12 28.18-3 36.23-6 64.41-1.6 14.89 26.35 15.88 40 15.49 14.15.25 39.84-1.24 38.3-15.53-3.04-28.13 12.1-36.18-6.06-64.36z" fill="#d23c6f" transform="translate(-32 -38)"></path><text font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol'" font-size="50.24" transform="translate(526.99 405.37)">Pouncival</text><circle class="cls-6" cx="477.9" cy="398.14" r="14.36"></circle></g></g><g data-name="iOS views" id="iOS_views"><text class="cls-10" transform="translate(544.05 651.5)">UIView</text><text class="cls-10" transform="translate(396.32 574.93)">UIImageView</text><text class="cls-10" transform="translate(624.8 578.93)">UITextView</text><path class="cls-11" d="M530 640.5l-148.69-.5V461.5M660.05 641.67l148.69-.5v-178.5M463.5 541v-93M696.5 541V424"></path></g><g data-name="Android views" id="Android_views"><text class="cls-12" transform="translate(517.85 156.5)">ViewGroup</text><text class="cls-12" transform="translate(393.13 233.93)">ImageView</text><text class="cls-12" transform="translate(641.04 233.93)">TextView</text><path class="cls-13" d="M463.5 340v-93M696.5 360V243"></path><path class="cls-11" d="M506.62 146.26l-127.69.5v178.5M680.67 145.09l125.69.5v179.5"></path></g></g><g id="ios"><path class="cls-14" d="M586.84 758.15c0 3.44-2.55 6.14-6.69 6.14-4 0-6.54-2.7-6.52-6.14s2.57-6.16 6.61-6.16 6.55 2.61 6.6 6.16zm-13.1 45.18v-35.42h13v35.42zM640.88 778.58c0 15.61-9.38 25.54-24.35 25.54s-23.32-11.28-23.32-24.77c0-14.13 9.26-25.34 24.13-25.34 15.6-.01 23.54 11.57 23.54 24.57zm-33.91.54c0 9.13 4 14.71 10.19 14.71s10-6.09 10-14.84c0-8.35-3.75-14.69-10-14.69-6.22 0-10.16 5.89-10.16 14.82zM648.67 790.41a29.89 29.89 0 0012.58 3c4.45 0 6.65-1.54 6.65-4s-2.18-3.69-7.67-5.57c-8.17-2.89-13.63-7.41-13.63-14.63 0-8.59 7.24-15.18 19.5-15.18a31.62 31.62 0 0113.12 2.49l-2.72 10.39a25.58 25.58 0 00-10.5-2.3c-4 0-6.14 1.46-6.14 3.58 0 2.47 2.58 3.46 8.7 5.75 8.75 3.2 12.65 7.88 12.65 14.63 0 8.39-6.51 15.52-20.68 15.52a34.76 34.76 0 01-14.27-3z" transform="translate(-32 -38)"></path><g id="app"><g id="nav"><path class="cls-7" d="M885 82h315v632H885z"></path><path class="cls-15" d="M892 677h305v68H892z"></path><path class="cls-16" d="M1078.76 738.9c-6.17 0-11.52 1.49-14.21 3.67-.77-1.43-5-2.36-6.43-2.36-2 0 1.31 2.62 1.31 5.24s-3.27 5.24-1.31 5.24c1.44 0 5.66-.94 6.43-2.37 2.69 2.19 8 3.68 14.21 3.68 8.61 0 15.63-2.9 16-6.55-.37-3.65-7.39-6.55-16-6.55zM1178.46 732s-4 1.22-5.47 8.2c0 0-1.69-1-5.49-.74l-1.5.14a6.66 6.66 0 00-2.07.61c-1.52-7-5.47-8.21-5.47-8.21-5.47 8.51-.91 10.94-1.82 19.45-.49 4.49 7.95 4.79 12.08 4.68 4.27.07 12-.38 11.56-4.69-.91-8.5 3.65-10.93-1.82-19.44zM978.31 755a.78.78 0 01-.57-.23s-8.31-8-8.46-8.16-1.34-1.68-1.6-2.11a7.94 7.94 0 01-.7-1.57 5.85 5.85 0 01-.3-1.8 6 6 0 011.64-4.46 6.27 6.27 0 014.56-1.61 5 5 0 011.64.28 6.61 6.61 0 011.56.75c.48.32.9.61 1.24.89a11.94 11.94 0 011 .88 11.94 11.94 0 011-.88c.34-.28.75-.57 1.23-.89a6.8 6.8 0 011.56-.75 5.11 5.11 0 011.65-.28 6.26 6.26 0 014.55 1.61 5.94 5.94 0 011.65 4.46c0 1.92-1 3.86-3 5.85l-8.09 7.79a.81.81 0 01-.57.23" transform="translate(-32 -38)"></path></g><g id="Choupette"><path class="cls-16" d="M994.8 695.53a65.82 65.82 0 01-6.94.86 20.79 20.79 0 004.13-6.48s-1.54 3.07-6.43 4.22a71.14 71.14 0 01.63-8c.67-1.8 2.75-8.13.6-12.53a12.93 12.93 0 01-.29 5.37c-.25-3.69-1.27-8.17-4-14.83a15.37 15.37 0 00-9.72 11.52 38.72 38.72 0 01.1-5.47 25.24 25.24 0 00-2 7.69 43.85 43.85 0 00-4.86 0 25.44 25.44 0 00-2.05-7.78 38.75 38.75 0 01.11 5.47 15.37 15.37 0 00-9.72-11.52c-2.75 6.66-3.77 11.14-4 14.83a13 13 0 01-.28-5.37c-2.16 4.4-.08 10.73.59 12.53a70.94 70.94 0 01.64 8c-4.9-1.15-6.44-4.22-6.44-4.22a21 21 0 004.13 6.48 66.29 66.29 0 01-6.94-.86 33.47 33.47 0 007.4 7.58 15.57 15.57 0 01-6.28-1.95c4.56 5.25 12.58 6.79 18 7.21v.28a71.25 71.25 0 008.75.2c3.36 0 5.81-.25 5.81-.25v-.18c5.42-.42 13.45-2 18-7.22a15.49 15.49 0 01-6.28 2 33.26 33.26 0 007.34-7.58z" transform="translate(-32 -38)"></path><text class="cls-17" transform="translate(972.36 657.03)">Choupette</text></g><g data-name="Mrs Norris" id="Mrs_Norris"><path class="cls-18" d="M970 616h208"></path><path class="cls-15" d="M987 604.42s-4.7 1.45-8 8.71a35.16 35.16 0 012 11.87c0 10-4 18.76-10.06 24 8.07-.05 20.21-1.32 19.42-8.67-1.68-15.72 6.73-20.21-3.36-35.91z" transform="translate(-32 -38)"></path><path class="cls-16" d="M981 625a35.16 35.16 0 00-2-11.87 32.19 32.19 0 00-2.08 6.43s-3.12-1.77-10.14-1.37l-1 .07h-.32l-.51.05-.9.1a12.51 12.51 0 00-3.83 1.11c-2.8-12.9-10.09-15.14-10.09-15.14-10.1 15.7-1.68 20.19-3.37 35.89-.88 8.3 14.69 8.85 22.3 8.63h1.93C977 643.76 981 635 981 625z" transform="translate(-32 -38)"></path><circle class="cls-15" cx="924.5" cy="593.5" r="7.5"></circle><text class="cls-17" transform="translate(972.36 597.03)">Mrs. Norris</text></g><g id="Tuna"><path class="cls-18" d="M970 556h208"></path><path class="cls-19" d="M987 544.42s-7.29 2.24-10.09 15.14c0 0-3.12-1.77-10.14-1.37l-1 .07h-.32l-.51.05-.9.1a12.51 12.51 0 00-3.83 1.11c-2.8-12.9-10.09-15.14-10.09-15.14-10.1 15.7-1.68 20.19-3.37 35.89-.88 8.3 14.69 8.85 22.3 8.63 7.89.14 22.2-.69 21.35-8.65-1.72-15.64 6.69-20.13-3.4-35.83z" transform="translate(-32 -38)"></path><text class="cls-17" transform="translate(972.36 537.03)">Tuna</text></g><g id="Tabby"><path class="cls-18" d="M970 496h208"></path><path class="cls-15" d="M989.52 514a164.53 164.53 0 01-1.62-31.36s-8.19 2.52-11.51 16.89c-.13-.67-16.5-.56-16.63.1-3.32-14.37-11.51-16.9-11.51-16.9a165.73 165.73 0 01-1.61 31.37 12 12 0 008.2 13.37l6.92 3.11a15.57 15.57 0 0013-.12l6.52-3.08a12 12 0 008.24-13.38z" transform="translate(-32 -38)"></path><path class="cls-14" d="M969 506.39s2.37-1.44 2-7.3h-2c.54 2.11 1.11 5.43 0 7.3zM955 513s-2 4.62-1.65 13.87a10.78 10.78 0 001.49.6l1.83.83A26.62 26.62 0 01955 513zM982 513c2.15 5-1.36 12.12-3.52 15.71l2.83-1.33a12.26 12.26 0 001.93-.81C984.93 518.16 982 513 982 513zM965.57 531.72c-1.56-1.08-6.86-5.1-5.73-9.23a12.25 12.25 0 00.14 7.29M959.87 522.39c0-.13.08-.26.13-.39a3.46 3.46 0 00-.13.39zM959.84 522.49v-.1zM976 524l-3.68 7.35a14.88 14.88 0 002.47-.89l1.25-.59A16.69 16.69 0 00976 524zM963 511c-1.8-3-1.08-8.13-.22-11.78-1.76.1-3 .23-3 .41 0-.24-.12-.48-.18-.72-.6 9.7 3.4 12.09 3.4 12.09zM972.7 511.58s4-2.4 3.41-12.18a21.74 21.74 0 00-3.35-.27c.92 3.66 1.84 9.27-.06 12.45zM966.35 506.05c-1.06-1.77-.61-4.82-.1-6.95h-1.88c-.28 5.58 1.98 6.95 1.98 6.95z" transform="translate(-32 -38)"></path><text class="cls-17" transform="translate(972.36 477.03)">Tabby</text></g><g data-name="Rum Tum Tugger" id="Rum_Tum_Tugger"><path class="cls-18" d="M970 436h208"></path><text class="cls-17" transform="translate(972.36 417.03)">Rum Tum Tugger</text><path class="cls-14" d="M994.64 455.79a66.64 66.64 0 01-7 .87 21.07 21.07 0 004.19-6.58s-1.34 2.67-5.47 4a26.94 26.94 0 01-14.36 4.48 3.51 3.51 0 01-1.25 0H972c2.15-.32 7-2.24 13.9-11.86v-.42c.68-1.82 2.79-8.26.6-12.73a13.37 13.37 0 01-.29 5.46c-.25-3.75-1.29-8.3-4.08-15.07a15.63 15.63 0 00-9.88 11.7 39.92 39.92 0 01.11-5.55 25.92 25.92 0 00-2.07 7.81 45.13 45.13 0 00-4.93 0 26 26 0 00-2.08-7.9 38.43 38.43 0 01.11 5.55 15.63 15.63 0 00-9.88-11.7c-2.79 6.77-3.83 11.32-4.08 15.07a13.37 13.37 0 01-.29-5.46 13.23 13.23 0 00-.71 7.74l.39-.38c4.78 10.64 12.74 15 12.74 15-7.32 2.24-11.38.44-13.63-2.34a8.65 8.65 0 01-4.07-3.45 21.07 21.07 0 004.19 6.58 66.64 66.64 0 01-7-.87 33.9 33.9 0 007.52 7.7 15.82 15.82 0 01-6.38-2 18.43 18.43 0 006.81 4.76c8.35-.78 10.93-3.26 11.65-4.28l.26-.43a2 2 0 01-.26.43 25.07 25.07 0 01-4.76 6.28 81 81 0 0013.44 1.08 66.71 66.71 0 007.69-.62 13.59 13.59 0 01-3.5-7.5c4.18 8.4 16.2 3.35 16.2 3.35l-.2.31a16.54 16.54 0 004-3.32 15.82 15.82 0 01-6.38 2 33.9 33.9 0 007.5-7.71z" transform="translate(-32 -38)"></path><path class="cls-15" d="M961.56 455.82s-8-4.32-12.74-15l-.39.38a26.67 26.67 0 001.32 5 70.93 70.93 0 01.64 8.09 12.86 12.86 0 01-2.46-.84c2.25 2.81 6.31 4.61 13.63 2.37zM960.63 461.92c-.72 1-3.3 3.5-11.65 4.28a32.74 32.74 0 006.89 2 25.07 25.07 0 004.76-6.28z" transform="translate(-32 -38)"></path><path class="cls-16" d="M960.63 461.92a2 2 0 00.26-.43zM972 458.56h-1.25a3.51 3.51 0 001.25 0z" transform="translate(-32 -38)"></path><path class="cls-15" d="M972 458.56a26.94 26.94 0 0014.36-4.49c-.34.11-.69.21-1.06.3a66.9 66.9 0 01.6-7.67c-6.96 9.62-11.8 11.54-13.9 11.86z" transform="translate(-32 -38)"></path><path class="cls-16" d="M989.5 464.82a31.69 31.69 0 01-12.5 3.84" transform="translate(-32 -38)"></path><path class="cls-15" d="M973.5 461.16a13.59 13.59 0 003.5 7.5 31.69 31.69 0 0012.5-3.84l.2-.31s-12.02 5.05-16.2-3.35z" transform="translate(-32 -38)"></path></g><g data-name="Pouncival" id="Pouncival-2"><path class="cls-18" d="M970 376h208"></path><path class="cls-15" d="M987 364.42s-7.29 2.24-10.09 15.14c0 0-3.12-1.77-10.14-1.37l-1 .07H964.94l-.9.1a12.51 12.51 0 00-3.83 1.11c-2.8-12.9-10.09-15.14-10.09-15.14-10.1 15.7-1.68 20.19-3.37 35.89-.88 8.3 14.69 8.85 22.3 8.63 7.89.14 22.2-.69 21.35-8.65-1.72-15.59 6.69-20.08-3.4-35.78z" transform="translate(-32 -38)"></path><text class="cls-17" transform="translate(972.36 357.03)">Pouncival</text><circle class="cls-16" cx="945" cy="353" r="8"></circle></g><g id="Spot"><path class="cls-18" d="M970 316h208"></path><text class="cls-17" transform="translate(972.36 297.03)">Spot</text><path class="cls-14" d="M989.7 334.05a165.62 165.62 0 01-1.61-31.36s-8.19 2.52-11.51 16.89c-.13-.67-16.51-.56-16.63.1-3.32-14.37-11.51-16.9-11.51-16.9a164.7 164.7 0 01-1.62 31.37 12 12 0 008.18 13.37l6.92 3.11a15.55 15.55 0 0013-.12l6.53-3.08a12 12 0 008.25-13.38z" transform="translate(-32 -38)"></path></g><g id="Maru"><path class="cls-18" d="M970 256h208"></path><text class="cls-17" transform="translate(972.36 237.03)">Maru</text><path class="cls-14" d="M985 272a11.9 11.9 0 015.23 1.21c.74-10.5 5.18-15.8-3.24-28.89 0 0-7.29 2.24-10.09 15.14 0 0-3.12-1.77-10.14-1.37l-.81.06c-.51 10.51-7.89 18.85-17 18.85a15.76 15.76 0 01-2.07-.16c0 1.07-.09 2.2-.22 3.4-.88 8.29 14.69 8.85 22.3 8.63 1.49 0 3.2 0 5-.07a11.83 11.83 0 01-1-4.8A12 12 0 01985 272z" transform="translate(-32 -38)"></path><path class="cls-15" d="M990.36 280.21a38.82 38.82 0 01-.13-7A12 12 0 00974 288.8c7.75-.36 17.05-2.12 16.36-8.59zM966 258.15h-.54l-.51.06-.9.09a12.65 12.65 0 00-3.83 1.12c-2.8-12.9-10.09-15.15-10.09-15.15-9.33 14.51-2.86 19.45-3.15 32.5a15.76 15.76 0 002.02.23c9.06 0 16.44-8.34 17-18.85z" transform="translate(-32 -38)"></path></g><g id="header"><path class="cls-16" d="M888 85h312v104H888z"></path><text class="cls-20" transform="translate(918.19 163.12)">Cat Cafe Menu</text></g><circle cx="1147.5" cy="715.5" fill="#a21732" r="4.5"></circle></g><g id="device"><path d="M1197.9 100H955.1c-30.43 0-55.1 26.67-55.1 57.1v586.8a55.1 55.1 0 0055.1 55.1h242.8a55.1 55.1 0 0055.1-55.1V157.1c0-30.43-24.67-57.1-55.1-57.1zm26.84 643.79a29.21 29.21 0 01-29.21 29.21h-237a30.69 30.69 0 01-30.68-30.69v-588a29.34 29.34 0 0129.3-29.31h30.12a5.43 5.43 0 015.43 5.43v.57a18.73 18.73 0 0018.74 18.73h128.16a18.2 18.2 0 0018.2-18.2v.84a7.37 7.37 0 017.37-7.37h28.93a30.64 30.64 0 0130.64 30.64z" fill="#134484" transform="translate(-32 -38)"></path><rect class="cls-19" height="7.41" rx="3" width="42" x="1022" y="90.29"></rect><circle class="cls-23" cx="1076.5" cy="93.5" r="4.5"></circle><circle class="cls-14" cx="1076" cy="93" r="2"></circle></g></g><g id="Android"><g data-name="app" id="app-2"><path class="cls-7" d="M9 77h300v639H9z"></path><g data-name="Choupette" id="Choupette-2"><path class="cls-24" d="M107.8 727.53a65.82 65.82 0 01-6.94.86 20.79 20.79 0 004.13-6.48s-1.54 3.07-6.43 4.22a71.14 71.14 0 01.63-8c.67-1.8 2.75-8.13.6-12.53a12.93 12.93 0 01-.29 5.4c-.25-3.69-1.27-8.17-4-14.83a15.37 15.37 0 00-9.72 11.52 38.72 38.72 0 01.1-5.47 25.24 25.24 0 00-2 7.69A43.85 43.85 0 0079 710a25.44 25.44 0 00-2-7.78 38.75 38.75 0 01.11 5.47 15.37 15.37 0 00-9.72-11.52c-2.75 6.66-3.77 11.14-4 14.83a13 13 0 01-.28-5.37c-2.16 4.4-.08 10.73.59 12.53a70.94 70.94 0 01.64 8c-4.9-1.15-6.44-4.22-6.44-4.22a21 21 0 004.13 6.48 66.29 66.29 0 01-6.94-.86 33.47 33.47 0 007.4 7.58 15.57 15.57 0 01-6.28-1.95c4.56 5.25 12.58 6.79 18 7.21v.28a71.25 71.25 0 008.75.2c3.36 0 5.81-.25 5.81-.25v-.18c5.42-.42 13.45-2 18-7.22a15.49 15.49 0 01-6.28 2 33.26 33.26 0 007.31-7.7z" transform="translate(-32 -38)"></path><text class="cls-17" transform="translate(85.36 689.03)">Choupette</text></g><g data-name="Mrs Norris" id="Mrs_Norris-2"><path class="cls-25" d="M83 648h208"></path><path class="cls-26" d="M100 636.42s-4.7 1.45-8 8.71A35.16 35.16 0 0194 657c0 10-4 18.76-10.06 24 8.07-.05 20.21-1.32 19.42-8.67-1.68-15.72 6.73-20.21-3.36-35.91z" transform="translate(-32 -38)"></path><path class="cls-24" d="M94 657a35.16 35.16 0 00-2-11.87 32.19 32.19 0 00-2.08 6.43s-3.12-1.77-10.14-1.37l-1 .07h-.32l-.51.05-.9.1a12.51 12.51 0 00-3.83 1.11c-2.8-12.9-10.09-15.14-10.09-15.14-10.1 15.7-1.68 20.19-3.37 35.89-.88 8.3 14.69 8.85 22.3 8.63h1.93C90 675.76 94 667 94 657z" transform="translate(-32 -38)"></path><circle class="cls-26" cx="37.5" cy="625.5" r="7.5"></circle><text class="cls-17" transform="translate(85.36 629.03)">Mrs. Norris</text></g><g data-name="Tuna" id="Tuna-2"><path class="cls-25" d="M83 588h208"></path><path class="cls-27" d="M100 576.42s-7.29 2.24-10.09 15.14c0 0-3.12-1.77-10.14-1.37l-1 .07h-.32l-.51.05-.9.1a12.51 12.51 0 00-3.83 1.11c-2.8-12.9-10.09-15.14-10.09-15.14-10.1 15.7-1.68 20.19-3.37 35.89-.88 8.3 14.69 8.85 22.3 8.63 7.89.14 22.2-.69 21.35-8.65-1.72-15.64 6.69-20.13-3.4-35.83z" transform="translate(-32 -38)"></path><text class="cls-17" transform="translate(85.36 569.03)">Tuna</text></g><g data-name="Tabby" id="Tabby-2"><path class="cls-25" d="M83 528h208"></path><path class="cls-26" d="M102.52 546a164.53 164.53 0 01-1.62-31.36s-8.19 2.52-11.51 16.89c-.13-.67-16.5-.56-16.63.1-3.32-14.37-11.51-16.9-11.51-16.9a165.73 165.73 0 01-1.61 31.37 12 12 0 008.2 13.37l6.92 3.11a15.57 15.57 0 0013-.12l6.52-3.08a12 12 0 008.24-13.38z" transform="translate(-32 -38)"></path><path class="cls-24" d="M82 538.39s2.37-1.44 2-7.3h-2c.54 2.11 1.11 5.43 0 7.3zM68 545s-2 4.62-1.65 13.87a10.78 10.78 0 001.49.6l1.83.83A26.62 26.62 0 0168 545zM95 545c2.15 5-1.36 12.12-3.52 15.71l2.83-1.33a12.26 12.26 0 001.93-.81C97.93 550.16 95 545 95 545zM78.57 563.72c-1.56-1.08-6.86-5.1-5.73-9.23a12.25 12.25 0 00.14 7.29" transform="translate(-32 -38)"></path><path class="cls-14" d="M72.87 554.39c0-.13.08-.26.13-.39a3.46 3.46 0 00-.13.39zM72.84 554.49v-.1z" transform="translate(-32 -38)"></path><path class="cls-24" d="M89 556l-3.68 7.35a14.88 14.88 0 002.47-.89l1.25-.59A16.69 16.69 0 0089 556zM76 543c-1.8-3-1.08-8.13-.22-11.78-1.76.1-3 .23-3 .41-.05-.24-.12-.48-.18-.72C72 540.61 76 543 76 543zM85.7 543.58s4-2.4 3.41-12.18a21.74 21.74 0 00-3.35-.27c.92 3.66 1.84 9.27-.06 12.45zM79.35 538.05c-1.06-1.77-.61-4.82-.1-6.95h-1.88c-.28 5.58 1.98 6.95 1.98 6.95z" transform="translate(-32 -38)"></path><text class="cls-17" transform="translate(85.36 509.03)">Tabby</text></g><g data-name="Rum Tum Tugger" id="Rum_Tum_Tugger-2"><path class="cls-25" d="M83 468h208"></path><text class="cls-17" transform="translate(85.36 449.03)">Rum Tum Tugger</text><path class="cls-24" d="M107.64 487.79a66.64 66.64 0 01-7 .87 21.07 21.07 0 004.19-6.58s-1.34 2.67-5.47 4A26.94 26.94 0 0185 490.56a3.51 3.51 0 01-1.25 0H85c2.15-.32 7-2.24 13.9-11.86 0-.14 0-.28.05-.42.68-1.82 2.79-8.26.6-12.73a13.37 13.37 0 01-.29 5.46c-.25-3.75-1.29-8.3-4.08-15.07a15.63 15.63 0 00-9.88 11.7 39.92 39.92 0 01.11-5.55 25.92 25.92 0 00-2.07 7.81 45.13 45.13 0 00-4.93 0 26 26 0 00-2.08-7.9 38.43 38.43 0 01.11 5.55 15.63 15.63 0 00-9.88-11.7c-2.79 6.77-3.83 11.32-4.08 15.07a13.37 13.37 0 01-.29-5.46 13.23 13.23 0 00-.71 7.74l.39-.38c4.78 10.64 12.74 15 12.74 15-7.32 2.24-11.38.44-13.63-2.34a8.65 8.65 0 01-4.12-3.48 21.07 21.07 0 004.19 6.58 66.64 66.64 0 01-7-.87 33.9 33.9 0 007.52 7.7 15.82 15.82 0 01-6.38-2A18.43 18.43 0 0062 498.2c8.35-.78 10.93-3.26 11.65-4.28l.26-.43a2 2 0 01-.26.43 25.07 25.07 0 01-4.76 6.28 81 81 0 0013.44 1.08 66.71 66.71 0 007.69-.62 13.59 13.59 0 01-3.5-7.5c4.18 8.4 16.2 3.35 16.2 3.35l-.2.31a16.54 16.54 0 004-3.32 15.82 15.82 0 01-6.38 2 33.9 33.9 0 007.5-7.71z" transform="translate(-32 -38)"></path><path class="cls-26" d="M74.56 487.82s-8-4.32-12.74-15l-.39.38a26.67 26.67 0 001.32 5 70.93 70.93 0 01.64 8.09 12.86 12.86 0 01-2.46-.84c2.25 2.81 6.31 4.61 13.63 2.37zM73.63 493.92c-.72 1-3.3 3.5-11.65 4.28a32.74 32.74 0 006.89 2 25.07 25.07 0 004.76-6.28z" transform="translate(-32 -38)"></path><path class="cls-16" d="M73.63 493.92a2 2 0 00.26-.43zM85 490.56h-1.25a3.51 3.51 0 001.25 0z" transform="translate(-32 -38)"></path><path class="cls-26" d="M85 490.56a26.94 26.94 0 0014.36-4.49c-.34.11-.69.21-1.06.3a66.9 66.9 0 01.6-7.67c-6.96 9.62-11.8 11.54-13.9 11.86z" transform="translate(-32 -38)"></path><path class="cls-16" d="M102.5 496.82a31.69 31.69 0 01-12.5 3.84" transform="translate(-32 -38)"></path><path class="cls-26" d="M86.5 493.16a13.59 13.59 0 003.5 7.5 31.69 31.69 0 0012.5-3.84l.2-.31s-12.02 5.05-16.2-3.35z" transform="translate(-32 -38)"></path></g><g data-name="Pouncival" id="Pouncival-3"><path class="cls-25" d="M83 408h208"></path><path class="cls-26" d="M100 396.42s-7.29 2.24-10.09 15.14c0 0-3.12-1.77-10.14-1.37l-1 .07H77.94l-.9.1a12.51 12.51 0 00-3.83 1.11c-2.8-12.9-10.09-15.14-10.09-15.14-10.1 15.7-1.68 20.19-3.37 35.89-.88 8.3 14.69 8.85 22.3 8.63 7.89.14 22.2-.69 21.35-8.65-1.72-15.59 6.69-20.08-3.4-35.78z" transform="translate(-32 -38)"></path><text class="cls-17" transform="translate(85.36 389.03)">Pouncival</text><circle class="cls-24" cx="58" cy="385" r="8"></circle></g><g data-name="Spot" id="Spot-2"><path class="cls-25" d="M83 348h208"></path><text class="cls-17" transform="translate(85.36 329.03)">Spot</text><path class="cls-24" d="M102.7 366.05a165.62 165.62 0 01-1.61-31.36s-8.19 2.52-11.51 16.89c-.13-.67-16.51-.56-16.63.1-3.32-14.37-11.51-16.9-11.51-16.9a164.7 164.7 0 01-1.62 31.37A12 12 0 0068 379.52l7 3.11a15.55 15.55 0 0013-.12l6.53-3.08a12 12 0 008.17-13.38z" transform="translate(-32 -38)"></path></g><g data-name="Maru" id="Maru-2"><path class="cls-25" d="M83 288h208"></path><text class="cls-17" transform="translate(85.36 269.03)">Maru</text><path class="cls-24" d="M98 304a11.9 11.9 0 015.23 1.21c.74-10.5 5.18-15.8-3.24-28.89 0 0-7.29 2.24-10.09 15.14 0 0-3.12-1.77-10.14-1.37l-.81.06C78.44 300.66 71.06 309 62 309a15.76 15.76 0 01-2.07-.16c0 1.07-.09 2.2-.22 3.4-.88 8.29 14.69 8.85 22.3 8.63 1.49 0 3.2 0 5-.07a11.83 11.83 0 01-1-4.8A12 12 0 0198 304z" transform="translate(-32 -38)"></path><path class="cls-26" d="M103.36 312.21a38.82 38.82 0 01-.13-7A12 12 0 0087 320.8c7.75-.36 17.05-2.12 16.36-8.59zM79 290.15h-.54l-.51.06-.9.09a12.65 12.65 0 00-3.83 1.12c-2.8-12.9-10.09-15.15-10.09-15.15-9.33 14.51-2.86 19.45-3.15 32.5A15.76 15.76 0 0062 309c9.06 0 16.44-8.34 17-18.85z" transform="translate(-32 -38)"></path></g><g data-name="header" id="header-2"><path class="cls-3" d="M19.48 76h276.37A13.15 13.15 0 01309 89.15V180H5V90.48A14.48 14.48 0 0119.48 76z"></path><text class="cls-20" transform="translate(31.19 154.12)">Cat Cafe Menu</text></g><g data-name="nav" id="nav-2"><path class="cls-26" d="M7.18 177H310v46H5v-43.82A2.18 2.18 0 017.18 177z"></path><path class="cls-3" d="M191.76 232.9c-6.17 0-11.52 1.49-14.21 3.67-.77-1.43-5-2.36-6.43-2.36-2 0 1.31 2.62 1.31 5.24s-3.27 5.24-1.31 5.24c1.44 0 5.66-.94 6.43-2.37 2.69 2.19 8 3.68 14.21 3.68 8.61 0 15.63-2.9 16-6.55-.37-3.65-7.39-6.55-16-6.55zM291.46 226s-3.95 1.22-5.47 8.2c0 0-1.69-1-5.49-.74l-1.5.14a6.66 6.66 0 00-2.07.61c-1.52-7-5.47-8.21-5.47-8.21-5.47 8.51-.91 10.94-1.82 19.45-.49 4.49 7.95 4.79 12.08 4.68 4.27.07 12-.38 11.56-4.69-.91-8.5 3.65-10.93-1.82-19.44z" transform="translate(-32 -38)"></path><circle cx="260.5" cy="209.5" fill="#ee76ab" r="4.5"></circle><path class="cls-3" d="M91.31 249a.78.78 0 01-.57-.23s-8.31-8-8.46-8.16-1.34-1.68-1.6-2.11a7.94 7.94 0 01-.7-1.57 5.85 5.85 0 01-.3-1.8 6 6 0 011.64-4.46 6.27 6.27 0 014.56-1.61 5 5 0 011.64.28 6.61 6.61 0 011.56.75c.48.32.9.61 1.24.89a11.94 11.94 0 011 .88 11.94 11.94 0 011-.88c.34-.28.75-.57 1.23-.89a6.8 6.8 0 011.56-.75 5.11 5.11 0 011.65-.28 6.26 6.26 0 014.55 1.61 5.94 5.94 0 011.65 4.46c0 1.92-1 3.86-3 5.85l-8.09 7.79a.81.81 0 01-.57.23" transform="translate(-32 -38)"></path></g></g><g data-name="device" id="device-2"><path class="cls-27" d="M314.08 104H66.92A34.91 34.91 0 0032 138.92v629.16A34.91 34.91 0 0066.92 803h247.16A34.91 34.91 0 00349 768.08V138.92A34.91 34.91 0 00314.08 104zM336 735.6a18.4 18.4 0 01-18.4 18.4H64.85A19.85 19.85 0 0145 734.15V139.67A23.67 23.67 0 0168.67 116h60.13a9.2 9.2 0 019.2 9.2v7a19.75 19.75 0 0019.75 19.8h64A19.23 19.23 0 00241 132.77v-7.63a9.14 9.14 0 019.14-9.14h62.32A23.54 23.54 0 01336 139.54z" transform="translate(-32 -38)"></path><rect class="cls-26" height="6" rx="3" width="93" x="111" y="738"></rect><rect class="cls-26" height="6" rx="3" width="34" x="140" y="97"></rect><circle class="cls-23" cx="123.5" cy="95.5" r="6.5"></circle><circle class="cls-23" cx="190.5" cy="95.5" r="4.5"></circle><circle class="cls-24" cx="122" cy="94" r="3"></circle><circle class="cls-24" cx="190" cy="95" r="2"></circle></g><path class="cls-24" d="M507.91 114.08l-2.73 11.25h-13.45l14.08-48.53h17.32l14.47 48.53h-14l-3.1-11.25zm10.77-9.59l-2.25-8.73c-.74-2.74-1.66-6.7-2.41-9.56h-.15c-.72 2.86-1.44 6.86-2.14 9.61l-2.09 8.68zM543.32 102c0-4.72-.15-8.79-.29-12.06h11.2l.57 4.51h.26a12.84 12.84 0 0110.62-5.31c8.24 0 12.76 5.64 12.76 15.32v20.9h-13V106c0-4.06-1.4-6.48-4.5-6.48a4.52 4.52 0 00-4.26 3.12 7 7 0 00-.36 2.61v20h-13zM622.34 74.21v39.92c0 4.4.15 8.86.29 11.2h-11.52l-.52-4.79h-.15c-2.34 4-6.64 5.58-10.69 5.58-8.26 0-15.09-7.14-15.09-18.27 0-11.91 7.48-18.74 15.83-18.74 3.92 0 7.14 1.14 8.73 3.42h.14V74.21zm-13 31a10.58 10.58 0 00-.09-1.68 5.28 5.28 0 00-5.11-4.53c-4.35 0-6.3 3.89-6.3 8.54 0 5.43 2.67 8.26 6.25 8.26a5.11 5.11 0 005.07-4.23 10.67 10.67 0 00.2-2.38zM630.37 101.86c0-5.64-.09-9-.29-12h11.09l.46 6.39h.29a10.18 10.18 0 019.44-7.19 10.3 10.3 0 012.59.22v12.19a14.91 14.91 0 00-3.31-.36c-3.84 0-6.41 1.6-7.1 4.46a12 12 0 00-.18 2.21v17.5h-13zM695.55 107.26c0 12.87-9.2 18.86-19.12 18.86-10.6 0-18.83-6.73-18.83-18.25 0-11.25 7.43-18.76 19.5-18.76 11.1 0 18.45 7.49 18.45 18.15zm-24.55.34c0 5.31 1.75 9.36 5.76 9.36 3.5 0 5.4-3.67 5.4-9.36 0-4.9-1.58-9.32-5.43-9.32-4.28 0-5.73 4.72-5.73 9.32zM714.89 80.15c0 3.44-2.55 6.14-6.69 6.14-4 0-6.54-2.7-6.52-6.14s2.57-6.15 6.61-6.15 6.55 2.6 6.6 6.15zm-13.1 45.18V89.91h13v35.42zM758.71 74.21v39.92c0 4.4.14 8.86.29 11.2h-11.53l-.52-4.79h-.14c-2.34 4-6.64 5.58-10.69 5.58-8.27 0-15.09-7.14-15.09-18.27 0-11.91 7.47-18.74 15.82-18.74 3.93 0 7.15 1.14 8.73 3.42h.15V74.21zm-13 31a10.58 10.58 0 00-.09-1.68 5.28 5.28 0 00-5.11-4.53c-4.36 0-6.3 3.89-6.3 8.54 0 5.43 2.66 8.26 6.24 8.26a5.12 5.12 0 005.08-4.23 11.3 11.3 0 00.2-2.38z" transform="translate(-32 -38)"></path></g><g data-name="Layer 4" id="Layer_4"><path class="cls-29" d="M291 348l78-23v135l-78-52V308M821 325l88-11v64l-88 82V325z"></path></g></g></svg>
In ⟮c1;mobile/app⟯ development, a ⟮c2;view⟯ is ⟮c3;the basic building block of UI⟯. They can be ⟮c4;nested⟯, it is views ⟮c4;all the way down⟯.

## user experience

user experience is (the design of) the experience of an user interacting with something.

### waiting

Waiting is less frustrating when there is an indication of progress and transparancy of how the progress relates to the whole (e.g. Kayak.com showing cheaper prices trundling in).
Jason Farman (Delayed Response) argues that what really matters about if we leave a waiting situation satisified is if we waited less than we expected, rather than the whole wait time.
The fact that our expectations are the thing that determines our assesment of waiting and progress bars has given rise to the progress bar that starts out slow and then speeds up towards the end (no matter if this is a correct interpretation)

## usability

Something that has high usability is usable safely, effectively, easily.
Usability engingeering is a field that is concerned with the usability of things, especially with human-computer interfaces.
Perhaps the most well-known advocate/export for usability is Nielsen.
A think-aloud protocol has users do a certain task and say whatever comes to mind as they are doing them.

### responsive design

responsive (web) design is (esp. web) design that adjusts to work ⟮c1;on a variety of different devices⟯
progressive enhancement is the (esp. web) design philosophy that emphasizes  creating a good-enough base level  and ⟮c1;then building on top of that for other targets⟯
Graceful degradation is the (esp. web) design philosophy that emphasizes building for ones ideal targets but ⟮c1;falls back on a good-enough experience⟯
progressive enhancement <-> graceful degradation
Mobile first is building the mobile site first (and expanding on that for desktop users)

## computer graphcis

A ⟮c1;FOUC (Flash of unstyled content)⟯ is when a ⟮c3;page (or some content)⟯ is briefly visible with ⟮c2;no styling/browser default styling⟯

### color

A ⟮c17;color model⟯ is a model of how ⟮c18;a set of channels⟯ ⟮c19;make up a color⟯. 
A ⟮c20;color space⟯ is a ⟮c21;color model⟯ ⟮c22;associated with⟯ ⟮c23;how the results are to be interpreted (viewing conditions etc.⟯) 
A ⟮c24;gamut⟯ is ⟮c25;a complete/'adjacent'⟯ ⟮c26;subset of a colors⟯. 
Often a ⟮c27;gamut⟯ refers specifically to ⟮c28;the subsset of colors⟯ that ⟮c29;can be displayed or represented by something⟯. 

⟮c30;Each pixel⟯ in a ⟮c31;color image⟯ is made up of ⟮c32;two or more channels⟯. 
⟮c33;Each channel⟯ in an image/pixel is ⟮c34;associated with a color⟯. 
⟮c35;channels⟯ of color may also be called ⟮c36;components⟯. 
⟮c37;A channel⟯ is ⟮c38;the value of a color⟯ for ⟮c39;a specific pixel, and thus the whole image⟯. 
⟮c41;Combining⟯ ⟮c40;the color channels⟯ of a pixel (and thus the image) ends you up with ⟮c42;the color of the pixel/image⟯. 

In the ⟮c43;RGB⟯ ⟮c44;color model⟯ a thingy has the ⟮c45;three⟯ ⟮c46;channels⟯ ⟮c47;red, green and blue⟯. 
In the ⟮c48;CMY⟯ ⟮c49;color model⟯ a thingy has the ⟮c50;three⟯ ⟮c51;channels⟯ ⟮c52;cyan, magenta and yellow⟯. 
The ⟮c53;CMYK⟯ ⟮c54;color model⟯ ⟮c56;adds a channe⟯l of ⟮c55;key⟯ (= ⟮c55;black⟯). 
The ⟮c57;key channel⟯ is ⟮c58;generally added to CMYK⟯ because ⟮c59;black ink is cheaper,⟯ and ⟮c60;producing black by mixing cyan, magenta and yellow is in practice quite hard⟯. 
The ⟮c61;CMY⟯ and ⟮c62;RGB⟯ ⟮c63;color models⟯ are ⟮c64;the most common color models in use today⟯, in part because ⟮c65;they correspond roughly to human tricromatic color vision⟯. 
An ⟮c66;additive color model⟯ is one where ⟮c67;colors⟯ ⟮c68;added together⟯ produce ⟮c69;progressively lighter colors⟯. 
⟮c70;Light emission⟯ follows ⟮c71;an addtive⟯ color model. 
A ⟮c72;subtractive color model⟯ is one where ⟮c73;colors⟯ ⟮c74;added together⟯ produce ⟮c75;progressively darker colors⟯. 
⟮c76;Light absorption⟯ follows ⟮c77;a subtractive⟯ color model. 
⟮c78;RGB⟯, being ⟮c79;an additive color model⟯, is mainly used for ⟮c80;displays and other places where light is emitted⟯. 
⟮c81;CMYK⟯ being ⟮c82;a subtractive color model⟯ is mainly used for ⟮c83;printing and other places where light is absorbed.⟯ 
⟮c84;RYB⟯ is an alternative ⟮c85;subtractive⟯ ⟮c86;color model⟯ still used in the arts. It can however not ⟮c87;create black⟯. 

⟮c88;Color depth⟯ indicates ⟮c89;the amount of bits used⟯ for ⟮c90;color⟯ ⟮c91;per pixel⟯ or ⟮c92;per channel⟯ (since ⟮c93;these rarely overlap⟯, there is no ⟮c93;confusion⟯.) 
⟮c94;Color depth⟯ is more rarely also called ⟮c95;bit depth⟯. 
Today, the ⟮c96;most common⟯ ⟮c97;color depth⟯ is ⟮c98;8 bit per channel⟯. 

the ⟮c99;common color depth of 8 bit per channe⟯l means values from ⟮c100;0 - 255⟯ / ⟮c101;00 to ff⟯. 
Most colors are specified by ⟮c102;specifying the color model⟯ and then ⟮c103;the components⟯ (e.g. ⟮c104;RGB 0, 120, 58⟯). 
⟮c105;RGB colors⟯ are also often displayed as ⟮c106;a hex triplet,⟯ which is generally ⟮c107;prefixed by a # character⟯. 
In certain places, e.g. HTML/CSS, hex colors ⟮c226;with reduplicated digits only (e.g. 663399⟯) can ⟮c227;be shortened to three-digit variants (e.g. 639⟯) 

<br>---<br> 
⟮c108;A primary color⟯ is ⟮c109;a member of⟯ a ⟮c110;set of colors⟯ (all ⟮c111;defined to be primary⟯) that ⟮c112;can be combined in varying amounts⟯ to ⟮c113;create a gamut of colors⟯. 

⟮c114;CMY⟯ and ⟮c114;RGB⟯ are ⟮c115;complementary⟯ in such a way that ⟮c116;C+R⟯, ⟮c116;M+G⟯, and ⟮c116;Y+B⟯ are ⟮c117;all 100% (255 with an 8 bit color depth⟯). To ⟮c118;get one channel⟯, ⟮c119;the other is subtracted from 100%⟯. 
To get ⟮c120;the K channel⟯ from ⟮c120;CMY⟯: K = ⟮c121;min(C, M, Y⟯) 
After ⟮c122;getting the K channel⟯, to ⟮c123;convert CMY to CMYK⟯: ⟮c125;Channel_new⟯ =&nbsp;&nbsp;<div style="width:fit-content; display:inline-block; text-align: center"><div style="border-bottom: 0.1em solid currentcolor">⟮c124;Channel - K⟯</div><div>⟮c125;1 - K⟯</div></div> 

⟮c129;Hue⟯ is what we might call ⟮c130;<i>color</i>⟯&nbsp;color. 
⟮c131;Hue⟯ is what ⟮c132;most languages⟯ ⟮c133;consider primary⟯ about ⟮c134;color⟯, with ⟮c135;other attributes such as light/dark/muddy/vivid/pastel⟯ ⟮c136;attached later⟯. 
⟮c137;Hue⟯ is often ⟮c138;generated from⟯ ⟮c139;RGB⟯, e.g. for ⟮c140;use in HSL &amp; HSV/HSB⟯. 
If ⟮c141;Hue⟯ is ⟮c142;generated⟯ from ⟮c142;RGB⟯ for ⟮c142;HSL/HSV⟯, it is specified in ⟮c143;a degree from 0 to 360 deg⟯ 


if Hue is specified in a degree measurement
degree|color
⟮c144;0deg/360deg⟯|⟮c145;red⟯
⟮c146;120deg⟯|⟮c147;green⟯
⟮c148;240deg⟯|⟮c149;blue⟯


Commonly, ⟮c156;saturation⟯ ≈ ⟮c157;chroma⟯ refers to ⟮c158;the distance⟯ of ⟮c159;a color⟯ ⟮c158;from⟯ t⟮c160;he white-gray-black spectrum⟯. 

⟮c161;Lighntess⟯ attempts to model ⟮c162;adding white/black paint⟯ to ⟮c163;make the color white/black⟯. 
⟮c164;100%⟯ ⟮c166;lightness⟯ is ⟮c165;white⟯ for ⟮c165;any saturation/hue⟯. 
⟮c167;50%⟯ ⟮c171;lightness⟯ ⟮c168;allows for fully saturated colors⟯. 
⟮c169;0%⟯ ⟮c172;lightness⟯ is ⟮c170;black⟯ for ⟮c170;any saturation/hue⟯ 
⟮c173;Value/brightness⟯ attempts to model ⟮c174;how shining more/less light on a thing⟯ will ⟮c175;change the color⟯. 
⟮c176;100%⟯ ⟮c181;value/brightness⟯ ⟮c177;allows for fully saturated colors.⟯ 
⟮c178;0%⟯ ⟮c179;lightness⟯ is ⟮c180;black⟯ for ⟮c180;any saturation/hue⟯. 
⟮c151;tint⟯|⟮c152;mixture of a color with white⟯
⟮c153;tone⟯|⟮c154;mixture of a color with gray⟯
⟮c155;shade⟯|⟮c150;mixture of a color with black⟯


⟮c182;HSL⟯ = ⟮c186;hue, saturation, lightness⟯. 
⟮c183;HSV⟯ = ⟮c187;hue, saturation, value⟯ ⟮c190;is the same as⟯ ⟮c188;HSB⟯ = ⟮c189;hue, saturation, brightness.⟯ 
⟮c184;HSL⟯ and ⟮c184;HSV/HSB⟯ are alternate ⟮c191;color models⟯, which are both ⟮c192;variants of/generated from⟯ ⟮c193;the RGB color model⟯. 
⟮c185;HSL⟯ and ⟮c185;HSV⟯ were created because ⟮c194;they are more natural to how we as humans understand color.⟯ 
⟮sa;While ⟮c195;RGB⟯ and ⟮c195;CMY⟯ are most naturally represented as ⟮c196;cubes⟯⟯, ⟮sb;⟮c197;HSL⟯ and ⟮c197;HSV/HSB⟯ are commonly represented as ⟮c198;cylinders⟯⟯. 
Since ⟮c199;the top and bottom⟯ of ⟮c200;a ⟮s202;HSL⟯ cylinder⟯ ⟮c201;all approach the same color (white and black respectively⟯), ⟮sb;⟮c202;HSL⟯ may also ⟮c203;be represented as a bicone⟯⟯. 
Since the ⟮c204;bottom⟯ of ⟮c205;a HSV/HSB cylinder⟯ ⟮c206;approaches the same color (black⟯), ⟮sb;HSV/HSB may more naturally be represented as a cone.⟯ 
⟮c207;HSL⟯ and ⟮c208;HSV/HSB⟯ both have ⟮s211-212;⟮c209;hue⟯ as ⟮c210;the degree⟯⟯, and ⟮s209-210;⟮c211;saturation⟯ as ⟮c212;the radius⟯.⟯ 
⟮c213;HSL⟯ has ⟮c214;lightness⟯ as ⟮c215;the height.⟯ 
⟮c216;HSV/HSB⟯ has v⟮c217;alue/brightness⟯ as ⟮c218;the height⟯.  
both ⟮c219;HSL⟯ and ⟮c219;HSV/B⟯ have the problem that ⟮c220;changing⟯ the ⟮c221;saturation⟯ and ⟮c223;to a certain extent⟯ ⟮c222;the hue⟯ ⟮c220;will change⟯ ⟮c224;the percieved lightness/brightness⟯, even when ⟮c225;they are supposed to be independent⟯. 

flex-container:⟮h∞;<img src="sm_hsl_cylinder.png">⟯⟮h∞;<img src="sm_hsv_cylinder.png">⟯
flex-container:⟮h∞;<img src="sm_hsl_cone.png">⟯⟮h∞;<img src="sm_hsv_cone.png">⟯

For any given color model, to ⟮c228;specify transparency⟯, you ⟮c229;add another channel⟯, which is called the ⟮c230;alpha⟯ channel.
For a color hex, you ⟮c231;specify the alpha channel⟯ by ⟮c232;adding another two-digit hex to the end⟯.
⟮c126;&lt;color-model&gt;-D⟯ is ⟮c127;just that color model⟯ with ⟮c128;an additional depth channel.⟯ 

RGB 3-tuple notation|color
⟮c1;Rgb(0, 0, 0⟯)|⟮c2;<img src="sm_Screenshot%202020-02-25%20at%2017.42.47.png">⟯
⟮c3;Rgb(0, 0, 255⟯)|⟮c4;<img src="sm_Screenshot%202020-02-25%20at%2017.43.44.png">⟯
⟮c5;Rgb(0, 255, 0⟯)|⟮c6;<img src="sm_Screenshot%202020-02-25%20at%2017.43.16.png">⟯
⟮c7;Rgb(0, 255, 255⟯)|⟮c8;<img src="sm_Screenshot%202020-02-25%20at%2017.44.39.png">⟯
⟮c9;Rgb(255, 0, 0⟯)|⟮c10;<img src="sm_Screenshot%202020-02-25%20at%2017.42.26.png">⟯
⟮c11;Rgb(255, 0, 255)?⟯|⟮c12;<img src="sm_Screenshot%202020-02-25%20at%2017.41.37.png">⟯
⟮c13;Rgb(255, 255, 0⟯)|⟮c14;<img src="sm_Screenshot%202020-02-25%20at%2017.45.11.png">⟯
⟮c15;Rgb(255, 255, 255)?⟯|⟮c16;<img src="sm_Screenshot%202020-02-25%20at%2017.41.09.png">⟯
⟮c233;#f2f12f⟯|⟮c234;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #f2f12f 0%, #f2f12f 100%);">⟯
⟮c235;#e6281f⟯|⟮c236;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #e6281f 0%, #e6281f 100%);">⟯
⟮c237;#e2e⟯|⟮c238;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #e2e 0%, #e2e 100%);">⟯
⟮c239;#daefe4⟯|⟮c240;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #daefe4 0%, #daefe4 100%);">⟯
⟮c241;#867d7e⟯|⟮c242;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #867d7e 0%, #867d7e 100%);">⟯
⟮c243;#17F099⟯|⟮c244;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #17F099 0%, #17F099 100%);">⟯
⟮c245;#132133⟯|⟮c246;<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #132133 0%, #132133 100%);">⟯


Color temperature is measured in Kelvin.
incandescent lights|~2500K
daylight|6000K+
candles|1500-2000K

#### color schemes

⟮c1,15;analogous ⟯|⟮c8;h15-21;Two or more colors that are all next to each other on the color wheel⟯|⟮c22;h8-14;<img src="sm_paste-1533923cee269fdd130a526f947f61f8c9c1a07a.jpg">⟯
⟮c2,16;complementary ⟯|⟮c9;h15-21;Two opposite colors on the color wheel⟯|⟮c23;h8-14;<img src="sm_paste-03f4e18bda3e8ee3b4153d5f2ef646224461c7d2.jpg">⟯
⟮c3,17;monochromatic ⟯|⟮c10;h15-21;A single color⟯|⟮c24;h8-14;<img src="sm_paste-6e50d848ef05e96cfe3f0542e368e14cf6ae37b3.jpg">⟯
⟮c4,18;tetradic (more specif: double complementary) ⟯|⟮c11;h15-21;two pairs of complementary colors ⟯|⟮c25;h8-14;<img src="sm_paste-76f4cf2d889e4aed755d6cc033dbeac563d0deee.jpg">⟯
⟮c5,19;split complementary (is a form ⟯|⟮c12;h15-21;A color and the colors adjacent to its complementary ⟯|⟮c26;h8-14;<img src="sm_paste-da8b825ba5b95610f8a2dae2a17a63c508bec3d5.jpg">⟯
⟮c6,20;tetradic (more specif. square⟯)|⟮c13;h15-21;Four colors equally spaced on the color wheel⟯|⟮c27;h8-14;<img src="sm_paste-fd4b5126038c4864c0345df2e6fb8f52cb12541f.jpg">⟯
⟮c7,21;triadic ⟯|⟮c14;h15-21;Three colors equally spaced on the color wheel⟯|⟮c28;h8-14;<img src="sm_paste-002328be373e9ab91dcae451d436c067fa5a2718.jpg">⟯


### blending

Blend modes (or mixing modes[1]) in digital image editing and computer graphics are used to determine how two layers are blended with each other. 
Blend modes typically use values from 0 to 1 for the channels for the math.
When describing blend modes, t denotes the top layer and b the bottom layer
In general, when channel is specified, assume it is done to each channel.
normal|use alpha compositing
multiply|channel_t * channel_b|result will be darker (since two numbers less than 1 multiplied will always be smaller)
screen|1 - (1 - channel_t) (1 - channel_b)|result will be always be lighter

### image rendering

Sprites are multiple graphics fused into an image, which is then masked to only show the relevant image
The two main advantages of sprites over multiple images is that  they can be easier to use and that   they take only one request to load which used to be better, but might not be anymore with HTTP/2

### refresh rates

⟮c5;FPS⟯ (computing context) is short for ⟮c6;frames per second⟯ 
The most common ⟮c7;display refresh rate⟯ as of 2020 is ⟮c8;60fps/hz⟯ 
Traditionally, it is said that ⟮c9;20-30 fps⟯ is ⟮c10;the minimum⟯ to see ⟮c11;smooth movement and not just a series of images⟯. 
⟮c12;1⟯ FPS = ⟮c13;1⟯ Hz 
medium|FPS
⟮c1;video (traditional⟯)|⟮c2;30fps⟯
⟮c3;film⟯|⟮c4;24fps⟯


### transparency & opacity

The ⟮c11;inverse of⟯ ⟮c9;transparency⟯ is ⟮c10;opacity⟯ 

transparency/opacity|visibility
⟮c1;0% transparency / 100% opacity⟯|⟮c2;completely visible⟯
⟮c3;100% transparency / 0% opacity⟯|⟮c4;completely invisible⟯
⟮c5;30% transparency /70% opacity⟯|⟮c6;70% visible⟯
⟮c7;55% transparency /45% opacity⟯|⟮c8;45% visible⟯



## design

⟮h∞;<img src="sm_paste-cb3a6dba13c1114c73bc6f0fe28db50a33115787.jpg">⟯⟮h∞;<img src="sm_paste-d33218361257ffbf6af9622ca81f2ec76c4c892c.jpg">⟯⟮h∞;<img src="sm_paste-77fe64317aade2f78384ed042619b7625fb24c43.jpg">⟯⟮h∞;<img src="sm_paste-36ea8c9033d617787cf777046d06e8b5f8db3454.jpg">⟯
It is often said (esp. in animation) that ⟮c2;good characters⟯ should ⟮c3;be recognizable by⟯ ⟮c1;their silhouette alone⟯ 


flex-container:<img src="sm_faces1.gif">
⟮h∞;<img src="sm_1280px-FedEx_Corporation_logo.svg.png">⟯
<img src="sm_Childe-Hassam-The-Flag-Outside-Her-Window-April-Aka-Boys-Marching-By-1918.jpg"><br>⟮c1;Negative space⟯ is ⟮c2;the area without subjects/areas of focus⟯
⟮c3;Positive space⟯ is ⟮c4;the area with subjects/areas of focus⟯
In the image, if ⟮c5;you see a vase⟯, the ⟮c6;black space⟯ is the ⟮c7;negative space⟯ and the ⟮c6;white space⟯ is the ⟮c7;positive space⟯
In the image, if ⟮c8;you see two faces⟯, the ⟮c9;white space⟯ is the ⟮c+;negative space⟯ and the ⟮c9;black space⟯ is the ⟮c+;positive space⟯
In the image, the ⟮c+;positive space⟯ is (probably/arguably) ⟮c+;the woman.⟯

<span class="c1-f">What are these examples for?</span><br><img src="sm_merlin_159438345_f559b53a-6da1-49f2-a8d8-141c8887d2a6-articleLarge.jpg"><img src="sm_merlin_159438405_49d288c9-c4ea-4540-a749-adb9bb055a59-articleLarge.jpg"><img  src="sm_merlin_159438372_c70d27a9-7ece-413f-8e68-65aea6e57894-articleLarge.jpg"><br>⟮c4;hostile/defensive architecture/design⟯ is architecture that ⟮c6;restricts/guides behavior⟯ to ⟮c5;protect property⟯ or ⟮c3;prevent crime⟯ 
hostile/defensive architecture might look like ⟮c7;&lt;image&gt;⟯ 
The most common people targeted by ⟮c8;hostile/defensive architecture/design⟯ in the west are ⟮c9;the homeless⟯ and ⟮c2;young people⟯ 

## misc

mentions indicate that a user is being addressed, often linking to that user and also sending a notification.
On most platforms, mentions begin with @.


## non-standard humans or non-humans

### either

#### captions

captions|transcribing audio content mainly for agents who can't hear (well)
subtitles|translating foreign language content

closed|can be en/disabled
open|cannot be en/disabled

#### curb cut effect

flex-container:⟮h∞;<img src="sm_paste-2ab6d6b8ccffb953b18c192a791aa3c2cbba86e5.jpg">⟯
⟮h∞;<img src="sm_paste-b6739c18073b7652f19b772187e5a52c68d24aa9.jpg">⟯⟮h∞;<img src="sm_paste-c77343d19ee4958e246f56f5e234d8f9682731c2.jpg">⟯

Only after ⟮c1;disabled people protested⟯ did ⟮c2;curb cuts begin to be instituted⟯. 
⟮c3;Curb cuts⟯ have only really ⟮c4;become common⟯ ⟮c5;in the last few decades⟯ 
⟮c6;Curb cuts⟯ had ⟮c7;many unexpected benefits⟯ besides ⟮c8;helping disabled people⟯, giving rise to the term ⟮c9;curb cut effect⟯. 
⟮c10;The curb cut effect⟯ states that ⟮c11;accessibility improvements⟯ provide ⟮c12;many and varied benefits for everyone⟯ besides ⟮c13;their initial aims⟯ 

#### non-directive play

flex-container:⟮h∞;<img src="sm_Isamu-Noguchi-Three-1440x943.jpg">⟯⟮h∞;<img src="sm_IMG_8551.jpg">⟯⟮c1;non-directive/self-directed play⟯ is play that ⟮c2;allows the players to do whatever they come up with⟯

⟮c3;self-directed play⟯ is easier to do when ⟮c4;the play tools are not designed with any particular end in mind⟯ 
⟮c5;self-directed play⟯ was advocated, especially in ⟮c6;playgrounds⟯, by ⟮c7;Isamu Noguchi⟯ 
⟮c8;Noguchi⟯ ⟮c9;long struggled⟯ to g⟮c10;et a self-directed play playground built⟯, but ⟮c11;one was eventually built in Sapporo⟯ 

### robots

#### robots/noindex

There are two ways to ⟮c5;specify what crawlers such as those from search engines can crawl⟯, ⟮c6;the robots.txt⟯ and ⟮c7;the noindex tag⟯. 
The ⟮c8;robots.txt⟯ follows/implements ⟮c9;the robots exclusion standard/protocol⟯. 
⟮c10;The robots.txt⟯ is a file with ⟮c12;a specific syntax⟯ to indicate ⟮c11;what can crawl sites how⟯. 
⟮c13;The robots.txt⟯ may not ⟮c14;always hide pages⟯, specifically, ⟮c15;the page may still display in search results⟯, but ⟮c15;lacking any descriptive content⟯. If you want ⟮c16;to hide the page completely⟯, use ⟮c17;a noindex tag or HTTP header⟯. 
The ⟮c18;noindex tag⟯ is a ⟮c19;HTML meta tag⟯ that ⟮c20;tells crawlers how they should crawl the given page⟯. 
Setting both ⟮c21;the robots.txt⟯ and ⟮c22;noindex tag⟯ for the same thing ⟮c23;can produce problems⟯ and ⟮c23;is not advised⟯. 
While ⟮c24;you can tell what crawlers should crawl⟯ via ⟮c25;robots.txt/noindex⟯, ⟮c26;there is no reason they have to respect it.⟯ 
⟮c27;Pages that should be on the robots.txt/have a noindex tag⟯ are e.g. ⟮c28;internal search pages, pages that require a certain state.⟯ 
If ⟮c29;a page should truly inaccessible to outside forces⟯, ⟮c30;using robots.txt/noindex tags is not enough⟯, it should then be ⟮c31;password-protected or similar.⟯ 
Example noindex tag: `&lt;⟮c1;meta⟯ name="⟮c2;robots⟯ (all) / ⟮c3;googlebot⟯ (only google) content="⟮c4;noindex⟯"&gt;` 

#### sitemap

sitemaps are XML, RSS/Atom, or .txt documents that describe the navigational structure of your site, and are often used by search engines

#### search

The most fundamental thing that influences your SEO is how many other links to your site exist, and who these sites linking to you are.
By linking to a site, you confer some of your sites reputation to that site.
SEO|Search engine optimization
related to navigation, google will reward a site that has a navigation that is ⟮c1;sensible⟯, uses ⟮c2;text (or e.g. aria tags)⟯, but ⟮c3;does not go overboard in its complexity⟯
Google may penalize if you have a bunch of pages with basically the same content.

As of 2021, ⟮c1;stuffing keywords⟯ in places is ⟮c2;no longer effective⟯ for ⟮c3;SEO⟯ 
As of 2021, for ⟮c4;SEO⟯, ⟮c5;a page title/ description⟯ should be ⟮c1;descriptive of the page content⟯ and ⟮c6;distinct from other page titles⟯. 

### Accessibility

⟮c2;Accessibility⟯ is ⟮c3;designing things⟯ ⟮c1;so as to be usable by people with disabilities (with a variety of bodies⟯)
Accessibility improvements often do not merely benefit the disabled, but also non-human users (e.g. web crawlers and thus SEO), users with different input methods (such as the keyboard)
For accessibility purposes, audio/video should have captions, and lighthouse will chide you if it doesn't

#### WAI & WCAG basics

⟮c1;the Web Accessibility Initiative (WAI)⟯ is the W3C initiative supporting accessibility.
the WCAG (Web Content Accessibility Guidelines) are guidelines for web accessibility published by the WAI.
The WCAG consists of principles, guidelines, successs criteria, and techniques.
WCAG principles are the general ideas underlying web accessibility: percievable, operable, undertandable, robust.
Each WCAG principle is broken up into one or more guidlines.
Each WCAG guideline has one or more successs criteria, which are characterized by being testable.
For each guideline and success criterion the WCAG also includes a wide variety of techinques for (better) achieving these.
WCAG techniques may either be <dfn>sufficient</dfn>, i.e. enough to meet a success criterion, or be <dfn>advisory</dfn>, which is going beyond the success criterion to better address the guideline behind it. Additionally, WCAG techniques may document common failures.
The WCAG defines three levels of conformance, A, AA, And AAA, for each success criterion.
In some countries websites, especially those of public sector bodies must conform with certain WCAG levels.
the WAI published the WCAG ⟮c5;2.1⟯ version in ⟮c6;2018⟯, and is expected to publish WCAG ⟮c5;2.2⟯ in ⟮c6;2021⟯ 
According to the WCAG ⟮c7;level AA⟯, color should have a ⟮c8;contrast ratio⟯ of at least ⟮c9;3:1⟯ for ⟮c10;large⟯ and ⟮c9;4.5:1⟯ for ⟮c10;normal⟯ text 
According to the WCAG ⟮c11;level AAA⟯, color should have a ⟮c12;contrast ratio⟯ of at least ⟮c13;4.5:1⟯ for ⟮c14;large⟯ and ⟮c13;7:1⟯ for ⟮c14;normal⟯ text 

#### WCAG success critera

The text of a link should be descriptive of the purpose of the link, even out of context.

##### Non-text content

the alt text should be blank if the image is merely presentational, don't just not specifiy it, or screen readers might e.g. read out the url
iframes and frames should have a title (doing what alt text would do for images)

#### WCAG techniques

Based off ⟮c2;the DOM tree⟯, the browser builds the ⟮c3;accessibility tree⟯ containing ⟮c1;all accessibility-relevant information⟯

##### Semantic HTML

Semantic HTML is HTML where the tags contain semantic information about the content
Semantic HTML includes elements like &lt;article&gt;, &lt;nav&gt;, &lt;summary&gt;, contrasting with elements like &lt;div&gt;, &lt;span&gt;


##### aria

ARIA attributes fall under the umbrella of WCAG techniques.
ARIA  Accessible Rich Internet Applications
ARIA is mainly realized in HTML attributes.
⟮c2;Where available⟯, prefer ⟮c1;semantic HTML⟯ over ⟮c3;ARIA⟯
ARIA attributes change the accessibility tree, but nothing else.
There are three types of attributes that ⟮c4;ARIA⟯ has: ⟮c1;Roles⟯, ⟮c2;States⟯ and ⟮c3;Properties⟯
ARIA ⟮c1;roles⟯ define the ⟮c2;main type of component⟯, e.g. ⟮c3;toolbar, banner⟯
ARIA ⟮c1;states⟯ define some property ⟮c2;that can change⟯
ARIA ⟮c1;properties⟯ define some property ⟮c2;that is expected to stay the same⟯
There are four types of aria ⟮c4;states⟯ &amp; ⟮c4;properties⟯: ⟮c1;drag-and-drop⟯, ⟮c2;live region⟯, ⟮c3;relationship⟯, and ⟮c5;widgets⟯

the ⟮c1;aria-label⟯ ⟮c2;attribute⟯ is for adding ⟮c3;a text description⟯ of ⟮c3;what something does⟯ where ⟮c4;the actual content doesn't suffice⟯
a reason for using aria-label might be e.g. because a close button is realized ⟮c4;with an icon font/an x⟯

# data storage

## memory

### medium

#### holes

In punch card/punched tapes, the two states of binary data represent the presence or absence of holes.
punched tape is like punched cards, but continuous

#### flash memory

Solid state memory/storage in theory is any storage without any moving part.
Flash memory is the most common type of solid state memory.

### mutability & volatility

ROM  Read only memory
ROM is memory that is set once, and then cannot be changed anymore, or only using a special technique.
ROM was used to store games on game cartidges, for example.
Memory that retains information after power is removed   Non-volatile memory
Memory that requires power to retain stored information   Volatile memory

### addressing

Memory is generally addressed via memory addresses.
Physical addressing is addressing memory by using addresses corresponding to actual memory addreesses
Logical Address = Virtual Address
Virtual/logical memory is addresed by virtual/logical addresses.
Logical/virtual addressing adds a layer of abstraction over physical addressing. 
Virtual memory & addresses are used by the OS for primary memory, but also may be used in other circumstances.
Nearly all current implementations of virtual memory for primary memory divide virtual memory into pages.
Pages of virtual memory typically have a fixed size or a few preditermined fixed lenths.
For primary memory, virtual addresses are mapped to physical addresses in the page table.
The MMU (Memory management unit) is a hardware device typically used to handle the page table/mapping of log to phys addr.
Each process has its own section in virtual memory.
Virtual memory will appear to an application using it to be continuous, though the physical memory it occupies may be discontinous.
Today, modern OSs only expose virtual memory to user-level programs.
Virtual memory benefits security, as it means programs can't access each other's memory.
Logical block addressing is logical addressing for secondary memory using one or more blocks.
A logical block contains its binary contents and a bit of metadata.
With logical blocks addressing, a file will always be a multiple of the block size
blocks are the smalles unit your file system can write in in.
blocks are usuall between 0.5kiB and 8kiB as of 2020.
Small blocks may cause storage overhead b/c the metadata to content ratio is smaller
large blocks may cause storage wastage b/c small files still need at least a single block.


#### memory management

swap/page storage are virtual memory that is secondary memory used as an extension of primary memory
swap/page storage may be a file(s) or a partition(s).
managing virtual memory pages within primary memory|paging
moving virtual memory from secondary to primary memory or v.v. (using pages)|swapping or paging
moving virtual memory from secondary to primary memory or v.v. (without using pages)|swapping
primary -> secondary memory|paged/swapped out
secondary -> primary memory|paged/swapped in

### fragmentation

⟮c2;Memory fragmentation⟯ is when memory is ⟮c3;allocated in many non-contiguous blocks⟯, meaning it has ⟮c1;small spaces that can't store anything useful⟯ 
⟮c4;Memory fragmentation⟯ results in ⟮c5;the wasting of storage⟯. 

### relation to processor

The difference between primary and secondary memory is that the processor can address primary memory directly.

#### primary memory/storage

The terms primary storage/memory, internal storage/memory, and main storage/memory are often used interchangeably.
As I will use the term, primary memory consists of CPU core Registers and Cache as well as main memory.
Both registers and cache are directly on the chip.
Nonvolatile RAM   NVRAM
SRAM  static random access memory
DRAM  dynamic random-access memory
RAM random-access memory
SRAM is faster than DRAM and is therefore used for the chace and internal registers.
RAM is sometimes used as a catch-all for any primary memory.
Principle of locality AKA locality of reference
principle of locality = (Principle of) Temporal Locality &amp; Spatial Locality
principle of locality relates to memory access, specifically it predicts what memory will be accessed next.
principle of spatial locality = Memory that is close (to the currently accessed memory cell) will tend to be accessed again
principle of spatial locality = Memory that has recently been referenced will be referenced again soon.
Memory closer to the processor is faster but more expensive and smaller, memory further away from the processor is slower but cheaper and larger.
memory speed:
registers > processor cache > main memory > secondary memory

#### secondary memory

secondary meory is generally non-volatile memory

##### drives

HDD  Hard disk drive
SSD  Solid state drive/device/disk
clonezilla is the standard FOSS program for cloning entire drives.

###### HDD

HDDs store bits of data data via magnetic north/south.
Physically, a HDD stores the data on rotating platters.
A HDD usually includes a few platters.
HDDs are thick even though individual platters are thin because HDDs generally contain multiple platters.
HDD platters are discs usually made up of a aluminum/glass plate coated with a magnetic coating.
in a HDD, the head performs read-writing.
in a HDD, the head is mere nanometers from the platter.
⟮h1;<img src="sm_250px-Samsung_Harddrive_headcrash_DSCN0124b.jpg">⟯
A head crash is the head of a HDD making contact with its rotating platter, slashing the surface and causing disk damage/failure.
Head crashes generally happen due to falling/jolts or due to dust sticking to the head.

flex-container:<img src="sm_hdd_w_labels.svg">
<img src="sm_1280px-Seagate_ST33232A_hard_disk_head_and_platters_detail.jpg"><img src="sm_220px-Laptop-hard-drive-exposed.jpg">
as of 2020, HDDs usually spin at 5400 or 7200 RPM.
as of 2020, HDDs are typically a few TB in size.

a HDD is made up of clusters which are made up of sectors.
A sector used to be 512 byte large normally; today, that is usually 4096 Bytes (4KiB)

⟮h∞;<img src="sm_cyl_head_sect_dia.svg">⟯
HDDs originally used a form of physical addressing known as CHS.
CHS = Cylinder Head Sector
CHS used the head, cylinder and sector (like coordinates) to specify a memory location.
CHS was replaced in the mid-90s by logical block addressing.

###### SSD

A flash memory device typically consists of multiple flash chips and a controller.
a flash chip is made up of blocks which are made up of pages
To write new data on a flash memory device, first you need to erase the old data.
Flash memory can either be NAND or NOR based.
NAND flash can typically erase only whole blocks, but write pages too
After a certain number of write cycles, flash memory begins to decay.
Flash memory is typically faster than magnetic memory.
SSDs are a type of flash memory device.

[⟮c;SSD chip⟯ [⟮c;block⟯ [⟮c;page⟯</span></div>[⟮c;page⟯</span></div>[⟮c;page⟯</span></div>[⟮c;...⟯</span></div></div>[⟮c;block⟯</span></div>[⟮c;...⟯</span></div></div>

## secondary memory organization

### devices

RAID = Redundant Array of Inexpensive/Independent Disks
SLED = Single Large Expensive disk
RAID <-> SLED
RAID uses multiple disks.
RAID disks are in some sort of configuration which aims to achieve one or more of the three aims reliability/redundancy, performance, capacity
RAID 0|Data is split among the drives (striped)|performance (r/w)
RAID 1|data is mirrored on all drives|reliability & some read performance

### partitions

A secondary memory device is divided into n partitions.
How partitions are layed out on a secondary memory device is described by the partition table.
in the past, the MBR would have also included a partition table.
the MBR partition table was limited to 64 byte, which allowed for up to four partitions.
Today, partition tables are generally GPT, since MBR was limited to addressing 2 TiB drives.
GPT  GUID Partition Table
GUID in GUID Partition Table  globally unique identifier

gparted and gnome-disks are GUIs for partition/disk management

mac

On mac, ⟮c7;drutil⟯ is the ⟮c8;CLI⟯ utility for ⟮c9;interacting with burnable media⟯. 
On mac, ⟮c10;diskutil⟯ is the ⟮c11;CLI⟯ utility for ⟮c12;interacting with harddrives.⟯ 

Verb|Function|Which of drutil/diskutil?
⟮c1;list⟯|⟮c2;list attached devices⟯|⟮c3;drutil, diskutil⟯
⟮c4;eject⟯|⟮c5;ejecting a device⟯|⟮c6;drutil, diskutil⟯



### file system

The file system is the method/system/whatever that controls/specifies how ⟮c1;data is organized within a partition⟯
A flat file system is a file system with no ⟮c1;subdirectories⟯
Most *nix file systems are case-sensitive, but the apple ones (AFS/HFS+) are not; furthermore, windows is not case-sensitive.
Even non-case-sensitive file systems are almost always case-preserving.
fsck checks/repairs a linux filesystem.
FUSE = Filesystem in userspace
FUSE  is system that allows users to create their own filesystems without editing kernel code
FUSE was originally developed for linux, but has been ported to other OSs such as win or mac
fuse is configured in /etc/fuse.conf

#### mounting

mouting is associating a device with a location in the directory tree.
/etc/fstab allows specifying default moun points for certain devices/partitions.
/etc/fstab ensures that the same device will always be mounted inn the same way.
mount and unmount are the commands to mount/unmount things in linux using sudo.
mount may take both a device and a mountpoint.
mount may take just a device or mountpoint, in which case it will try to mount this in the way specified in /etc/fstab.
in contrast to mount, pmount allows one to mount a device without being root, but only if one conforms to a certain set of rules (its policy)

#### file info

stat|info about file
file|get file type and related info

### directory structure

⟮c1;the directory structure⟯ is the way data is organized in a file system using directories.
If the directory structure is a tree, it is often called a/the directory tree.
filesystem hierarchy is a rough synonym of directory structure
In *nix-likes, the root directory is the directory all other directories descend from.
In *nix-likes, since all other directories descend from the root directory, *nix-likes only have a single directory tree.
In *nix-likes, the root directory is `/`
In windowslikes, each partition is its own root directory, with a drive letter assigned.
Windows drive letters have the syntax <letter>:
An absolute path begins at the root directory.
A relative path begins at the current working directory.

In general on *nix systems, whatever/share contains architecture-independent data


#### navigation


##### traversal

autojump is a tool that remembers which places you've navigated to, and allows quick jumping to the most commmonly used place.
j foo| jump to most commonly used directory containing foo
jc foo|jump to most commonly used **child** directory containing foo

cd|move to specified directory

cd without an argument moves back to your home directory
cd - moves back to previous directory (not parent directory)

###### file manager/browser

file browser = file manager
a file manager/browser is a program that provides an user interface for managing files and folders.
mc ("midnight commander"), nnn are TUI file browsers.
Nautilus is file manager for GNOME.

⟮h∞;<img src="sm_Screenshot%202020-02-23%20at%2018.08.49%20(1).jpg">⟯
For ⟮c2;Finder⟯, ⟮c1;whenever you search anything in the top right bar⟯, ⟮c3;a Searching/Find window opens⟯. ⟮hb;To ⟮c4;add filters to the search⟯, ⟮c5;click the small plus in the top right corner⟯. ⟮hb;You can use this to search ⟮c6;pretty much any of the files properties⟯ with ⟮c7;fine granularity⟯.⟯⟯ 

##### information

pwd|print path of current directory
tree|print a directory tree
tree -L <n>|go to depth n
ls|list file in directory

-s|display files and directories with their sizes
-S|sorting by size in output
-F|list all files and directoreis annotated with /*@

something/|directory
something@|symlink
something*|executable

exa is a reinplementation of ls in rust with more features and opinionated defaults.

fzf is a shell filter which takes an input of a list of files, allows interactive fuzzy search and selection, and outputs the selection.

du & dust estimate storage usage of files in current directory.
`-d / --max-depth (for du) --depth (for dust)`   only go to the specified depth

realpath gets the absolute path for a file name
basename strips the path and suffix from a file name

###### find

find|find files
find-command ::= find {<global-option>} {<starting-point-path>} {<expression>}
If no starting point is specified for find, it takes the current working directory.

-type CHAR (e.g. b, c)   find files that are of one of the 7 unix file types 
-size SIZE   find files that are larger than SIZE
-name foo   find files that contain foo in their name (case-sensitive)
-iname foo   find files that contain foo in their name (case-⁑insensitive⁑)
! expression   true if expression is false 
-printf PATTERN   print the filename according to PATTERN

fd is a simpler and faster version of find implemented in rust.
fdupes finds duplicate files.

###### grep

grep is a tool that takes a regex, applies it to a set of files, and prints the lines that match.
There are tons of grep variants:
agrep|grep with fuzzy matches

There are also many alternative variants of grep using more modern regexes, and also significantly faster:
speed: rg > ag > ack

greps exit status if it finds a match is 0, if it does not find a match, it is 1.
grep -c count the produced lines.
grep -v = grep --invert-match
grep -F/--fixed-strings interpet pattern as fixed string, not as regex
`-C NUM/--context=NUM`   show this much context

#### directory structures

##### home dir

Generally one home directory per user.
On *nix, the home directory of a user generally contains all the stuff pertaining ot a user.
FHS: Home directories live in /home/
$XDG_CONFIG_HOME/autostart contains .desktop files to run on system start
$XDG_DATA_HOME/fonts contains fonts for a specific user

##### XDG Base Directory Specification

XDG Base DIrectory Specification is the spec governing the organization of files in your home directory   

XDG Base Dir Var|default|global equivalent
$XDG_DATA_HOME|$HOME/.local/share|/usr(local/)share
|$HOME/.local|/usr/local
|$HOME/.local/lib|/usr/local/lib
|$HOME/.local/bin|/usr/local/bin
$XDG_CONFIG_HOME|$HOME/.config|/etc
$XDG_CACHE_HOME|$HOME/.cache|/var/cache

##### FHS

FHS  Filesystem Hierarchy Standard
FHS (Filesystem Hierarchy Standard) is the Linux spec for ⟮c1;directory structure⟯
source code should be in src for reference only

###### /sys

/sys provides a window to the kernel.
/sys/class|contains (a view of) different types of devices
/sys/class/power_supply|contains (a view of) the power supplies
/sys/class/power_supply/BAT<n>|information about the nth battery
/sys/class/backlight|contains (a view of) the screen backlights.

###### /boot

/boot contains things necessary for booting, most importantly the kernel.

###### /proc

/proc contains information for each process and a lot of runtime system info.

###### /var

/var contains data likely to change often.
the structure of /var is provided by the OS

/var/mail/ and/or /var/spool/mail contain MBOXes for each user 
Of /var/mail/ and /var/spool/mail, the semantics are the same, and thus one is most often a symlink to the other.
/var/spool/   data awaiting processing
/var/cache/|cache data
/var/backup/|backups of key system file
/var/crash/ contains crash dumps of the system
/var/log|global log data
/var/lock|global lock files (for mutexes)
/var/lib data to maintain program state that doesn't have  a better directory to be in. 
/var/lib state information is valid even after reboot.

###### /opt

/opt   software packages (complete and kind of foreign)
programs in /opt are usually more self-contained and system-fremd.

###### /srv

/srv is a directory for data served by the system
/srv is often organized into subfolders by protocol (though this is not a requirement.)
/srv is not used particularly commonly

###### /mnt and /media

/media is where the system mounts things automatically (e.g. removable media), and /mnt is where you mount things manually (with generic semantics)
You are not forced to mount things in /mnt, you can mount them wherever you want.

###### /opt

/opt contains fairly self-contained programs
/var/opt contains variable data of programs installed in /opt
today, usage of /opt is fairly rare

###### /run and /var/run

today, /var/run is deprecated in favor of and a symlink to /run
/run or /var/run contains runtime variable data that programs rely on that is cleaned or tirimmed at reboot

###### /usr

/usr is called usr because it contains userland and not kernel land data
Data within /usr should be usable on any FHS-compliant host, ergo data specific to host or time should not go in /usr.
Data within /usr should be read-only
/usr is for programs installed by the OS/package manager, while /usr/local is for programs installed by the root user
the structure of /usr/local mirrors the structure of /usr
/usr(/local)/include is for C include files
stuff in a share directory is data sharable sharable across all architectures of a given OS
/usr(/local)/src contains source code of installed programs for reference only.
typically, /usr and /usr/local include at least bin, lib, include and share

###### bins

whatever/bin is generally for executables
Originally and still in some unixes, /bin would have contained system-essential binaries, while /usr/bin and /usr/local/bin would have contained non-system essential bins (and analogously for lib)
today, /bin often just is a symlink to /usr/bin (and analogously for lib)
whatever/lib generally conains libraries for whatever/bin
whatever/lib32 and 64 are libraries for the architecture specifically, most commonly when two versions of the same library for different arches are installed.
instead of whatever/bin, games may also go in whatever/games
/sbin is for binaries needing superuser priviledges/for system administration
sbin = superuser binary

###### /tmp

/tmp is for temporary files.
/tmp is sometimes emptied on process exit or on boot.
/var/tmp is like /tmp, but meant to last longer and thus autocleaned less or not at all
Organization within /tmp is pretty hodgepodge.

###### /etc

/etc contains global config files for all the programs that run on your Linux/Unix system
/etc/hosts
/etc/motd|contains the message of the day
/etc/machine-info contains machine metadata such as type of computer, deployment, location and pretty-printed hostname
/etc/hostname contains the usesrs static hostname.
hostnamectl administers the stuff in /etc/hostname and /etc/machine-info, i.e. all the hostnames and the machine metadata.
hostname - show or set the system's host name
Instead of /etc, some programs stored in /usr/local store their config in /usr/local/etc

###### /dev

/dev contains device files.
It makes sense to treat devices as just another file, as the operations they support (reading, writing or both) are the same as a file.
device files are files that are interfaces to device drivers (or more rarely other things).
udev is a system managing the /dev directory and userspace hardware events.

####### drivers

on *nix, any device is identified by its major and minor number.
on *nix, drivers generally should provide a mechanism but not a policy.

|identifies
major number|driver
minor number|device of driver
if two device files have the same major number, they are managed by the same driver
if two device files have the same major and minor number, they are the same device

####### not real devices

/dev/random and /dev/urandom are CSPRNGs of nix* systems
the difference between /dev/random and /dev/urandom is that the former blocks to wait for more entropy if necessary, the latter does not.
the man suggests one use /dev/random for long-lived GPG/SSL/SSH keys, and /dev/urandom for anything else.
/dev/full is  always full
/dev/zero returns as many 0x00 as you like.
anything written to /dev/null discards the data, whence its nicknames bit-bucket/black hole
/dev/video<n> represents attached cameras.

####### block device files

The beginning of the device file name specifies the kernel's used driver subsystem to operate the block device.
Originally, the /dev/sd<char> was only used for block devices using SCSI.
Because ATA/SATA/PATA devices suppoort a subset of the commands of SCSI, linux decided to also handle them by the kernel's SCSI driver subsystem, therefore their device files also use the  /dev/sd<char> naming scheme. 
/dev/nvme<n>n<n> represents devices attached via NVMe
for /dev/nvme<n>n<n>, the first <n> represents the index of the controller, the second <n> represents the device on the controller.
/dev/vd<char> represents devices attached to a virtio block device interface, which is an interface for virtual devices.
/dev/mmcblk<n> represents devices handled by the kernels mmc driver, such as SD cards.
/dev/fd/<n> are device files representing the file descriptors of the current process, however /dev/fd<n> (notice the difference!) indicates the nth floppy disk connected.
/dev/hd<n> are device files representing entire, raw hard disks (not commonly used today)
/dev/input contains device files for

<char> and <n> as indices are genrally assigned based on which was discovered first
to represent a partition, add <index> to the relevant device file if the name ends in a character, and p<index> if it ends in a number.
e.g. /dev/sda1 or /dev/loop0p2

A loop device is a normal file mounted as a block device, which you then can use as part of a filesystem.
.iso files might be good candidates for mounting as a loop device.
loop devices are mounted at /dev/loop on linux

####### character device files

/dev/stdin and /dev/stdout are symlinks to /dev/fd/0 and /dev/fd/1
piping to `source /dev/stdin` executes the text as a command

##### Mac

⟮h∞;<img src="sm_Screenshot%202020-07-09%20at%2014.36.21.jpg">⟯⟮c2;macOs⟯'s ⟮c1;/private⟯ folder contains ⟮c3;a few directories that would have been found in / on FHS-compliant devices⟯, namely ⟮s1-3;⟮c4;etc⟯, ⟮c5;tmp⟯, and ⟮c6;var⟯⟯

## files

### file operations regardless of contents

mv will silently overwrite if moving to something that already exists.
dd   copying (similar to cat/cp) with some low-level options
shred overwrites a file multiple times so it is difficult to recover, however this interacts badly with SSDs
touch|create emtpy file
mkdir|create empty directory
cp|coping stuff

rsync is an improved version of rcp and shares much the same general interface, which is still often used for incremental backups, even if local.

rnr   regex renaming utility that actually works well


#### diff

⟮c4;diff⟯ is a tool that ⟮c5;shows the differences between files⟯. 
⟮c6;diff⟯ is originally ⟮c7;a cli program of the same name⟯. 
There are variants of ⟮c8;the original cli program diff⟯ that change how it work somewhat, e.g. ⟮c9;sdiff⟯ for ⟮c10;side-by-die diffs⟯ and ⟮c11;icdiff⟯ for ⟮c12;both colored and side-by-side diffs⟯ 
⟮c13;diff⟯ is now offered as ⟮c14;a subcommand of⟯ ⟮c15;many other tools⟯. 
⟮c16;npm⟯ ⟮c2;diff⟯ provides ⟮c3;diffs between packages⟯, some of which must be ⟮c1;published to the npm registry⟯ 
⟮c17;git diff⟯ shows the difference between things ⟮c18;in/related to a git repository⟯. 
⟮c21;no argument⟯|⟮c22;show diff between unstaged and staged/committed⟯
⟮c23;--staged/--cached (synonyms⟯)|⟮c24;show diff of staged changes with latest commit (or specified commit⟯)


further, ⟮c19;diff-like output⟯ is now used in ⟮c20;a wide variety of gui applications⟯ 

### files as binary

A hex editor is an editor that allows you to edit the fundamental binary data of a file displayed as hex

od|output files in octal, but also in other repreesentations
od -x|hex dump

### file types by relation to OS

linux: "Everything is a file"
Plan 9: "Really everything is a file"

folder (windows) = directory (*nix)

#### permissions & owners

The user-and-group model means that for each file every user on the system falls into one of three categories: the owner of the file, someone in the file’s group and everyone else
chown changes the owner and/or group of the file
chown-command ::= {<option>} [<owner>][:[<group>]] {<file>}
The three permissions that unix tracks are ⟮c1;read⟯, ⟮c2;write⟯,, and ⟮c3;execute⟯
⟮c1;x⟯|⟮c2;execute⟯
⟮c3;w⟯|⟮c4;write⟯
⟮c5;r⟯|⟮c6;read⟯



#### 7 types of files

In unix, there are 7 types of files.
Types of files in linux: ⟮c7;Regular file⟯ ⟮c6;Directory⟯ ⟮c5;Symlink⟯ ⟮c4;FIFO/named pipe⟯ ⟮c3;Socket⟯ ⟮c2;Device file (block)⟯ ⟮c1;Device file (character)⟯

The file type is one of the following characters:
identifying characters (e.g. ls)|
-|regular file
b|block device
c|character device
d|directory
l|symbolic link
p|FIFO (named pipe)
s|socket
?|some other file type

##### named pipe

named pipe = FIFO
named pipes are functionally very similar to a temporary files.
the use-case for using named pipes instead of anonymous pipes is that you don't need to read/write at the same time, that it persists and thus communication can happen multiple times, that processes that can read/write that aren't child processes of each other.
mkfifo creates a new named pipe
named pipes must be deleted manually (via rm)

##### links

ln creates hardlinks by default, and symlinks with -/--symbolic.
ln orders its arguments the same way cp would.
symlink is short for symbolic link.
A symbolic link is a file that is a reference to another file in form of a path.
If the file a symbolic link points to is moved, the symbolic link now points to nothing.
since links exist, the file system isn't actually a tree, but a directed graph.
most programs treat symlinks transparently, however rm/mv/... edit the symlink file itself.
if using rm or mv on a symlink to a directory, if you don't include the trailing slash, they will act on the symlik like normal, if you do include the trailing slash, they will try to remove the directory itself.
A hard link is a reference to an inode.
A hard link only exists as a directory entry, in fact, all directory entries are hard links.
To use a hard link, the file must be on the same filesystem.
If a file moves, a hard link will still be pointing to it.
readlink prints the value of a symbolic link.

##### directories

In *nix, directories are nothing but a file, where the files 'contained' within are only associated with it via their directory entry.
dentry = directroy entry.
in the ext filesystem, a directory file is made up of a list of directory entries.
In the ext filesystem, a directory entry contains the inode number, file name and file name length.
the . and .. entries are maintained by the directory files themselves.
Within the ext filesystem, the first entry in any directory file is the . entry.
Within the ext filesystem, the second entry in any directory file is the .. entry.
.|current directory
..|parent directory
If there is an inode not referenced by any directory entry, it will be placed in lost+found.

##### device files

two of the seven types of files are device files.
The two types of device files are block device files and character device files.
Block device files grant random access.
Character device files grant sequential access.

#### special names

When config files are split up into multiple files, .d directory names are often used.
.d directory names are often used to give them a different names from normal files doing something  similar.
dotfiles are files starting with a dot.
Dotfiles are generally hidden by default.
Dotfiles are often used for config or metadata.

##### sockets

Unix IPC sockets are distinct from network/internet sockets
A socket in unix is realized as a file descriptor
⟮c1;Unix (domain) sockets⟯ are used for ⟮c2;bidirectional⟯ ⟮c3;IPC⟯
/dev/log = socket for logging


### file formats

#### indication

⟮c1;File format⟯ and ⟮c2;file type⟯ are ⟮c3;basically synonyms⟯. 
the ⟮c4;file format/type⟯ is ⟮c5;the structure/specification⟯ of what ⟮c6;the binary contents⟯ of ⟮c5;a file following this ⟮s4;file format⟯⟯ ⟮c7;mean/how they should be interpreted⟯. 
There are ⟮c8;three common ways⟯ to specify ⟮c9;a file format⟯: ⟮s8;⟮c10;Filename extensions⟯, ⟮c11;internal metadata⟯, and ⟮c12;external metadata⟯.⟯ 

⟮c13;Windows⟯ and ⟮c14;Mac⟯  use ⟮c15;file extensions⟯ to ⟮c16;identify file type⟯. 
⟮c17;Linux⟯ generally uses ⟮c18;magic numbers⟯ to ⟮c19;identify file type⟯. 
⟮c20;File extensions⟯ can be ⟮c21;useful⟯ on ⟮c22;Linux⟯, but ⟮c23;are generally not necessary⟯. 

Specifying ⟮c28;file format⟯ via ⟮c26;internal metadata⟯ is having some sort of information ⟮c27;as part of the file⟯ that specifies its ⟮c28;format⟯. 
⟮c24;Magic numbers⟯ are a form of ⟮c25;internal metadata⟯. 
⟮c29;magic numbers⟯ are ⟮c30;a byte/series of bytes⟯ (often at ⟮c31;the beginning of the file⟯) that ⟮c32;identify the file format⟯. 

Specifying the ⟮c33;file format⟯ via ⟮c34;filename extensions⟯ involves ⟮c35;suffixing⟯ ⟮c36;the filename⟯ with ⟮c37;a dot⟯ and ⟮c37;some short name⟯. 
many ⟮c38;file extensions⟯ are ⟮c39;three-letter⟯ because ⟮c40;dos did not allow for longer file extensions⟯ 
⟮c41;.htm⟯ is ⟮c42;a synonym for .html⟯ that only exists because ⟮c43;dos required 3 char file extensions⟯ 

Specifying ⟮c44;file format⟯ via ⟮c45;external metadata⟯ is having some sort of information ⟮c46;as part of a message/protocol/file system⟯ that specifies its ⟮c44;format⟯. 

⟮c47;Media type⟯ is a way for ⟮c49;identifying the file format⟯ of a file via ⟮c48;external metadata⟯. 
⟮c50;Media type⟯ is ⟮c51;the most common way⟯ for identifying file format on ⟮c52;the internet⟯. 
⟮c53;Media type⟯ ⟮c55;used to⟯ be called ⟮c54;MIME type⟯. 
⟮c56;Media type⟯ syntax: ⟮c57;&lt;type&gt;/&lt;subtype&gt;⟯⟮c58;{+&lt;suffix&gt;⟯}⟮c59;[;&lt;parameter&gt;]⟯ ⟮(c:60;&lt;tree&gt;⟯ left out because not commonly used) 
Common types for media type's ⟮c61;type⟯ are a⟮c62;pplication, audio, video, image, text⟯ 
Common ⟮c63;subtypes⟯ for ⟮c64;the type image⟯ might be ⟮c65;webp, png, svg+xml, jpeg⟯ 
If a file is ⟮c66;XML⟯, its ⟮c68;media type⟯ gets ⟮c67;a suffix of xml (+xml⟯) 
The ⟮c69;HTTP header⟯ for ⟮c70;media type⟯ is ⟮c71;Content-Type⟯. 

A ⟮c72;mailcap⟯ ⟮c73;file⟯ maps ⟮c74;media types⟯ to ⟮c75;applications to view/execute them.⟯ 
⟮c76;Mailcap files⟯ consist of ⟮c77;mappings⟯, with ⟮c78;one⟯ per ⟮c78;line⟯. 
⟮c79;Mailcap mapping⟯ syntax: ⟮c80;&lt;media-type&gt;⟯⟮c81;;⟯⟮c82;&lt;program-to-execute&gt;⟯ ⟮c83;%s⟯ 
For ⟮c84;mailcap⟯, ⟮c85;%s⟯ represents ⟮c86;the file of the relevant MIME type⟯ that ⟮c87;the program gets passed⟯ 

##### common file extensions

File format|File extension
⟮c1;TypeScript source code⟯|⟮c2;.ts⟯
⟮c3;M3U playlist⟯|⟮c4;.m3u⟯
⟮c5;Tex source document⟯|⟮c6;.tex⟯
⟮c7;WebVTT⟯|⟮c8;.vtt⟯
⟮c9;JS Modules⟯|⟮c10;either .js or .mjs⟯
⟮c11;Markdown source document⟯|⟮c12;.md⟯
⟮c13;YAML source document (common but not advised⟯)|⟮c14;.yml⟯
⟮c15;YAML source document (advised but less common⟯)|⟮c16;.yaml⟯
⟮c17;bzip2 archive⟯|⟮c18;.bz2⟯
⟮c19;class files (latex⟯)|⟮c20;.cls⟯
⟮c21;windows executable⟯|⟮c22;.exe⟯
⟮c23;iCalendar⟯|⟮c24;.ics⟯
⟮c25;ruby source coude⟯|⟮c26;.rb⟯
⟮c27;rust source code⟯|⟮c28;.rs⟯
⟮c29;short for style / but are called packages⟯|⟮c30;.sty⟯
⟮c31;plaintext files (arbitrary⟯)|⟮c32;.txt⟯
⟮c33;vCard⟯|⟮c34;.vcf⟯
⟮c35;Free/busy time (iCalendar⟯)|⟮c36;.ifb (or .ifbf on macOS⟯)
⟮c37;BibTeX source file⟯|⟮c38;.bib⟯
⟮c39;arbitrary binary data⟯|⟮c40;.bin⟯
⟮c41;JSON document⟯|⟮c42;.json⟯
⟮c43;SCSS syntax source file⟯|⟮c44;.scss⟯
⟮c45;sass syntax source file⟯|⟮c46;.sass⟯
⟮c47;XML document⟯|⟮c48;.xml⟯
⟮c49;fountain source document⟯|⟮c50;.fountain⟯
⟮c51;shell script⟯|⟮c52;.sh⟯


#### binary

Binary files without a specification/documentation/parser are basically meaningless/unreadable.
What the binary files contents mean is defined by the file format.
Binary files are generally smaller and quicker to process than plaintext files

##### encoding as text

⟮c2;binary-to-text encodings⟯ represent ⟮c1;binary data⟯ with ⟮c1;plain text⟯ 
⟮c3;binary-to-text encoding⟯ is ⟮c4;inefficient⟯ but is ⟮c4;necessary⟯ to ⟮c5;send binary data over plaintext channels⟯, e.g. in ⟮c6;email⟯. 
the most common ⟮c7;binary-to-text encoding⟯ is ⟮c8;base64⟯. 
⟮c9;base64⟯ uses ⟮c10;ASCII⟯ to ⟮c11;represent binary data⟯. 
⟮c12;base64⟯ can encode ⟮c13;6⟯ bit of ⟮c14;data⟯ in ⟮c13;8⟯ bit of ⟮c14;text⟯. 
⟮c15;data URIs⟯ are a type of URI defined by ⟮c16;the data scheme⟯ that provide a way to ⟮c17;include arbitrary data inline⟯. 
⟮c18;data URIs⟯ most commonly use the ⟮c19;binary-to-text encoding base64⟯ to ⟮c20;encode their data⟯. 
data URI syntax `⟮c21;data:⟯⟮c22;[&lt;media type&gt;]⟯⟮c23;[;base64]⟯⟮c24;,&lt;data&gt;⟯` 
base64 is a command-line program to en/decode things as base64

##### bitmaps

In the technical definition, a bitmap maps some domain to some bits.
In the technical definition, a pixmap is a bitmap mapping a pixel to a set of bits.
While in the technical definition, a pixmap is a hyponym of bitmap, they also may be treated synonymously, or sometimes a bitmap is seen as a hyponym of pixmap where one uses one bit per pixel.
The common file format for a pixmap image is BMP.
Pixmap images are very large, since they don't have any compression.

##### multimedia

(multi)media files are almost always binary files

###### video/sound

Default mac japanese voice is  Kyoko

####### players

ffmpeg media player   `ffplay`

mpv|terminal based video player

mpv plays files, urls, and playlists.

Play a playlist<filename>   --playlist=&lt;filename&gt;
don't open a new video window<filename></filename>   --no-video

######## mpd mpc

mpd is short for Music Player Daemon.
mpd acts as a server, which you can start via the `mpd` command (either directly or via a service)
As a proper server, mpd occupies a port on the host.
You can interface with the mpd server with a number of clients, e.g. mpc

mpc -p port or --port=port|connect to mpd at the specified port
`mpc queue(d)`|⁑show⁑ next song
`mpc current`|show currently playing songm<br><div class="sub">
`mpc update`|update collectiion by scanning for changed files
`mpc stats`|display mpd playing info such as total play time up until now, etc.
`mpc rescan`|rescan whole music directory
`mpc lsplaylists`|list all current playlists
`mpc ls`|list the contents of the music directory
`mpc load &lt;name&gt;`|load a certain playlist
`mpc clear`|clear queue
`mpc shuffle`|reshuffle the playlist
`mpc single`|toggle single mode (will stop playing after one song, or repeat one song if repeat is toggled)
`mpc repeat`|toggle repeat
`mpc random`|toggle random playback (that is, pick songs from the queue at random)
`mpc prev`|go to previous song
`mpc playlist`|show the current playlist
`mpc pause`|pause
`mpc next`|go to next song
`mpc toggle`|play if paused, pause if playing</div>

####### processing

######## ffmpeg

ffmpeg is mainly a video/audio converter

ffmpeg-command ::= ffmpeg <global-options> <input-specifier>{ <input-specifier>} <output-specifier>{ <output-specifier>}
input-specifier ::= [<input-options>] -i <url>
output-specifier ::= [<output-options>] <url>
input-options ::= {<input-only-option><input-output-option>}
output-options ::= {<output-only-option><input-output-option>}
input-file-option-specifier ::= <input-index>:<stream-index>

ffmpeg input and stream index are zero-based

input-output-options
-ss <position>|seek to position
-to <position>|stop at position
`-preset FOO`   set the speed (and thus the effectiveness) of the encoding (values such as veryfast, medium, slow...)

###### images / combined

####### types

⟮h∞;<img src="1280px-VectorBitmapExample.svg.png">⟯
Vector images/graphics are images created directly from geometric shapes.
Vector images are contrasted wtih raster images/graphics.
Raster images are images created from a matrix/grid of square pixels. 
The main advantage of vector images being that they are infinitely scalabe.
The process of generating a raster image from a vector image is known as raserization.
Vector images are most commonly edited in dedicated vector graphics editors or text editors.
Adobe Illustrator|proprietary, desktop|.ai
Affinity Designer|proprietary, desktop|.afdesign
Inkscape|FOSS, desktop|SVG
SVG-edit|FOSS, web|SVG

######## SVG

SVG is the standard format for vector images
SVG is a subformat of XML.
SVG files have the file extension of .svg
SVG|Scalable Vector Graphics
The ⟮c16;current version of SVG⟯ is ⟮c6;1.1.⟯, with version ⟮c6;2⟯ being ⟮c7;in planning since forever⟯. 
Often, ⟮c17;SVG⟯ is ⟮c10;included in HTML⟯. This can be done by i⟮c11;ncluding it directly in the source⟯, r⟮c12;eferencing it in places the browser would normally take an image (<img>, background-image⟯), or ⟮c13;pointing to it within an <object> or an <iframe>⟯ 
⟮c14;&lt;foreignObject&gt;⟯ is an SVG element that allows you to ⟮c15;include non-SVG XML⟯, most commonly ⟮s15;⟮c8;HTML⟯⟯. 


########## affinity designer

flex-container:⟮h∞;<img src="sm_Screenshot%202020-04-05%20at%2018.40.27.jpg">⟯

To ⟮c2;select a color in affinity designer⟯ (must be in ⟮c3;Pixel Persona⟯) ⟮c1;Select &gt; Select Sample Color⟯ 
To ⟮c4;turn a color transparent⟯ in affinity designer ⟮c5;select a color, then delete it with backspace⟯ 

####### viewers

feh|terminal-launched image viewer
imgcat|in-terminal image viewer

####### processing

unpaper cleans/post-processes scanned pages
pdftk and qpdf are the most common CLI tools for pdf transformation
gifsicle is a CLI program to manipulate gifs
remove.bg is an AI tool that can remove the bg of images with people in them.
remove.bg is accessible via an API as well, which can be called via a command `removebg`

######## ocrmypdf

`⟮c9;ocrmypdf⟯` is a command line tool to ⟮c10;add OCR text to scanned PDF files⟯. 
```
ocrmypdf ⟮c11;SOURCE DEST⟯
```
⟮c1;specify language⟯|⟮c2;`-l deu/fra/deu+fra...`⟯
⟮c3;correct slight skew⟯|⟮c4;`--deskew`⟯
⟮c5;clean pages before ocring⟯|⟮c6;`--clean`⟯
⟮c7;change/correct rotation (the one in steps of 90°⟯)|⟮c8;`--rotate-pages`⟯


######## imagemagick

⟮c31;Imagemagick⟯ is ⟮c32;a set of programs⟯ for ⟮c33;modifying images.⟯ 
⟮c34;Imagemagick⟯ mainly exists as ⟮c35;a cli⟯, has ⟮c36;a basic X window gui⟯, and ⟮c37;API bindings⟯ for ⟮c38;pretty much any programming language under the sun⟯. 
⟮c39;imagemagick⟯ contains ⟮c40;a bunch of subcommands⟯, which ⟮c41;do different things⟯ but ⟮c42;often accept similar arguments⟯ 
imagemagick options/arguments ⟮c43;start with a single dash,⟯ regardless of length 
All imagemagick subcommands may be ⟮c44;prefixed by magick (e.g. magick mogrify, magick animate⟯) or ⟮c45;not⟯. 
The main two commands for ⟮c46;image conversion⟯ w/ ⟮c47;imagemagick⟯ are ⟮c48;mogrify⟯ ⟮(c:49;in-place⟯) and ⟮c48;convert⟯ ⟮(c:49;out-of-place⟯) 
Many of imagemagicks arguments needing to specify ⟮c50;some kind of shape/size⟯ accept a ⟮c51;geometry⟯ argument with the syntax ⟮c52;&lt;size&gt;⟯⟮c53;[&lt;offset&gt;]⟯ where the size specifier follows the syntax 
⟮c54;&lt;width&gt;⟯⟮c55;x⟯⟮c54;&lt;height&gt;⟯⟮c56;[&lt;operator&gt;]⟯ 



table:span=2;Imagemagick subcommands
⟮c1;`import`⟯|⟮c2;Imagemagick screenshot utility⟯
⟮c3;`identify`⟯|((c:4;::Imagemagick display details of an image file
```lang=text;
magick identify -verbose rose.jpg
Image: rose.jpg
  Format: JPEG (Joint Photographic Experts Group JFIF format)
  Mime type: image/jpeg
  Class: DirectClass
  Geometry: 70x46+0+0
  Units: Undefined
  Type: TrueColor
...
```
))
⟮c5;`display`⟯|⟮c6;Imagemagick image viewer⟯
⟮c7;`animate`⟯|⟮c8;Imagemagick animation creator⟯
⟮c9;`compare`⟯|⟮c10;Imagemagick visual comparison tool<img src="sm_paste-ebe2143588b596e4c4762fa1d4f79aaad9bf0665.jpg">⟯
⟮c11;`composite`⟯|⟮c12;Imagemagick overlay image tools<img src="sm_paste-941c2b6b4528410451a2670256f0499b19879054.png">⟯
⟮c13;`convert`⟯|⟮c14;Imagemagick convert between image formats<img src="sm_paste-8ba1c45c2dc3cc0f2cd231dfec641b7b7e64e382.jpg">⟯
⟮c15;`montage`::m⟯|⟮c16;Imagemagick montage creator<img src="sm_paste-65d507ceb80556af17e0f02061e7f7f54fc9e73d.jpg">⟯




table:span=2;Imagemagick options
⟮c17;`-crop`⟯|⟮c18;crop⟯
⟮c19;`-trim`⟯|⟮c20;remove borders around the image⟯
⟮c21;`-resize SIZE-SPECIFIER`⟯|⟮c22;resize the image to SIZE-SPECIFIER⟯
⟮c23;`-quality QUALITY`⟯|⟮c24;set the (e.g. jpeg) quality to QUALITY (1-100 for jpeg⟯)
⟮c25;`-fuzz distance`⟯|⟮c26;make matching colors more, well, fuzzy⟯
⟮c27;`-flop`⟯|⟮c28;Mirror along the y-axis (in x direction, text will be mirrored L&lt;-&gt; R⟯)
⟮c29;`-flip`⟯|⟮c30;Change to upside down⟯


#### plaintext

##### utilities

###### output/info

cat|output a file
tac|cat, but reversed line-by-line
wc|count words, characters and lines

wc output ordering
⟮c1;lines⟯ ⟮c2;words⟯ ⟮c3;characters⟯

bat is a more fancy version of cat with auto syntax highlighting, line numbers, git integration etc. implemented in rust.

###### editors

a stream editor is a filter used to do text transformations
a line editor is a stream editor that applies its commands to some or all of the lines.
original line editor for linux: ed
ex was a line editor then based on ed.
In contrast to sed, ed -> ex could be used both interactively and noninteractively
sed was based of the noninteractive features of ed.
vi was based on the interactive features of ex.
vim is a more-reature rich of vi.
nvim is a refactor of vim which aims to be even more feature rich
nvim = neovim
To a large extent, nvim is backwards compatible with vim
To a large extent, vim is backwards compatible with vi.
vi/vim/nvim is largely mode-based.

sed claims to be a stream editor, but is more specifically a line editor.

sed <options> <command> {<file>}
command ::= [<addr>]<command-char>[<options>]
addr ::= <int-or-regex>[,<int-w-op-or-regex>[!]]
int-or-regex ::= <int>|/<regex>/
int-w-op-or-regex ::= ([<operator>]<int>)|(<regex-delim-start><regex><regex-delim-end>)
regex-delim-start ::= /|\\<char>
regex-delim-emd ::= /|<char>

sed command-char|function|options
s|regex
y|char transliteration|/{<char>}/{<char>}/|replace any of the first chars with the corresponding char in the second set of chars| transliterate ‘a-j’ into ‘0-9’: 'y/abcdefghij/0123456789/'

sed's y/... command is similar to the standalone program tr.
Ruby and Perl have a string method tr that works similar to sed's y/... / the program tr.

For sed, specifying a regex within an addr selects lines that match the regex
For sed, using the \<char> syntax as a regex starting delimiter must then continue using <char> as a delimiter, allowing one not to have to escape \

nano|basic cmd-line text editor

###### basic filters

lolcat   make output rainbowy
cowsay   make an ascii cow say the specific thing
sort|sort file line by line
-n sort by order of magnitude
uniq|remove adjacent (!) matching lines
cut|extract specific sections of each line based on delimiters
-f <list>|only extract fields <list>
-d <char>|treat <char> as delimiter
nl|number lines
rev|reverse each line of a file ('horizontally\)

The commands head and tail print the first/last few lines of a file.
The amount of lines printed by head/tail defaults to 10

###### pandoc

Pandoc is a haskell-based powerful converter between text-based formats.
By default, pandoc acts as a filter.
Pandoc readers convert documents to an AST.
Pandoc filters modify the AST.
Pandoc writers convert its ASTs to a specific format.
Only features supported by pandoc markdown are guaranteed to survive pandoc conversion

The behavior of some of the readers and writers can be adjusted by enabling or disabling various extensions.
for pandoc extensions, + enables it and - disables it.
pandoc-format-specifier ::= <pandoc-format>{(+|-)<pandoc-extensions>}

-s/--standalone produces valid standalone files such as HTML by adding header & footer material via a specified template.

By default pandoc creates an output pdf by using latex as an intermediary, you can change this behavior with --pdf-engine.


###### generation

fortune|display a random fortune

yes[ <string>]
yes outputs y or <string> until killed.
yes can be used to e.g. provide always answer yes for whatever a script asks by using yes | ...

##### types

Markup files are subset of plaintext files.
Markup files are written in markup languages.
markup languages consist of normal text and specific markup, which are intermingled.

###### markup

####### across languages

bold (no importance impl)|\textbf{} (though there are others)|&lt;b>|**text** or __text__
italic (no importance impl)|\textit{}|&lt;i>|*text* or _text_
emphasize (generally via italics)|\emph{}|&lt;em>|N/A
strongly emphasize||<strong>|N/A
underline|\underline{}|&lt;u>|N/A
strikethrough foo (whithout special semantics)|different ones in packages|&lt;s>foo&lt;s>|~foo~ or ~~foo~~ (most md flavors)
hyperlink link with title title|\href{link}{title}|&lt;a href="link">title&lt;/a>|[title](link)
hyperlink link with title link|\url{}|&lt;a href="link">link&lt;/a>|[link](link)
block quotation of foo|quote, quotation, or verse environment|&lt;blockquote>&lt;/blockquote>|`>foo` or `> foo` (space after > is optional)
Inline quotation of foo|\enqote{foo} (package csquotes)|&lt;q>foo&lt;/q>
inline source code||&lt;code>|``
create a newline|\\ or \newline|&lt;br>| two spaces or \&lt;newline character>
Heading (level one) "foo"|relevant section command|&lt;h1>foo&lt;/h1>|# foo or foo\n===(number doesn't matter)
Heading (level two) "foo"|relevant section command|&lt;h2>foo&lt;/h2>|## foo or foo\n---(number doesn't matter
Heading (level three) "foo"|relevant section command|&lt;h3>foo&lt;/h3>|### foo 
Heading (level six) "foo"|relevant section command|&lt;h6>foo&lt;/h6>|###### foo 
A code block foo||&lt;pre>&lt;code>foo&lt;/code>&lt;/pre>| originally a block indented by four spaces and separated by newlines, but most flavors now have fenced code blocks, which are done like ``` or ~~~(or more)\nfoo\n``` or ~~~
a paragraph foo|\par{foo}|&lt;p>foo&lt;\p>|\n\npar\n\n (uses blank lines)
image with url/source Asuka and alt text best girl|\includegrapics{Asuka} (no alt text possible)|&lt;img src="Asuka" alt="best girl">|![best girl](Reina)
horizontal line|\rule (or \hrule, but both take arguments)|&lt;hr>| three or more *** ___ --- 
superscript text foo|^{foo}|&lt;sup&gt;foo&lt;/sup&gt;
subscript text foo|_{foo}|&lt;sub&gt;foo&lt;/sub&gt;
indicate a variable semantically||<var>
keyboard input||<kbd>
sample output||<samp>
title of a cited work||『
preformatted text that is to be presented exactly as written||<pre>

using \url{} or \href{} requires the package hyperref in Latex
package hyperref also does autolinking to things such as the TOC

strike is similar to &lt;s>, but obsolete
&lt;tt> used to indicate teletype text, but is now obsolete
&lt;big> used to indicate big text, but is now obsolete; however &lt;small> still works.
&lt;center> used to indicate centered text but is now obsolete

most text markup languages (HTML, Latex, md) will ignore duplciate spaces.
most text markup languages (HTML, Latex, md) will transform newlines into a single space unless otherwise indicated.

In fountain, in contrast to markdown, only * and ** do italic/bold, _ is reaserved for underlined


i|italic|conventionally italic
em|italic|more important
b|bold|conventionally bold
strong|bold|super important
u|underline|has non-textual annotation of some kind
mark|yellow highlighter|highlighted ≈ area of interest
 

non-breaking space|\nonbreakspace or ~|&amp;nbsp;
ampersand||&amp;amp;
non-breaking hyphen|"~
soft hyphen|\- (only hyphtenates in indicated location) "- (allows hyphenation in other places in the word)|&amp;shy;&amp;#8203;
"=
if you want a word ⟮c3;with a hyphen⟯ to be ⟮c2;able to be split anywhere⟯ (using babel ngerman), use ⟮c1;"=⟯
zero-width space||<wbr> or &amp;#8203;

hyperref|create links automatically and \href, \url commands


nested blockquotes| `>>` or `> > `(space after > to begin blockquotes is optional)

Pandoc md is a superset of most other markdown flavors
Pandoc md defaults to tilde-delimited code blocks.
In pandoc md, you can specify heading identifiers to contain things such as classes, ids, etc
pandoc-md-heading ::= #{#} &lt;title> [\{{<class>|<id>|...}\}]


RTF|Rich Text Format

####### tex, especially latex

⟮c3;Tex⟯ consists of ⟮c1;tex-core⟯ and ⟮c2;plain-tex⟯ 
⟮c4;plain-tex⟯ is ⟮c5;the set of macros that the tex typsetting program uses⟯; ⟮c6;tex-core⟯ is ⟮c7;the typesetting program (that transforms it into output⟯) 
⟮c8;Tex⟯ and thus ⟮c8;latex⟯ is meant for ⟮c9;typesetting⟯ 
⟮c13;TeX⟯ and thus ⟮c13;LaTeX⟯ mainly work via ⟮c14;macros⟯ 
⟮c15;Mathjax⟯ renders ⟮c16;a subset of latex⟯ ⟮c17;in browsers (using js⟯) 
⟮c18;current⟯ latex version: ⟮c19;Latex 2e⟯ 
⟮c20;next⟯ latex version: ⟮c21;Latex 3⟯ 
<q>latex</q> is properly capitalized ⟮c22;LaTeX⟯ 
<q>tex</q> is properly capitalized ⟮c23;TeX⟯ 
the x in ⟮c24;tex and latex⟯ is pronounced as ⟮c25;a voiceless velar fricative (e.g. loch, bach⟯) 

⟮c10;latex⟯ is ⟮c11;a set of tex macros⟯ that is supposed to be ⟮c12;more semantic⟯. 
texinfo is a set of macros for tex for generating hypertextual documentation

info|read texinfo files

######## Commands

A typical ⟮c5;command⟯ looks ⟮c1;⟯⟮c3;name⟯⟮c2;{⟯⟮c4;argument⟯⟮c2;} ⟯ 
a ⟮c9;command⟯'s ⟮c10;required arguments⟯ (AKA ⟮c11;arguments⟯) are ⟮c12;delimited by {⟯} 
a ⟮c6;command's⟯ ⟮c7;optional arguments⟯ (AKA ⟮c8;options⟯) are ⟮c13;delimited by []⟯ 
{{c14::}} ⟮c15;starts⟯ ⟮c16;a command⟯ 
Generally, ⟮c17;commands⟯ take ⟮c18;the thing they act on⟯ ⟮c19;as a required argument⟯. 
⟮c20;Some commands⟯ instead ⟮c21;apply to anything⟯ ⟮c22;following the command⟯ ⟮c23;until the end of environment or group⟯, these are known as being in ⟮c24;declaration form⟯. 

⟮c28;The name⟯ ⟮c29;of a command⟯ ⟮c30;used as an environment⟯ is known as that commands ⟮c31;environment form⟯ 
the ⟮c26;environment form⟯ of ⟮c27;\foo⟯ would look like {{c25::`\begin{command}...\end{command}`}} 
⟮c32;Most (afaik) commands⟯ in ⟮c33;declaration (\command (no args⟯)) form can also be used  ⟮c26;in an environment form⟯ 
⟮c34;The environment form⟯ of a command is based on ⟮c35;its declaration form.⟯ 

######### new commands

To ⟮c1;create a new command⟯, use ⟮c2;\newcommand⟯, which goes in ⟮c3;the preamble⟯ 
⟮c4;\newcommand⟯ has the syntax: ⟮c4;\newcommand⟯⟮c9;{&lt;name&gt;⟯}⟮c10;[&lt;number-of-arguments&gt;]⟯⟮c11;{&lt;latex-code-to-execute&gt;⟯} 
Within ⟮c7;\newcommand⟯, you ⟮c8;refer to arguments⟯ ⟮c6;positionally⟯ with ⟮c5;#n⟯ 
⟮c12;\newcommand{\euler}{\mathrm{e}⟯ makes ⟮c13;\euler output \mathrm{e}⟯ 
```
\newcommand{\abs}[1]{\left|#1\right|}
```

######## Sections

Latex ⟮c11;sections⟯ ⟮c12;go until⟯ ⟮c13;the beginning of the next section⟯ 
Latex sections are declared via ⟮c14;command. (e.g. \part⟯) 
Latex ⟮c15;section commands⟯ take ⟮c16;the full section title⟯ as ⟮c10;a mandatory argument⟯ and ⟮c16;a short title (e.g. for TOC⟯) as ⟮c10;an optional argument⟯. 
± \subsection[shortitle]{This is the full title} ±<br>
⟮c8;Article⟯ notably does not havet the ⟮c9;\chapter⟯ section command. 

######### Latex section hierarchy

1. ⟮c1;sb;part⟯
2. ⟮c2;sb;chapter⟯
3. ⟮c3;sb,6-7;section⟯
4. ⟮c4;sb,6-7;subsection⟯
5. ⟮c5;sb,7;subsubsection⟯
6. ⟮c6;sb;paragraph⟯
7. ⟮c7;sb;subparagraph⟯

######## latex groups

in Latex, ⟮c2;groups⟯ ⟮c1;create a scope⟯ 
`⟮c3;\bgroup ... \egroup⟯` or ⟮c4;`{ ... }`⟯ ⟮c5;delimit a group⟯ 

######## latex labels and refs

In latex, using ⟮c8;\label⟯ you ⟮c9;define a marker⟯, which ⟮c10;you can then later reference⟯. 
the main advantages of ⟮c11;using labels⟯ in latex instead of ⟮c12;manually referring to the indices of the things⟯ is that ⟮c13;they auto-update⟯ 
⟮c19;\label⟯ takes ⟮c21;an argument⟯ of ⟮c20;the name of the marker.⟯ 
⟮c18;\label⟯ goes ⟮c14;within⟯ ⟮c16;the thing being labeled⟯ as ⟮c17;the first thing⟯ if ⟮c14;there is a 'within'⟯, and ⟮c15;after⟯ otherwise. 
It is common practice to ⟮c22;prefix the name of the marker⟯ with a ⟮c23;most often 3-character⟯ ⟮c24;abbreviation⟯ of ⟮c25;the type of the marker⟯ plus ⟮c26;a colon⟯ 
± \label{sec:foo} ±<br>

abbr|for
⟮c1;eq⟯|⟮c2;equation⟯
⟮c3;sec⟯|⟮c4;section⟯
⟮c5;fig⟯|⟮c6;figure⟯


In latex, you can ⟮c27;reference markers⟯ defined with ⟮c28;\label⟯ with ⟮c29;\ref⟯, ⟮c30;\pageref⟯ or ⟮c31;\eqref⟯. 

command|refers to?|from package
⟮c7;\ref{foo}⟯|⟮c8;returns the index of foo⟯
⟮c9;\pageref{foo}⟯|⟮c10;returns the page on which foo is found⟯
⟮c11;\eqref{foo}⟯|⟮c12;returns the index of foo, but surrounded by parentheses⟯|⟮c13;amsmath⟯


######## Lengths

######### rigid and rubber

The two types of lengths ⟮c5;latex⟯ has are ⟮c6;rigid lengths⟯ and ⟮c6;rubber lengths⟯. 
a ⟮c7;rubber length⟯ is a length that ⟮c8;⁑can⁑ shrink or grow⟯ 
a ⟮c9;rigid length⟯ is a length that ⟮c10;will not shrink or grow⟯ 
Lengths in latex are ⟮c16;rigid⟯ by ⟮c17;default⟯ 
⟮c11;rubber lengths⟯ can ⟮c12;only shrink or grow⟯ by ⟮c13;the length we specified⟯ 
⟮c14;plus &lt;length&gt; ∨ minus &lt;length&gt;⟯ indicate ⟮c15;a rubber length⟯ 

indicator|meaning
⟮c1;plus &lt;length&gt;⟯|⟮c2;length can grow by that amount⟯
⟮c3;minus &lt;length&gt;⟯|⟮c4;length can shrink by that amount⟯


```
 \blackbar{101pt}\hspace{100pt minus 2pt}\blackbar{101pt}}YYY
```


######### creating lengths

To ⟮c1;create a length foo⟯, you first have to ⟮c2;declare it⟯ with ⟮c3;\newlength{\foo⟯} and then ⟮c2;initialize it⟯&nbsp; ⟮c4;with \setlength{\foo}{bar⟯}. 
⟮c5;\setlength⟯ can also be used to ⟮c6;change the value⟯ of ⟮c7;preexisting length keywords⟯. 
If you ⟮c8;change the value of preexisting length keywords with \setlength⟯, ⟮c9;things that use these lengths itnernally⟯ will also change. 
⟮c11;\parindent⟯|⟮c12;represents length of first line in paragraph indentation⟯
⟮c13;\parskip⟯|⟮c10;represenets the vertical distance between paragraphs⟯



######## math

######### packages

the package ⟮c1;amsmath⟯ contains ⟮c2;a bunch more stuff related to math⟯. 
the package ⟮c3;mathtools⟯ is ⟮c4;a superset of⟯ ⟮c5;amsmath⟯, and also ⟮c6;fixes some of its bugs⟯ 
the package ⟮s9-10;⟮c7;amssymb⟯ ⟮c8;adds more math symbols⟯⟯; the package ⟮s7-8;⟮c9;amsthm⟯ ⟮c10;adds more theorem/proof related stuff⟯⟯. ⟮c11;these both⟯ ⟮c12;need to be separately loaded from amsmath/mathtools⟯ if desired. 

######### environments

Fundamentally, ⟮c7;math⟯ in LaTeX is always ⟮c8;contained in its own environment.⟯ 
There are ⟮c9;two types of math environments⟯ in ⟮c10;LaTeX⟯, ⟮c11;displayed (block in CSS terms⟯) and ⟮c12;inline⟯. 
There exists ⟮c15;a basic built-in environment⟯ for ⟮c13;both&nbsp;types of math environments⟯, ⟮c14;displayed⟯ and ⟮c14;inline⟯. 
The ⟮c16;basic built-in version⟯ of ⟮c17;both types of math environment⟯ has ⟮c18;a shorthand⟯ ⟮c19;derived from TeX⟯ which  is ⟮c20;now deprecated⟯. 
The ⟮c21;TeX derived⟯ ⟮c22;shorthands⟯ for ⟮c23;the built-in math environments⟯ involves ⟮c24;using the $ character⟯. 
The basic built-in version of both types of math environment has a shorthand exclusive to LaTeX whose use is encouraged. 
The ⟮c25;LaTeX-exclusive⟯ ⟮c26;shorthands⟯ for ⟮c27;the built-in math environments⟯ involves ⟮c28;using escaped parentheses\bracket characters.⟯ 

environment name|TeX shorthand|LaTeX shorthand
⟮c1;math⟯|⟮c2;$...$⟯|⟮c3;\​(...\​⟯)
⟮c4;displaymath⟯|⟮c5;$$...$$⟯|⟮c6;\​[...\​]⟯


⟮c29;amsmath/mathtools⟯ adds a bunch more ⟮c30;displayed⟯ ⟮c31;math environments⟯. 
For the ⟮c32;amsmath/mathtools environments⟯ there are often ⟮c34;two versions⟯, ⟮s34;one ⟮c33;with a star⟯ and ⟮c33;one without⟯⟯. 
⟮c35;amsmath/mathtools environments⟯ ⟮c37;w/o a star⟯ are ⟮c36;numbered⟯, ⟮c37;w/ a star⟯ they are ⟮c36;not numbered⟯. 

environment|name|image
⟮c41;equation/equation*⟯|⟮c42;same as displaymath (added to have numbered version⟯)
⟮c38;gather/gather*⟯|⟮c39;center-align lines⟯|⟮h39;<img src="sm_2021-05-18--15-11-30-screenshot.png">⟯
⟮c40;multline/multline*⟯|⟮c43;first line left-aligned, then all center-aligned, final line right-aligned⟯|⟮h43;<img src="sm_2021-05-18--15-16-19-screenshot.png">⟯


The ⟮c38;align/align* environment⟯ aligns ⟮c39;parts of the equation⟯ ⟮c40;vertically⟯ in relation to ⟮c41;the anchor⟯, which is the ⟮c42;&amp; symbol⟯ 
⟮c43;split⟯ is ⟮c44;the same as⟯ ⟮c45;the align environment⟯, but ⟮c46;within the equation environment⟯&nbsp;

the ⟮c47;autobreak⟯ environment contained in ⟮c49;the eponymous package⟯ ⟮c48;auto inserts linebreaks into formulae⟯ 
In ⟮c50;the autobreak environment⟯, ⟮c51;any newline⟯ is treated as ⟮c52;a possible point to break⟯ 
⟮c52;proof⟯ provides ⟮c53;an environments for proofs⟯ 
the ⟮c54;cases environment⟯ renders ⟮c55;multiple lines⟯ with ⟮c56;an extensible left curly-brace⟯ for ⟮c57;piecewise-defined functions⟯ 

⟮h∞;<img src="sm_CkJlF.png">⟯


######### newtheorem

\newtheorem is used in the document preamble
⟮c7;\newtheorem⟯ ⟮c8;creates a new theorem envronment⟯ 
⟮c9;\newtheorem⟯ takes ⟮c10;two arguments, and one option⟯. 
⟮c1;The first argument to \newtheorem⟯|⟮c2;the name of the environment that we create by the call to \newtheorem (i.e. how we will refer to it later⟯)
⟮c3;The second argument to \newtheorem⟯|⟮c4;The heading that the environment that we create by the call to \newtheorem will have⟯
⟮c5;The option of \newtheorem⟯|⟮c6;based on what the theorem will be numbered⟯


For ⟮c13;\newtheorem⟯, if ⟮c12;[foo]⟯ occurs {{c11::between the two {args} }}, it is ⟮c14;a reference to another theorem⟯ -&gt; ⟮c14;with which it will share numbering⟯ , if it occurs {{c11::after the two {args} }}, it is ⟮c15;a reference to a section⟯ -&gt; ⟮c15;under which it will be numbered⟯ 

```
\newtheorem{theo}{Theorem}
...
\begin{theo}
```


######## Symbols

######### case-changed symbols

For arrows, if the ⟮c1;first letter⟯ is ⟮c2;lowercase⟯, it will render the ⟮c3;thin arrow (→⟯), if the ⟮c1;first letter⟯ is ⟮c2;uppercase⟯, it will render the ⟮c3;thick arrow (⇒⟯). 
so `⟮c9;\right/left/up/downarrow⟯` renders ⟮c10;a thin right arrow →⟯, and ⟮c9;\Right/Left/Up/Downarrow⟯ renders ⟮c10;a thick, double-line right arrow ⇒⟯. 
the four directional arrows are created by \right/left/up/downarrow
⟮c11;\rightarrow⟯ can also be created by ⟮c12;\to⟯ 
⟮c13;\Rightarrow⟯ can also be created by ⟮c14;\implies⟯ 
For greek letters, if the ⟮c4;first letter⟯ is ⟮c5;lowercase⟯, it will render the ⟮c6;lowercase letter⟯, if the ⟮c4;first letter⟯ is ⟮c5;uppercase⟯, it will render the ⟮c6;uppercase letter⟯. 
so ⟮c7;\pi⟯ ⟮c8;inserts a lowercase pi π⟯ and ⟮c7;\Pi⟯ ⟮c8;inserts an uppercase pi Π⟯ 

######### logic symbols

symbol|command(s)|requires package
⟮c1;∧⟯|⟮c4;s5;\land⟯ ⟮c5;s4;\wedge⟯
⟮c2;∨⟯|⟮c3;s6;\lor⟯ ⟮c6;s3;\vee⟯
⟮c3;¬⟯|⟮c7;s8;\lnot⟯ ⟮c8;s7;\neg⟯
⟮c9;∴⟯|⟮c10;\therefore⟯|amssymb

######### set symbols

\supset|⊃
\supseteq|⊇
\supsetneq|⊋
\subset|⊂
\subseteq|⊆
\subsetneq|⊊
\cup|∪
\cap|∩
⟮c7;\in⟯|⟮c8;set membership⟯
⟮c7;\notin⟯|⟮c8;negation of set membership⟯
⟮c7;\ni|⟮c8;reversed set membership symbol⟯
∖|set difference/relative complement
⟮c25;\o⟯|⟮c26;ø⟯

######### comparison operators

⟮c17;\leq⟯|⟮c18;≤⟯
⟮c19;\geq⟯|⟮c20;≥⟯
⟮c21;\approx⟯|⟮c22;≈⟯

######### various symbols


command|symbol
⟮c1;\LaTeX⟯|⟮c2;insert the latexlogo⟯


\times|×


⟮c3;\ldots⟯|⟮c4;an ellipsis on the baseline …⟯
⟮c5;\cdots⟯|⟮c6;an ellipsis slightly below the midline ⋯⟯




⟮c23;\infty⟯|⟮c24;∞⟯
\prime|′ (the prime)
\degree|°


⟮c9;\dots⟯ ⟮c10;is equivalent to \ldots⟯ in ⟮c11;vanilla latex⟯. 
If using ⟮c12;amsmath⟯ and ⟮c13;within math mode⟯, ⟮c14;\dots⟯ ⟮c15;decides between \ldots and \cdots⟯ ⟮c16;based on context⟯ 

######## language & encoding

Package|Function
⟮c1;babel⟯|⟮c2;foreign language support⟯
⟮c3;fontenc⟯|⟮c4;output character encoding⟯
⟮c5;inputenc⟯|⟮c6;input character encoding⟯


######## beginning of document

⟮c16;Latex commands⟯ are ⟮c17;either defined in the .cls file⟯ (and thus ⟮c18;you can use them by default⟯) or ⟮c19;in packages⟯. 

The ⟮c20;first statement⟯ in a latex document must be  ⟮c21;\documentclass⟯ 
⟮c22;The required argument⟯ of ⟮c23;\documentclass⟯ is ⟮c24;the document clas⟯s 
calling {{c14::\documentclass{foo} }} ⟮c15;loads foo.cls⟯ in the background 
⟮c25;The optional argment⟯ of ⟮c26;\documentclass⟯ contains ⟮c27;global options such as font size, orientation, paper size...⟯ The part of the document between {{c11::\documentclass{...} and \begin{document}}} is ⟮c28;the preamble⟯ ⟮c29;\usepackage⟯ is used to ⟮c30;import a package and thus its commands⟯. 


⟮c31;Any \usepackage declarations⟯ must go in ⟮c32;the preambl⟯e. 
⟮c12;\RequirePackage⟯ is like ⟮c13;\usepackage⟯, with the dif that it can be used ⟮c1;before \documentclass⟯ and ⟮c33;is really only used by people writing packages/classes⟯ 

⟮c34;The document environment⟯ contains ⟮c35;the entire document (anything that will be visible⟯) 
⟮c36;after \begin{document⟯} there is often ⟮c37;a set of commands⟯ setting ⟮c38;metadata⟯ called ⟮c39;the top matter/topmatter⟯ 
⟮c1;\abstract⟯|⟮c2;set the abstract of e.g. the paper⟯
⟮c3;\author⟯|⟮c4;set document author⟯
⟮c5;\date⟯|⟮c6;set document date⟯
⟮c7;\title⟯|⟮c8;set document title⟯
⟮c9;\and⟯|⟮c10;separating multiple authors within \author⟯


⟮c40;\maketitle⟯ then ⟮c41;renders top matter⟯ into ⟮c42;the title page⟯ 




######## document classes and their specific features

######### beamer

The ⟮c8;documentclass⟯ for ⟮c7;creating presentations⟯ is ⟮c9;beamer⟯. 
The highest-level division of ⟮c10;beamer⟯ is ⟮c11;the frame⟯. 
A beamer ⟮c12;frame⟯ can be defined ⟮c13;by command or as an environment⟯ 
⟮c14;Frames⟯ ⟮c15;may consist of multiple⟯ ⟮c16;slides⟯. 
⟮c17;\pause⟯ inserts a ⟮c18;breakpoint⟯ into the frame, creating a ⟮c20;first slide⟯ ⟮c19;with all the content up to⟯ the ⟮c18;breakpoint⟯, and a ⟮c20;second slide⟯ ⟮c19;which also contains the contents after⟯ the ⟮c18;breakpoint⟯ 
⟮c21;\frametitle{foo⟯} ⟮c22;sets foo as the title of the frame⟯ 

l⟮c24;atex presentations⟯ are ⟮c25;styled⟯ via ⟮c23;themes⟯ 
The kind of themes that latex presentations can have are ⟮c31;presentation⟯, ⟮c32;color⟯, ⟮c33;font⟯, ⟮c34;inner⟯, ⟮c35;outer⟯ 
⟮c26;the elements inside of a frame (enumerations, blocks, theorems, etc⟯) are styled via ⟮c28;inner themes⟯ 
⟮c27;the elements outside of a frame (headers, footers, etc.⟯) are styled via ⟮c29;outer themes⟯ 
⟮c30;Setting themes⟯ is done via ⟮c36;the \usetheme command⟯ 

⟮c37;Overlay specifications⟯ specify ⟮c38;which slides⟯ to ⟮c39;apply a command to⟯, or ⟮c38;on which slides⟯ ⟮c40;to show a thing⟯ 
⟮c41;Overlay specifications⟯ are written ⟮c42;&lt;some_number/list/range&gt;⟯ 
± \item&lt;-2,4-5,7&gt; ±<br>
⟮c43;\only⟯⟮c44;&lt;overlay-spec&gt;{text⟯}: ⟮c47;only render the text⟯ ⟮c49;on the specified slides⟯ 
⟮c45;\uncover⟯⟮c46;&lt;overlay-spec&gt;{text⟯}: ⟮c48;only render the text⟯ ⟮c50;on the specified slides,⟯ but ⟮c51;still take up space on the other slides⟯&nbsp;

⟮h∞;<img src="sm_L5.png">⟯

When using the ⟮c54;beamer⟯ class, you can use ⟮c52;modes⟯ to ⟮c53;only do things in certain circumstances (handout, presentation, slide notes etc.⟯) 
Command to ⟮c71;only do something in a certain mode⟯ ⟮c55;mode⟯⟮c56;&lt;⟯⟮c59;certain_mode⟯⟮c56;&gt;⟯⟮c57;{⟯⟮c58;things to do⟯⟮c57;} ⟯ 
Latex beamer modes
onion-box:[all [presentation [⟮c3;s1-2;beamer⟯][⟮c4;s1-2;second⟯][⟮c5;s1-2;handout⟯][⟮c6;s1-2;trans⟯]][⟮c1;article⟯]]

⟮c52;\institute⟯ ⟮c53;sets document institute (e.g. TU Fak. 1⟯) (exclusive to ⟮c54;beamer⟯) 

⟮c61;\titlepage⟯ is ⟮c62;functionally equivalent⟯ to ⟮c63;\maketitle⟯, but ⟮c60;will insert a missing frame if necessary⟯ 
⟮c55;block⟯ is ⟮c56;an environment⟯ representing ⟮c57;a text box⟯ in latex ⟮c58;beamer⟯, taking ⟮c59;an additional argument⟯ of ⟮c60;its title⟯ 
the ⟮c61;columns environment⟯ allows ⟮c62;a multicolumn setup⟯ in latex ⟮c70;beamer⟯  
⟮c63;within the columns environment of beamer⟯, ⟮c64;\column{foo⟯} ⟮c65;inserts a column of width foo⟯. 
⟮c66;theorem⟯ is an ⟮c67;environment⟯ that ⟮c68;delimits a theorem⟯ ⟮(c:69;beamer⟯ only) 
flex-container:⟮h∞;<img src="sm_Beamerblock.png">⟯⟮h∞;<img src="sm_Beamercolumns.png">⟯⟮h∞;<img src="sm_Beamermaths.png"> ⟯

######### KOMAScript

⟮c9;KOMA-script⟯ is ⟮c10;a bundle of classes⟯ generally more ⟮c11;versatile⟯ than ⟮c11;builtin equivalents⟯ (if ⟮c12;even  extant⟯). 
⟮c13;KOMAoptions⟯ allows you to ⟮c14;set a bunch of options⟯ ⟮c15;of koma script classes⟯ 
variant of ⟮c16;article class⟯ ⟮(c:18;KOMA-script⟯): ⟮c17;scrartcl⟯ 

class for ⟮c20;letters⟯ ⟮(c:19;KOMA-script⟯):⟮c21;scrlttr2⟯ 
changing the scrlttr2 template can be can be done the option [] to \documentclass{scrlttr2} 
⟮c25;Setting variables⟯ for ⟮c23;koma script templates⟯ (but seemingly actually only used for ⟮c24;scrlttr2⟯): ⟮c25;setkomavar⟯{{c26::{key}{val} }} 
⟮c22;Set the date of a scrlttr2 letter to today⟯: {{c27::\setkomavar{date}{\today}}} 
⟮c28;Set the subject of a scrlttr2 letter to Ceterum censeo carthaginem...⟯:{{c29::\setkomavar{subject}{Ceterum censeo carthaginem...}}} 
⟮c30;.lco⟯ files are ⟮c31;regular .tex⟯ files, but are used as ⟮c32;scrlttr2 templates⟯ 
The ⟮c33;actual body of a letter⟯ using ⟮c34;scrlttr2⟯ is indicated by ⟮c35;the letter environment⟯. It may ⟮c36;recieve a second argument⟯ of ⟮c37;the target address⟯ 


headerrows=2;span=2;Within the scrlttr2 letter environment
command|effect
⟮c1;\closing{foo}⟯|⟮c2;set the closing line (e.g. Best wishes, ) to foo⟯
⟮c3;\opening{foo}⟯|⟮c4;set the opening line (e.g. Dear Mrs. Soandso, ) to foo⟯
⟮c5;\encl{foo}⟯|⟮c6;define things that are enclosed (attachments⟯)
⟮c7;\ps⟯|⟮c8;define a postscript⟯



######## text formatting

⟮c1;centering⟯ is a ⟮c2;declaration form command⟯ that ⟮c3;centers content⟯. 
⟮c4;center⟯ is ⟮c5;an environment⟯ that ⟮c6;centers content⟯. 

######### text sizes

1. tiny
2. scriptsize
3. footnotesize 
4. small 
5. normalsize
6. large
7. Large
8. LARGE
9. huge
10. Huge

######## compilation

⟮c22;pdf(la)tex⟯ ⟮c23;compiles⟯ ⟮c24;(la)tex to pdf⟯ 
⟮c1;\listoffigures⟯|⟮c2;generate a list of figures⟯
⟮c3;\listoftables⟯|⟮c4;generate a list of `table`s⟯
⟮c5;\tableofcontents⟯|⟮c6;generate a table of contents⟯


Whenever ⟮c9;latex compiles⟯ and you ⟮c7;have used one or more of \listoffigures, \listoftables, \tableofcontents⟯, it will ⟮c8;emit a .lot, .lof, or .toc file⟯ respectively. 
Latex constructs the ⟮c10;.aux⟯ and ⟮c11;.log, .lof, or .toc⟯ files by ⟮c12;keeping account of anything that would be relevant⟯ for those ⟮c13;while compiling⟯. 
Latex uses ⟮c14;the .lot, .lof, or .toc files⟯ on ⟮c15;the next run⟯ ⟮c16;to generate the actual listoffigures, listoftables or table of contents⟯. 
The reason ⟮c17;latex needs to compile at least twice⟯ is so ⟮c18;it can populate the references⟯ for things like ⟮c19;lot, lof, toc as well as various things in .aux⟯ correctly. 
The ⟮c20;aux⟯ file keeps track of ⟮c21;various things relevant to latex compilation⟯. 

######### logging

⟮c1;Logging⟯ is done to ⟮c2;.log⟯ for ⟮c4;latex itself⟯ and ⟮c3;.blg⟯ for ⟮c4;bibtex/biber⟯. 

######### synctex

⟮c2;Synctex⟯ is the utility that ⟮c3;synchronizes changes between⟯ ⟮c1;source documents and pdf output⟯

######## additional functionality

######### headers and footers

⟮c10;\pagestyle{foo⟯} sets ⟮c13;the style⟯ of ⟮c11;your headers and footers⟯ to ⟮c12;the format defined by foo⟯ 
for ⟮c14;anything more fancy⟯ with ⟮c15;headers and footers⟯ than ⟮c16;\pagestyle⟯ can do with ⟮c17;builtin formats⟯, you need the package ⟮c18;fancyhdr⟯ 
⟮c19;\pagestyle{fancy⟯} activates a ⟮c20;sensible default⟯ ⟮c8;fancyhdr⟯ config 
after&nbsp;⟮c5;\pagestyle{fancy}⟯ you need ⟮c9;\fancyhf{} ⟯ to ⟮c7;remove the elements of the default page syle⟯ 

For more ⟮c21;advanced header/footer config⟯ using ⟮c22;fancyhdr⟯, use ⟮c23;\(l/c/r)head{⟯} or ⟮c23;\(l/c/r)foot{}⟯

⟮c1;\(l/c/r)foot{foo}⟯|⟮c2;insert an element foo at that position in the footer⟯
⟮c3;\(l/c/r)head{foo}⟯|⟮c4;insert an element foo at that position in the header⟯


to style headers and footers with ⟮c24;fancyhdr⟯ in ⟮c2;double-sided documents (e.g. books⟯) use ⟮c6;\fancyhead⟯ and ⟮c6;\fancyfoot⟯ 

######### ending commands

⟮c4;⟯ and ⟮c5;\newline⟯ both ⟮c8;generate a linebreak (/end the current line⟯) 
⟮c2;\​⟯ but not ⟮c2;\newline⟯ takes an ⟮c3;option⟯ to specify how ⟮c1;large the vertical gap to the new line⟯ should be 
⟮c6;par⟯ ⟮c7;generates a paragraph break (/end the current paragraph⟯) 
⟮c15;a blank line⟯ is the construct most often used to ⟮c16;create a paragraph break⟯. 
⟮c10;\newpage⟯ and ⟮c11;\clearpage⟯ both ⟮c9;generate a new page (/end the current page⟯) 
⟮c12;\clearpage⟯ is like ⟮c12;\newpage⟯, but ⟮c12;\clearpage⟯ ⟮c14;forces floats to go on a new page⟯, while ⟮c12;\newpage⟯ will in multicollumn mode ⟮c13;actually just create a new column (not necessary a new page⟯) 

######### pdf metadata

the package ⟮c5;hyperref⟯ also handles ⟮c6;metadata⟯ via ⟮c7;the \hypersetup command⟯. 
The ⟮c8;hypersetup⟯ command defines ⟮c9;pdf metadata⟯ by taking ⟮c10;keys⟯ with ⟮c11;the syntax of pdf&lt;name&gt;, e.g. pdfauthor or pdftitle⟯ 
⟮c1;pdfbookmark⟯ is a ⟮c12;hyperref⟯ command that ⟮c2;inserts a pdf ToC thingy (visible e.g. in the adobe reader sidebar⟯) 
Arguments to ⟮c4;pdfbookmark⟯⟮c3;[section]⟯⟮c2;{Title} ⟯⟮c1;{uid(of some kind, no standard)} ⟯ 
⟮c12;hypcap⟯ is a package extending ⟮c14;hyperref⟯ {{c13::make hyperref figure links link to the correct thing} 

######### page geometry

⟮c1;layout⟯ is a package that allows you to ⟮c2;show the setup of the page (how much spaces is being taken up by margins etc.⟯) 
⟮c3;geometry⟯ is a package that allows you to ⟮c4;change page layout (margins etc.⟯) 
You can use ⟮c5;the  geometry package⟯ to ⟮c6;change the page layout globally⟯ by using ⟮c7;the optional argument⟯ of ⟮c8;the \usepackage call⟯. 
You can use ⟮c9;\newgeometry{options⟯} to ⟮c10;change the page layout⟯ for ⟮c11;the following pages⟯, and 
⟮c12;\restoregeometry⟯ to ⟮c13;reset the page layout to the original state⟯ (both package ⟮c14;geometry⟯) 

########## lscape

using the package ⟮c1;lscape⟯, you can use ⟮c4;the landscape environment⟯ to make ⟮c5;the thing go into landscape mode⟯ 
If using ⟮c2;pdflatex⟯, you use ⟮c3;pdflscape⟯ instead of ⟮c6;lscape⟯. 

######### images

⟮c1;graphicx⟯ is a package that allows us to ⟮c2;use images/graphics⟯ in ⟮c3;latex⟯. 
You define the ⟮c4;root directory⟯ for where ⟮c5;graphicx⟯ should ⟮c6;look for images⟯ with ⟮c7;\graphicspath{\foo⟯} 
To ⟮c8;include an actual image⟯ with ⟮c9;graphicx⟯, use ⟮c10;\includgraphics{path⟯}. 
⟮c11;Changing attributes of images⟯ included w/ graphics is done in ⟮c12;the optional argument⟯ of ⟮c13;\includegraphics⟯ 

######### hyphenation

The ⟮c14;hyphenation⟯ command takes a ⟮c15;list of words⟯ as an ⟮c16;argument⟯, which will ⟮c17;only be hyphenated⟯ in ⟮c18;the places indicated with dashes⟯ 
⟮c19;hyphenat⟯ is a package to ⟮c20;en/disable autohyphenation⟯, e.g. in ⟮c21;words that contain hyphens or in monospaced fonts⟯ 
in general, if a word ⟮c11;contains a non-alphabetic character⟯, ⟮c13;latex⟯ will only ever ⟮c12;split the word on that hyphen⟯ 

Latex|Result
⟮c1;$-$ (or other inline math env notation⟯)|⟮c2;a mathematical minus⟯
⟮c3;---⟯|⟮c4;an em-dash⟯
⟮c5;--⟯|⟮c6;an en-dash⟯
⟮c7;⟮c1;-{}-⟯⟯|⟮c8;--⟯
⟮c9;-⟯|⟮c10;a hyphen⟯


######### blockquotes

the ⟮c7;quote⟯, ⟮c8;quotation⟯, and ⟮c9;verse⟯ environments all ⟮c10;indent the material, blockquote-style⟯. They ⟮c11;differ in⟯ ⟮c12;what they indent additionally, if anything⟯. 
⟮c1;quotation environment⟯|⟮c2;indents the beginning line of a paragraph additionally⟯
⟮c3;quote environment⟯|⟮c4;indents nothing additonally⟯
⟮c5;verse environment⟯|⟮c6;indents every line of a paragraph but the first one additionally⟯



######### verbatim

Package ⟮c5;verbatim⟯ contains the ⟮c6;verbatim⟯ and ⟮c6;comment⟯ ⟮c7;environments⟯.
environment|function
⟮c1;comment⟯|⟮c2;a block comment⟯
⟮c3;verbatim⟯|⟮c4;the text, exactly as you have inputted it (similar to &lt;pre&gt;⟯)


######### drawing (tikz)

⟮c1;tikz⟯ is a package for ⟮c2;creating images⟯ based on ⟮c3;LaTeXlike commands⟯ 
⟮c4;TikZ⟯ is short for ⟮c5;TikZ ist kein Zeichenprogramm⟯ 
⟮c6;TikZ⟯ has ⟮c7;its own pacakge/library system⟯, for which you ⟮c8;import packages/libraries⟯ via ⟮c9;\usetikzlibrary⟯ in ⟮c10;the preamble⟯ 
⟮c11;tikzpicture⟯ is the ⟮c12;environment⟯ that ⟮c13;delimits tikz commands to draw an image⟯ 

######### resizing braces

In latex, ⟮c1;parentheses⟯ and ⟮c2;square brackets⟯ ⟮c4;can just be inserted⟯, ⟮c3;curly braces⟯ ⟮c4;must be escaped⟯. 
⟮c5;curly braces⟯ must ⟮c6;be escaped even⟯ if ⟮c7;as part of \left or \right⟯ 
± e.g. `\left\{` ±<br>
⟮c8;prefixing⟯ ⟮c9;parentheses, square brackets or (escaped) curly brackets⟯ with ⟮c10;\left⟯ (if ⟮c11;opening⟯) or ⟮c10;\right⟯ (if ⟮c11;closing⟯) will ⟮c12;make them resize if around something larger (e.g. a fraction⟯) 
± e.g. `$$\left[\frac{foo}{bar}\right]$$` ±<br>

######### links (hyperref)

######### including other pdfs

⟮c1;pdfpages⟯ is a ⟮c2;package⟯ to ⟮c3;include other pdfs within the latex documents⟯ 
⟮c4;pdfpages⟯ mainly features the command ⟮c5;\includepdf⟯ which ⟮c6;allows include a pdf document in the latex document⟯ 
⟮c7;\includepdf⟯ allows specifying ⟮c8;how you want to include what⟯ in ⟮c9;its options⟯ 
⟮c10;to control the pages that are included⟯, \includepdf⟮c11;[pages=foo]⟯ 

######### color

the ⟮c9;packages⟯ ⟮c7;color⟯ and ⟮c7;xcolor⟯ allow ⟮c8;using various color-related commands⟯. 
⟮c10;xcolor⟯ is ⟮c11;an extension/superset of⟯ ⟮c12;color⟯. 


command|effect
⟮c1;\definecolor{name}{color_space (e.g. rbg)}{values (e.g. 0.858, 0.188, 0.478)}⟯|⟮c2;define new colors⟯
⟮c3;\pagecolor{color}⟯|⟮c4;colors the background of a page in the specified way⟯
⟮c5;\textcolor{color}{text}⟯|⟮c6;colors the text in a specific color⟯


######### misc

command|Effect
⟮c1;\noindent⟯|⟮c2;prevent the paragraph from being indented⟯
⟮c3;\nolinebreak / \nobreak⟯|⟮c4;prevent latex from breaking here⟯
⟮c5;\textwidth, \columnwith, \linewidth⟯|⟮c6;width of the current text (different variants for different circumstances⟯)
⟮c7;\neg&lt;whatever&gt;space (\negmedspace, \negthickspace⟯)|⟮c8;negative space (pulls things closer together⟯)


Command|does
⟮c1;\today⟯|⟮c2;render today's date in the format <span id="insert-here"></span><script>var [, month, day, year] = new Date().toDateString().split(" "); document.querySelector('#insert-here').innerHTML = `${month} ${day}, ${year}`;</script> (by default⟯)
⟮c3;\bar{foo}⟯|⟮c4;bar above foo⟯
⟮c5;a' or a^{\prime}⟯|⟮c6;render an a with a prime⟯


####### MD

In ⟮c1;markdown⟯, you can include arbitrary ⟮c2;HTML⟯. 
In ⟮c7;markdown⟯, you need to ⟮c3;put blank lines⟯ ⟮c4;before and after⟯ ⟮c5;block-level⟯ elements, this includes ⟮c6;HTML in markdown⟯. 
To ⟮c8;indent something under something else⟯ in md, ⟮c9;indent the source code thing by four spaces⟯. 

######## GFM

⟮c1;Github-flavored⟯ ⟮c2;markdown⟯ supports creating ⟮c3;task lists⟯ via the syntax ⟮c4;`- [ ]`⟯ 
You ⟮c5;complete⟯ ⟮c6;github-flavored markdown task lists⟯ via the syntax `⟮c7;- [x]⟯` 

###### non-markup

####### citations

######## software

reference/citation/bibliographic management software is software that manages citation information


table:name|license|distingishing characteristic
JabRef|FOSS|often used for LaTeX
Citavi|Proprietary|only really used in germany
Zotero|FOSS|most common

######## CSL

CSL|Citation Style Language 
CSL is a standard for describing citations.
CSL has XML, JSON, YAML realizations.
The CSL-processor is citeproc.
citation-js is a npm module and CLI for citation magic using various different formats.

######## BibTeX

BibTeX is the format (La)TeX uses to describe citation information.
bibtex-entry ::= @<type>\{<unique-key>, <list-of-props>\}
list-of-props ::= <key> = <value>{, <key> = <value>}
type ::= book|article|...

####### toml xdg systemd

INI files inspired XDG desktop files.
XDG desktop files inspired systemd unit files.
TOML was inspired by INI, XDG and systemd unit files.
TOML|Tom's obvious, minimal language

####### m3u

m3u is a plain-text file format for playlists
m3u merely has a de-facto standard.
There are two variants of m3u, one which is very basic and extended m3u, which allows for directives.
Careless handling of m3u has often lead to security flaws.

m3u-file ::= {<entry>}
entry ::= [<path>|<URL>]<CRLF>

extended-m3u-file ::= #EXTM3U<CRLF>{<entry>}
entry ::= [<resource-entry>|<directive>]<CRLF>
resource-entry ::= (<path>|<URL>)[ #<string>]
directive :: #<directivename>[:<argument>]

####### ICAL/VCARD

ical|text/calendar|calendar information|RFC 5545|.ics
vcard|text/vcard|contact information|RFC 6350|.vcf
The iCalendar object is organized into individual lines of text, called content lines. 
Any content lines not acting as delimiters are called properties.
Rough general ENBF:
ical, vcard ::= {<contentline>}
contentline ::= <name>{;<param>}:<value><CRLF>
name ::= <iana-token>|<x-name>
param ::= <param-name>=<param-value>{,<param-value>}

The iana-tokens "BEGIN" and "END" signify the beginning and end of an icalendar or vcard object, or a component/subcomponent in the case of Ical.
There is currently only one subcomponent, VALARM
BEGIN and END take a value of VCALENDAR for an ical object and VCARD for an vcard object

ical-object ::= <ical-begin-line><version-line><prodid-line>{<ical-component>}<ical-end-line>
ical-begin-line ::= BEGIN:VCALENDAR<CRLF>
ical-end-line ::= END:VCALENDAR<CRLF>
version-line ::= VERSION:2.0<CRLF>
prodid-line ::= PRODID:<string><CRLF> # UID of creator
ical-component ::= <begin-line>{<contentline>|<ical-component>}<end-line>
begin-line ::= BEGIN:<component-name><CRLF>
end-line ::= END:<component-name><CRLF>

In vCard, properties are direct children of the ⟮c1;the vCard object⟯
In general, an .ics contains one ical object, however a .vcf may contain multiple ical objects

vcard-object ::= <ical-begin-line><version-line>{<contentline>}<ical-end-line> # no prodid
cal-begin-line ::= BEGIN:VCARD<CRLF>
ical-end-line ::= END:VCARD<CRLF>
version-line ::= VERSION:4.0<CRLF>

icalendar lines may be a maximum of 75 octets long. If they are longer, they are broken up into multiple lines, where a leading space/tab on the new line indicates it is a continuation.

ical/vcard property names
ATTENDEE   the users attending/assigned a task
DTEND   end time
DTSTART   start time
ORGANIZER   the organizer of the event
RRULE   rules for repeating
SUMMARY   title/summary
VALARM   Alarm/Reminder
VEVENT   Event
VFREEBUSY   free/busy time
VJOURNAL   Journal entry
VTIMEZONE   timezone definition
VTODO   Task/Todo

####### dictionary-based

######## TOML

in ⟮c1;TOML⟯, ⟮c2;the top-level table⟯ starts at ⟮c3;the beginning of the document⟯ and ends before/at ⟮c4;the first table header⟯ 
in ⟮c5;TOML⟯, a ⟮c6;header⟯ looks like ⟮c7;[foo]⟯ 
in TOML, ⟮c8;a header (on its own line⟯) ⟮c9;starts a table⟯ TOML: ⟮c10;standard tables⟯ continue until ⟮c11;the next table (or EOF⟯) 
to ⟮c12;create subtables⟯ via the standard table syntax, you use ⟮c13;dot notation within the header⟯. 
to create ⟮c14;an array of⟯ ⟮c15;standard tables,⟯ you ⟮c16;surround the header with double braces like so: [[header]]⟯ 
TOML also supports ⟮c17;JSON style tables⟯, (though ⟮c18;they use = instead of :⟯), but only if ⟮c19;they do not contain a newline⟯. 
TOML: ⟮c20;fruit.apple.color = "red"⟯ produces ⟮c21;a table named fruit that has a table named apple that has a key color with the value red⟯ 

######## YAML

YAML|YAML Ain't Markup Language

######### Anchors & merge keys

YAML ⟮c7;anchors⟯ ⟮c8;save a reference to a value⟯, which ⟮c9;then can be included in a different location⟯ via ⟮c10;an alias.⟯ 
⟮c11;A merge key⟯ ⟮c12;merges the values of an anchor⟯ ⟮c13;into the current leve⟯l, thus allowing ⟮c14;overwriting some of the values if necessary⟯. 
A YAML ⟮c15;alias⟯ goe⟮c16;s where a value would normally⟯ 
A YAML ⟮c17;anchor⟯ goes ⟮c18;between key and value⟯ 
A YAML ⟮c19;merge key⟯ goes ⟮c20;instead of a key⟯, and ⟮c21;takes an alias as a value⟯. 
⟮c1;&amp;foo⟯|⟮c2;anchor⟯
⟮c3;*foo⟯|⟮c4;alias⟯
⟮c5;&lt;&lt;⟯|⟮c6;Merge key⟯


######## JSON

JSON|JavaScript Object Notation
JSON is a plaintext file format.
JSON has the same syntax as JS object literals, with a few exceptions.
In JSON but not JS object literals, keys must be quoted.
In JSON but not JS object literals, functions are forbidden.
In JSON, the top-level item can either be an object or an array.

JSON Pointers allow referring to things within json
JSON Pointers are paths starting with and separated by / (e.g. /foo/bar)

JSON does not allow comments by default, however many implementations of it do in fact allow JS-style comments.
The version of JSON that allows comments is used frequently by microsoft technologies.
The version of JSON that allows comments is often called jsonc (though there are other things called jsonc)

######## Schema

JSON schemas are schemas for JSON, YAML, usually written in JSON, though they can be written in different things.
top-level keys
title|title for the schema
description|description for the schema
$schema|URL of the version of JSON Schema this document adheres to 
$id|base url for the document, similar to <base> in HTML

\$ref allows you to refer to another schema to implement the element, rather than definining it here, by passing a JSON pointer.
format|force string to have specific format (e.g. ISO 8061)
format: date|time|datet-time|force string to be a valid date, time or datetime
enum|specify an enum of allowed values 
pattern|specify a regex that the value must conform to
default|specify a default value that should be assumed if a value is missing

in JSON Schema, to specify that there are multiple relevant specifications for a type in the sense of AND, OR, XOR, there are the keywords allOf, anyOf, oneOf

to use your ⟮c+;JSON Schemas⟯ as ⟮c+;TS typeings⟯ use the ⟮c+;npm package⟯ ⟮c+;json-schema-to-typescript⟯

######## jq yq

jq|process JSON
yq|process YAML & convert to/from JSON
yq -y/-Y roundtrip back to YAML
`yq ⟮c1;&lt;command&gt;⟯ ⟮c2;&lt;flags&gt;⟯ {⟮c3;&lt;file&gt;⟯}`
`yq ⟮c2;-t/--to-type⟯ ⟮c1;yaml⟯/⟮c1;json⟯/...` ⟮c3;outputs the file as the specified file format⟯

####### subtitles

WebVTT|Web Video Text Tracks Formats
⟮c33;WebVTT⟯ and ⟮c33;.srt⟯ are file formats for ⟮c34;subtitles⟯. 
⟮c35;WebVTT⟯ is ⟮c36;based on⟯ and ⟮c36;similar to⟯ ⟮c37;.srt⟯ 
⟮c38;.srt⟯ is ⟮c39;more common⟯ than ⟮c38;WebVTT⟯, but ⟮c38;WebVTT⟯ is ⟮c40;more new/featurefu⟯l. 
⟮c41;Youtube⟯ amongst others does not support ⟮c42;srt or WebVTT tag formatting⟯, and ⟮c43;pretty much nothing⟯ supports ⟮c44;most of WebVTT's most advanced features⟯. 
⟮c45;WebVTT and .srt⟯ mark up their payload with ⟮c46;HTML/XML-style tags⟯. 
Things in ⟮c47;WebVTT/.srt⟯ are ⟮c48;generally separated⟯ by ⟮c49;a blank line (i.e. two newlines⟯) 

WebVTT delimits ⟮c51;major sections⟯ with ⟮c50;allcaps words⟯: 
section name|section semantics/function
⟮c1;WEBVTT⟯|⟮c2;s32;Begin WebVTT document⟯ ⟮h2;(may be followed by ⟮c32;text header on the same line⟯⟯)
⟮c3;STYLE⟯|⟮c4;inline styling section⟯
⟮c5;NOTE⟯|⟮c6;comment⟯



A ⟮c52;cue⟯ is ⟮c53;the main unit of information⟯ in ⟮c54;WebVTT/.srt.⟯ 
⟮c55;A cue⟯ ⟮c56;starts (.srt)/may start (WebVTT⟯) with ⟮c57;a header line⟯. 
⟮c58;The header line that starts a cue⟯ must be ⟮c59;a running number indicator⟯ in ⟮c60;.srt⟯, this is ⟮c61;optional⟯ in ⟮c60;WebVTT⟯ 
⟮c62;The line after the header line if it exists or the first line of a WebVTT/.srt⟯ ⟮c63;cue⟯ contains ⟮c64;the time to show the text⟯, consisting of ⟮c65;two timestamps (RFC 3339 (hh):mm:ss.ttt⟯) ⟮c66;separated by ` -&gt; ` (notice the spaces).⟯⟮c67;&nbsp;Every line of a cue after the line specifying the time⟯ specifies ⟮c68;text to be shown.⟯ Together, these are known as ⟮c69;the payload⟯. 
Every line of a cue may optionally be ⟮c70;started by `- `⟯, this will ⟮c71;not be displayed⟯ 



    <tr><th colspan="2">WebVTT-specific properties
CSS property syntax|CSS function
⟮c7;vertical:rl/lr make captions go from top to bottom and either right -&gt; left or left -&gt; right (changes the direction of other settings by 90 deg⟯)
⟮c8;line:0-100%⟯|⟮c9;display the cue at % offset from the top (or left/right if vertical is specified) (i.e., along the y axis if no `vertical`⟯)
⟮c10;position:0-100%⟯|⟮c11;display the cue at % offset from the left (or top/bottom if vertical is specified) (i.e., along the x axis if no `vertical`⟯)
⟮c12;size:0-100%⟯|⟮c13;set the width of the cue to %⟯
⟮c14;&lt;c.foo&gt;content&lt;/c&gt;⟯|⟮c15;specify a class foo to target⟯
⟮c16;&lt;ruby&gt;...⟯|⟮c17;add furigana etc.⟯
⟮c18;&lt;v foo&gt;⟯|⟮c19;indicate that foo is speaking⟯
⟮c20;align:start/end...⟯|⟮c21;align the captions along the x-axis (if not `vertical`), i.e. the same axis as the position property⟯
⟮c22;&lt;font color="...⟯|⟮c23;Set the text to a certain color⟯
⟮c24;&lt;b&gt;, &lt;i&gt;, &lt;u&gt;⟯|⟮c25;make the text bold, italic or underlined⟯


    <tr><th colspan="2">WebVTT-specific selectors
CSS Selector|Selects
⟮c26;::cue(.foo⟯)|⟮c27;Target a cue with class foo (&lt;c.foo&gt;⟯)
⟮c28;::cue⟯|⟮c29;Target any WebVTT cue (shown subtitle⟯)
⟮c30;::cue(b⟯)|⟮c31;Target a &lt;b&gt; tag within WebVTT⟯

If you ⟮c72;specify timestamp text (WebVTT only⟯), then ⟮c73;any text before a timestamp text whose time you are at or after⟯ is ⟮c74;previous text⟯, ⟮c75;the text from the current to the next timestamp tag⟯ is ⟮c76;active text⟯ and ⟮c77;text after the next timestamp tag⟯ is ⟮c78;future text⟯. 
If we specify ⟮c79;&lt;track kind="chapters"&gt;⟯, cues ⟮c80;may not overlap time-wise⟯, and payloads ⟮c81;may not contain tags⟯ 

####### misc

Ignore files specify things which a given utility should ignore.
Pretty much all VCSs have ignorefiles.
prettierignore.

#### complex

epub is a format for ebooks that is in essence just a zip wrapper + scaffolding around web technologies such as HTML, CSS, JS, SVG, etc.

##### container

A container format is a file format that contains different parts.
The component parts of a container format may be called chunks, segments, streams, or something else.
In general, the component parts of a container format have some kind of header aand a body.
IFF is a chunk-based file format.
IFF chunks begin with a type ID, followed with a specifier of the length of the chunk.
RIFF and AIFF are file formats based on IFF, but TIFF (surprisingly) isn't 

##### archive

An archive file format generally wraps multiple files into one file, compresses a file, or does both at the same time.
Archive file formats generally preserve directory structure and metadata
zip is an archive file format that compresses and wraps multiple files into one file.
tar is an archive file format that wraps multiple file, but does not compress them.
gzip and bzip2 are archive file formats that compress but do not wrap multiple files.
gzip or bzip2 are often applied after tar to achieve both wrapping and compression.
A tarball may be a .tar file, or a .tar.gz/.tar.bz2 file
gzip has the ending .gz

tar is a command to manipulate tar files
zip is the command to create zip files, unzip the command to unizp files
bzip2 is the command to manipulate bzip3 files

#### cross-cutting

##### email

Fundamentallly, all emails in an email account (generally associated with a single email address, but not necessarily) are stored in an an (email) mailbox
Message/mail delivery agents are programs that deliver emails to a mailbox.

###### mbox & imf

In the mbox format, an entire mail directory is held in a single file.
The mbox format consists of individual IMF messages.
The fileformat for emails is generally IMF.
The mbox format has problems with concurrency (safety and performance).
To prevent corruption, mbox files generally need to use file locking to prevent problems arising from concurrency.
mbox ::= <mbox-email>{<mbox-email>}
mbox-email ::= <from-line><IMF-message><LF>
from-line ::= From <sender-email> <utc-datetime><LF>
IMF-message ::= <headers><body><LF>
headers ::= {<key>: <value><LF>}
body ::= <LF><body-contents>

The IMF uses CRLF, however when stored in mbox, they use LF instead.

###### maildir

The maildir format is a format to store mailboxes and mail directories.
The maildir format has three subdirectories (at least) for any directory.
The three mandatory directories for any subdirectory in maildir are cur, new, and tmp.
Using maildir, an arriving message will be sorted into tmp until it is processed completely, then it is inserted into new.
Using maildir, once a mail in new has been read, it si sorted into cur.

## VCS

VCS|Version Control System
Version control system (VCS) are systems for tracking/managing changes to things.
Most commonly in a VCS, a repository contains all the files and folders of the project and their history.

### git 

Git is a VCS, but really isn't.
Git is fundamentally a content-addressable filesystem with a VCS user interface written on top of it.
Git is a content-addressable filesystem in that it fundamentally indexes files by hash keys.

#### objects

Objects are the various things git has.
Objects in git are stored in .git/objects
files in .git/objects are further sorted into subdirectories with the first 2 characters of their hash, with the contained file names having the leftover 38 characters.
Git objects are text files.
git objects have their hashes as their names, allowing them to easily be referenced.
git objects are commits, trees, blobs and annotated tags.

##### inspecting

the `git cat-file` command is the swiss army knife for inspecting git objects.

-p|Pretty-print the contents of &lt;object> based on its type. (can be used to retrieve the file from the store)
-t|Instead of the content, show the object type identified by &lt;object>.

##### hashes

hashes can be abbreviated to their first n characters, as long as those are unique.
the command `git hash-object` takes some data and returns the hash git would hash it with.
If you use the flag -w, `git hash-object` actually writes the file to .git/objects and returns the hash.
The type of hash git uses is a 40-character SHA-1 hash

##### commits

At its most simple, a repository contains a series of commits.
A commit is an object consisting of a few metadata.
Across different VCSs, a commit may be associated a snapshot (a copy of the file) or a diff, though git chooses a snapshot (contrary to what I thought)
The commit object has its hash as its name.
A commit consists of a hash of the tree, a hash of the parent commit, author, committer, date, and message.
Running `git commit` adds a new commit with the files in the staging area.

##### trees

A tree is a git object representing the directory structure of the project at time of commit as an ordered list.
The file representing the tree has 'entry' (not a real term) per line.
A tree 'entry' consists of file permissions, object type, object hash, and filename.
The object type of a tree 'entry' is usually "blob" for files or "tree" for a subdirectory.
tree git objects are confusingly named, as they are ordered lists and only become trees by their ability to refer to other trees.

##### blobs

A blob is a git object representing the contents of a file.

##### annotated tags

A tag git object contains the hash of the tagged object, the type of tagged object (usually a commit), the tag name, author, date and message.

#### heads

the HEAD is a pointer to the currently checked out commit/branch head.
You are in detatched HEAD state is when your HEAD is pointing directly to a commit.
checking out a commit/branch moving the HEAD to that commit/branch head.
the command to check out a commit/branch head is `git checkout`.
the newer porcelain command to check out a branch head is `git switch`.
the HEAD is implemeted by storing the hash of the commit or the file for the branch header (i.e. refs/head/whatever) we're pointing to in .git/HEAD 
HEAD may also often be used as a keyword for git commands.

#### repository

The working directory contains the repository directory as well as the current versions of all the files in the repository.
The repository directoy contains all git internals, and is called .git.
Whenever you stage a file, it is added to the staging area and its blob is added to .git/objects.
The staging area is a directory listing containing the hashes of all staged files.
The staging area is implemented by a single file, .git/index.
`git add` stages a file.
git status tells us about our working directory and staging area.
The staging area is not emptied by committing! But after commiting, there is no difference between the staging area and the working directory
If you changed a file, it's unchanged version will be living in the staging area, while its `modified` version will be living in the working directory. To make it part of the staging area, you need to `git add`.

##### tracked and untracked files

At the beginning of a git repository, all files are untracked.
All files that have been `git add`ed at some point become tracked files.

##### .gitignore

there is also a per-clone version of the gitignore in form of the .git/info/exclude file.
Patterns which a user wants Git to ignore in all situations (e.g., backup or temporary files generated by the user’s editor of choice) generally go into a file specified by core.excludesFile in the user’s ~/.gitconfig. Its default value is $XDG_CONFIG_HOME/git/ignore. If $XDG_CONFIG_HOME is either not set or empty, $HOME/.config/git/ignore is used instead.

By default, any line in a gitignore contains one pattern to ignore.
If a line is prefixed by !, a line in a gitignore instead contains a pattern to reinclude. 

##### creating a new repository

`git init` creates a new repository by creating the repository directory.



#### commit history

git log shows a set of commits of the commit history.
`git reset` can be used to reset your HEAD to the specified past commit.
git reset moves the HEAD/branch heads to the specified commit, as well as the staging area, but does not modify the working area.

##### retrieval

`git checkout <commit> <filename>` retrieves the file <filename> as of commit <commmit>

#### branches

branches split the linear relationship of the commit history.
In git, a branch merely consists of a branch head.
A branch head is a pointer to the commit at the tip of the branch.
git stores branch heads as files in .git/refs/head
Each file in .git/refs/head, i.e. each branch head contains the hash of a commit.
A branch can be kept track of by only a branch head since every commit has the hash of the previous commit.
When we create a new branch, git creates a new branch head pointing to the specified commit.
`git branch` without arguments lists the current branch heads.
A newly created repository contains one branch head, master/main.

##### creating branches

`git branch` with two arguments A, B creates a new branch A with the commit to start at specified by B.
`git checkout -b` works the same as git branch with two arguments, but also checks out the new commit.

##### unifying

to include changes from another branch into the current branch, one has two choices: rebase and merge
Compared to merging, rebasing results in a more 'pretty' commit history

###### merging

two possible merges: fast-forward, three-way-merge
In a fast-forward merge, the the HEAD is (pointing to) a direct ancestor of the commit we're merging in.
In a fast-forward merge, it is merely the pointers that differ, so the merge merely moves the pointer forward
Any merge that is not a fast-forward merge is a three-way merge
a three way involves two different states and thus must create a merge commit.
In a three-way merge, the merge is performed based on the diff with the common ancestor commit.
In a three way merge, if the same section of the ancestor commit has been changed, it creates create a merge conflict.
A merge conflict is indicated by special syntax within the file.
merge-conflict ::= <seven-left-angle-brackets> <branch-name><newline><code-version-1><newline><seven-equals-sign><newline><code-version-3><newline><seven-right-angle-brackets> <branch-name><newline>
After fixing a merge conflict, you need to commit again.

To abort a maerge during a merge conflict: git merge --abort

###### rebasing

Rebasing in git is taking the changes from somewhere (e.g. a branch) and applying them on another branch as if the changes had been made there originally

#### rev-parse

the suffixes ~<n> and ^<n> are for moving back in the tree of commits.
~<n> goes n commits back into the history
~0 = this commit, ~1 = parent commit, etc. 
~ is an alias for ~1
^<n> selects the nth parent commit sibling if there are multiple.
^1 = ~1, ^2 is the second commit of a merge commit, etc.

#### plumbing and porcelain

Git has two kinds of commands, plumbing and porcelain.
Git's plumbing commands are older and more low-level.
Git's porcelain commands are newer and more high-level.

#### remotes

Remotes are ⁑links to⁑ other git repositories. (!)
Remotes may be on the same device, or other devices (e.g. online).
The default name for a remote is 'origin'.
`git remote` is used to administer remotes.
`git remote add foo bar` adds a new remote to the current repository, where foo is the name we will call this remote, and bar is its URL.
remotes are stored in .git/config
In .git/config, each remote has its own header

##### pushing, fetching, pulling

things git push/fetch transfers are refs and objects.


###### pushing

git push transfers all the information a remote does not yet have but needs of a certain refspec to that remote.
`git push [<repository> [<refspec>]]`
If the repository is left out from git push, it will take it from the branch.*.remote (i.e. the configured remote for the branch) config, or origin if none is found.
When the command line does not specify what to push with <refspec>... arguments or --all, --mirror, --tags options, the command finds the default <refspec> by consulting remote.*.push (i.e. the push key for the specified remote) configuration, and if it is not found, honors push.default configuration to decide what to push

###### fetching

`git fetch [<repository> [<refspec>]]`
If the repository is left out from git push, it will take it from the branch.*.remote (i.e. the configured remote for the branch) config, or origin if none is found.


##### remote tracking branches

A remote tracking branch someremote/foo is a local copy of the foo branch on the remote, possibly as distinct from the truly local foo branch.
to list remote tracking branches, use `git branch --remotes`
remote tracking branches are named `<remote>/<branch>`
A tracking branch is a local branch that is directly related to a remote tracking branch.
The remote tracking branch of a tracking branch is called the upstream branch.
Establishing a new tracking branch can be done by creating a new local branch for a remote tracking branch e.g. via `git checkout -b newLocalBranch <remote>/<branch>`, for which the shorthand `git checkout --track <remote>/<branch>` exists.

##### refspec

A refspec tells git how to map references from a remote to the local repo.
refspec-format ::= [+]<src>:<dst>
<src> in a refspec is the pattern for references on the remote side
<dst> in a refspec is the pattern for references on the local side
If a plus is included in a refspec, it tells git should update even if it isn't a fast-forward 
Default refspecs for pushing and fetching for each remote are established in the remote entry in the config file.

##### cloning

`git clone` creates a new directory containing a copy of a remote repository, setting up remote tracking branches for each branch of the remote repository.

#### config

per-repository config for git is stored in the .git/config file.
Global git config is stored in the .gitconfig or the ~/.config/git/config file.
Git config files are ini-likes

#### tags

tags are pointers to specific commits.


#### hooks

git supports hooks in the form of git hooks.
git hooks are stored in .git/hooks
you can use any language for git hooks as long as you can specify it via a shebang
by default, none of the git hooks run because they are postpended by .sample - removing this will make them run at the relevant time.
git hooks are not synchronized between origins by default, to do that, you would have to store them in the repository themselves and symlink them or sth.
there are 6 local and 3 server hooks.

local hooks
name|does|arguments passed to script|exiting non-0 does
pre-commit|after git commit, but before prompting for message|none|aborts commit
prepare-commit-msg|prepopulates text editor with commit message|name of temporary file with message, type of commit, hash of commit|aborts commit
commit-msg|after commit message was entered (for validating commit message)|name of temporary file with message|aborts commit
post-commit|after commit-msg hook (e.g. for notifications)|none|nothing
post-checkout|after running git checkout|previous HEAD, new HEAD, branch or file checkout|nothing
pre-rebase|called before git rebase|2, but I don't want to deal with them right now|aborts the rebase

server hooks
pre-recieve|when recieving commits from git push|none, but recieves commit reference via stdin|rejects the push
update|
post-recieve|after push has succeeded|none|nothing

#### github

Github is a hosting service for git repositories.

##### Issues & PRs

Github issues track desired changes such as features, bugs, etc.
A milestone is a set of github issues.
PR = Pull Request
A pull request is a request to merge the specified changes into the branch
If you refer to an issue with ⟮c2;#number⟯ and a word such ⟮c3;as closes, fixes etc.⟯ within a ⟮c4;commit⟯, it will ⟮c1;close the issue⟯ (or ⟮c1;close it⟯ once ⟮c5;merged into the default branch⟯)

# hardware/low-level

## hardware only

### electrical connectors

⟮h∞;<img src="Connectors.jpg">⟯⟮h∞;<img src="1280px-ConnectorSymbols.svg.png">⟯


An ⟮c1;electrical connector⟯ is a device that ⟮c2;joins electric conductors⟯ ⟮c3;mechanically⟯ and ⟮c4;electrically⟯.
In ⟮c5;electrical connectors⟯, the ⟮c6;mechanical connection⟯ is ⟮c7;to allow the electrical connecton to stay in place⟯ and thus ⟮c8;an electrical circuit to be created⟯. 
Most ⟮c9;electrical connectors⟯ have ⟮c10;a gender (male or female :( ⟯) 
An ⟮c20;electrical connector⟯ that is ⟮c21;a protusion⟯ is ⟮c22;male⟯. 
An ⟮c23;electrical connector⟯ that is ⟮c24;a receptacle/indentation⟯ is ⟮c25;female⟯. 
An ⟮c11;electrical connector⟯ with ⟮c12;male gender⟯ is also called ⟮c13;a plug.⟯ 
An ⟮c14;electrical connector⟯ with ⟮c15;female gender⟯ is also called ⟮c16;a socket/jack⟯. 
A ⟮c17;terminal⟯ is ⟮c18;the point where a conductor ends⟯. It may be ⟮c19;an electrical connector⟯. 

### transistor -> logic gate -> logic circut

#### transistors

A transistor has three terminals.
In a transistor, if you apply power to two certain terminals, power can flow through two other terminals. (of course, between both of the sets of the terminals, one will be the same.

⟮h∞;<img src="sm_transistor-current-explanation.png">⟯
BJT  Bipolar junction transistor
The three terminals in a bipolar transistor are called ⟮c1;base⟯, ⟮c2;collector⟯, and ⟮c3;emitter⟯.
BJT are either PNP or NPN.
NPN transistor  Negative Positive Negative transistor
PNP transistor  Positive Negative Positive transistor
for NPN transistors, applying power (at the base) allows the current to flow.
for PNP transistors, applying negative/no power (at the base) allows the current to flow.
For NPN BJT transistors, if you apply power to the base, it will flow to the emitter, allowing a stronger current to flow between collector and emitter.

flex-container:<img src="sm_tmpr_uvk0fj.png">


flex-container:<img src="sm_tmpadmp5k8t.png">
The three terminals in a field-effect transistor (FET) transistor are called ⟮c1;gate⟯, ⟮c2;source⟯, and ⟮c3;drain⟯.
FET  Field-effect transistor
MOSFET   metal–oxide–semiconductor field-effect transistor
CMOS|Complementary metal–oxide–semiconductor
MOSFET is the most common type of FET.
most ICs that use MOSFETs are manufactured with CMOS

today, most ICs are made with CMOS-manufactured MOSFETs

#### logic gates

Logic gates are made up of a few transistors in a specific arragnement (depending on the gate).

XOR|<img src="sm_120px-XOR_ANSI_Labelled.svg.png">
XNOR|<img src="sm_120px-XNOR_ANSI_Labelled.svg.png">
OR|<img src="sm_120px-OR_ANSI_Labelled.svg.png">
NOT|<img src="sm_120px-NOT_ANSI_Labelled.svg.png">
NOR|<img src="sm_120px-NOR_ANSI_Labelled.svg.png">
NAND|<img src="sm_120px-NAND_ANSI_Labelled.svg.png">
AND|<img src="sm_120px-AND_ANSI_Labelled.svg.png">

Either NAND or NOR gates could be used to create any possible logic circuit since they are functionally complete 
Today, NAND is the most commonly used logic gate, since it's functionally complete and can be built with few trasnistors

#### circuits

A ⟮c+;logic circuit⟯ consists of interconnected logic gates.
A combinatorial logic circuit is one whose output only¬ depends on its input.
A sequential logic circut is one whose output depends on its input, and the previous state.

### processors

#### architecture

A stored-program computer stores data and instructions in the same way.
The VNA implements a stored-program computer.
VNA: CPU = CU + ALU
In the VNA, the CPU, memory and IO are connected to/via the bus.

flex-container:<img src="sm_tmp_xpihn7q.png">
In the (modern revisions of) von neumann architecture, the three buses are the ⟮c1;control bus⟯, the ⟮c2;address bus⟯, and the ⟮c3;data bus⟯
Stored-program computers can present a security risk due to the fact that data can contain maliscious instructions.

The harvard architecture separates instructions and data (= does not store them in the same way/treat them differently)
Modern processors are claimed to be stored-program computers (specifically VNA), but since they separate data and instructions to a certain extent, they may be considered modified Harvard architecture to a certain extent.

#### electronics

##### integrated & discrete circuits

IC = integrated circuit
an integrated circuit is a set of electronic circuit on a piece of semiconductor material.
A chip is the piece of semiconductor material on which an integrated circuit is realized.
Today, the chip is almost always made using silicon.
The opposite of an integrated circuit is a discrete circuit.
A discrete circuit is a 'traditional' circuit, i.e. a circuit made up of different parts.
ICs are orders of magnitude faster, smaller, less power hungry, etc. than discrete circuits.

##### processors

A processor is any circuit that performs operations.
A processor core is a self-contained processing unit.
A processor can potentially consist of multiple processor cores.
A microprocessor is a processor implemented on an IC.
Almost all modern processors are microprorcessors.

A SoC is a IC that doesn't just include the CPU, but also other components, such as the GPU, memory, radio modems, etc.
As time has been progressing, more and more things have been moving onto the SoC.
moore's law is the observation that the number of transistors in a IC doubles ⟮c1;every two years⟯

#### CPU

CPU = central processing unit

CPU is often used in three different senses: The whole unit executing instructions, potentially consisting of multiple CPU cores, a CPU core, or even the whole SOC, potentially containing the GPU, modems, etc.
to differentiate, I will call CPUs in the sense of a self-contained processing unit CPU/processor cores.
to differentiate, I will never call SOCs CPUs (if I can avoid it.).
to differentiate, I will call the main processor, potentially consisting of multiple CPU cores, a CPU.
A multi-core processor is when the chip contains multiple CPU cores.

##### registers

A processor generally has between 10-100 registers.
There are many different kinds of registers:
register|contains
General Purpose Registers|mostly whatever you like
Register: Stack Pointer|stack pointer
address register|memory addresses
data register|binary data
accumulator|intermediary results of a calculation
status/flag register|status flags for the outcome of operations

status register = flag register

The flag/status register might hold flags such as 
zero flag|ALU calculation was zero
overflow flag|ALU calculation resulted in result larger than word size
sign flag|ALU calculation resulted in negative number

Program counter (PC) is also called Instruction Pinter (IP)
The Instruction Pointer/Program counter is a register that contains the memory address of the next instruction.
The instruction Register contains the current machine language instruction (opcode + operands)

Instead of a single accumulator, modern processors generally have many registers that can be used as accumulators.

##### ALU

ALU  Arithmetic logic unit
https://upload.wikimedia.org/wikipedia/commons/0/0f/ALU_block.gif
the ALU is a combinational logic circuit.
The ALU performs arithmetic and bitwise operations.
A basic ALU takes two imputs and returns an output, generally all of the word size of the encapsulating CPU.
A basic ALU, besides its two inputs and an output, has a status flag input and output as well as an opcode input.

###### Adders

An adder is a logic circuit (I think?) that chains logic gate to perform addition.
Adders are used within the ALU.
A half-adder adds two binary digits and outputs a sum and a carry.
A full adder is like a half-adder, but also takes a carry-in.
A half and a full-adder ouptuts an output of size 2 bit.
Chaining full adders allow us to do arbitrary large binary addition.

##### CU

CU  Control Unit

#### machine code & instruction set

Assembly language is largely syntactic sugar for machine code.
Machine code consists of machine language instructions.
Machine code and thus machine language instructions are what run directly on the processor, at least in the classical model.
In fact, by now, there is often a layer below machine code known as microcode.
opcode is short for operation code
Within a machine language, an instruction is defined by an opcode.
Within a machine language, an instruction consists of the opcode it is defined by, plus zero or more operands.
An instruction set architecture defines the instruction set plus a bunch of other processor features (such as registers, addressing, I/O) (however, the two terms are often also used interchangably)
The instruction set is the set of operations a processor supports, which bit sequences represent which  machine language instructions, and how the arguments are organized.
Depending on the instruction set, machine langauge instructions may all be the same length or not.
In a general sense, a word is the fundamental unit used by a processor of a given ISA ≈ how many bits a PU may address at once.
The length of a word is the word size.
In general, most registers are word-sized, as are memory cells.
The largest possible memory address is also word-sized (since otherwise, how would you address them) .
what is 32 bit in a 32-bit processor and 64 bit in a 64-bit processor is the size of memory addresses and thus the ⟮c1;the word size⟯

A Load-store architecture is a type of instruction set architecture which only has instructions that either do ALU operation ⟮c1;access (load/store) memory⟯, never at the same time.
For a load-store architecture, all things being operated on must be in registers.

The machine code of a program depends on the ISA, but also on other things about the computer (e.g. OS)

arch with no args prints the current ISA family
the arch command can be made to run programs on other ISA families via arguments.

##### Instruction-level parallelism

Instruction-level parallelism is the parallel execution of instructions of a single thread (thus it is different from concurrency).
In general, the goal of instruction-level parallelism is to keep all of the processor busy
fors of instruction-level parallelism include Instruction pipelining, Out-of-order execution + register renaming, speculative execution + branch prediction.
Instruction pipelining attempts to keep every part of the processor busy with some instruction by dividing incoming instructions into a series of sequential steps (the eponymous "pipeline") performed by different processor units with different parts of instructions processed in parallel.
Out-of-order execution executes instructions as resources are available, rather than the order in the program, if this is possible.
register renaming is a technique that abstracts logical registers from physical registers.
Register renaming allows us to eliminate false data dependencies coming from write after read dependencies, enabling more out-of-order execution.
If compilers did not reuse registers, register renaming would not be necessary, however this is often difficult in practice.
speculative execution is executing instructions before we know if they will be needed
speculative execution is worthwhile if the cost of waiting until we know if the instructions will be needed to be executed is higher than the cost of speculatively executing.
speculative execution is most commonly referred to in the case of instuction pipelining, but may also be performed in many higher-level tasks.
speculative execution (in processors) is most often performed in the case of control flow, where branch prediction is often used to try and guess which branch is most likely.

###### RISC instruciton pipelining

Instruction fetch > Instruction decode and register fetch > Execute > Memory access > Register write back 

##### Hazards

In processors, a hazard is when the next instruction cannot execute in the following cycle, or doing so would lead to an error.
Data dependence is when an instruction depends on the data of the preceeding statement.
Data hazards ocur when instructions exhibit data dependence modify data in different stages of a pipeline, potentially leading to race conditions.
Three type of data hazards:
read after write, write after read, write after write.
read after write is a true dependency: it cannot be resolved.
write after write is an output dependency: it can be resolved by just anulling the first write.
write after read is an anti-dependency, it can be solved by register renaming.

##### RISC CISC

RISC  Reduced instruction set computer
CISC  Complex instruction set computer

The design goals of RISC and CISC are different: while CISC tries to use as few lines of assembly as possible and thus uses more complex, featureful instructions that take multiple clock cycles, RISC uses simple instructions that only take a single clock cycle to be quick.

###### CISC

x86 is a family of instruction set architectures
x86 are the most common type of CISC architectures.
x86 architectures with 64-bit word size are called x86_64
x86_64 may also be called AMD64 or Intel 64
the architecture is called x86 b/c the first processor with it was the Intel 8086.
CISC is the dominant architecture on desktop/laptops as of 2020, though it is slowly changing

###### RISC

ARM is a family of instruction set architectures
ARM ISAs are the most common type of RISC arcchitectures.
While PowerPC was also a RISC ISA and was widely used in all sorts of products, RISC largely became mobile/embedded-only in the mid 2000s until 2021, with apple's switch to ARM RISC processors and their use in in e.g. the worlds most powerfull supercomputer 富岳.
RISC chips generally have far lower power consumption than CISC chips.
Most but not all RISC ISAs, including ARM and RISC-V, are also load-store ISAs.
CPI = clocks/cycles per instruction
In general, a RISC ISA has 1 CPI, with fixed-length instructions.
⟮c1;RISC-V⟯ is a ⟮c2;RISC⟯ instruction set architecture that is ⟮c3;open source⟯.

#### cache

processor caches are used to speed up memory access, which is especially important since processor memory is orders of magnitude slower than processing speed.
The cache levels that are common as of 2021 are L1, L2 and L3 cache, with L4 cache slowly becoming more common.
L1 cache is the fastest cache level, and it goes downwards from there
Multi-level caches are caches that are composed of different cache levels.
The organization of multi-level caches into faster/slower cache levels is known as the cache hierarchy.
processor finds memory location in cache   cache hit
processor does not find memory location in cache   cache miss
When a cache miss occurs, the processor generally needs to wait while the data is being fetched
the ⟮c1;Cache replacement policy⟯ is the policy that decides what to 'evict' on having to add something new to the cache on a cache miss

#### clocking

A clock signal ⟮c1;coordinates/synchronizes the circuits⟯ the circuits of the thing it's governing.
A clock signal is usually a square wave with a high and low state.
In relation to the clock signal's square wave the circuits activate on ⟮c1;on one (or both) of the (vertical-ish) edges⟯, depending on the implementation
⟮c1;A synchronous circuit⟯ is a circuit where the changes are synchronized by a clock signal.
processors are (made of) synchronous circuits
DDR  Double data rate
⟮c1;DDR (double data rate)⟯ is the technology that activates the circuit. both on the rising and the falling edge of the clock signal

### chipset


flex-container:<img src="sm_chipset.svg">
The chipset is responsible for data flow between the processor, memory and other components
In the past, the northbridge and southbridge made up the chipset.
The northbridge controlled/connected the faster components such as the CPU, memory, PCIe.
the southbridge controlled/connected IO, PCI/AGP.
When they still existed northbridge and the southbridge were connected.
Over time, more and more of especially northbridge chipset functions moved onto the SoC, and so the chipset is as of 2020 generally just one chip. 
Slowly, even the functions of the one chip left of the chipset are moving onto the SoC itself.

### assembler

Why don't we just write programs in machine code/assembler?  extremely mühselig and error-prone
Today, assembler/machine code is almost always generated by compilers/interpreters/etc.

### scheduling

scheduling is the action of assigning resources to perform tasks.
In the context of processors, scheduling is the assigment of processor cores to execute threads.

## layering on hardware 

firmware is software that is hard to change, often because it's physically built in.
BIOS and UEFI are both firmware, though BIOS is firmer.

### hardware interfaces

ACPI  advanced configuration and power interface
ACPI is a low-level interface to the power hardware of the computer, allowing for power management; it is currently the standard for that purpose.
ACPI executes the requests it gets as bytecode, acting like black box, and thus presenting a built-in security risk.
The ACPI exposes its interface as ACPI tables.
The Windows Platform Binary Table is an ACPI tible that allows software to persist even beyond reinstalls.
The Superfish vulnerability was enabled by the Windows Platform Binary Table.

### booting

Booting comes from bootstrap load, which itself comes from the idea of pulling yourself up by your bootstraps.
Booting is initializing the computer.
The difficulty of booting is how do you get the computer into a state where it can execute stuff without being able to execute stuff.
has ended when the OS has reached a certain state.
When the user presses the power button, the computer, and especially the CPU gets power, and executes a hardcoded JUMP fo a place in ROM (or a specific place in normal secondary memory) where the BIOS/UEFI sits (though some non-x86 ISAs may do it differently)
All x86 processors start in real mode, which has the features the intel 8086 had, with 20 bit addresses addressing memory non-virtually - this allows for backwards compatibility.

#### BIOS/UEFI

UEFI  Unified Extensible Firmware Interface
BIOS  Basic Input/Output System
The BIOS/UEFI comes preinstalled.
The BIOS stores its setting in nonvolatile BIOS Memory (also inaccurately called CMOS).
One of the more important thing stored in nonvolatile bios memory is boot device priority.
UEFI stores its settings in NVRAM.
Once the BIOS/UEFI is loaded, it typically performs a POST
POST = power-on self-test
POST tests for and initializes connected peripherals.
after BIOS/UEFI are finished, they load the first-stage boot loader.
BIOS loads the first-stage boot loader by looking for the boot sector on the boot device, from then on BIOS is no longer involved in booting.
BIOS is a simple de-facto standard, UEFI is a far more complex actual standard.
UEFI loads the boot loader directly, without using a boot sector.
UEFI has largely replaced BIOS as of 2020.
UEFI is controlled by a large set of industry stakeholders known as teh UEFI forum.
CSM (UEFI context)  Compatibility Support Mode
CSM is the mode of UEFI that makes it similar to BIOS by loading MBR or something from the first-stage boot loader.

to manipulate the UEFI boot manager from linux, use the command efibootmgr
-o/--bootorder|change the boot order

##### SMBIOS

DMI  Desktop Management Interface
The original common inteface for managing components of a computer was teh DMI, but it was end-of-lifed in 2005
SMBIOS  System Management BIOS
Originally, the SMBIOS interacted with the DMi
The SMBIOS provides an interface for accessing BIOS/hardware info.
CLI command for interacting with SMBIOS (formerly with the DMI): dmidecode

#### boot loader

MBR  Master boot record
The boot sector is typically one sector large
If boot sectors are still used, what sits in them is the first-stage boot loader.
Boot sectors were/are usually in the beginning of the drive
The MBR is 512 byte large, which used to be the size of the boot sector into which the MBR needed to fit.
The main purpose of the first-stage boot loader is to load the second-stage bootloader.
MBR consists both of a first-stage bootloader and a partitioning table.
THe second-stage boot loader, perhaps after some user choosing, loads the kernel.
When using GRUB, all the boot sector contains is a pointer to the next boot stage.
When using GRUB, the boot menu that allows you to choose the os is loaded in the second stage of the bootloader.

### the OS

#### the kernel

Primary memory is often divided into kernel space and user space, mainly for security.
Kernel stuff runs in kernel space while user prcesses runs in userspace.
Monolithic kernels do more stuff in kernel space than micokernels.
Instead of doing stuff in kernel space, mircokernels provide servers that do things in userspace.
The daemon responsible for paging (swapper/sched) is the process with PID 0.
A system call is a request to the kernel of an OS.
system call -> syscall. 

Drivers run in kernal space.
Drivers expose a well-defined interface of the hardware to the OS, but otherwise act as a black box.

#### the init process

The init process is launched by the kernel.
In unix, the init process is the first processes that launches when a computer boots.
The init process is a daemon and has PID 1.
older *nixes|init
newer linuxes|systemd
macOs|launchd

# security

## authentication

Authentication is proving one's identity.

### nonce

⟮h∞;<img src="300px-Replay_attack_on_hash.svg.png">⟯Nonce (<span class="c1-scr">short for number once</span>) is a number (generally random) that can only be used once in a cryptographic communication, to make sure an attacker can't repeat a data transmition (called a replay attack)

### challenge-response

challenge–response authentication is a family of protocols in which one party presents a question ("challenge") and another party must provide a valid answer ("response") to be authenticated.

#### passwords

#### CAPTCHA

Captcha is short for "completely automated public turing test (to tell) computers (and) humans apart"
A CAPTCHA is a challenge-response test to prove that the user is a human.
The requirement for a captcha is that computers should not be able to pass it, but should be able to grade it
Captchas were invented around 2000
The original generation of captchas used text
Originally, the text of captchas was generated and distorted, later (e.g. in recaptha) hard-to-read text from scanning books was used
Google's implementation of captcha is known as reCaptcha
The first (v1) generation of ReCAPTCHA would show users one word that was known, and one word that was difficult to automatically OCR.
in ReCAPTCHA v1 of the two words, if the known word was correct, the unknown one would be labelled as probably correct too
ReCAPTCHA v1 was fed off of and used to scan books.
reCAPTCHA v2 displays only a single checkbox, and uses behavioral analysis to check the risk of a bot. If high risk, an image captcha is displayed.
ReCAPTCHA v2 is being used to train the image recognition of google's AI
reCAPTCHA v3 checks if you are a bot purely based giving you a score in the background

## crypt

### ciphers

⟮c1;a cipher⟯ is an algorithm for performing encryption/decryption
Ciphertext is the text that is the result of ⟮c1;using a cipher⟯
A substitution cipher is a cipher where an unit of plaintext is replaced by an unit of cipher text
The caesar cipher is a kind of substitution cipher where the replacement is done by rotating the entire alphabet by some number.

### keys (symmetric and assymetric)

Today's cryptosystems (such as TLS, Secure Shell) use both symmetric encryption and asymmetric encryption, often by using asymmetric encryption to securely exchange a secret key which is then used for symmetric encryption. 


flex-container:<img src="sm_tmp51mx5j9z.png">
⟮c1;Symmetric key encryption⟯ is ⟮c2;where both parties have the same key⟯. 
⟮c3;In symmetric key encryption⟯, ⟮c4;one party encrypts the data⟯, ⟮c5;sends the cyphertext along⟯, and then the other party ⟮c6;decrypts the data using the same key⟯. 
The difficulty of ⟮c7;symmetric key encryption⟯ is that ⟮c8;you need to exchange the key securely, which is difficult.⟯ 


flex-container:<img src="sm_tmp424stpwy.png">
⟮c9;In public key cryptography⟯ aka ⟮c10;asymmetric cryptography⟯, ⟮c12;both parties⟯ have ⟮c11;two keys⟯, ⟮c11;a public⟯ and ⟮c11;a private key⟯. 
In ⟮c13;public key cryptography⟯, ⟮c14;you publish⟯ ⟮c15;your public key⟯ ⟮c14;widely⟯, and ⟮c14;keep⟯ ⟮c15;your private key⟯ ⟮c14;secret⟯. 
If you want to ⟮c16;encrypt a message⟯ in ⟮c17;public key cryptogrpahy⟯, you ⟮c18;apply your targets public key to it⟯. 
If you want to ⟮c19;decrypt a message⟯ sent to you ⟮c20;via public key cryptography⟯ (which we assume ⟮c21;has been encrypted with your public key⟯), you ⟮c22;apply your private key to it.⟯ 


flex-container:<img src="1200px-Private_key_signing.svg.png">
For ⟮c23;digital signing⟯, ⟮c25;you⟯ ⟮c24;encrypt it with your private key⟯. ⟮c25;The recipient⟯ ⟮c24;decrypts it with your public key.⟯ This proves ⟮c26;that the message is from you⟯, since only ⟮c27;your public key can decrypt things encrypted with your private key⟯. 

### random numbers

C(S)PRNG  Cryptographically (secure) pseudorandom number generator
PRNG  pseudorandom number generator
RNG  random number generator

## attacks

### brute-force

A brute-force attack is an attack of something such as a password ⟮c1;By trying until successful⟯


### buffer overflow

Buffer overflow is when a buffer of a specific size is written to with data larger than that buffer, thus writing to a different memory location.
In a buffer overflow attack, a buffer overflow is intentionally produced (e.g. by entering too-long user input), with executable code in the overflown part (ergo a code injection attack), which may then be executed as normal code.
C and C++ are well-known to be vulnerable to buffer overflow.


### Injection

Code injection is an attack vector where malicious code is injected due to some flaw.
Code injection can often be prevented by sanitizing user input.
Delimiter/terminater-based code injection uses delimiters, e.g. of strings or similar, to escape from string interpretation to code interpretation.

### network 

#### MITM


flex-container:<img src="sm_mitm_illus.svg">
A  ⟮c1;man-in-the-middle⟯ attack is when an attacker ⟮c2;inserts themseves⟯ into the ⟮c3;communication⟯ between ⟮c3;two parties⟯ believing ⟮c4;to be talking to each other directly⟯.

##### key exchange

<h1>
  ⟮c5;MitM attack⟯
</h1>
⟮h∞;uh1;<img src="sm_MitM1.jpg">⟯
⟮c1;h∞;uh2;<img src="sm_MitM2.jpg">⟯
⟮c2;h∞;uh3;<img src="sm_MitM3.jpg">⟯
⟮c3;h∞;uh4;<img src="sm_MitM4.jpg">⟯
⟮c4;h∞;<img src="sm_MitM5.jpg">⟯

⟮uh∞;After the MitM for public key encryption has been set up...⟯<br>
⟮c12;the server⟯ and ⟮c12;client⟯ ⁑actually⁑ have ⟮c13;the MitMs public key⟯ 
⟮c10;the server⟯ and ⟮c10;client⟯ ⁑think⁑ they have ⟮c11;each other's public key⟯ 
⟮c6;the MitM⟯ looks like ⟮c6;the server⟯ to ⟮c7;the client⟯ 
⟮c8;the MitM⟯ looks like ⟮c8;the client⟯ to ⟮c9;the server⟯ 

⟮c14;public key⟯ ⟮c15;mitm attacks⟯ are countered with ⟮c16;certificate authorities⟯ 

#### XSS

XSS  Cross-site scripting
Cross-site scripting (XSS) is a code-inejction attack where malicious client-side scripts are injected into web pages being viewed by users

#### DOS

DoS = denial of service
DDoS = distributed denial of service
In a DoS, the goal is to make a network resource unavailable.
In general, DoS succeed in making the network resource unavailable by taking up all its resources.
DoS may be performed by flooding the target with requests, or with some more sophisticated techniques.
A DDoS attack is a DoS performed from many different sources.

##### Low and Slow

###### Slow Loris

A ⟮c1;slowloris/slow loris⟯ is a type of ⟮c2;DoS (Denial of service)⟯ attack, more specifically a type of ⟮c3;Low and Slow⟯ attack.
A slow loris takes advantage of the fact that the http (1.1.) header section ends CRLF (last header) CRLF (blank line).
A slow loris works by opening as many connections to the server as possible, and sending a little bit of the header section every few seconds or so, so it doesn't time out, but never ending it.
If the server e.g. creates a new thread for each incoming request and only kills it once it has sent the response, under a slow loris it quickly reaches its thread limit, and can no longer serve new (legitimate connections)
A slow loris is easy to pull off, because it needs very little bandwith and only a normal computer.

## privacy

### device fingerprinting

A device/browser fingerprint is the set of information about the device/browser that together renders it uniquely identifiable.
since fingerprinting exists, a user can generally be tracked even without a cookie (or similar)
Having social media buttons on your page generally enables the providers to track you (whether via fingerprint/cookies/whatever). Sometimes, a toggle button is added to prevent this.

# OSs

## global

OS|Operating System
roughly, the OS could be considered the layer between hardware and programs

### userland

#### clipboard

clipboard-cli is an npm package that exposes the command clipboard which works as a shell filter for the clipboard, copying or pasting as needed.
xclip allows interaction with the X clipboard
A clipboard manager is a computer program that adds functionality to an operating system's clipboard.
Many clipboard managers allow the pinning of items, in maccy with ⟦⌥⟧ ⟦p⟧
Maccy is a FOSS clipboard manager for macOS.

#### screen selection

slop|queries for a selection from the user and prints the region to stdout
maim|screenshot-taking-utility

slop or maim -s 
-t float / --tolerance=float   How far in pixels the mouse can move after clicking, and still be detected as a normal click instead of a click-and-drag
-t 9 999 999 / --tolerance=9 999 999 (spaces only for readability)   force the selection of a window (by cursor)

maim
-i string / --window=string   cature the desired window (name could be gotten dynamically via various x utilities for example)
-g string / --geometry=string   capture the selected geometry rect

#### backups/snapshots

rsnapshot|Rsync based snapshot utility

#### notifications

Spec for how notifications should work on linux   Desktop Notifications Specification
libnotify is the most common implementation of the Desktop Notifications Specification
To use libnotify, you need to also install a notification server/daemon.
dunst is a minimal notification server/daemon.
to send notifications on linux, you can use the CLI notify-send.

#### fonts

⟮c1;FontBook⟯ is the ⟮c2;mac⟯ GUI for ⟮c3;font handling⟯. 
For ⟮c4;manual font installation⟯ on mac, you can ⟮c5;copy them⟯ to ⟮c6;/Library/Fonts⟯ or ⟮c6;~/Library/Fonts⟯ 

#### text expanders

Text expanders are programs which allow OS-wide macros.

##### espanso

⟮c2;Espanso variables⟯ are made available in the ⟮c1;environment⟯ of the `shell` type. 
An espanso var with `⟮c3;name: foo⟯` will be available as `⟮c4;$ESPANSO_FOO⟯` for any shell scripts. 
⟮c5;fields within a form⟯ are available as `⟮c6;$ESPANSO_FORMNAME_FIELDNAME⟯` for any espanso shell scripts 
```lang=yaml;
- trigger: ":reversed"
  replace: "Reversed {{myshell}}"
  vars:
    - name: mytime
      type: date
      params:
        format: "%H:%M"
    - name: myshell
      type: shell
      params:
        cmd: "echo $ESPANSO_MYTIME | rev"
```


to ⟮c2;insert a random choice of different options⟯ use the type ⟮c1;random⟯, ⟮c3;the options⟯ are specified ⟮c4;in the choices sequence of params⟯ 
```
  - trigger: ":quote"
    replace: "{{output}}"
    vars:
      - name: output
        type: random
        params:
          choices:
            - "Every moment is a fresh beginning."
            - "Everything you can imagine is real."
            - "Whatever you do, do it well."
```

using espanso, I've created an expansion that uses `!!!` to run an arbitrary shell command and insert the results

### kernelland

### installation

A live OS is a bootable OS on some kind of removable device.
A live OS typically also allows installation of the OS and may be the main means of installing an OS
A live USB is a live OS on an USB stick.
A live CD is a live OS on a CD.
Unetbootin is a cross-platform untility for creating bootable USBs

### virtualization

Virtualization is creating something virtual instead of something real.
For the isolated execution of programs, generally either virtual-machine-based virtualization or os-level virtualiztion is used.
A virtual machine is a form of virtualization where an entire operating system is virtualized.

#### OS-level virtualization

chroot changes the root directory of a process, preventing it from changing anything outside.
A chroot jail is the environment set up by chroot.
Often, the basis of OS-level virtualization is a chroot jail.
OS-level virtualization is where multiple isolated user space instances exist on the same OS.
Containerization is (is an implementation) of OS-level virtualization, which generally refers to specifically using OS-level virtualization for running one app, including all its dependencies and its own fs.
Using OS-level virtualization/containerization, interactions with the larger OS is only allowed through limited, specified channels.
An application being contained in a container is said to be containerized.
Containerization improves security and portability.
Containerization is the standard for most mobile operating systems.
Containerization may limit functionality and increase size (since dependencies cannot be shared)
Docker is the most common service for os-level virtualiztion/containerization.

### communication between OSs

scrcpy is a program that provides display and control of android devices from the computer via USB or the internet(TCP/IP).

## mac

## windows

### misc

Right-clicking the ⟮c1;windows start button⟯ brings up a ⟮c2;context menu⟯ with ⟮c3;a bunch of system tools⟯ 

## *nix

### different *nixes

#### POSIX

The Portable Operating System Interface (POSIX) is a family of standards specified by the IEEE Computer Society for maintaining compatibility between operating systems.
POSIX specifies both kernel- and user-level APIs as well as various shells and utilities.

#### differences

Different *nixes have different versions of different command-line tools, on account of having descended in different ways from the original unix.
coreutils are the basic GNU file, shell and tex manipulation utilities.
the GNU versions of basic command-line tools is generally more featureful than other versions.
the GNU versions of basic command-line tools is generally the one that is assumed e.g. online.
You can install the GNU coreutils on non-GNU systems via homebrew.
If there is also a preexisting version of the command when the GNU coreutils are installed with homebrew, they are prefixed with g (e.g. gdir instead of dir).
If you need the normal names of the GNU coreutils when installed with homebrew (e.g. because they're being used in a preexisting script etc, add the directory they're in (/opt/homebrew/opt/coreutils/libexec/gnubin) to your $PATH

#### what's in a *nix

##### GNU/Linux

GNU is the set of free software that accompanies the linux kernel in GNU/Linux.
GNU = GNU's not unix
The GPL was originally created for GNU
(GNU) GPL = GNU General Public License
Linux technically refers to the Linux kernel.
GNU software set + Linux kernel = GNU/Linux
Often, Linux alone is used (technically incorrectly) to refer to GNU/LInyx

A Linux distribution is GNU/Linux plus a set of other stuff, which depends on the flavor.

Android uses the Linux Kernel but not GNU or any of the other libraries.
From ⟮c3;android⟯ ⟮c1;1.0⟯ until ⟮c2;9⟯, ⟮c3;android⟯ versions had ⟮c4;sweets⟯-based names, with each name ⟮c5;going one further in the alphabet⟯

###### WSL

WSL = Windows Subsystem for Linux
The Windows Subsystem for Linux is a Linux VM/compatibility layer for Windows
The Windows Subsystem for Linux allows you to do things like run a shell environment of linux on windows, and even X11 applications
To install the Windows Subsystem for linux, turn it on in the "Turn windows features on or off" dialog, then download the distro from the windows store
The windows drives with letters C, D, ... are accesible from the WSL as /mnt/c, /mnt/d ...

##### Android

⟮c2;Android features⟯ depend on the relevant ⟮c1;API level⟯, which starts at ⟮c3;1⟯ and is at ⟮c4;30⟯ as of android ⟮c5;11⟯ 

Curreny android has one ⟮c1;API level⟯ per ⟮c2;major version⟯ (e.g. ⟮c2;android 11⟯), but it used to be ⟮c3;multiple ones per version⟯ (bc in the past ⟮c4;minor versions⟯, e.g. ⟮c4;2.2.⟯ Gingerbread and even ⟮c5;patch versions⟯, e.g. ⟮c5;2.2.3⟯ Gingerbread ⟮c6;introduced new features⟯) 

#### libraries & systems

##### linux

###### input

On Linux, input devices are often handled on linux by the library libinput, which is also the name of the command used to interface with it. 
libinput is native in wayland, but optional in X, which can also manage input devices directly, whose implementation you can interface with via xinput.

###### grapical display & related systems

pango is a linux library for international text rednering.

####### X

the X window system is the whole thing with X servers, X clients, an X server, X11, ...
The core part of the X window system is the X server.
the Xorg X server is the main implementation of the X Server
by default, the X server handles displays and kb/mouse.
When something of interest happens, the X server sends events to its clients.
The X server handles the actual displaying to the display.
If one wants to display something using X, one sends an request to the X Server.
X11 is the communication protocol of the X window system.
X clients are things such as individual applications.
X clients may be anywhere, including on another computer.

X thingies installed by default live in /usr/share/X11
X local config changes live in /etc/X11
xorg is configured in X11/xorg.conf(.d)

######## window manager

In Unix, a window manager handles window management.
to the X window system, the window manager is just another client.
A window manager does things such as resizing, minimizing, closing
wmctrl   Manage an X window manager
A desktop environment is a window manager plus a set of base applications and some other stuff such as a clipboard manager, toolbar, etc.
Well-known desktop environments are GNOME, KDE, XFCE, Unity...

######## starting X

startx is a wrapper around to xinit.
xinit/startx source .xinitrc when run.
.xprofile and /etc/xprofile is run by X before your window manager is run.
.xsession is (at least in theory) only sourced when logging in from a display manager

######## Login

A X display manager is a graphical login manager which starts a login session on an X server.
the GNOME X display manager is gnome's display manager.
GDM = GNOME display manager
LightDM is the most common alternative to GDM.

######## DE

D-Bus is a protocol/interface/middleware for messaging between processes (IPC).
AccountsService is a D-BUs service for accessing the list of user accounts and information attached to those accounts.

What Desktop Environment you're using   XDG_CURRENT_DESKTOP
What Desktop Environment you selected from the display manager (might be limited to gnome display manager)   GDMSESSION

######## CLI

xdotool allows automation of X windows
xdpyinfo gets info about an x server
xwininfo gets information about open windows
xev shows X events such as keyboard, resizing, clicking etc.

###### systemd

In SystemV style init, the init process was actually called init.
In SystemV style init, the device starts by executing numbered startup scripts one at a time.
Because SystemV executes startup scripts one at a time, it is relatively slow.
SystemV style init has largely been replaced by systemd, though the switch was recieved largely negatively.
In contrast to SystemV init, systemd is not composed of scripts, but of large, precompiled binaries.
In contrast to SystemV init, which was just the init process, systemd is additionally a huge architecture managing may parts of the OS.
systemd targets replaced SystemV runlevels.
When systed has bootstrapped itself, it next looks at default.target

within the relevant systemd folder (/var/systemd, /etc/systemd, /run/systemd), system is the directory that contains the unit files.
There are different systemd folders depending on the persistence that is desired, and the origin of the modification.
/run/systemd|lost at reboot
/lib/systemd|persitent (package-manaed software, the os)
/etc/system|persistent (device admin)

####### units

systemd deals with system units.
A systemd unit represents any kind of system resource.
systemd units contain dependencies to tell us what we need to load first.
Systemd units end .unittype.
an instance of a systemd unit is denoted by <instance-name>@<unitname>.<unittype>
Systemd units are stored in unit files.

.timer   timed functionality similar to cron
.target   a state to be reached
.socket   sockets
.service   Managing some kind of service
.mount   predefined mount points
.automount   .mounts that will be automatically managed
.path   notifying when a path becomes available

When a .path units path becomes available, ⟮c1;an associated .service⟯ is started.
When a .socket unit has some activity, an associated service is started.
When a .timer units time state is reached, an associated unit is started.

######## targets

reboot.target   The target for rebooting
poweroff.target   The target for turning off the computer
multi-user.target   multiuser (but no GUI)
graphical.target   multiuser ⁑with GUI⁑
default.target   what the machine should try and aim for when booting (another target generally)

######## CLI

Passing systemctl a target (such as reboot) without the .target will execute that target
The main command to administer systemd is systemctl
starting/stopping an unit for systemd does that ⟮c1;right now⟯ but temporarily
enabling/disabling an unit for systemd does that ⟮c1;next reboot/session (by default)⟯ but permanently.
To both start and enable/stop and disable, use enable/disable --now.
syntax: systemctl (start|stop|enable|disable) <unit>
To see if a thing is currently enabled or active, use is-enabled/is-active <unit>
reload <unit> reloads a specific unit.
reset-failed resets all failed units
daemon-reload refreshes changed systemd settings
The systemctl subcommands list-* lists relevant systemd-related things, however there is not a list-unit subcommand for every unit.
list-sockets|list sockets and what happens
list-jobs|list active systemd jobs
list-units|list all units
list-unit-files|list unit files

when using systemctl, if not specifying a suffix, it will assume .service
when using systemctl, for mount/device operations, besides using .mount and .device names,  you can use the respective paths (e.g. /dev/sda2)

loginctl controls the systemd login manager
systemd-analyze allows for systemd debugging

###### various subsystems & specs

####### NetworkManager

NetworkManager aims to provide an 'it just works' type network epxerience for linux
NetworkManager stores its saved connections in /etc/NetworkManager/system-connections/

####### bluetooth

The most common low-level bluetooth stack for linux is bluez
hcitool is a command allowing noninteractive bluetooth config.
bluetoothctl is a command allowing interactive commincation with bluetooth.
As of 2021, bluetooth on linux is still pretty buggy.
Bluetooth high-level-ish management software on linux: blueman, blueberry, bluedevil

####### sound

Linux's reasonably low-level sound interface is ALSA.
ALSA|Adavance Linux Sound Architecture
amixer is a command to control alsa.
PulseAudio is often layered on top of ALSA
pactl is a command to manage pulse audio
in linux soudn jargon, an output is a sink

####### language

ibus and fcitx are linux frameworks for multilingual input
mozc is a plugin for ibus/fcitx/whatever for japanese input.
ibus-daemon is the command for managing ibus
fcitx-configtool allows managing fcitx graphically.

##### state change

`shutdown`|shutting your system down
reboot|restart your computer
shutdown{ <option>}[ <shudown-time>][ <wall-message>]

caffeinate creates assertions to alter system sleep behavior. 
If no assertion flags are specified, caffeinate creates an assertion to prevent idle sleep.  
If a utility is specified with -u, the caffeinate assertions will persist for the duration of the utility's execution. 
if no utility is specified with -u, caffeinate creates the assertions directly, and those assertions will persist until caffeinate exits, or until the timeout specfied w/ -t.

#### leaving the shell

termux-open-url   open an url in its default application (termux)
termux-open   open something it its default application
`⟮c11;open⟯` ⟮c12;opens⟯ ⟮c13;files/folders⟯ and ⟮c14;urls⟯ with ⟮c15;the default application (or one you specify⟯) 
⟮c16;xdg-open⟯ is then X equivalent of ⟮c17;macOs `open`⟯ 


    <tr><th colspan="2">`open`
⟮c1;-R⟯|⟮c2;reveals the file in finder⟯
⟮c3;-a someapplication⟯|⟮c4;Specify the application to open with⟯
⟮c5;-e⟯|⟮c6;open the file with textedit⟯
⟮c7;-f⟯|⟮c8;reads from stdin⟯
⟮c9;-t⟯|⟮c10;open the file with your default text editor⟯


#### misc

`redshift`|make screen red/yellowish (linux)

set color temperature    `-O temp `
reset color temp   `-P`

`nightlight`|make screen red/yellowish (mac)

`nightlight status`|show `nightlight` status   
`nightlight on`|enable `nightlight`   
`nightlight schedule`|manage `nightlight` schedule   
`nightlight temp`|show current `nightlight` color temperature (with arg: set it)

CLI tool for managing displays|`display_manager.py`
`display_manager.py res`|manage resolutions (display_manager.py)
`display_manager.py res width height`|Set the resolution to width * height (display_manager.py)

date is a tool for showing, formatting or changing date and time
If run without arguments, date gets the current date and time.
date-command ::= date [<formatting-syntax>|<setting-syntax>|<dst-syntax>]
formatting-syntax ::= {<option>}[ +<output-format-specifier>]

option|does
⟮c1;-u / --utc / --universal⟯|⟮c2;use UTC⟯
⟮c3;-d date / --date=date⟯|⟮c4;calculate the date for the specific date⟯
⟮c5;-I/--iso-8601⟯|⟮c6;output the date as ISO 8601⟯


Sleep is a command that waits for the specified time.
sleep-command ::= sleep{ <number><suffix>}
suffix ::= s|m|h|d
for sleep, multiple number-suffix specifier waits for their sum

recode - converts files between character sets
insect - shell scientific calculator

unoconv is a CLI util to convert files using libreoffice in the background.

tee redirects a stream to stdout and to all listed files

### processes

On unix systems, a process is an (instance of a) program that is ⟮c1;running⟯
On unix, a process is the instance that has its own heap.

#### process relationshps

IPC|inter-process communication.

PPID|Parent Process ID
PID|Process ID


#### process management

ps|list of processes
pstree|processes as a tree

procs is a more fancy version of ps written in rust

#### file descriptors

A file descriptor is a positive integer that uniquely identifies a file (or file-like) things.
Each process has its own file descriptors.
The file descriptiors of a single process are stored in their own file descriptor table.
The kernel maps the file descriptors the file descriptor table of a single process to the file table.
The file table is a system-wide table of all open files.
The file table contains reference to the relevant inodes.
Each process has three file descriptors allocated automatically, namely for the standard streams.
the standard streams consist of stdin, stdout and stderr
The standard streams different from other file descriptors is that they are always allocated automatically, and that many mechanisms will use them by default.
stdin   0
stdout   1
stderr   2

using `-` to refer to stdin or stdout is a common convention specified by posiz, but not a feature of the shell or anything else

#### daemons

A daemon is a process running in the background, not under the direct control of a user.
In *nix, a daemon is generally a process which is a child of the init process.
A daemon is usually created either by a process forking a child process and then immediately exiting, thus causing init to adopt the child process, or by the init process directly launching the daemon. 
The names of daemons generally end with d.

#### exit codes

true|do nothing, sucessfully (exits 0)
false|do nothing, unsuccessfully (exit non-0)

#### process management tools

top is a process viewer.
htop is a more fancy version of top with a better TUI and interactivity.

### terminal system

#### job control

job control is mainly performed by signals.
A job is a shell concept, but generally corresponds to a process group.
Jobs mainly exist to be siginalled by signals, all processes in a job are signalled at once.
`^Z` (as keyboard input)   Stop (not kill) the current program
the bg command takes a suspended command (e.g. one that was Ctrl-Z ed) and resumes its execution in the ⁑background⁑
fg  resume stopped task in foreground
bg  resume stopped task in background
⟮c1;&amp;⟯ at the ⟮c2;end of an command⟯ ⟮c3;puts it in the backround⟯ (but it ⟮c3;still continues running⟯)
jobs|show processes running in the background

#### terminal

A terminal may be a physical/hardware terminal, a virtual terminal/console, or a terminal window.
/dev/tty represents the current terminal, regardless of what kind of terminal it is (hardware, virtual, etc.)
the tty command tells us which device file is implementing the current terminal

##### terminal architecture


flex-container:<img src="file://~/Downloads/terminalsys.svg">

A physical terminal is connected via cables to an UART driver.
screen, keyboard etc. are connected via drivers to a virtual terminal (not a window).
The UART driver or virtual terminal are connected to the line discipline.
The line discipline may be disabled, in which case the characters are sent directly and instantly to the process, the so called raw mode.
cooked/canonical mode is when the line discipline is enabled, which means that text is only sent to the application after a newline is sent.
cooked = canonical mode
The line discipline is typically disabled for TUI applications or similar and for the shell, which implements its own line discipline.
the line discipline is connected to the tty driver.
The tty driver is passive, while it has fields and methods, they need to be called from outside, e.g. via signals.
the tty driver seems to be the parent process of the session leader.
stty administers the options for the tty driver.
The tty driver is the thing that has all all the processes living in a terminal as descendants (?)

###### physical terminals and terminal emulators

Terminal emulator is properly a synonym for virtual terminal/console, though sometimes terminal emulator is used in the wider sense of 'any thing that emulates a hardware terminal', though I would consider this incorrect usage. Nevertheless, I wil use virtual terminal for this to avoid ambiguity. 
virtual terminal = virtual console.
vt/vc is short for virtual terminal/console.
Virtual terminals are realized by a /dev/tty<n> file.
/dev/tty<n> files are provided by the kernel.
Hardware terminals are realized by /dev/ttyS<n> files (I think)
tty may be a synonym for virtual terminal (since all virtual terminals are realized via /dev/tty<n>), or as a synonym for any non-pseudo-terminal terminal.
Each physical terminal would have been its own separate thing, and so each virtual terminal is also its completely separate thing.
Virtual terminals occupy the whole screen, they decidedly don't live within a GUI.
/dev/tty0 represents the current controlling virtual terminal.
When in a GUI, /dev/tty0 may be the virtual terminal the window server is running in.
On linux, pressing ctrl + alt + f<number> switches to tty<number>
In linux, the window manager lives within a virtual terminal.
Linux typically starts with 6 virtual ternubaks, and then one additional one (tty7) to run the window manager in.
ttys (physical terminals and virtual terminals) are initialized by `getty`, which mainly calls `login`.

each /dev/tty<n> has a corresponding /dev/vcs<n> (including /dev/tty0, which means that /dev/vcs0 corresponds to the memory of the current virtual terminal)
the /dev/vcs<n> contains what is visible on the screen of a /dev/tty<n>

###### pseudo terminals

A pseudo-terminal consists of two device files, a master file and a slave file.
In a pseudo-terminal, a terminal window such as xterm (or sth like ssh) replaces the virtual terminal. 
In a pseudo-terminal, instead of being connected directly to the line discipline, the thing replacing the virtual terminal is connected to the pseudo-terminal master device file. 
The kernel links the pseudo-terminal master device file (ggf. filtering through the line discipline) to the pseudo-terminal slave device.
The link between pseudo-terminal master and pseudo-terminal slave is full duplex.
The pseudo-terminal slave fulfilles the role that the tty driver would normally, e.g. holding on to processes.
If you input something e.g. to a terminal window, it is written to the pseudo-terminal master device, which is transferred to the pseuod-terminal slave, which redirects it to the relevant process. 
the file /dev/ptmx is the pseudo terminal master multiplexer, which spawns new pseudo terminals.
Opening /dev/ptmx gives you a file descriptor for the master device and spawns a slave device in /dev/pts.
/dev/pts/<n> represents a pseudo terminal slave.
When sshing, the pseudo terminal master device is connected to your terminal/terminal window/virtual terminal, but the pseudo terminal slave is instead on the remote machine.
The thing that creates the pseudo terminal slave on the remote machine is sshd.

###### system console

In the past, many hardware/physical terminals might have been connected to one computer.
In the past, the system console would have been its own hardware/physical terminal connected directly to the computer.
Today, the system console is merely the device file /dev/console.
In most modern systems /dev/console is merely a symlink to /dev/tty (however it may also point at something else)
In any case /dev/console and /dev/tty have different major numbers.

##### terminal window

A terminal window must be one level of emulation deeper than a virtual terminal, since it lives in a GUI which in linux at least itself lives within a virtual terminal.
A terminal emulated within a GUI is known as a terminal window
Alternative terminal window (mac)|iTerm2
xterm is the classic terminal window for the X window system.
most terminal windows are based of xterm
the default terminal window for gnome is gnome-terminal.
all the various terminal windows generally have a command of the same name to launch them/specify options
most terminal windows take the -e argument to execute the command in the newly opened terminal window.
Termux is a terminal window for android.

##### process interaction with terminals

PGID|Process group ID
SID|Session ID
pgrp|process group

On unix, every process has a parent.
A process group is a collection of one or more processes.
A session is a collection of one or more process groups.
Processes may not migrate between sessions.

To the terminal, the shell is just one more process running within it.

ctty = controlling terminal (doesn't have to be a tty)
A session has one controling terminal.
all processes within a session inherit the controlling terminal via fork()
Signals can only be sent by/via the controlling terminal and only to its forground process group.
The relevant foreground process will have its in/output connected to the tty driver of the controlling terminal.
Any session has exactly one foreground process groups, all other process groups are in the background.
Each session is managed by a session leader.
the shell is the session leader, and is always the process group leader of its process group
The session leader updates the tty driver and does some other admin stuff, e.g. creating new porcess groups for pipelines.
for the process group leader, PGID == PID
for the session leader, SID == PGID == PID


##### signals

signals allow the kernel to communicate asynchronously with a process (group).
The thing that is signalled when being singalled from a terminal is always an entire process group.
In the context of terminals, signals may be sent by/via TTY driver or some other part of the terminal subsystem.
signal names are all-caps and start SIG.
In a terminal, any input, including stuff such as ^Z gets sent to the tty driver (or maybe the line discipline - I'm not quite sure, and people seem to be disagreeing). 
For some key combinations, such as ^Z, the tty driver will not transmit the input, but instead turn this into a signal and send this to the foreground process group.
For some key combinations, such as ^D, the tty driver will not transmit the input, but instead turn this into a different character and transmit this instead.
Other key combinations, including some ^<char> combinations may merely be passed on to the process.
Ergo some ^<char> combinations may always send the same signal (but leave it up to the process how to respond to the signal), some ^<char> combinations may send a different character (which will be treated by that process as that characer), and some ^<char> combinations will just send ^<char>, which the process may handle if it so chooses.
You can change which ^<char> the terminal driver handles how via stty.
^C|SIGINT|tty  driver
^\|SIGQUIT|tty driver
^Z|SIGTSTP|tty driver
^D|EOT/EOF|tty driver
^L|FF|processs|often interpreted as 'clear the screen' (shells) or 'redraw the screen' (curses)

kill sends a signal to a process, given its PID
killall sends a signal to a n processes, given a string that their name contains
by defaut, kill and killall send SIGTERM

##### appearance

Things such as color and cursor movement in the terminal are implemented via control characters.

##### shell commands for terminal management

There are a number of shell commands that nevertheless still are concerned with terminals, and not with shells

###### virtual terminal

fgconsole   get the number of the current tty
fgconsole --next-avaliable   get next unallocated vt
openvt|run a program on the next free vt.
deallocvt   remove unused virtual terminals
chvt N   change to ttyN
Couldn't get a file descriptor referring to the console is an error you encounter using commands meant for virtual terminals somewhere else

###### any terminal 

the who utility displays all active terminal sessions and for each the users logged into them, datetime of login, and hostname if not local.
    sam$ who
    sam      console  Dec  4 01:44 
    sam      ttys002  Jan  9 12:34 
    sam      ttys007  Jan 24 23:26 
uptime -  prints general system stats: time of day, uptime, amount of users logged in, and and the average number of jobs in the run queue over the last 1, 5 and 15 minutes.
w is an extended version of who, which shows everthing who does, plus what is currently running in the terminal and the time since the user last typed anything. w also the stats that `uptime` shows.
    sam$ w
    9:10  up 52 days,  7:26, 3 users, load averages: 2.10 2.05 2.01
    USER     TTY      FROM              LOGIN@  IDLE WHAT
    sam      console  -                04Dec21 52days -
    sam      s002     -                09Jan22  3:34 -bas
    sam      s007     -                Mon23    9:41 -bas

#### shell

the shell is typically the foreground process in a given terminal, but may be the background process e.g. if we're using a TUI.
The shell runs in the foreground of a terminal if its being used interactively.
The shell is a special kind of program.
The shell is the interpreter that executes the commands.
For bash, there are two commands that allow changing settings of the shell, set and shopt.
The difference between set and shopt is that set is a POSIX-compliant command originally from the original bourne shell, while shopt is bash-only.
SHELLOPTS|options set via set
BASHOPTS|options set via shopt

##### variants

The first shell, introduced in 1971, was called the thompson shell with the executable sh.
the pwb/masey shell was introduced in 1977 and built on top of the thompson shell, keeping the executable sh.
The bourne shell was introduced in 1979 and also had/has the executable sh.
Today, the executable sh most often is a sym- or hardlink to a different shell, e.g. bash or csh.
csh is a more c-like shell developed from the thompson shell.
tcsh itself is a more advanced version csh.
Today, csh is most often a sym- or hardlink to tcsh.
ash, bash, ksh, and zsh are descendants of the bourne shell.
bash is the shell of GNU, and perhaps the most common shell as of 2020.
bash = bourne again shell

##### history

history can be en/disabled via the history parameter of set.
The history list is a list of commands that the shell internally stores.
the HISTSIZE environment variable determines how much of a the history list will be saved on exit.
the histfile stores the command history as a file. 
The path of the histfile is determined by the HISTFILE environment variable.
For bash, the default history path is ~/.pash_history.
the HISTFILESIZE environment variable detrmines the maximum length of the histfile.
When the shell starts up, the HISTFILE is truncated to HISTFILESIZE and then loaded into the bash history list.
When the shell exits, it saves the last HISTSIZE lines of the history list to HISTFILE, either overwriting the contents, or appeding if the histappend option is set. afterwards, the HISTFILE is truncated to HISTFILESIZE.
If the HISTTIMEFORMAT is set, the time stamp information associated with each history entry is written to the history file, marked with the history comment character. 

The HISTCONTROL and HISTIGNORE variables may be set to cause the shell to save only a subset of the commands entered.

The builtin command fc may be used to list or edit and re-execute a portion of the history list. 
The history builtin may be used to display or modify the history list and manipulate the history file.
With no options, history displays the history list with line numbers.

##### various features

###### The directory stack

in nix, there is a stack of directories called the directory stack.
in nix, you can push/pop from the directory stack with the commands pushd/popd.
pushd not only pushes the specified directory to the stack, but also cds there.
The dirs command shows the contents of the directory stack.
dirs, pushd and popd all take a positional argument +/-<n>, which do something with the nth directory counting from zero and from the start/end respecitvely
dirs +/-<n>|display the nth directory counting from the start/end
pushd +/-<n>|bring the nth directory counting from the start/end to the top of the stack by rotating the stack
popd +/-<n>|remove the nth directory counting from the start/end from the directory stack (without cding)

##### Prepopulated environment variables

PWD|current directory
OLDPWD|directory before last pwd
DIRSTACK|everything on the directory stack
PAGER|set the pager
HOME|user home directory
BROWSER|web browser

EDITOR and VISUAL are shell environement variables ⟮c1;setting the default editors⟯
PATH is for where to find executables.
PATH contains, well, paths, separated by colons.
For anything in PATH we can execute it by just using its name, to execute anything else we would have to use its path.
`⟮c1;which⟯` takes ⟮c2;a string⟯ and ⟮c3;searches⟯ ⟮c4;the PATH⟯ to see ⟮c5;what the path of the binary of this command is.⟯

command prompt is often just shortened to prompt.
The command prompt is one or more characters indicating the command-line is ready to accept input.
The PS<n> environment variables set the command promt in different circumstances.
PS<n> exist from 1-4.
PS1|default command prompt
PS2|prompt for following lines for multiline commands
PS3|options for `select`
PS4|execution of shell script debugging trace (whatever that is)
Bash additionally executes the content of the PROMPT_COMMAND just before displaying the PS1 variable.
for PS<n>, ash supports a set of \ initiated special escape sequences for things such as the time, hostname, number of current jobs etc.

##### login shell

A login shell is is the first shell that executes after you `login`.
login indicates to the shell that the shell should be a login shell by prepending the name of the shell with a -, so that $0 will e.g. be -bash, not bash.
-l/--login forces bash to be a login shell (in this case), $0 will not be prefixed with -)
In bash, you can also use shopt login_shell to see if bash is a login shell.
On mac, all interactive shells become login shells, meaning that .bashrc is not ever automatically read.
linux can rely on the login shell startup files being executed since the login shell is started before the OS has become interactive
mac cannot rely on the login shell startup files being executed before the first shell has been opened.

##### startup files

pretty much all shells have a set of startup files that they run as normal shell code when starting a new shell.
when bash starts non-interactively, it looks for startup files in the paths listed in BASH_ENV.
when bash starts interactively, which files it reads from depends on if it thinks its a login shell.
if bash is not a login shell, it reads from ~/.bashrc and on some versions of bash also from /etc/bash.bashrc
if bash is a login shell, it reads from /etc/profile, and then exactly one of ~/.bash_profile &gt; ~/.bash_login &gt; ~/.profile
It may be advisable to have one of the files loaded when something is a login shell load .bashrc, to ensure consistent behavior.
When an interactive login shell exits, or a non-interactive login shell executes the exit builtin command, Bash reads and executes commands from the file ~/.bash_logout, if it exists.

There are other files for environment variables that may be read at different times unrelated to the shell: .pam_environment, /etc/environment

##### Shell lifecycle

0. The shell may get its input from a file, a string, or the terminal, and splits it into lines.
1. The shell performs history expansion
2. the shell tokenizes the input
3. the shell parses the input into commands
4. The shell performs expansions
5. the shell performs redirections
6. the commands are executed
7. the shell waits for the commands to complete and collects its exit status

since shell syntax (such as filename expansion) are performed far before something like sudo is executed, if you lack permission to see things those things will not work.
To use shell syntax/features with sudo permissions, the easiest way is to create a sudoed subshell (sudo bash -c "command")

###### whence commands?

####### interactive shell

Bash uses a simple heuristic to determine if the shell is interactive: (if neither an non-option argument nor -c or -s is specified and error/iput are connected to terminals) OR (-i is specified), it is interactive.
While an interactive shell is meant to read/write to a terminal, there is no guarantee it is in a terminal if you force it with -i.
if a shell is interactive, $- will contain i, and $PS1 will be set (otherwise unset).
Interactive shells have a bunch of unique rules and semantics.

######## readline

An interactive shell will typically use the GNU readline library to allow line-editing of entered commands.
While GNU readline is most commonly used in interactive shells, it may be used in may different places.
GNU readline has both emacs and vi editing modes, with emacs editing mode enabled by default.
The emacs and vi arguments for set allow switching between those two modes.

######## tab completion

compgen generates potential autocompletes for a certain string based on its option

####### noninteractive shell

bash -s|read commands from standard input
bash -c|read commands from following string
shell scripts execute in their own shell by default
Unless you force it, the shell a script will execute in is a noninteractive shell.

###### history expansion

history expansion allows us to splice parts of the history list into the current input stream
In history expansion, the line from the history list that is used is called the event.
In history expansion, the parts of the event that are included are the words (broken into words with normal bash tokenization & parsing).
In history expasnion, various modifiers are available to modify words.
history-expansion ::= !<event-designator>[<word-designator>]{:<modifier>}
If the histverify shell option is enabled, and Readline is being used, history substitutions are not immediately passed to the shell parser. Instead, the expanded line is reloaded into the Readline editing buffer for further modification. If Readline is being used, and the histreedit shell option is enabled, a failed history expansion will be reloaded into the Readline editing buffer for correction.
only ‘\’ and ‘'’ may be used to escape the history expansion character, but the history expansion character is also treated as quoted if it immediately precedes the closing double quote in a double-quoted string.
Event designators allow the selection of the event for history expansion.
<n>|nth command in history list
-<n>|nth last command from current command
!|last command (synonym for -1)
<string>|most recent command preceding the current position in the history list starting with string.
?<string>|most recent command with string before a newline
?<string>?|most recent command containing string
#|the entirety of the command line as typed so far
word-designator ::= <positional-selector>|*|<integer>*
positional-selector ::= <position>[-<position>]
position ::= <integer>|$|^|%
<integer> corresponds to an index of a word starting at zero
^ and $ corresponding to the first and last argument (not words!)
% corresponds to  first word matched by the most recent ‘?string?’ search

the special word designator * corresponds to 1-$
the special word designator <integer>* corresponds to <integer>-$

modifiers for history expansion

h & t remove everything from a pathname but the head/tail
r / e remove a suffix .suffix / remove everything but the suffix
p prints the new command but does not execute it
s/old/new/ regex like substitution
(more exist)

indexes for ! for repeating start at 1 for the first command and go from there

###### tokenization

to the shell, a word is a sequence of characters treated as a unit by the shell. words are separated by whitespace or the characters ‘|’, ‘&’, ‘;’, ‘(’, ‘)’, ‘<’, or ‘>’. (this has nothing to do with IFS)

###### parsing (quoting)

since bash allows strings without quotes, double quotes actually perform a function somewhat similar to raw strings/escaping, except that the constructions starting with the metacharacters $, `, and ! still work.
In bash, $'...' treats the contents as raw strings, but allows for C-style escape seuqences.
In bash, $"..." translates the string according to the current locale settings

###### Expansion

Expansion is replacing a thing with another thing or things.

Expansions are performed in the order: brace > tilde > parameter > command substitution > arithmetic > process substitution > word splitting > filename expansion > quote removal 

Only brace expansion, word splitting, and filename expansion can increase the number of words of the expansion; other expansions expand a single word to a single word. The only exceptions to this are the expansions of "$@" and $* (see Special Parameters), and "${name[@]}" and ${name[*]} (see Arrays).

####### Brace expansion

Brace expansion is similar to filename expansion, but things expanded to need not exist as files.
Brace expansion is a mechanism for generating strings.
Brace expansion syntax: [&lt;preamble&gt;]\{(&lt;comma-separated-strings&gt;|&lt;sequence-expression&gt;\}[&lt;postscript&gt;]
comma-separated-strings: &lt;string&gt;{,&lt;string&gt;} 
sequence-expression: &lt;start&gt;..&lt;stop&gt;[..&lt;step&gt;]
Bash calls its range syntax a <dfn>sequence expression</dfn>.
a{d,c,b}e results in ade ace abe
For brace expansion, bash generates all string alternatives, separated by spaces.
Since bash does brace expansion before anything else, it can contain other metacharacters, e.g. * or _, but they will be interpeted at the appropriate step later.

####### Tilde expansion

tilde expansion is performed if a word begins with a tilde.
tilde expansion takes an argument that is specified between the tilde and the next /
With tilde expansion, if no argument is given, the tilde will merely evaluate to $HOME
~foo|the home directory of the user with the name foo
~+/foo|$PWD/foo
~-/foo|$OLDPWD/foo
~<n> as well as ~+<n>|what would be displayed by dirs +<n> (ie the nth directory on the directory stack)
~-<n>|what would be displayed by dirs -<n> (ie the nth directory on the directory stack counting from the back)

The ‘$’ character introduces parameter expansion, command substitution, or arithmetic expansion. 

####### Shell parameter expansion

While parameter expansion is disabled within '', it works in "", but also in unquoted strings.
In shell parameter expansion, the thing being expanded may be enclosed in curly braces, which is optional in some circumstances, and mandatory in others.
Assinging to a variable does not require the $ character, but referring to a variable is a form of parameter expansion and therefore does.
Bash supports a bunch of fancy parameter expansion features, which all require there to be {} surrounding them.

Within parametere expansion, prefixing a parameter with ! indicates indirection.
Indirection in parameter expansion means that if your parameter expands to another parameter name, it will then recursively expand this (to one level of depth)

Within parameter expansion, * and @ are nearly equivalent.
Within parameter expansion, to refer to an entire array, use arrayname[@/*]
Within parameter expansion, to refer to the special parameters $* or $@, use just * or @.

Bash allows specifying defaults for parameters within parameter expansion.
Bash's three operators for specifying defaults within parameter expasion are :-, :+ and :=.
Bash default for parameter syntax: parameter(:-|:+|:=)default
:- and := within parameter expansion evaluate to the parameter if not unset or null, or to the alternative otherwise.
The difference between :- and := is that :- will leave parameter unchanged, while := will substitute the value of parameter with the default.
:+ is the exact inverse of :-, it will only evaluate to the default if it is not null or unset.

Bash's slicing feature is performed within parameter expansion:
Bash slice syntax: ${parameter:start:length}

Many parameter expansions allow a pattern which is evaluated according to the usual pattern matching rules.

Bash's replacing within string is performed within parameter expansion:
general pattern (replace first instance) ${parameter/find/replace}
//pattern/replace|replace all instance
/#pattern/replace|replace if at beginning of string
/%pattern/replace|replace if at end of string

parameter#pattern get the shortest substring that matches pattern at the beginning
parameter##pattern get the longest substring that matches pattern at the beginning
parameter%pattern get the shortest substring that matches pattern at the end
parameter%%pattern get the longest substring that matches pattern at the end
parameter^pattern test each single character against the pattern, and uppercase the first one that matches
parameter^^pattern test each single character against the pattern, and uppercase all that match
parameter,pattern test each single character against the pattern, and lowercase the first one that matches
parameter,,pattern test each single character against the pattern, and lowercase all that match

parameter@operator do different things with the string depending on the operator
parameter@U|uppercase the string
parameter@u|uppercase the first character
parameter@L|lowercase all characters
parameter@Q|quote the parameter

Getting the length of something is done within parameter expansion: #parameter

####### Command substitution

Command substitution takes a command and replaces it (and the syntax) with its output.
Command substitution is performed in the modern syntax with $(command).
Command substitution is performed in the older, deprected syntax with `command`.
Command substitution may be nested.

####### Arithmetic expansion

Arithmetic expansion evaluates arithmetic and replaces it (and the syntax) with the result.
Arithmetic expansion is performed by $(())

####### Process substitution

Process substitution allws referring to the in or output of another process as a file.
To implement process substitution, bash creates an anonymous pipe with two file descriptors.
anonymous pipes file descriptors start at /dev/fd/63 and count downards
Process substitution runs asynchronously.
<(command) provides the output of command as a file for further use.
\>(command) provides a 'file' for a command to write to that will be used as stdin for the provided command. 
command1 >(command2) is equivalent to command1 | command2 if command1 supoorts outputting to sdout
e.g. a command doesn't output to stdout, but just a file
<() is used more commonly than >() because it is more common that a program expects multiple inputs as files than that it outputs multiple outputs as files.

####### Word splitting

Word Splitting	  	How the results of expansion are split into separate arguments.
the shell scans the results of parameter expansion, command substitution, and arithmetic expansion, if they did not occur within double quotes, for word splitting.
Word splitting means splitting the things mentioned above into words using $IFS
IFS is a prepopulated environment variable specifying what counts as a word separator.
IFS is used by a number of commands and control structures (e.g. looping) by default.
IFS is short for internal field separator.
The default value of IFS is whatespace.


####### File name expansion

filename expansion expands strings containing wildcards to pathnames.
filename expansion is perfomed using an utility/syntax known as glob.
The process of filename expansion is also known as globbing.
globbing recognizes wildcards.
a wildcard is a character(s) that expand to something else but their literal value.
a word containing a wildcard is known as a pattern

In the file name expansion stage, bash scans each word for a pattern and replaces it with an alphabetically sorted list of filenames matching the pattern.
In the file name expansion stage, bash retains patterns that didn't match anything as-is by default.
nullglob makes patterns disappear if they don't match anything
failglob makes patterns fail if they don't match anything.
When a pattern is used for filename expansion, the character ‘.’ at the start of a filename or immediately following a slash must be matched explicitly, unless the shell option dotglob is set. The filenames ‘.’ and ‘..’ must always be matched explicitly, even if dotglob is set. 
To see what a command will actually get from a file name expansion, you can prefix it with `echo`

wildcard|matches
*|matches 0-n arbitrary characters, excluding directory separators
**|0 - infinity characters, including directory separators
?|matches 1 arbitrary character
@(foo|bar|baz)|one of the options foo, bar, baz
?(foo|bar|baz)|zero or one of the options foo, bar, baz
+(foo|bar|baz)|one ⁑or more⁑ of the options foo, bar, baz
!(foo|bar|baz)|none of the options foo, bar, baz
*(foo|bar|baz)|zero or more of the options foo, bar, baz
[^&lt;characters&gt;]   one character that is none of &lt;characters&gt;
[!&lt;characters&gt;]   one character that is none of &lt;characters&gt;
[aml]   one of the characters a, m, l
[a-m]   one character in range of characters a-m

to activate bash wildcards using (), you have to enable extglob with shopt

.gitignore uses a similar syntax to globbing

####### Quote removal

After the preceding expansions, all unquoted occurrences of the characters ‘\’, ‘'’, and ‘"’ that did not result from one of the above expansions are removed. 

###### Redirection

Before a command is executed, its input and output may be redirected using a special notation interpreted by the shell. 

redirecting input [<n>]<[&](<path>|<n>)
redirecting output [<n>]>[>|\|][&](<path>|<n>)

redirecting input opens the file for reading at file descriptor <n> (most commonly standard input)
redirecting output opens the file for writing at file descriptor <n> (most commonly standard input)
clobbering a file is to overwrite its contents.
redirecting ouptut will clobber by default, unless noclobber is enabled, in which case > must be followed by | to force clobbering
redirecting output will append instead of clobber if > is used instead of >>
if one wants to redirect standard output and error at the same time, there is the short form &><path> or >&<path>, of which the first is preferred. adding another > appends instead, as per usual.
<n><&<n> <n>>&<n> make the first file descriptor <n> refer to the same file as the second file descriptor <n> is pointing to.
e.g. 1>out.txt 2>&1  make the file descriptor 1 refer to the same file as the file descriptor 2
<n>>&- or <n><&- close the file descriptor <n>.
<n>>&<n>- or <n><&<n>- make the first file descriptor <n> refer to the same file as the second file descriptor <n> is pointing to, and then close the second file descriptor <n> (basically a move)
using <> instead of < or > opens the file in read&write mode
using <> and & allows one to read from and write to the same file

for redirecting, the <n> before the < or > may be the number of any file descriptor, though the standard streams are most common.

1> may be abbreviated > 
0< may be abbreviated <

if a file is to be used as input to a command, there is often no reason to do cat file | command, since one could also do command < file

###### command execution

####### aliases

alias-command ::= alias{ name=vale}
the alias command with no arguments lists available aliases
aliases are only replaced if they are the first word of a simple command.
Aliases have very error-prone semantics, so using shell functions is almost always preferred.
sometimes an extra file bash_aliases is created for storing aliases, however bash does not itself read from bash_aliases so it needs to be sourced from other files.

####### pipelines

the character indicating an anonymous pipe is |
In a general sense, a ⟮c8;filter⟯ ⟮c9;takes some input⟯, ⟮c+;transforms it⟯, and ⟮c+;produces some output⟯.
In shell contexts, filters are combined with anonymous pipes.
Multiple filters combinded by anonymous pipes are a pipeline.
In shell contexts, filters normally recieve their input from STDIN and output it to STDOUT.
Well-behaved programs should operate as filters inf possible.
|& is the same as |, but it also outputs its standard error thrugh the pipe.
While they are often called merely pipes, the pipes in pipelines are actually anonymous pipes.
anonymous pipes <-> named pipes.

Pipes, whether anonymous or named, basically consist of two file descriptors (one read, one write) and a buffer.
pipes are simplex in direction.
The default behavior in a pipe is for the writing and reading ends of a pipe is to exhibit blocking behavior. 
When in a pipeline, the write file descriptor is connected to the stdout of the first process and the read file descriptor is connected to the stdin of the second process.

When the second process reads from the buffer created by a pipe, this is called draining the pipe.

theoretically, any program that reads from stdin should read from terminal input if given no standard input (as cat does), however some programs don't.

######## liquid (semantically appropriate)

Liquid also features filters prominently to transform values, and also uses the pipe | as a separator.
filter name (liquid)|filter action|constraints
⟮c1;date: "formatstring"⟯|⟮c2;date formatting⟯
⟮c5;markdownify⟯|⟮c6;transform from markdown⟯|⟮c7;jekyll only⟯
⟮c25;append: foo⟯|⟮c26;append foo to the string⟯
⟮c3;prepend: foo⟯|⟮c4;prepend foo to the string⟯


####### exit status

exit allows you to exit the current (sub)shell, optionally specifying an exit code.
success|0 
some kind of failure|not 0
miscellaneous error|1
(bash builtins) incorrect usage (invalid/missing arguments)|2

##### concepts

###### Parameters

In bash, a parameter is an entity that stores a value.
In bash (as in other languages), a positional parameter one passed by position (indicated by $1 ... $9)
In bash, there is a special set of parameters that is auto-set.
In bash, a variable is a type of parameter, specifically one denoted by a name.
In bash, a parameter may be indicated by a name (names are the usual type of [a-zA-Z0-9_]), by a number, or by a special character.
In bash assignment statements, only some forms of expansion are performed, specificaly tilde, parameter, command and arithmetic (ergo not brace and filename)
Bash assignmet statements may appear as arguments to the declaration commands
In the context where an assignment statement is assigning a value to a shell variable or array index (see Arrays), the ‘+=’ operator can be used to append to or add to the variable’s previous value.
+= in bash may add, append to array or append to string depending on the context.

Besides the positional parameters, shell has a set of special parameters which are auto-populated, but to which cannot be assigned.
*/@|expands to all positional parameters. They are the same when unquoted, when quoted $* expands to a single word separated by IFS, and $@ expands to separate words "$1" "$2"...
#|amount of positional parameters
?|exit status of most recent command/pipeline (foreground)
$|PID of shell, except in (), where it still has the PID of the shell and not the subshell
!|PID of job in background
0|name of shell or shell script
-|options the shell was launched with

NOT CONTENT JUST STOPPING THE PARSER FROM FREAKING OUT $

###### declaration commands

declaration commands = {alias, declare, typeset, export, readonly, local}

declare-command ::= declare {<option>} {<name>[=value]}

-f|functions with definitions
-F|functions without definitions
-r|readonly

in bash, declare prints the variables to which a given option applies if no names are given, or applies the option to the given names if some are given.
Thus the declare builtin can be used for a light form of typing.
for declare options, using + instead of - turns off the attribute instead (yes, really)
The typeset command is supplied for compatibility with the Korn shell. It is a synonym for the declare builtin command.
the type command indicates what it would be interpeted as if used as a command name (e.g. is a shell builtin, is a function, etc.).

#### conventions

##### commands

most configurable commands are done so by a config file, either at ~/.commandname or XDG_CONFIG_HOME/commandname if following the XDG base directory specification, some also read from a global config file generally in /etc. Some commands also have a file ending in rc for config in those locations, though rc files generally specify commands to run beforehand more than settings.

The unix philosophy says each program should do one thing well and be designed to work together with other programs, most commonly by accepting text as IO.

###### common syntax considerations

-o PATH|generally short for/equiv to --out or --output
-O|output to current directory with same name. (curl, wget)
-(-)out, --output PATH|Write the output to a path (presumably, instead of STDOUT). Mac accept some sort of string interpolation, e.g. via C format string|curl, say, youtube-dl
--progress|show an indicator of progress|say
-f THINGY|generally short for/equiv to --file, sometimes also --from or --format
--file FILE|Use the file as input|say
-t SECONDS|Specify a length of caffeination in seconds|caffeinate (macOs only)
-t THINGY|Generally short for --to
-r|generally short for/equiv to --recursive
-R|generally short for/equiv to --recursive|chown
--recursive
-v|generally short for/equiv to --verbose or --version more rarely for --voice
--voice VOICE|speak whaterver with the relevant voice (generally only for things on mac that can use `say` in the background)
--verbose|verbose output
--version|show the version
-h|generally short for/equiv to --human-readable or --help
--human-readable|human readable output
--help|show a short set of info/options, generally shorter than man
-i|generally short for/equiv to --interactive, may also be short for --in-place, --include, --ignore-case/--case-insensitve
--include|
--interactive|prompt before doing something
--in-place|edit in-place, i.e. don't emit an extra file
-n NUMBER|amount of something
-n|generally short for --number
-d|prevent display from sleeping|caffeinate (macOs only)
-s|generally short for/equiv to --set
-u|generally short for/equiv to --unset
--dry-run|show what would happen withou changing anything
-a|show dotfiles or archive mode = preserve various attributes & structures
-E|use ERE instead of BRE (Only where applicable, obv)
--lines|count/specify the number of lines

Options ≈ switches ≈ flags are indicated by hyphen(s) followed by characters
By convention, an option started by a single hyphen is one character long.
By convention, an option started by two hyphens is multiple characters long.
Generally, multiple single character flags can be joined into one: -h -a = -ha
In general, mac only features short flags, while linux also has long ones (this presumably has a deeper reason that I currently don't know)
In general commands that do something from a source to a target (e.g. cp, mv) have the default syntax SOURCE TARGET
⟮c1;⟯
-- normally ends the list of flag arguments and allows you to pass plain arguments


##### man

Most CLI commands have a manual page, which can be diplayd with man.
When we want a man entry for a composite command (e.g. git log, jekyll serve), the man entry headword (by convention) is the same, but hyphenated (git-log, jekyll-serve)
The numbers in parenthesis after the names of things (xterm(1), efence(3)) come from sections of the manual
The standard sections of the manual include:
1      User Commands
2      System Calls
3      C Library Functions
4      Devices and Special Files
5      File Formats and Conventions
6      Games et. Al.
7      Miscellanea
8      System Administration tools and Deamons

##### pagers

a ⟮c1;pager⟯ is ⟮c2;a terminal program⟯ that ⟮c3;paginates⟯ its input. 
the ⟮c5;default pager⟯ for the terminal is set in the env variable ⟮c4;PAGER⟯. 
`⟮c6;less⟯` is the most common ⟮c7;pager⟯. 

### users and groups

GID|group id
UID|user id
groups/users on nix are uniquely identified by their user or group ID.
groupadd is the command for creating new groups.
gpasswd is the command for managing /etc/group and /etc/gshadow.
id is the command for printing things like UID, GID, etc.
the groups command lists the groups a user is in.
/etc/groups defines the groups on the system:
etc-groups ::= {<group-name>:<password-encrypted>:<GID>:<member_list><newline>}
passwd – modify a user's password

#### commands

whoami|show current username
login|login as user
logout|logout of shell

#### superuser

superuser = root = admin(istrator)
OS-independently, the superuser/root/administrator is a user with large to unlimited power over the system.
In unix, the superuser is the user with the UID 0.
In unix, the three groups that hasve superuser/sudo-related priviledges are wheel, sudo and admin.
sudo allows executing a single command with superuser priviledges.
To use sudo you need to enter your own password, to use su you need the password of the relevant user, in this case the superuser password.
Who can use sudo is managed in /etc/sudoers
visudo edits the sudoers file in a safe fashion with your configured VISUAL/EDITOR.
getpass is the C function that makes sure that password input is hidden (nothing is displayed) on the comamnd line
sudo usually caches the entered credentials for a short while.
The su utility requests appropriate user credentials and switches to that user ID (the default user is the superuser).  A shell is then executed.
su = substitute (in the past super) user
sudo = substitute (in the past super) user do

-E = --preserve-env

##### polkit

polkit is a toolkit to allow finer-grained control than just running sudo.
Polkit defines ⟮c1;actions⟯, ⟮c2;who can use them (group/user)⟯, and ⟮c3;under which circumstances⟯.
pkexec works like sudo, but instead opens a window for password entry (it also depends on polkit policies)

### projects

freedesktop.org was formerly called X Desktop Group (XDG)
freedesktop.org governs projects such as the X Window System, wayland or systemd

# communication

## concepts

A telegraph is a system for communicating at a distiance via coded signals
semaphore is telegraphy via visual signalling.
master/slave is (problematically) when one entity controls or serves as an example to other entity(s)
Crosstalk is a signal transmitted on a channel causing an undesired effect on another circuit or channel

### serial and parallel

Serial communication sends its information one after another over the channel.
Parallel communication sends multiple piecies of information simultaneously over multiple subchannels.
One would expect parallel communication to be faster than serial communication, with the factor equivalent to the amount of channels/wires/whatever, however serial communication can often be clocked far higher to make up for it.
Serial communication is often far easier/simpler to implement and thus less error-prone, cheaper and thinner/lighter than parallel communication.

### allow & deny

an allowlist implies forbidding everything by default
an allowlist enumerates a set of things that may pass
a denylist implies allowing everything by default
an denylist enumerates a set of things that may not pass
allowlists were/are known as whitelists
denylists were/are known as blacklists

### pushpullpoll

pulling is where the request initiates from the client, and is responded to by the server
pushing is where a request is initiated by a server.
polling is frequently checking whether a thing is in a certain state
polling may be used to simulate push protocols.

### state

#### sessions

In computer science, a ⟮c4;session⟯ is ⟮c2;started at some point⟯, ⟮c3;ends at some point⟯, and during this time ⟮c1;maintaines state⟯.
A browser session starts when the browser is opened and ends when the browser is closed (unless session restoring is used.)
A login session starts when a user logs in and ends when a user logs out or the existence of the session is otherwise terminated.

### proxy

⟮h∞;<img src="Proxy_concept_en.svg">⟯
A ⟮c1;proxy (server)⟯ is a ⟮c2;server/server application⟯ that ⟮c3;acts as an intermediary between⟯ ⟮c4;a client requesting a resource⟯ and ⟮c4;the server providing that resource.⟯
A reverse proxy is a proxy that appears to clients to be an ordinary server, but forwards requests to other servers in the background.
⟮h∞;<img src="Reverse_proxy_h2g2bob.svg">⟯
Reverse proxies are sometimes called surrogates or gateways.

### directions

simplex|one direction only
duplex|bidirectional
half duplex|bidirectional, but only one at a time
full duplex|bidirectional, both simultaneously

### fresh and stale

In technical contexts, ⟮c1;fresh⟯ and ⟮c2;stale⟯ are often contrasted. 
In technical contexts, something ⟮c3;fresh⟯ is ⟮c4;still relevant/valid/useful⟯. 
In technical contexts, something ⟮c5;stale⟯ is ⟮c6;no longer relevant/valid/useful⟯. 

## design

The ⟮c+;robustness principle⟯ is "⟮c+;be conservative in what you send⟯, and ⟮c+;liberal in what you accept⟯".
The robustness principle is often said to be ⟮c+;good design⟯, but also ⟮c+;create bad de-facto standards⟯

## interfaces 

At its most general interface is a shared boundary across which information flows.
An interface specifies specific channels (endpoints, methods, ...) for the access of information.

### API

API = application programming interface
An API is an interface of a piece of software/module/web service/etc.
the point where one interfaces with an API is an endpoint
Glue code is code that is needed to make two things (mostly interfaces) which are not interoperable interoperable.
A wrapper library is a library that contains one or more other libraries and transforms their interface into a different interface.
wrapper libraries may be glue code, but also may be for abstraction or to improve a mediocre interface.
API bindings are glue code to allow one to call a specific API.
API bindings for libraries are generally wrapper libraries.
A foreign function interface allows one to call functions of a different language from ones given language.
A foreign function interface often calls C or C++ functions (due to their ubiquity).
To use a foreign function using a foreign function interface often requires you to write some glue code (e.g. the signatures), though most of the glue code is handled by the language itself.
ffis may be glue code. 
One could write one's own API bindings or a wrapper library using a foreign function interface.
A shim is a library that takes API calls for something else and then does something with them.
A shim may do one or more of with a given call: redirect it, change the arguments, handle it itself.
A polyfill is a shim for a browser API, which passes it through if available, and implements it itself if not.

#### APIs for certain purposes

Data|Name|Interface
⟮c1;DWD open weather data⟯|⟮c2;Bright Sky⟯|⟮c3;JSON⟯


## protocols

A protocol is a set of rules that allows transmitting messages via a medium.
Protocols are often layered to produce a protocol stack.
While the medium over which a message may be transferred for a protocol may be an actual medium, in protocol stacks the medium is merely a lower protocol.
In protocol stacks, the only truly physical medium is the lowest layer.
A message in any protocol typically consists of some headers/metadata and a payload.
A protocol data unit is the fundamental unit a protocol transmits, i.e. its message.
If a protocol is acting as a medium for a higher layer in a protocol stack, a service data unit is the payload of the protocol data unit of the current protocol, which IS the protocol data unit of the higher layer.

Protocols that are transferred over wires as a medium typically also define the characteristics of these wires and the eletrical connectors connecting them.

PDU = Protocol data unit
SDU = Service data unit

### hardware / low-level

#### NFC

NFC = Near field communication
NFC works via induction.
NFC works at a distance of up to ~4 cm

#### PCI

PCI   Peripheral Component Interconnect
PCIe  Peripheral Component Interconnect Express
PCI is a parallel bus, PCIe is a serial bus
PCI, AGP (older), PCIe (today) are the protocols/connectors that were/are used to connect things on the motherbord, especially PC expansion cards but also some of the things soldered on.

#### thunderbolt

Thunderbolt 1 and 2 are transmitted via the MiniDisplayPort connector.
Thunderbolt 3 and 4 are transmitted via the USB C connector.
Apple and Intel co-developed Thunderbolt around 2011.
Thunderbolt was designed to run over optic fiber cables, but actually generally runs over copper.
1|10 Gbit/s
2|20 Gbit/s
3|40 Gbit/s
4|40 Gbit/s

#### DP

https://upload.wikimedia.org/wikipedia/commons/f/f1/DisplayPort_Connector.svg|DisplayPort Connector
<img src="sm_300px-Mini_DisplayPort_on_Apple_MacBook.jpg">|Mini DisplayPort Connector
Mini and nonmini ⟮c4;DisplayPort⟯ is mainly for ⟮c1;video / audio⟯, but can also carry ⟮c2;USB⟯ and ⟮c3;other data (e.g. thunderbolt)⟯

#### ATA

ATA is short for Advanced Technology Attachment, though due to IBM trademarks its officially short for nothing.
ATA was renamed PATA after SATA was introduced.
ATA/PATA|parallel
SATA|serial
PATA & SATA are interfaces for secondary storage
SATA is the successor to PATA
SATA
I|1.5Gb/s
II|3Gb/s
III|6Gb/s
III Rev 3.2|16 Gb/s

#### usb

USB   Universal serial bus
USB can transmit both data of various kinds as well as power.
The speed of USB depends on the version of USB, indicated with a number.
The role in the master/slave architecture of USB is indicated by a letter.
The connector type of USB depends on the letter indicating its role within the master/slave system, as well as the size specifier.

A|Master
B|Slave
AB|complicated
C|Either Master or Slave dynamically

Size specifiers: ø, mini, micro.

USB C only exists as a single size.

USB versions: 1.0, 1.1, 2.0, 2.0 revised, 3.0, 3.1, 3.2, 4.0

Within USB 3, usb 3.1 and 3.2 were renamed

table:class=yesno;Standard |USB 1.0 |USB 1.1 |USB 2.0 |USB 2.0 Revised |USB 3.0 |USB 3.1 |USB 3.2 |USB4
type=th;Maximum transfer rate |span=2;12 Mbps |span=2;480 Mbps |5 Gbps |10 Gbps |20 Gbps |40 Gbps
type=th;Type A |span=4;<img src="https://upload.wikimedia.org/wikipedia/commons/7/7e/USB_Type-A_receptacle.svg" width="75" height="50"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/f/f4/USB_3.0_Type-A_receptacle_blue.svg" width="75" height="67"> |span=2;class=no;Deprecated
type=th;Type B |span=4;<img src="https://upload.wikimedia.org/wikipedia/commons/2/28/USB_Type-B_receptacle.svg" width="50" height="60"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/8/8c/USB_3.0_Type-B_receptacle_blue.svg" width="59" height="75"> |span=2;class=no;Deprecated
type=th;USB-C|span=3;class=no;N/A|span=5;<img src="https://upload.wikimedia.org/wikipedia/commons/0/07/USB_Type-C_Receptacle_Pinout.svg" height="80">
type=th;Mini-A|class=no;N/A|span=3;<img src="https://upload.wikimedia.org/wikipedia/commons/e/eb/USB_Mini-A_receptacle.svg" width="75" height="50"> |span=5;class=no;Deprecated
type=th;Mini-B|class=no;N/A|span=3;<img src="https://upload.wikimedia.org/wikipedia/commons/e/ec/USB_Mini-B_receptacle.svg" width="67" height="50"> |span=5;class=no;Deprecated
type=th;Mini-AB|span=3;class=no;N/A|<img src="https://upload.wikimedia.org/wikipedia/commons/f/f3/USB_Mini-AB_receptacle.svg" width="60" height="40"> |span=5;class=no;Deprecated
type=th;Micro-A|span=3;class=no;N/A|<img src="https://upload.wikimedia.org/wikipedia/commons/8/86/USB_Micro-A.svg" width="75" height="50"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/4/42/USB_3.0_Micro-A.svg" width="117" height="50"> |span=2;class=no;Deprecated
type=th;Micro-B|span=3;class=no;N/A|<img src="https://upload.wikimedia.org/wikipedia/commons/1/1b/USB_Micro-B_receptacle.svg" width="75" height="42"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/a/a8/USB_3.0_Micro-B_receptacle.svg" width="117" height="50"> |span=2;class=no;Deprecated
type=th;Micro-AB|span=3;class=no;N/A|<img src="https://upload.wikimedia.org/wikipedia/commons/6/6c/USB_Micro-AB_receptacle.svg" width="75" height="50"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/7/7a/USB_micro_AB_SuperSpeed.png/117px-USB_micro_AB_SuperSpeed.png" width="117" height="69"> |span=2;class=no;Deprecated

USB has a tree (bus + star) topology 


##### usb 4

USB 4 was released in 2019.
As of USB 4, the only connector type is USB C.

### Internet Protocols

#### network admin tools

ifconfig is a linux tool to configure networke interfaces, though it is often deprecated in favor of iproute2.
iproute2 collects a bunch of legacy networking commands into a few commands, the most important of which are ip and tc.
speedtest-cli test the speed of your connection

#### model comparison

##### models

The OSI model remains useful, but unimplemented.
In both the OSI and the TCP/IP Model of how computers communicate, the application layer is the ⟮c1;top⟯ layer.
Internet protocol suite = TCP/IP
The internet protocol suite is a protocol stack
Instead of the OSI model, the TCP/IP model is used to model the communication on the internet today.
One of the first networks to implement the ⟮c1;TCP/IP protocol suite⟯ and one of the precursors to ⟮c2;the internet⟯ was ⟮c3;ARPANET⟯

##### layers

table:OSI Model|TCP/IP Model|PDU (TCP/IP)|Communicant identifier
Application|span=1,3;Application||path of URL (I think)
Presentation
Session
Transport|Transport|segment (TCP) / datagram (UDP)|Port
Network|Internet|Packet|IP Address
Data Link|Link|frame|MAC Address
Physical

Frame contains IP packets contains segment/datagram contains application protocol message

TCP/UDP segments/datagrams are transmitted in IP packets between hosts.
IP packets are transfered in frames between routers.

table:style=table-layout: fixed;|||style=background-color: #9f9;Data||type=th;⟮c1;s∞;Application⟯
||style=background-color: #d8b;UDP / TCP header|style=background-color: #8d8;(UDP / TCP) data||type=th;⟮c2;s∞;Transport⟯
|style=background-color: #87e;IP header|span=2;style=background-image: linear-gradient(to right, #b7a 50%, #8d8 50%);(IP) data||type=th;⟮c3;s∞;Internet⟯
style=background-color: lightsalmon;Frame header|span=3;style="background-image: linear-gradient(to right, #87e 33%, #d8b 33% 66%, palegreen 66%);(Frame) data|style=background-color: lightsalmon;Frame footer|type=th;⟮c4;s∞;Link⟯

<style> tr td {width: 15%} tr th {width: 40%} </style>

##### hardware

layer no|layer name|device that moves things here
3|Network/Internet|Router
2|Data Link|Switch, Bridge, WAP
1|Physical|hub

WAP|Wireless Access Point

Network hubs act to connect a network on the physical layer by mirroring an incoming signal to all other ports, thus seeming like a directly connected network on the data link layer.
Network bridges/switches act to connect multiple link-layer network segments, which thus aggregates them to a single network on the network/internet layer.
A wireless bridge is a network bridge used for wireless networks.
A network switch is a multiport network bridge.
A network switch uses the MAC addresses to make sure that the the frame is sent to only the host that needs it.
Routers pack IP packets into frames and forwards those to the next router.
A ⟮c1;wireless router⟯ performs the functions of ⟮c2;a router⟯ and of ⟮c2;a wireless acces point⟯ (and sometimes others as well)
Most commonly, a ⟮c1;(network) gateway⟯ is a ⟮c2;router⟯ that ⟮c3;provides access to (acts as a door to) a local network⟯, but the term may also ⟮c4;refer to a bunch of other things⟯
If a (normal office/home) computer user wants to load a web page, at least two network gateways are accessed—one to get from the office or home network to the Internet and one to get from the Internet to the computer that serves the web page.

While you may have as many Switches, bridges, and hubs as you like, to connect to the internet at large, you'll need a router.

Multilayer switches are switches that don't just operate on the data link layer, but also on higher layers (generally 3 and/or 4).
Content switches are multilayer switches that operate up to layer 7, and are often used in CDNs

The function of a firewall is to filter  incoming network traffic.
a firewall filters network traffic according to a variety of rules, the most basic of which might be blocking most ports unless needed
A firewall generally operates on the network/internet layer and up.

###### alternative names

a ⟮c1;network switch⟯ is more rarely also called a ⟮c2;bridging⟯/⟮c2;switching⟯ ⟮c3;hub⟯ or a ⟮c4;MAC bridge⟯

#### layers

##### layer 7

HTTP, SMTP, POP, SSH, telnet...

###### common concepts

####### URLS & Hyperlinks

######## URI

IRI   Internationalized Resource Identifier
URI   Uniform Resource Identifier
URN|Uniform Resource Name
URLs generally locate things on the internet, generally on the application layer.
URIs used to be subdivided into URLs and URNs.
Mainly historically, URLs were for locating things, and URNs were unique identifiers of a resource.
Today, URNs are merely another scheme of URIs, urn:
URL and URI are often used synoynously even in expert circles, even RFCs disagree.
URI can only use an ASCII-subsset.
Within URIs ASCII subset, there is a distinction between reserved and unreserved characters.
URI unreserved characters: ⟮c5;alphanumerical⟯, ⟮c4;-⟯, ⟮c3;_⟯, ⟮c1;.⟯, ⟮c2;~⟯ (the rest are reserved)
IRIs are a superset of URIs that also allow for non-ASCII characters.

In URLs, Reserved characters and characters outside of the URL character set need to be URL/percent-encoded

uri ::= <scheme>:[//<authority>/]<path>[?<query>][#<fragment>]
host ::= <ipv4-address>|<ipv6-address>|<FQDN>
authority ::= [<userinfo>@]<host>[:<port>]
userinfo ::= <username>[:<password>]
query ::= <key>=<value>{<query-delimiter><key>=<value>}
query-delimiter ::= &|;

The password part of the userinfo component of an URI is deprecated (password inplaintext)
For HTML, the fragment of an URI is often an ID

URI schemes are generally the same as the application-level protocols they refer to, though there are schemes that do not correspond to protocols.
file is a scheme that is not a protocol, it allows accessing local files.
Most browsers have a scheme to navigate their own internal admin pages.
apt|installing apt packages
browsername|scheme for whatever browser-internal pages
tel|phone numbers
mailto|email messages

mailto-url ::= mailto:[&lt;email-address&gt;{,&lt;email-address&gt;}][?&lt;email-key&gt;=&lt;value-percent-encoded&gt;{&amp;&lt;email-key&gt;=&lt;value-percent-encoded&gt;}]
email-key ::= subject | cc | body | ...

######## URN 

the path of URN URIs can theoretically be anything, however it typically has the following syntax
urn-path ::= <urn-namespace>:{<urn-subnamespace>:}<unique-id> 
urn-namespace ::= ISBN|ISSN|UUID|...
e.g. urn:oasis:names:specification:docbook:dtd:xml:4.1.2

######## origins

The group of scheme/host/port making up a web resources origin are sometimes called the (scheme/host/port) tuple
in a scheme, host, port tuple, host is actually the FQDN
a web resources ⟮c1;origin⟯ is defined by its ⟮c2;scheme/protocol⟯, ⟮c3;FQDN(often inaccurately just called host)⟯, and ⟮c4;port⟯ tuple
Two or more URLs that share a common origin (s/h/p tuple) are same-origin, all others are cross-origin
The ⟮c1;same-origin⟯ policy allows ⟮c2;same-origin⟯ access by ⟮c3;default⟯, and ⟮c3;provides predefined channels and restrictions⟯ for ⟮c2;cross-origin⟯ access
The ⟮c1;same-origin⟯ policy is relevant only when ⟮c2;two pages want to communicate⟯
The same-origin policy is ⟮c1;active⟯ (⟮c1;in some shape or form⟯) in ⟮c2;all modern browsers⟯

######## domains

A domain consists of n labels separated by dots.
The further right a label is in a domain name, the higher it is in the hierarchy.
FQDN = fully qualified domain name
PQDN = partially qualified domain name
TLD = top-level domain
The FQDN is the domain including all labels.
The PQDN is a domain which only includes a part of the FQDN.
The rightmost label of a FQDN is the TLD.
the second-rightmost label of a FQDN is a second-level domain.

A host is a device connected to a computer network.
In technically correct usage, the leaf of a given FQDN is the hostname.
hostname comes from it being the name of the host, a device connected to a network.
frustratingly hostname is often also used as a synojym for PQDN or FQDN
Domains to the left of a domain label are subdomains of that label.
Domain is a very ambiguous term: It may refer to everything but the hostname, any PQDN, or the FQDN.
a public suffix is a domain under which one can or at one point could register a domain name.
examples: .co.uk, .com, .tech
Many public suffixes are TLDs, but e.g. .co.uk is a public suffix but not a TLD, while some country codes are TLDs but not public suffixes (since authorities of some country code TLDs (e.g argentinia in the past) only allow registrations on subdomains such as .com.ar)
A registrable domain name consists of a single label plus a public suffix.
A registrable domain name is so called because it is or at one point would have been registrable

In the past, the www hostname was popular, since webservers might have had many different application-level services and thus there was a desire to enforce separation between them.

######### linux hostnames

Linux has three hostnames, static, transient, and pretty.
The pretty hostname can be pretty much anything
The static hostname is used for programmatic purposes, the transient hostname is used as a fallback.
While the pretty hostname can be pretty much anything, static and transient hostname are limited to 64 characters.

the `hostname` command shows the hostname, which is the same for DNS, NIS and YP.

######## hotlinks, deeplinks

hotlinking = inline linking
Hotlinking is embedding a resource from ⟮c1;another fqdn⟯
A deep link may be a link that links to any other page than the site's home page, a link that links to content within an installed app instead of a webpage (polysemy).
A link to the homepage of a page is called a surface link

####### URL manipulation libraries/objects

`URL`|JS

The ⟮c+;URL⟯ constructor takes ⟮c+;a string of the url⟯, and optionally ⟮c+;a base url⟯ (if the url is ⟮c+;relative⟯)

###### applications

####### cURL

⟮c3;cURL⟯ is a project for ⟮c4;transferring data⟯ using various ⟮c5;application protocols⟯. 
one half of ⟮c6;cURL⟯ is ⟮c7;the command-line tool⟯ ⟮c8;curl⟯. 
the other half of ⟮c9;cURL⟯ is ⟮c10;the library libcurl⟯ with ⟮c11;bindings for most major programming languages⟯. 
curl syntax: ⟮c12;curl⟯ ⟮c13;[options]⟯ ⟮c14;{URLs⟯} 

⟮c15;s16;-i⟯ and ⟮c16;s15;--include⟯ ⟮c17;show HTTP response headers⟯ 
To ⟮c18;set custom headers⟯ in curl, use ⟮c19;s20;-H⟯/⟮c20;s19;--header⟯ ⟮c21;"My-Header: My value"⟯ 
To ⟮c22;set the query string⟯ to a certain value in curl, use ⟮c23;s44;-d⟯ OR ⟮c44;s23;--data⟯ ⟮c24;'key=value&amp;key2=value2'⟯ 
To ⟮c25;simulate a filled in form⟯ with curl, use ⟮c26;s45;-f⟯ or ⟮c45;s26;--form⟯ ⟮c27;"key=value"⟯ (supports ⟮c28;more fancy syntax for files etc.⟯ )  
To make curl ⟮c29;fail on error⟯, use ⟮c30;s31;-f⟯ or ⟮c31;s30;--fail⟯ 
To ⟮c32;make a HTTP HEAD request (instead of the default GET⟯) with curl, use ⟮c33;s34;-I⟯ or ⟮c34;s33;--head⟯. 

To ⟮c35;make curl follow redirects (e.g. 301 Moved Permanently⟯), use ⟮c36;s37;-L⟯ or ⟮c37;s36;--location⟯ 
If ⟮c38;you've specified -L/--location⟯ for curl, ⟮c39;--max-redirs⟯ sets ⟮c40;how many redirects you want to follow⟯. ⟮c41;-1⟯ means ⟮c42;infinite redirects⟯ 

There are bunch of sites ⟮c43;designed to be `curl`ed⟯ to do something useful. 

Site|Does what when `curl`ed?
⟮c1;wttr.in⟯|⟮c2;get weather⟯


####### various data-fetching CLIs

######## youtube-dl

⟮c1;youtube-dl⟯ is a ⟮c8;CLI⟯ tool for ⟮c2;downloading from⟯ ⟮c4;mainly⟯ ⟮c3;youtube⟯, ⟮c4;but also from other platforms⟯. 
basic syntax for youtube-dl: `⟮c5;youtube-dl⟯ ⟮c6;[OPTIONS]⟯ ⟮c7;URL {URL⟯}` 


youtube-dl: ⟮c9;don't actually download the video, just preview⟯, so to speak: ⟮c10;-s/--simulate⟯ 

There is ⟮c11;a set of options⟯ for ⟮c12;youtube-dl⟯ that ⟮c13;start with --get-⟯ and ⟮c14;only return the requested information (e.g. id, format, filename, title, duration, etc.⟯) 
  ± --get-format, --get-title, etc. ±<br>

The ⟮c15;--format / -f FORMAT⟯ option of youtube-dl is for s⟮c16;electing the format you want to download the thing in⟯. 
You can ⟮c17;list available formats for --format⟯ with ⟮c18;--list-formats/-F⟯ 


--format accepts a sophisticated syntax as an argument: (it's actually slightly more complicated, but I've simplified a little)
```
Format specifier syntax: ⟮c19;--format⟯ ⟮c20;&lt;format-specifier&gt;⟯⟮c21;{,&lt;format-specifier&gt;⟯}  # for ⟮c22;downloading mutliple formats at once⟯
⟮c23;format-specifier⟯: ⟮c24;&lt;single-format&gt;⟯⟮c25;{/&lt;single-format&gt;⟯} # for ⟮c26;relative precedence of multiple formats, depending on what's available⟯
⟮c27;single-format⟯: ⟮c28;&lt;single-format-selector&gt;[+&lt;single-format-selector&gt;]⟯ # if ⟮c29;two are specified⟯, ⟮c30;the first one is for video and the second is for audio⟯
⟮c31;single-format-selector⟯: ⟮c32;[&lt;general-quality&gt;]⟯⟮c33;{\[&lt;property&gt;&lt;operator&gt;&lt;value&gt;\]⟯}
⟮c34;general-quality⟯: ⟮c35;&lt;file-extension&gt;|&lt;quality-keyword&gt;⟯
⟮c36;file-extension⟯: # will ⟮c37;get the best format⟯ of ⟮c38;the given file extension, e.g. mp3⟯
⟮c39;quality-keyword⟯: ⟮c40;best|worst|bestvideo|worstvideo|bestaudio|worstaudio::contains |⟯
⟮c41;property⟯: # things such as ⟮c42;filesize, width, height, tbr (total average bitrate), fps, ...⟯
⟮c43;operator⟯: # things such as ⟮c44;=, !=, &gt;.... as well as ^=, $=, *= etc.⟯
```


The ⟮c45;s46;-x⟯/⟮c46;s45;--extract-audio⟯ option makes ⟮c47;youtube-dl extract the audio into its own file⟯. 
If ⟮c48;using -x/--extract-audio⟯, you ⟮c49;can specify the format⟯ ⟮c50;with --audio-format FORMAT⟯, which ⟮c51;accepts the subset of things for --format FORMAT⟯ that ⟮c52;make sense for audio⟯. 


###### protocols

####### WHOIS

whois is the command to query WHOIS.

####### SMTP, IMAP, POP

SMTP = Simple Mail Transfer Protocol
IMAP = Internet Message Access Protocol
POP = Post Office Protocol

SMTP is used by mail servers for sending and recieving email, and by mail clients typically only for sending messages
IMAP or POP3 are both used to retrieve email messages (though they can be used for other things)
IMAP keeps messages on the server while POP3 deletes them (by default)
Between IMAP and POP3, IMAP is more feature-rich.

####### HTTP

HTTP|HyperText Transfer Protocol

⟮c1;HTTPS⟯ is an ⟮c2;encrypted⟯ version of ⟮c3;HTTP⟯
A ⟮c1;mixed content⟯ page is a ⟮c2;HTTPS⟯ page that ⟮c3;also includes content fetched over HTTP⟯

When you navigate to a new URL, the browser sends an HTTP request
The client sendds a HTTP request, and the server returns an HTTP response.
http-request-message ::= <http-request-header-part><CRLF>[<http-request-body>]
http-request-header-part ::= <http-request-line>{<http-request-header>}
http-request-line ::= <request-verb> <path> <HTTP-version><CRLF>
http-request-header ::= <key>: <value><CRLF>
HTTP/2 did not change the HTTP semantics, merely stuff under the hood.

in HTTP/1.1, in a request, besides the request line, a host header is necessary
HTTP request verbs are case-sensitive
If a form is submitted via POST, the query string ends up in the body of the request message
If a form is submitted via GET, the query string ends up in the request url as the query element
When you make a GET request to a directory, e.g. `/directory/`, it will return `/directory/index.html`, if extant, or possibly the directory listing if enabled, otherwise 404

http-respose-message ::= <http-response-header-part><CRLF>[<http-response-body>]
http-response-header-part ::= <http-status-line>{<http-response-header>}
http-response-line ::= <<CRLF>
http-reponse-header ::= <key>: <value><CRLF>

######## request verbs

TRACE   Ask the server to return a diagnostic trace
PUT   Ask the server to store the data
POST   Post data up on the web server
OPTIONS   Ask the server to return the list of request methods it supports
HEAD   Get the header that a GET request would have gotten
GET   Get a resource from the server
DELETE   Ask the server to delete the data
CONNECT   Tell a proxy to connect to another host and simply reply the content

######## status codes

⟮c1;Status-Code⟯|⟮c2;Reason-Phrase⟯|Further explanation
⟮c3;1xx⟯|⟮c4;Informational⟯
⟮c5;100⟯|⟮c6;Continue⟯|⟮c6;The server is working on it, dammit!⟯
⟮c7;2xx⟯|⟮c8;Success⟯
⟮c9;200⟯|⟮c10;OK⟯|⟮c10;The request is fulfilled.⟯
⟮c11;3xx⟯|⟮c21;Redirection⟯
⟮c12;301⟯|⟮c22;Move Permanently⟯|⟮c22;The resource has moved permanently.⟯
⟮c13;302⟯|⟮c23;Move Temporarily⟯|⟮c23;The resource has moved temporarily.⟯
⟮c14;304⟯|⟮c24;Not Modified⟯|⟮c24;The resource has not been modified⟯
⟮c15;4xx⟯|⟮c25;Client Error⟯
⟮c16;400⟯|⟮c26;Bad request⟯|⟮c26;The server could not understand the request⟯
⟮c17;401⟯|⟮c27;Authentication Required⟯|⟮c27;Requires Username/Password⟯
⟮c18;403⟯|⟮c28;Forbidden⟯|⟮c28;Server refuses to supply the resource, regardless of identity of client⟯
⟮c19;404⟯|⟮c29;Not Found⟯|⟮c29;The requested resource cannot be found in the server⟯
⟮c32;405⟯|⟮c20;Method Not Allowed⟯|⟮c20;The method used (e.g. POST) is a valid method, but the server does not allow that method for the resource requested⟯
⟮c33;451⟯|⟮c30;Unavailable For Legal Reasons (refrence to ray bradburry⟯)</td>
⟮c33;5xx⟯|⟮c30;Server Error⟯
⟮c34;500⟯|⟮c31;Internal Server Error⟯|⟮c31;Server is confused⟯
⟮c35;501⟯|⟮c39;Method not Implemented⟯|⟮c39;The method name is invalid (e.g. Get instead of GET⟯)
⟮c36;502⟯|⟮c40;Bad Gateway⟯|⟮c40;Proxy recieved bad response from upstream server⟯
⟮c37;503⟯|⟮c41;Service Unavailable⟯|⟮c41;Server cannot respond due to overloading or maintenance⟯
⟮c38;504⟯|⟮c42;Gateway timeout⟯|⟮c42;Proxy/Gateway recieved a timeout from an upstream server (gateway seems to be a bit of a misnomer here, or at least it doesn't refer to a router but justt is a synonym for proxy⟯)


######## cache

A ⟮c9;cache⟯ is a thing that ⟮c10;stores data⟯ so that ⟮c11;future requests for that data⟯ ⟮c12;can be served more quickly⟯. 
With ⟮c13;caching and esp. with HTTP caching⟯, the guiding principle is that you want to ⟮c14;store the thing as long as possible⟯, but ⟮c15;update it as soon as it changes⟯. 

A ⟮c16;web cache⟯ AKA ⟮s16;⟮c17;HTTP cache⟯⟯ is ⟮c18;a cache for HTTP requests⟯. 
⟮c19;web/HTTP caches⟯ can either be ⟮c20;shared⟯ or ⟮c21;local/private⟯. 
a ⟮c22;shared⟯ ⟮c23;HTTP cache⟯ sits ⟮c24;somewhere in the internet⟯ and ⟮c25;has many users⟯. 
a ⟮c26;local/private⟯ ⟮c27;HTTP cache⟯ sits ⟮c28;in your web browser⟯ and ⟮c29;is only used by you⟯. 
⟮c30;Any HTTP request⟯ will ⟮c31;first be routed through⟯ ⟮c32;your browser cache⟯ and perhaps ⟮c33;a few network caches⟯ to see if ⟮c34;there is a fresh copy of the response available⟯. 

The main mechanism ⟮c35;HTTP caching⟯ uses is ⟮c36;the Cache-Control header⟯. 
In the days of ⟮c37;HTTP 1.0⟯, the ⟮c38;Pragma header⟯ was used for ⟮c39;caching⟯. 
The ⟮c40;Cache-Control header⟯ is sent ⟮c41;by the server⟯ and&nbsp;specifies ⟮c44;if a resource can be cached⟯, ⟮c42;who can cache it⟯, and ⟮c43;how long it can be cached⟯. 
The ⟮c45;Cache-Control header::caching⟯ consists of ⟮c46;a comma-separated list⟯, with either ⟮c47;boolean keywords⟯ or ⟮c48;key=value pairs⟯ ⟮h∞;(cookie e.g. has a ; separated list) ⟯. 
To specify ⟮c49;how long⟯ ⟮c50;a cache entry⟯ is ⟮c49;fresh (when it becomes stale⟯), one can either specify ⟮c51;max-age=value⟯ as ⟮c52;part of the Cache-Control header⟯ or ⟮c53;the separate Expires header⟯. 
⟮c54;Maximum value⟯ for ⟮c55;Cache-Control:⟯ ⟮c56;max-age⟯ is ⟮c57;1 year⟯ 


    <tr><th colspan="2">Keywords for Cache-Control for if to/who can cache a resource
⟮c1;public⟯|⟮c2;Cache anything, even things that are not normally cached (weird HTTP status codes etc.⟯)
⟮c3;private⟯|⟮c4;Don't cache in shared cache, only in private cache (e.g. browser⟯)
⟮c5;no-cache⟯|⟮c6;Check with the server for change with each request (but don't redownload if unchanged⟯)
⟮c7;no-store⟯|⟮c8;Do not cache the resource in any way⟯


an ⟮c58;ETag⟯ is a mechanism for ⟮c59;judging whether a resouce has changed⟯. 
An ⟮c60;ETag⟯ is ⟮c63;a fingerprint⟯ for ⟮c61;a specific version⟯ of ⟮c62;a file⟯. 
An ⟮c64;ETag⟯ is ⟮c65;opaque⟯ to ⟮c66;the client⟯ but ⟮c65;transparent⟯ to ⟮c66;the server⟯ 
For ⟮c72;ETags⟯, the ⟮c71;server⟯ needs to decide on ⟮c70;a fingerprinting algorithm⟯ that ⟮c68;takes into account⟯ ⟮c69;the file and the version⟯ and ⟮c68;outputs⟯ ⟮c67;a fingerprint⟯. 
The ⟮c73;ETag fingerprint⟯ is sent along by ⟮c76;the server⟯ as ⟮c74;a part of the response⟯ in ⟮c75;an ETag header⟯. 
If we're using ⟮c77;ETags⟯ and ⟮c78;a resource expires⟯, the ⟮c80;client⟯ sends along the ⟮c77;ETag⟯ ⟮c79;fingerprint⟯ in ⟮c79;a If-None-Match header⟯. The ⟮c80;server⟯ uses this to check whether ⟮c81;the fingerprint⟯ still ⟮c82;corresponds to the current version of the file⟯, and returns ⟮c83;304 Not Modified⟯ if ⟮c85;true⟯, or ⟮c85;else⟯ a ⟮c84;normal 200 OK response⟯. 

There's no ⟮c88;built-in/non-hacky way⟯ in ⟮c87;HTTP⟯ to ⟮c86;notify a client that a resource has expired⟯ if they don't ask for it. 
⟮c89;Cache busting⟯ AKA ⟮s89;⟮c90;revving⟯⟯ is a '⟮c93;hack⟯' to ⟮c91;force browsers to redownload new resources⟯ even if ⟮c92;they are not expired.⟯ 
⟮c94;Cache busting⟯ sets ⟮c95;the longest possible max-age⟯ on resources, and if ⟮c96;there are changes⟯, it ⟮c97;renames the file in some way (e.g. a hash suffix⟯), which ⟮c98;forces the browser to redownload⟯. 
⟮c99;Cache busting⟯ is generally done by ⟮c100;build tools such as Webpack automatically⟯ 

⟮h∞;<img src="sm_tmpyvxwccqz.png">⟯


######### cookies

By default, HTTP is stateless, ergo technologies such as cookies exist to enable state.

⟮c1;Cookies⟯ are a concept within ⟮c2;HTTP⟯. 
⟮c3;Cookies⟯ allow ⟮c6;the server⟯ to ⟮c4;keep track of state⟯ in ⟮c5;HTTP⟯, which is itself essentially ⟮c4;stateless⟯. 
⟮c7;Cookies⟯ are usually ⟮c8;first set⟯ by ⟮c9;the server⟯. 
The ⟮c10;server⟯ ⟮c13;sets the cookies⟯ via the ⟮c11;`Set-Cookie`⟯ ⟮c12;HTTP Header.⟯ 
The ⟮c14;browser⟯ ⟮c17;sends⟯ ⟮c16;all relevant cookies⟯ ⟮c17;back to the server⟯ ⟮c15;on each request⟯. 
Syntax of the ⟮c18;`Set-Cookie` HTTP Header⟯: `⟮c19;Set-Cookie⟯: ⟮c20;&lt;cookiekey&gt;=&lt;cookievalue&gt;⟯⟮c22;{;⟯ ⟮c21;&lt;cookiepropertykey&gt;[=&lt;valuepropertykey&gt;]⟯⟮c22;} ⟯` 
The ⟮c23;`Set-Cookie` HTTP Header⟯ typically contains ⟮c24;one cookie⟯ and ⟮c24;its properties⟯, to ⟮c25;set multiple cookies⟯ ⟮c26;set multiple headers⟯ (there is also a way of ⟮c27;separating them with commas⟯, but ⟮c28;this is nonstandard and often does not work⟯) 
The browser ⟮c29;sends cookies back on request⟯ via ⟮c30;the `Cookie` HTTP header⟯. 
The syntax of the `⟮c31;Cookie⟯` header: `⟮c31;Cookie:⟯ ⟮c32;&lt;cookiekey&gt;=&lt;cookievalue&gt;⟯⟮c33;{;⟯ ⟮c34;&lt;cookie2key&gt;=&lt;cookie2value&gt;⟯⟮c33;} ⟯` 
Since ⟮c35;cookies are sent back on each request⟯ and since ⟮c36;there are spec-defined size constraints⟯, ⟮c37;the things sent in cookies⟯ are usually ⟮c38;quite small, often only a UID⟯. 

⟮c39;Session cookies⟯ are cookies that ⟮c40;only last until the browser is closed⟯, allthough ⟮c41;they can often be restored by the browser via session restoring⟯. 
⟮c42;Cookies⟯ without an ⟮c43;Expires⟯ or ⟮c43;Max-Age⟯ attribute are ⟮c44;session cookies⟯. 
⟮c45;Persistent cookies⟯ are ⟮c46;cookies that last for a specific time⟯. 
⟮c47;Cookies⟯ with an ⟮c48;Expires⟯ or ⟮c48;Max-Age⟯ attribute are ⟮c49;persistent cookies⟯. 

Due to the ⟮c53;cookie spec⟯, one can usually rely on ⟮c54;cookies⟯ being able to hold at least ~⟮c50;4kb⟯ and at least ⟮c51;50⟯ ⟮c52;cookies per domain⟯, though ⟮c55;often the real limits are far higher⟯ 

Since ⟮c61;persistent cookies⟯ are ⟮c62;deleted⟯ ⟮c63;after their Max-Age&gt;age or their Expires date has passed⟯, one can ⟮c62;delete⟯ them by ⟮c64;manually moving this into the past⟯. It is also common practice to ⟮c65;set their content to an empty string⟯. 

By default, ⟮c66;cookies⟯ ⟮c67;are only sent⟯ for ⟮c68;requests⟯ for ⟮c69;the FQDN that the cookie was sent from⟯. 
By default, ⟮c70;cookies⟯ ⟮c71;sent from a certain FQDN⟯ are ⟮c72;not included⟯ in ⟮c73;the browsers requests for subdomains⟯. 
Specifying the ⟮c74;`Domain`⟯ property of a ⟮c75;cookie⟯ means ⟮c76;it will be sent⟯ for ⟮c77;requests for the specified FQDN⟯, and ⟮c76;all⟯ subdomains (thus being more permissive than the default!) 
By default, ⟮c78;cookies⟯ are ⟮c81;sent by the browser⟯ ⟮c80;no matter⟯ ⟮c79;the path in the URL⟯ ⟮(c:80;only⟯ ⟮c79;the FQDN⟯ matters). 
If the ⟮c82;Path⟯ attribute is ⟮c83;specified for a cookie⟯, ⟮c84;browsers will only sent the cookie⟯ on ⟮c85;requests for the specified path (or subpaths⟯). 

⟮c86;Cookies⟯ that ⟮c87;originate from⟯ ⟮c88;the same domain as the current domain⟯ ⟮h88;(including ⟮c89;subdomains⟯ if ⟮c89;Domain is set⟯) ⟯ are known as ⟮c90;first-party cookies⟯, all others are ⟮c90;third-party cookies⟯. 

⟮c91;Cookies⟯ ⟮c92;used to maintain the state of being logged⟯ in are known as ⟮c93;authentication cookies⟯ (the whole process is known as ⟮s91-93;c94;cookie-based authentication⟯ ) 
⟮c94;Cookies⟯ used to ⟮c95;maintain the state of an unique user⟯ ⟮c96;with whom to associate browser histories⟯ are known as ⟮c97;tracking cookies⟯. 

The ⟮c98;Secure⟯ property of a cookie means ⟮c101;that it is only ever sent over HTTPS⟯. 
The ⟮c99;HttpOnly⟯ property of a cookie ⟮c102;makes it inaccesible via JS⟯. 
The ⟮c100;SameSite⟯ property of a cookie can take three values, ⟮c103;Strict⟯, ⟮c103;Lax⟯, or ⟮c103;None⟯. 
The ⟮c104;SameSite⟯ property uses a definition of ⟮c105;Site⟯ which consists of ⟮c106;the registrable domain name⟯ and ⟮c107;scheme⟯ (which ⟮c108;can only be http or https anyway, since cookies are a HTTP-only concept.⟯) 
Cookies with ⟮c109;SameSite=Strict⟯ are ⟮c110;only sent⟯ when ⟮c111;the site (registrable domain name + scheme⟯) ⟮c112;the request is being sent to⟯ is ⟮c113;the same as the site of the cookie⟯, i.e. ⟮c114;not on cross-site requests⟯. 
Cookies with ⟮c115;SameSite=Lax⟯ are sent ⟮c116;in the same circumstances as SameStrict=Strict⟯, plus on ⟮c117;cross-site requests⟯, if ⟮c118;the request is a browser navigation one (not e.g. for resources only⟯). 
Cookies with ⟮c119;SameSite=None⟯ have ⟮c120;no cross-site restrictions⟯, but ⟮c121;Secure must also be set⟯. 

The JS inteface for ⟮c56;cookies⟯ is ⟮c57;document.cookie⟯ 

A ⟮c58;zombie cookie⟯ is a cookie that ⟮c59;is restored even when deleted⟯, by using ⟮c60;various nooks and crannies of different internet technologies.⟯ 


######### Content Negotiation

Content Negotiation is a mechanism of HTTP that allows serving different versions of a document at the same URI depending on the prefrences of the user agent.
The headers for content negotiation are Accept and Accept-Language, Accept-Charset, Accept-Encoding

######## CDN

CDN = content delivery network or content distribution network
A CDN is a geographically distributed network of servers. 
The goal of a CDN is to provide high availability and performance by distributing the service spatially relative to end users.
unpkg|FOSS|npm pacakges
jsdelivr|FOSS|different platforms

####### telnet/ssh

SSH = secure shell
Telnet is a protocol that sends text plainly and immediately as 8-byte ASCII characters, with the high bit unset.
the SSH protocol, in contrast to the telnet protocol and the various rsh commands/protocols, is encrypted (via public-key cryptography).
SSH is a protocol whose main purpose is accessing the shell on other computers.
In accessing the shell on other computers, the SSH protocol has replaced rsh/telnet.
Besides accessing the shell on other computers, the SSH protocol allows for other network services, such as data transfer.
The berkeley r-commands are a suite of commands and associated protocols that are variants of well-known commands, but may be run remotely.
The berkeley r-commands all start r.
In doing various things on remote hosts, SSh has replaced the various berkeley r-command.
Specifically, to copy data between remote hosts, the scp command running over SSH has replaced rcp.
The berkeley r-commands, telnet and now SSH all have a client-server architecture.

SSH-commands allows using a short user@hostname form isntead of a full URL.
scp is cp (same syntax etc.) but remotely using SSH.
For scp, when using user@hostname, add the file with :filename to the end\

ssh-keygen manages keys for SSH.

####### NIS/YP

YP = Yellow Pages
NIS = Network Information Service
NIS and YP are the same thing, just that YP was trademarked in GB and hence NIS.
NIS/YP is a protocol for sharing configuration files between computers.
domainname shows or sets the NIS/YP (!) domain nime
aliases for domainname: nisdomainname, ypdomainname
dnsdomainname shows the systems DNS domain name (the part of the FQDN)

####### DNS

DNS|Domain Name System
the problem that both the hosts file and DNS want to solve is mapping hostnames/domain names to IP addresses.
the hosts file came about in the ARPANET era, where it was manually shared and updated.
DNS superceded the hosts file for the most part.
Today, the hosts file is used in some network bootstrapping, but mainly as a resource for internet resource blocking/redirection
To use the hosts file to block something, set its IP address to 0.0.0.0
hosts-file ::= {<hosts-line><linebreak>}
hosts-line ::= <ip-address> <hostname>{ <hostname>}

######## dig

dig is a CLI utility to look up DNS records.
dig-command ::= dig {<option>}[ <DNS-server>][ <resource-name>][ <record-type>]{ <query-option>}
query-option ::= +<query-option-name>

dig defaults to the DNS specified in /etc/resolv.conf if none is specified.
dig defaults to type of A if the record type is not specified

query option names
short|very short output
noall|don't show any of the sections
answer|show the answer part of the response (only has an effect if answer has been hidden e.g. with noall)

In digs output, non-records begin with ;;, non-records do not.

8.8.8.8|Google DNS nameserver

####### WebSocket

WebSocket is an application-layer communications protocol with client and server APIs.
WebSocket, being an application-layer protocol, is distinct from HTTP, but uses the same TCP ports, mainly for firewall-related reasons
WebSocket, in contrast to HTTP allows full-duplex communication and streams of data
WebSocket use the scheme `ws:` (if unencrypted) or `wss:` (if encrypted)
To change from HTTP to WebSocket, the WebSocket handshake uses the HTTP Upgrade header

######## client

on the client side, sockets are created via the `WebSocket` constructor
the `WebSocket` constructor recieves the necessary argument of the url, and an optional argument of which sub-protocols to use
to send data on a `WebSocket`, use the method `send()`
To ⟮c3;react to incoming data⟯ ⟮c2;event handlers are registered⟯ on the WebSocket object
the four common events a `WebSocket` might recieve client-side are open, message, close, error

######## server 

the most common node web sockets library is `ws`

####### DHCP

DHCP = Dynamic Host Configuration Protocol
DHCP is a protocol used for automatically assigning IP addresses and other parameters.
DHCP is an application-layer protocol using UDP as the transport layer
DHCP follows a client-server model
the four stages of DHCP operations are often abbreviated DORA
DORA = ⟮c3;DISCOVER⟯, ⟮c3;OFFER⟯, ⟮c4;REQUEST⟯, and ⟮c4;ACK(nowledge)⟯
The DHCP messages (e.g. DISCOVER) may also be referred to by prefixing  DHCP (e.g. DHCPDISOVER)
In general, a ⟮c1;client⟯ sends a ⟮c2;DHCP⟯ ⟮c3;DISCOVER⟯ request ⟮c4;on startup⟯ and then ⟮c5;periodically before it expires⟯
The ⟮c3;DHCP⟯ client sends its ⟮c1;DISCOVER⟯ and ⟮c1;REQUEST⟯ messages as a ⟮c2;broadcast⟯ initiallty, for ⟮c4;renewal⟯ it may also use ⟮c2;unicast⟯
On recieving a ⟮c1;DISCOVER⟯ request, the ⟮c2;DHCP server⟯ uses ⟮c3;its policies⟯ to decide which if any ⟮c4;IP address to assign⟯, and sends back an unicast message ⟮c5;OFFER⟯
A client can receive DHCP offers from ⟮c1;multiple servers⟯, but it will ⟮c2;accept only one DHCP offer⟯
In response to the DHCPOFFER, the client replies with a DHCPREQUEST message, broadcast to the server (can be unicast if renewal), requesting the offered address.
After the client ⟮c3;obtains an IP address via DHCP⟯, it should ⟮c4;probe the newly received address⟯ (e.g. with ⟮c1;ARP/NDP⟯) to prevent ⟮c2;address conflicts caused by overlapping addresses⟯

client         server
  |               |
  |---DISCOVER--->|
  |               |
  |<----OFFER-----|
  |               |
  |----REQUEST--->|
  |               |
  |<-ACKNOWLEDGE--|
  |               |

##### between application and transport

TLS/SSL are on top on the transport layer, but beneath the application layer, and are used as if they were the transport layer.
SSL is deprecated in favor of TLS, however TLS is often still called SSL

##### layer 4

The most common protocols in the ⟮c24;transport⟯ layer are ⟮c25;TCP⟯ and ⟮c25;UDP⟯. 
The ⟮c25;transport⟯ layer, directly beneath the ⟮c26;application⟯, but above the ⟮c27;internet⟯ layer is the ⟮c28;2nd⟯ layer from the top of the internet portocol suite. 
⟮c29;TCP⟯ is ⟮c30;more complex⟯ than ⟮c31;UDP⟯ (amongst other things) because it is ⟮c32;stateful⟯ 

###### nc

nc as a command is read netcat
nc allows you to make raw TCP/UDP connections.
nc [<options>] [<hostname>] [<port>]

###### ports

Ports exist only in software 
A ⟮c33;port⟯ is ⟮c34;uniquely identified by⟯ a ⟮c35;port number⟯. 
A ⟮c37;port number⟯ is a ⟮c36;16⟯ bit integer 
Ports that are ⟮c38;only used for a short time⟯ to do something are known as ⟮c39;ephemeral⟯ ports, which are generally used for ⟮c40;clients⟯ (because ⟮c40;the port of the client can be anything anyway⟯) 
the ⟮c44;dynamic⟯ or ⟮c45;private⟯ ports are often used as ⟮c46;ephemeral⟯ ports 

Port range</th>
    <th colspan="2">Is called
⟮c47;&lt;1024⟯|⟮c48;well-known⟯
⟮c49;1024 - 49151 (2^15 + 2^14⟯)|⟮c50;registered⟯
⟮c51;49152 (2^15 + 2^14) - 2^16⟯|⟮c52;dynamic⟯|⟮c53;private⟯



Generally, an ⟮c54;application protocol⟯ will have a ⟮c55;port number⟯ it ⟮c56;is associated with⟯ (esp. on ⟮c57;the server side⟯). 

####### preassigned

Protocol|Port
FTP|21
⟮c1;SSH⟯|⟮c2;22⟯
⟮c3;telnet⟯|⟮c4;23⟯
⟮c5;SMTP (plaintext⟯)|⟮c6;25⟯
⟮c7;DNS⟯|⟮c8;53⟯
⟮c9;HTTP⟯|⟮c10;80⟯
⟮c11;IMAP (plaintext⟯)|⟮c12;143⟯
⟮c13;HTTPS⟯|⟮c14;443⟯
⟮c15;SMTP (encrypted⟯)|⟮c16;587⟯
⟮c17;IMAP (encrypted⟯)|⟮c18;993⟯


####### conventional

HTTP dev servers|8080 or 8000

ports below 1024 require root permission to open

###### sockets

TCP|stream sockets
UDP|datagram sockets
A socket is a software interface to handle incoming/outgoing network traffic.
The most common type of socket is network/internet socket, and thus is often just called socket.
A network/internet socket exists at the transport layer
The socket address of a network/internet socket is the combination of IP address and port number.
A network/internet socket is minimally identified by the combination of socket address and transport protocol
A network/internet socket that has been connected to another socket (e.g. when using TCP), also is identified by the remote socket address.

###### TCP

TCP = Transmission Control Protocol

####### handshake

TCP three-step handshake
Client --SYN--&gt; Server
Client &lt;--SYN-ACK-- Server
Client --ACK---&gt; Server

###### UDP


####### Datagram header

the UDP ⟮c1;datagram header⟯ consists of ⟮c2;4⟯ ⟮c3;fields⟯ of ⟮c2;2⟯ ⟮c3;bytes⟯ for a total of ⟮c2;8⟯ ⟮c3;bytes⟯ (⟮c2;64⟯ ⟮c3;bit⟯)


field|optionality
source port|optional
destination port|mandatory
length|mandatory
checksum|mandatory in IPv6


octets|0 &amp; 1|2 &amp; 3
!type=th;0|style=background-color: #fa9;Source port|Destination port
!type=th;4|Length|style=background-color: #fa9;Checksum

####### Datagram

the maximum size of a ⟮c2;UDP datagram⟯ is ⟮c1;2^16 bytes⟯ (although IPv6 ⟮c3;jumbograms⟯ do allow more, and ⟮c4;headers⟯ take up some of that)

##### layer 3

The ping utility uses the ICMP protocol's mandatory ECHO_REQUEST datagram to elicit an ICMP ECHO_RESPONSE from an IP.
the main protocol that lives on the network (OSI)/internet (TCP/IP) layer is IP.

###### IP

IP  Internet protocol
IP has the task of delivering packets from the source host to the destination host solely based on the IP addresses in the packet headers.
IP (in general) works because connected routers know where packages starting with a certain IP routing/network prefix should go, and so on

the ⟮c1;host URL element⟯ for the ⟮c2;loopback address⟯ is usually ⟮c3;localhost⟯
the IP protocol data unit (the packet) is alternatively sometimes also called datagram.

####### hops

flex-container:<img src="Hop-count-trans.png">


A ⟮c+;hop⟯ occurs every time a ⟮c+;packet⟯ is ⟮c+;passed from one network to the next⟯. 
The ⟮c+;hop⟯ count is thus a rough measure of ⟮c+;distance between devices⟯.

####### address space

⟮h∞;<img src="1024px-Regional_Internet_Registries_world_map.svg.png">⟯
RIR = Regional Internet Registry
NRO = Number Resource Organization
There are 5 RIRs.
the 5 RIRs are affiliated via the NRO
5 RIR areas:, one for Africa, most of NA, latin and central america + Mexico, Europe + Russia/West Asia, and one for most of Asia + Oceania

####### headers

the ⟮c3;IPv4 header⟯ consists of ⟮c1;14⟯ ⟮c2;different fields⟯
TTL = Time To Live
TTL in IPv4 contexts was supposed to measure seconds, but was actually implemented as a hop count.
TTL as hop count was implmeneted by an 8-bit integer, usually starting at 64. When it reached 0, the packet was discarded and an ICMP time exeeded message was typically sent.
TTL exists amongst other reasons to prevent an infinite routing loop.
⟮c1;TTL⟯ is called ⟮c2;hop limit⟯ in ⟮c3;IPv6⟯

####### addr

######## IPv

The first major version of IP was IPv4, which is being succeeded by IPv6
The main reason IPv6 was introduced is that there are not enough IPv4 addresses

IPv4|32
IPv6|128

IPv4-addr = 1*3DIGIT "." 3("." 1*3DIGIT)

######### IPv6

the ⟮c+;quibbles/hextets/hexadectets/quad-nibbles⟯ of a IPv6 address are separated by ⟮c+;colons⟯
within an IPv6 address, ⟮c+;consecutive quibbles⟯ of ⟮c+;only zeroes⟯ may be ⟮c+;replaced with <q>:­:</q>⟯, but only ⟮c+;once in an address⟯, and not for ⟮c+;a single quibble⟯
within an ⟮c+;IPv6 address⟯, within a ⟮c+;quibble⟯, any ⟮c+;leading⟯ ⟮c+;zeroes⟯ may be ⟮c+;removed⟯


######## division

IP addresses have always been divided between network prefix and host identifier.
network prefix is also called routing prefix
host identifier is also called rest field or interface identifier
How network prefix and host identifier have been divided has varied over time

######### History

In the very beginning (until the 1980s) IP addresses were divided between the first octet as network prefix and the last 3 octets as host identifier.
In the very beginning (until the 1980s) what we call network prefix was called network number, and what we call host identifier was called rest field.
In the early 80s, IP addresses transitioned to classful IP addresses.
In classful IP addresses, there were different classes, which each had different network prefixes and host identifiers of different lengths.
In classful IP addresses, the first or first few bits would have indicated which class it was, the next however many relevant numbers would have been the network prefix, and finally the host identifier
⟮c+;Classful IP addresses⟯ were used until ⟮c+;the early 90s⟯ (⟮c+;1993⟯) and then replaced with ⟮c+;Classless Inter-Domain Routing⟯ (⟮c+;CIDR⟯)


######### CIDR

CIDR = Classless Inter-Domain Routing
cidr-notation ::= [<IPv4-addr>]/<int-0-32>
⟮c+;CIDR notation⟯ indicates ⟮c+;the length⟯ of ⟮c+;the network prefix⟯ (equivalently: ⟮c+;the amount of leading 1-bits⟯ of the ⟮c+;network mask⟯) as an ⟮c+;integer⟯, normally ⟮c+;after the IP address⟯ separated by ⟮c+;a `/`⟯
/24 = an IPv4 network that has a 24-bit newtwork prefix and 8-bit host identifiers

########## CIDR blocks

<img src="sm_cidr_addr.svg">

A CIDR block is a group of IP addresses sharing the same network/routing prefix.
⟮c+;CIDR Blocks⟯ ≈ ⟮c+;network/routing prefixes⟯ may be ⟮c+;further subdivided⟯, with ⟮c+;more and more⟯ of the IP address being looked at to ⟮c+;direct the traffic⟯
A CIDR block A which is completely contained within another CIDR block B is a subnet of B, B is a supernet of A.
All networks are implicitly subnets of the IP address space.
a ⟮c+;supernet(work)⟯ has a ⟮c+;shorter⟯ ⟮c+;network prefix⟯, whose ⟮c+;subnets⟯ will have a ⟮c+;longer⟯ ⟮c+;network prefix⟯ that ⟮c+;starts with⟯ the ⟮c+;supernet⟯&nbsp; ⟮c+;network prefix⟯
the largest ⟮c+;CIDR block (= sub/supernet)⟯ the IANA assigns is ⟮c+;/8⟯ (⟮c+;16 million⟯ addresses)

######### broadcast & network identifier

A ⟮c1;subnet/CIDR block⟯'s ⟮c2;broadcast⟯ address is the ⟮c3;all-ones⟯ version of the ⟮c4;host (any relevant IP address)/network (all-zeroes) identifier⟯
A ⟮c+;subnet/CIDR block⟯'s ⟮c+;network identifier⟯ address is the ⟮c+;all-zeroes⟯ version of the ⟮c+;host identifier⟯
The network identifer address is often functionally treated as the broadcast address.
The network identifier address of 173.240.0.0/16 is 173.240.0.0
The broadcast address of 173.240.0.0/16 is 173.240.255.255.

########## max broadcast and max identifier

Ergo, 255.255.255.255 (/0) is (theoretically) the broadcast address to all IP addresses in existence.
A godzillagram is theoretically a message to 255.255.255.255, which should theoretically broadcast to all IP addresses in existence.
Since gateways generally do not let godzillagrams pass, 255.255.255.255 generally merely boradcasts to your whole network.
Since network identifier addresses are generally aliases to broadcast addresses, 0.0.0.0/0 is an alias to the broacast address 255.255.255.255/0.
0.0.0.0/32 represents the undefined/NULL address, and may be used when one has not yet aquired an IP address or when accepting all incoming connections.

######### special IP addresses

all IP adresses with the CIDR notation ⟮c+;127.0.0.0/8⟯ (⟮c+;127.0.0.1⟯ - ⟮c+;127.255.255.254⟯, excluding ⟮c+;network identifier⟯ and ⟮c+;broadcast addresses⟯) are ⟮c+;loopback⟯ addresses
of the IPv4 loopback addresses, generally 127.0.0.1 is used.
localhost = 127.0.0.1 (IPv4)
IPv6 reserves only a single loopback address, which is ­:­:1

The private IPv4 address blocks sorted from largetst to smallest are: ⟮c1;10.0.0.0⟯/⟮c2;8⟯, ⟮c3;172.16.0.0⟯/⟮c4;12⟯, ⟮c5;192.168.0.0⟯/⟮c6;16⟯
(100000 = Prof X dual-wielding dual swords, 172160 = Android 17 outrunning a caravan of refugees, 192168 = Anakin skywalker outrunning a dragon)

####### NAT

NAT = Network Address Translation
⟮c1;NAT⟯ ⟮c2;maps one IP address space to another⟯ by ⟮c3;modifying the info in the IP header⟯
NAT could be one-to-one or one-to-many, generally one-to-many is implied
For one-to-many NAT, most commonly the combination of IP address and port number is sued to unabiguously identify the reciver
NAT (Network Address Translation)  allows mitigation of IPv4 address exhaustion because one IP address can be used for an entire network
the form of NAT where ⟮c+;the combination of IP address and port number is used to identify the recipient⟯ may also be known as ⟮c+;NAPT⟯ (⟮c+;network address and port translation⟯) , ⟮c+;PAT⟯ (⟮c+;port address translation⟯) or ⟮c+;IP masquerading⟯ amongst others

####### tracing

traceroute and tracepathe are *nix utilities to measure IP paths and transit durations.
⟮c1;tracepath⟯ is a ⟮c2;non-superuser⟯ version of ⟮c3;traceroute⟯
tracepath/traceroute sends messages with adjusted TTL values and uses ICMP time exceeded messages to identify the routers traversed by packets from the source to the destination.

####### ICMP

ICMP = Internet Control Message Protocol
ICMP is used to send IP/routing-related error/control message.
ICMP messages are sent within an IP packet

##### layer 2 & 3 

ARP = Address Resolution Protocol
NDP = Neigbor Discovery Protocol

ARP|IPv4
NDP|IPv6

ARP/NDP is used to discover the link layer address associated with a given internet layer address

##### layer 2

##### layer 2 & 1 (TCP/IP Link layer)

NIC = Network interface controller
A NIC is a hardware component used to connect a computer to a computer network (layer 1 & 2 (physical and data link))
MAC addresses identify NICs uniquely.
MAC addresses are 48 bit long.
MAC address = media access control address
Mac addresses are most commonly used with IEEE 802 technologies.

###### IEE 802

IEEE 802 networking technologies contain technologies such as bluetooth (formerly, now managed/standartized by the bluetooth special interest group), ethernet, and WLAN
IEEE 802.3|Ethernet
IEEE 802.11|WLAN/WIFI

####### WLAN

WLAN may run in ⟮c1;infrastructure⟯ or ⟮c2;ad-hoc mode⟯
(WLAN) In infrastructure mode, clients connect to  ⟮c1;a central WAP (Wireless Access Point)⟯
(WLAN) In ad-hoc network mode, clients connect ⟮c1;to each other peer to peer⟯

####### Ethernet

The ethernet frame header contains quite a few fields, amonst which the most important might be destination MAC address and source mac address

IPoE is short for IP over Ethernet
PPPoE is short for Point-to-Point Protocol over Ethernet

### protocols higher than the OSI/TCP/IP

For HTTP APIs, the endpoint is most commonly an URL + request verb.

#### REST

⟮c1;REST⟯ is short for ⟮c2;Representational State Transfer⟯
⟮c2;REST⟯ is a set of ⟮c1;constraints⟯/⟮c1;design principles⟯ for ⟮c3;APIs⟯
⟮c1;REST⟯ as an idea was created in ⟮c2;2000⟯ by ⟮c3;Roy Fielding⟯ in his ⟮c4;doctoral dissertation⟯
On a theoretical level, ⟮c1;REST⟯ consists of ⟮c2;6⟯ ⟮c3;constraints/criteria⟯.
While REST is theoretically implementation-independent, REST APIs generally transmit their data over HTTP as JSON
sometimes, HTTP APIs are called REST APIs even if they don't follow all constraints
an API following REST is often called RESTful
for the client-server constraint of REST to be met, client and server should be independent of each other, as long as the interface is not altered
Code on demand as a REST API constraint means that a REST endpoint may return code to execcute
RESTful APIs must be stateless, that is, the server does not have state, but rather any state information is transmitted by the client
The thing a RESTful API returns is called aaresource

##### six principles (alphabetical)

Cacheability
Client-server achitecture/decoupling
Code on demand
Layered system architecture
Statelessness
Uniform interface

##### HATEOAS

HATEOAS = Hypermedia as the Engine of Application State
HATEOAS(Hypermedia as the Engine of Application State) is part of the uniform interface constraint of REST
HATEOAS requires the responses of an API to contain all the relevant hyperlinks for further requests/action
in a RESTful API following HATEOAS, the API may change its URLs without creating incompatibilites
in a RESTful API following HATEOAS, one hits an initial API URL and navigates via hyperlinks from there.
Access in a RESTful API following HATEOAS is similar to a web-browsing user hitting a home page and finding their way from there

#### OAuth

OAuth is short for Open Authorization
The current version of OAuth  is OAuth 2
Most APIs use OAuth for granting access to them, e.g. to monitor access and enforce API limits.
OAuth is also commonly used to grant access to information of other accounts without giving up your password.
OAuth is often used for logging in with Facebook, GitHub, Google, etc.
In OAuth there are 4 roles/actors, the resource owner (= User), the client (= Application), Resource Server (= Where the accounts are located), and Authorization Server
in OAuth, any client (= application) needs to register themselves with a resource server.
When registering an application with a resource server, one needs to provide a callback URL, which is where the resource server will redirect users after registering. 
After registering an applicationwith the resource server, it will issue a client ID and secret.
the client ID is public, the secret must be kept private.
client ID and secret are functionally the username and password of the application
The permissions to be granted or not in OAuth are known as scopes.
While the flow of OAuth using redirection etc. is the most common flow, there are others

OAuth 2.0 (grant type: Authorization code)

flex-container:<img src="tmp7t5et6aw.png" />

TODO transorm flow into ascii art maybe

In general, when users want to sign in using OAuth:
1. the application makes a request using its client id
2. The user sees a screen asking them to grant access
3. The user clicks ok (or not) and is redirected
4. We get an authorization code
5. We exchange the authorization code for an access token
6. We can now make API requests

### misc

MTP|Media transfer protocol
PTP|Picture transfer protocol

## networks

A network is a group of connected nodes that communicate via a medium, and almost always via a protocol.

### concepts

#### routing

Routing is the process of selecting a path for traffic in a network or between or across multiple networks. 

##### addresses

An address is the identifier of an entity(ies) in a network, often relevant to a specific protocol.
A broadcast address is an address that identifies a subgroup of entities to target with a broacast transmission.
Loopback is the routing of signals/streams back to their source without intentional processing/modification.

##### routing schemes/architectures

Routing architecture visualization|name
⟮c1;<img src="sm_unicast.svg">⟯|⟮c2;Unicast⟯
⟮c3;<img src="sm_multicast.svg">⟯|⟮c4;multicast⟯
⟮c5;<img src="sm_broadcast.svg">⟯|⟮c6;broadcast⟯
⟮c7;<img src="sm_anycast.svg">⟯|⟮c8;anycast⟯



#### topologies

The topology of a network is how its vertices are arranged.
A tree network may consist of star networks connected ⟮c1;via a bus network⟯, or may be a tree just as a network.
In a bus, everyone attached recieves the transmission.
In a bus, only one entity can send at a time.
Sometimes, bus is used to refer any connection between two points, even if it isn't a bus (this definition is nonsense)
A daisy chain is a topology where devices are linked in a line or ring.

topology name|how it looks
⟮c1;star⟯|⟮c2;<img src="StarNetwork.svg">⟯
⟮c3;ring⟯|⟮c4;<img src="RingNetwork.svg">⟯
⟮c5;fully connected mesh⟯|⟮c6;<img src="FullyConnectedMeshNetwork.svg">⟯
⟮c7;partially connected mesh⟯|⟮c8;<img src="PartiallyConnectedMeshNetwork.svg">⟯
⟮c9;bus⟯|⟮c10;<img src="BusNetwork.svg">⟯
⟮c11;line⟯|⟮c12;<img src="BusNetwork.svg">⟯
⟮c13;tree⟯|⟮c14;<img src="TreeNetwork.svg">⟯


### types

#### telegraphs

The first type of telegraph was the optical telegraph.
The electrical telegraph began to overtake optical telegraphs middle of the 19th century.
electrical telegraph is often just shortened to telegraph.
The electrical telegraph uses electrical pulses as a medium.
Telegraph stations were connected by wires.
The first telegraph was the needle telegraph, later replaced by the telegraph with key and sounder.
⟮h∞;<img src="morse-vail-telegraph-key-1844-science-source.jpg">⟯A ⟮c1;telegraph key⟯ was/is a electrical switch where ⟮c2;pressing it⟯ would ⟮c3;produce a signal⟯ (and ⟮c4;holding it⟯ would ⟮c5;produce a longer one⟯).
The telegraph sounder would have produced clicks from the electrical impulses.
Telegraphs were operated by telegraph operators until the advent of teh writing  pelegraphs.

#### telex

flex-container:<img src="sm_dbb1bf63cbbb7831ac766c93ee6e10d8.jpg"><img src="sm_220px-Fernscheiber_01.jpg"><img src="sm_s-l1600.jpg">

Telex was the network of teleprinters common in a large part of the 20th century.
Rough synonyms (not abbreviations): Teleprinter, Teletypewriter, Telex
Abbreviations: teletypewriter -> teletype -> tty
Teletypewriters/teleprinters/telex/ttys have keyboard for input and a printer for output.
Video terminals then came to replace teletypewriters especially for computer IO
Teletypewriters + video terminals = physical/hardware terminals.

#### the internet

On a basic level, the internet is a system of globally interconnected ⟮c1;computer⟯ ⟮c1;networks⟯.
The internet runs on the internet protocol suite.

An intranet is a computner network for an organization, but which uses most of the the Internet protocol suite. 
An intranet that can be acessed from approved 3rd parties too is sometimes called  an extranet

##### standards

IANA  Internet Assigned Numbers Authority
IETF  Internet Engineering Task Force
BCP   Best current practice
RFC   Request For Comment

RFCs are generally published by the IETFs.
RFCs may document internet standards, but RFCs may also be informational or experimental and non-normative. 
BCPs are a subset of RFCs.

⟮c1;W3Schools⟯ weirdly is ⟮c2;unaffiliated with the W3C⟯ 
⟮c9;W3Schools⟯ is a website for ⟮c3;documentation/information⟯ for ⟮c4;web technologies/languages⟯ as well as ⟮c4;other languages⟯. 
In ⟮c5;the early 2010s⟯ ⟮c10;W3Schools⟯ was known to have ⟮c6;much low-quality information and errors⟯, leading to ⟮c7;the website w3fools pointing it out⟯. However, ⟮c8;today, most of it has been fixed⟯. 

##### the web

WWW = World Wide Web
The WWW runs on the internet, using the protocol HTTP(S).
The WWW is only one of many technologies running on the internet.
A web browser is a program to access the WWW.
The WWW was developed in CERN in 1989 by Timothy Berners-Lee.
The first web browser was written in 1990, the WWW was released in 1991.
The main organization working on web standards is the W3C.
World Wide Web Consortium = W3C
A web site is a collection of web pages, generally one that share a domain name/FQDN

###### user agents

User agent may mean any device that accesses web services for an user, or autohyponymously to a web browser specifically, or to the HTTP header User-Agent.

lynx, w3m|text-based browser

Qutebrowser is a vim-like browser written in python.
In qutebrowser, quickmarks are bookmarks that have a short name
For qutebrowser, you do ⟮c1;advanced config⟯ in ⟮c2;the config.py⟯ 
In the config.py of qutebrowser, you ⟮c3;can change most settings⟯ ⟮c4;on the `c` object⟯ 
In qutebrowser, greasemonkey scripts become active merely by placing them in $XDG_CONFIG_HOME/qutebrowser/greasemonkey

###### file-sharing

ephemeral file-sharing sites allow you to upload files which expire after a while

###### performance

https://developer.mozilla.org/en-US/docs/Web/Performance/Critical_rendering_path
https://developer.mozilla.org/en-US/docs/Web/Performance/Lazy_loading
TODO: More structure. How do these relate? WHat aspect of performance are they optimizing? Perhaps use PRPL as a structure, or something else, or a combination.

####### speculative parsing

Speculative parsing is that the browser will not block when hitting a script tag, but instead just continue parsing while fetching the script, and using the parsed DOM if the script hasn't modified it (which only really happens via document.write()).
Speculative parsing does not apply to images/css/videos, which will not block even if speculative parsing is disabled (the fact that it doesn't is a common myth)

####### lazy loading

lazy loading is loading things only when needed.
In general, one lazy-loads the things that are not critical to performance.
To enable lazy loading for images and iframes, set loading="lazy", these images will only load once they are a specific distance away from the viewport.

####### server push

Server push allows the server to send along resources it knows the browser will need directly on the first HTTP request (without the browser having requested them)
Server push is a feature of HTTP/2, used by specifying it in the HTTP header

####### minifcation

⟮c1;Minifying⟯ is ⟮c2;removing unnecessary characteristics⟯ (e.g. ⟮c2;longer names, whitespace⟯) from ⟮c3;source code⟯ to ⟮c4;reduce size⟯
⟮c1;minified files⟯ are commmonly indicated by ⟮c2;.min(.whatever)⟯

####### media compression

Images used ⟮c3;on the web⟯ are typically ⟮c2;specifically compressed⟯ beforehand, e.g. ⟮c1;by using programs such as imageoptim⟯

Image compression tools
|GUI|CLI|API|other
imageoptim|y|y|y
squoosh|web|y|n
sharp|n|n|n|npm module

####### PRPL

Push/Preload the most important resources
Render the initial route ASAP
Pre-cache remaining assets
Lazy-load other routes and non-critical assets

the "render the initial route ASAP" of PRPL is basically "reduce time to first (contentful) paint"
"render the initial route ASAP" can be achieved server-side by SSR/Static Generation, and client-side by stuff like async or defer (and maybe others)

######## P

⟮c1;&lt;link rel="preload"⟯ specifies that you ⟮c3;will need the resource very soon⟯, and that it should be downloaded ⟮c2;asyncly⟯ with ⟮c2;high priority⟯
⟮c1;&lt;link rel="preload"⟯ needs an ⟮c2;as=⟯⟮c3;"kind(e.g. style, script, image)"⟯
If you've specified a resource with &lt;link rel="preload", you still need to actually include it later

####### defer & async

defer & async are two attriubtes for <script> that influence how it is loaded.
Ignoring speculative parsing, when the browser hits a <script> tag, it blocks until it's loaded, which is not ideal since scripts are quite large, and the browser could be loading things in parallel.
Instead of the default behavior, the `defer` and `async` attribute of scripts tells the browser to load the script in the background.
Between  the `defer` and `async` attributes, defer executes scripts loaded in the background ⟮c1;when the dom is fully built⟯, in the order they were in the document
Between  the `defer` and `async` attributes, async executes scripts loaded in the background ⟮c1;as soon as possible⟯, in the order in which they load, no matter source order.

####### RAIL

RAIL is a performance model that centers on the user.
RAIL is short for Response, Animation, Idle, Load.
RAIL's perfomance model consists of goals for the four things of which it consists.
Response|respond to user input within 100ms. To account for other background tasks, budget 50ms.
Animation|provide an animation frame every 16ms (= 60FPS). Since browsers take about ~6ms to render a frame, budget max 10ms to calculate the frame. 
Idle|Use idle time so that other goals are met. Perform work in idle time in bursts of 50ms or less so that the Response goal is met.
Load|(subject to change with new technology) Load within 5s on first load and in 2s on subsequent loads on mobile.

####### minification

Source maps allow mapping minfied/compressed/otherwise transformed code back to the original source
to indicate a source map, at the bottom of the optimized file, add a magic comment or use the http header
source map magic comment: //# sourceMappingURL=foo/bar.js.map 

####### Google speed

PageSpeed Insights|Lab data & realworld data|Web Vitals|only website by default
Lighthouse|only lab data|Web Vitals & other data|GUI (devtools & website), CLI, CI pipeline

Lighthouse's Performance audits provides a grade consisting of (the scores of individual) metrics, but also offers opportunities and diagnostics::d... as ways to improve the metrics
Lighthouse consists of 5 categories, Performance, PWA, Best Practices, Accessibility, and SEO.

⟮c1;Web Vitals⟯ are the stats that ⟮c2;google⟯ measures to judge ⟮c3;the user experience of your websites⟯
⟮c1;Core Web Vitals⟯ are the subset of ⟮c2;Web Vitals⟯ that ⟮c3;apply to all web pages (and are thus considered very important)⟯
as of 2020, there are 3 core web vitals
Largest Contentful Paint, Cumulative Layout Shift|Core Web Vitals & Lighthouse Metrics
First Input Delay|Core Web Vitals 
First Contentful Paint, Speed Index, Time to Interactive, Total Blocking Time|Lighthouse Metrics

A ⟮c1;layout shift⟯ is when a ⟮c2;visible element⟯ ⟮c3;shifts position⟯ between ⟮c4;render frames⟯ (in bad cases causing users to e.g. ⟮c5;click the wrong button⟯)
⟮c1;Cumulative Layout Shift (CLS)⟯ is how google measures the ⟮c2;badness⟯ of the ⟮c3;layout shifts⟯ you've going on
The ⟮c1;largest contentful paint⟯ is when the ⟮c2;largest media/text block⟯ (which elements are exactly considered is more complicated) loaded, relative to ⟮c3;when the page first started loading⟯


a ⟮c1;long task⟯ is when ⟮c2;the main JS thread⟯ is ⟮c3;blocked⟯ for more than ⟮c4;50ms⟯
⟮c1;Total Blocking Time⟯ as a Lighthouse metric measures ⟮c2;cumulative length⟯ of ⟮c3;long tasks⟯ between ⟮c4;First Contentful Paint⟯ and ⟮c5;Time To Interactive⟯
the ⟮c1;Lighthouse Speed Index⟯ is how quickly ⟮c2;the viewport is visually populated with content⟯
⟮c1;Time to Interactive⟯ as a ⟮c2;lighthouse⟯ metric is the time it takes for a page to ⟮c3;become fully interactive⟯

CLS  Cumulative Layout Shift 
FCP  First Contentful Paint
FID  First Input Delay
LCP  Largest contentful paint

###### web analytics

In web analytics, a bounce is a person who only views one page of a site and then leave.
The bounce rate is the percentage of total site visitors who bounce.

##### infrastructure

###### clients

A thin client is a low-performance computer that mainly exists to connect with a server, which handles most of the computing & storage.
A zero client is a thin client driven to extremes, so that it has no local storage and barely any computing ability of its own.
Hardware terminals are basically zero clients.
a rich/fat/heavy/thick client is a client that contrasts with a thin client in that it can do more stuff itself.

## platforms running on the internet

### search engines

#### google

WIthin google search, ⟮c1;tbm⟯ is the key of the query parameter that ⟮c2;specifies the type of search (Image, News, Shopping etc.⟯) 
For example, ⟮c3;Specifying the search mode in google search as images⟯ is done by ⟮c4;`tbm=ish`⟯ 
Force google to ⟮c5;only finde pages from a certain domain⟯ is done by ⟮c6;site:foo.com⟯ 

### fora

#### text & imageboards

A ⟮c5;textboard⟯ is a ⟮c6;simple⟯ kind of Internet ⟮c7;forum⟯; most require neither ⟮c4;registration⟯ nor ⟮c4;entry of a screen name⟯. 
An ⟮c8;imageboard⟯ is like a ⟮c9;textboard⟯, just with ⟮c10;images⟯. 
⟮c11;Textboards⟯ as well as ⟮c11;imageboards⟯ were invented in ⟮c12;Japan⟯. 
⟮c1;Textboards⟯ such as ⟮c2;2channel⟯ are generally popular in ⟮c3;Japan only⟯, while ⟮c1;imageboards⟯ (e.g. in the form of ⟮c2;4chan⟯) are popular in ⟮c3;english-speaking countries too⟯ 

# applications

⟮c1;Photoscape X⟯ is notable for being a ⟮c2;GUI⟯ program that has ⟮c3;batch editing of photos⟯


#### full-on programs

##### subscriptions

podboat   podcast management for newsboat
newsboat|good rss reader
newsboat is the maintained fork of newsbeuter
newsboat stores the things its subscribed to in an urls file.
newsboat-subscription-file ::= {newsboat-subscription-line}
newsboat-subscription-line ::= <url>{ <newsboat-tag>}
newsboat-tag ::= <newsboat-tag-no-spaces>|<newsboat-tag-spaces>
newsboat-tag-no-spaces ::= <operator-prefix><string>
newsboat-tag-spaces ::= "<operator-prefix><string>"
operator-prefix ::= ~|!

~|make this the name of the feed
!|hide the feed


-x string, --execute=string   execute a command
commands e.g. reload

##### mail

mail or the older mailx are *nix builtins to manage mail.

##### bacvkup

borg, restic

##### termdown

termdown is a terminal timer utility.
termdown [OPTIONS] [TIME]
You can specify the time for termdown in a variety of formats.
SPACE|Pause
R|Reset
Q|Quit
L|Lap
-|subtract 10s
+|add 10s

--critical SECONDS|Draw final N seconds in red and announce them individually with --voice

##### pass

`pass` terminal-based password manager
`pass` edit plaintext version of file  `pass edit somepassword`
`pass` delete a password  `pass rm somepassword`
`pass` command for listing the passwords  pass ls (or just pass)
`pass` command for adding passwords  `pass insert/add`

##### misc

cal/ncal display a mini ascii calendar

#### online data fetching

`urban`|Terminal urban dictionary browser
`trans`|Use google translate to translate text
`deepl`|Use deepl to translate text

lang-specifier (trans, deepl) ::= [<lang>]:<lang>{+<lang>} ## leave out first arg for detection


#### sysadmin

powertop - cli program to analzye power consumption
mac: system_profiler|report system hardware and software configuration (mac)

##### hardware info

lspci   list pci devices
lshw   list hardware config
lsblk   list block devices
-f/--fs|list some extra info, esp. UUID
lsusb   list USB devices


# standards

unofficial extensions are generally indicated x-whatever

## licenses

A rights managed license allows only specific uses.
A royalty-free item is one with a license which allows unlimited uses without paying any more money.

### CC

The three attributes that a CC license can require (or not) are Attribution, Share Alike, No Derivates.
As of 2013, the newest version of CC is 4.0
CC0 releases the work into the public domain.

## identifiers


### language

The locale of a user is a set of values for a set of parameters related to language and region.
The locale is generally specified as an identifier.
On POSIX platforms, locales are specified as environment variables with a certain syntax.
posix-locale-identifier ::= language[_location][.charset][@modifier]
the environment variables for locales are LANG as well as various LC_*.
All LC_* locale variables are overwritten with LC_ALL.

the locale command shows the currently specfied locales.
/etc/locale.gen and the command locale-gen associated with it is used for generating locales

#### BCP47

A ⟮c17;IETF language tag⟯ indicates exactly ⟮c18;in which language a thing is⟯. 
Currently, the standard for ⟮c19;IETF language tags⟯ on the internet is ⟮c20;BCP47⟯. 
BCP 47: ⟮c21;&lt;primary-language&gt;⟯⟮c22;[-&lt;extended-language&gt;]⟯⟮c23;[-&lt;script&gt;]⟯⟮c24;[-&lt;region&gt;]⟯⟮c25;[-&lt;variant&gt;]⟯⟮c26;[-&lt;extension&gt;]⟯⟮c27;[-&lt;privateuse&gt;]⟯ 
BCP 47 language tags should be kept ⟮c28;as short as possible⟯. 

The ⟮c29;primary language⟯ subtag of ⟮c30;BCP 47⟯ is specified as ⟮c31;a language code⟯. 
A ⟮c32;language code⟯ consists of ⟮c33;2 or 3 letters⟯. 
⟮c34;Language codes⟯ are standartized in ⟮c35;ISO 639.⟯ 
⟮c36;3-letter language codes⟯ are standartized ⟮c37;in ISO 639-2 and -3⟯. 
⟮c38;2-letter language codes⟯ are standartized ⟮c39;in ISO 639-1⟯. 
⟮c41;extlang (extended language⟯) subtags are for ⟮c42;sublanguages of a given language (e.g. hakka chinese, the variants of arabic⟯) 
⟮c43;script⟯ subtags&nbsp;are for ⟮c40;writing systems⟯, and always ⟮c44;4 characters long⟯ 
⟮c45;region⟯ subtags are for ⟮c46;locations (countries, other geo regions⟯) 
⟮c47;variant⟯ subtags&nbsp;are for ⟮c48;dialects or other variations (however, use other tags if possible⟯) 

BCP 47 language tag|meaning
⟮c1;en⟯|⟮c2;english (no further info⟯)
⟮c3;zh-hak⟯|⟮c4;hakka chinese⟯
⟮c5;zh-Hans⟯|⟮c6;Chinese written in hanzi (simplified⟯)
⟮c7;en-GB⟯|⟮c8;english as spoken in great britain⟯
⟮c9;az-Latn⟯|⟮c10;azerbaijani, written in latin script⟯
⟮c11;ast⟯|⟮c12;asturian (no further info⟯)


tag|problem
⟮c15;it-IT⟯|⟮c16;unneccesary specification of IT (italian as spoken where else?⟯)
⟮c13;es-Latn⟯|⟮c14;Unneccesary Latn (As opposed to spanish written in kanji? :P⟯)



In HTML, the ⟮c50;language of the document⟯ should be indicated with ⟮c51;a lang attribute⟯ ⟮c52;on &lt;html&gt;⟯o 
In HTML, ⟮c49;anything that is not in the language indicated on &lt;html&gt;⟯ should be ⟮c53;indicated by an element with a lang attribute.⟯ 
In HTML, the ⟮c54;lang attribute⟯ takes ⟮c55;BCP 47 language tags⟯. 


### media

#### DOI

DOI = Digital Object Identifer
A DOI is a eternally persistant identifier of exactly one work.
DOIs are standartized by the ISO.
DOIs are mainly popular in academia.
https://doi.org/ is the DOI resolver.
DOI resolver + DOI resolves to an online representation/page of the resource
One can identify DOIs by prefixing the DOI resolver or the URN namespace `doi:`
doi-syntax ::= <registrant-identifer>/<object-identifier>

#### ISBN

ISBN   International Standard Book Number
There is one ISBN per version of a book, such that different editions, hardcovers/paperbacks, etc. each have unique ISBNs
ISBN-10 and ISBN-13 are the two types of ISBNs there are, with 10 and 13 characters each.
the original standard was ISBN-10, but since that was filling up, it was switched to an ISBN-13.
Serial publications don't get ISBNs, but instead ISSNs.

### licenses

Copyleft is type of restriction that does not allow creators of thing B including thing A to restrict the access to thing B more than thing A.
GPL is a type of copyleft license.
Share-alike is a type of copyleft license.

SPDX is a format for software licneses

spdx-license-expression ::= <spdx-simple-expression>|(<spdx-license-expression> <operator> <spdx-license-expression>)|\(<spdx-license-expression>\) # slightly simplified
spdx-simple-expression ::= (<license-name>-<license-version>)[+]
Each SPDX license has a short and a long name.
The + at the end of a SPDX license indicates this version or later.

### versions

semver = semantic versioning
semver is the most common way to specify version identifiers
semantic-versioning-version ::= <semantic-versioning-version-specifier> {<connective> <semantic-versioning-version-specifier>}
semantic-versioning-version-specifier ::= [<operator>]<major>.<minor>.<patch>
operator ::= ~ | ^ | <relational-operator>
connective ::= \|\| | && | - 

patch|backwards-compatible bugfixes
minor|new functionality in a backwards-incompatible manner
major|incompatible changes to existing API

~A.P.X|of the same A.P, but higher levels of the same patch are acceptable, i.e A.P.Y...
^A.P.X|any that do not modify leftmost nonzero digit


Using semver, for each of major, minor or patch you can instead specify a * to indicate that any are acceptable.

### date & time

#### Unix time

Unix time measures seconds passed since the unix epoch.
The unix epoch is the datetime at which unix time starts.
The unix epoch is 1970-01-01T00:00:00 UTC. 
Unix time is also called various other things including unix, posix, epoch, and time, none of them correct.

#### datetimes

Most common format is RFC 3339 / ISO 8601
RFC 3339 is almost the same as ISO 8601

#### time zones

The primary standard for time is UTC.
The primary standard for time used to be GMT.
UTC's standard specifies that time is divided into days, hours, minutes, and seconds, how much of each each contains, leap seconds, etc, and what time it is according to that system.
Ergo, UTC is a time system and the current time in that system, while UTC offsets are ways to define time in relation to UTC, but are not UTC themselves (!)
Timezones are defined in reference to UTC via UTC offsets.
UTC-offset ::= UTC(+|-)<time>
UTC may be specified using an UTC offset as UTC+0
Nevertheless, what people often are referring to when they say UTC is the system of UTC offsets
Today, GMT is an alias for UTC+0

### emoji shortcodes

The ⟮c1;common syntax for emoji⟯ is sometimes called '⟮c2;emoji shortcodes⟯'
⟮c3;emoji shortcodes⟯ are delimited by ⟮c4;colons⟯, and have names in ⟮c5;lowercase⟯ connected by ⟮c6;underscores⟯.
The ⟮c8;emoji shortcode⟯ for ⟮c7;💙⟯ might be ⟮c9;:blue_heart:⟯
The ⟮c10;emoji shorcodes⟯ don't have ⟮c11;a spec⟯, but you ⟮c12;can use them in many places⟯, including sites such as ⟮c13;Discord, GithHub, and Slack and a whole lot more⟯
In ⟮c14;some places⟯ (e.g. ⟮c14;discord⟯), you can ⟮c15;prefix⟯ ⟮c16;emoji shortcodes⟯ with ⟮c15;+⟯ to ⟮c17;add a reaction⟯.
I can ⟮c20;type emoji using emoji shortcodes⟯ but ⟮c18;using spaces instead of underscores⟯ anywhere using ⟮c19;espanso⟯. 

### dice notation

⟮c6;Dice notation⟯: `⟮c1;&lt;amount&gt;⟯⟮c2;d⟯⟮c3;&lt;sides&gt;⟯⟮c4;+⟯⟮c5;&lt;add-to-end-result&gt;⟯` 
In ⟮c8;dice notation⟯, you can leave out ⟮c9;the amount of dice to roll⟯, if ⟮c7;its one⟯. 
⟮c11;4d10+3⟯ is an example of ⟮c12;Dice notation⟯, it means ⟮c13;roll 4 10-sided dice and add 3 to the overall result⟯ 
the shell command ⟮c10;`roll`⟯ ⟮c14;rolls dice⟯, specified in ⟮c15;dice notation⟯ 

## databases

### geonames

Geonames is the worlds largest databae of geographical features, their locations, type, names, and names in alternative languages.
Geonames is updated via crowsourcing.
Geonames is licensed under CC BA.

# programming (mostly)

## Expressions

An expression evaluates to = returns a value.
e.g. `6`, `6 * 2`, `true ? "foo" : "bar"`

## Statements

Statements are the fundamental unit of programming in imperative programming languages (used in some restricted sense).
Ergo, imperative programming languages (in some restricted sense) are those that use statements as their fundamental unit, in this sense a program consits of n statements.
Statements do not return a value.
Since statements do not return a value, they either do nothing or cause side effects.
var test = 2 + 6; -> side effect of initializing a variable test
An expression statement is a statement that consists of a single expression.

### imperativeness

Imperative vs. declarative may be understood as a spectrum.
If imperative/declarative is understood as a spectrum, the more imperative something is, the more you're specifying the actual steps necessary for something to happen.
If imperative/declarative is understood as a spectrum, the more declarative something is, the more you're merely specifying what you want to happen, unconcerned about the steps.
On the imperative/declarative spectrum, functional languages are quite far on the declarative side.
Markup languages such as HTML are quite far on the declarative side of the imperative/declarative spectrum.

### statement separators and terminators

A statement separator is used to demarcate boundaries between two separate statements. A statement terminator is used to demarcate the end of an individual statement.
Semicolons are used in programming languages for two things: statement separators and statement terminators. When a language uses semicolons as statement separators, this allows you to write more than one statement on the same line.
Semicolons as statement terminators aren’t optional and are used to definitively mark the end of a statement.

Typically, even if programming languages have semicolons as statement terminators, they don't go after block statements. JS is the exception to this, where you can but don't have to do this.

semicolons as statement separators and statement terminators|C#|Java|Perl|Rust
semicolons as statement separators, newlines as statement terminators|Lua|Python|Ruby|sh
semicolons as statement separators and statement terminators, complex exceptions apply|JS

In languages which have newlines as statement terminators, typically the statement-terminating newlines can be escaped (generally by \ ) 
e.g. print("foo" + \
"bar")

### Blocks

In ⟮c3;most programming languages⟯, a ⟮c2;block⟯ is a ⟮c1;statement⟯.  
However, in ⟮c4;Rust⟯ (and in ruby to, though its weird, as blocks have the same syntax/are merely anon functions w/o arguments), ⟮c5;blocks⟯ are ⟮c6;expressions⟯. 

⟮c7;Blocks⟯ ⟮c8;contain/consist of⟯ ⟮c9;one or more⟯ ⟮c10;statements⟯. 
⟮c11;In/with⟯ ⟮c11;constructs⟯ or ⟮c11;languages⟯ that are ⟮c12;block-scoped⟯, ⟮c13;a block defines a scope⟯. 
⟮c14;Curly-brace/bracket languages⟯&nbsp;are defined as languages that ⟮c15;use curly-braces⟯ ⟮c16;to define blocks⟯. 
Many programming languages have been influenced by C, sometimes called C-family languages.
C was a curly-brace language, and so many C-family language are curly-brace languages.
(ba)sh is not generally a curly-brace language, but it still allows creating block statements via {} (but also via `()`)
bash calls its block statements command grouping.
bash block statements/command grouping is what is used by bash functions.
The difference between bash block statements using () and using {} is that () spawns a subshell and thus a new scope, while {} executes the commands in the current shell.
Examples of ⟮c17;curly-brace/bracket languages⟯ I can write are ⟮c18;C#⟯, ⟮c19;ECMAScript⟯ -&gt; {⟮c19;Javascript⟯, ⟮c19;TypeScript⟯}, ⟮c20;Java⟯, ⟮c21;Perl⟯, ⟮c22;Rust⟯, SCSS (but not Sass). 
Most ⟮c23;curly-brace/bracket languages⟯ ⟮c24;are thus because they are strongly influenced by⟯ ⟮c25;C⟯. 
In some programming languages (JS, Lua, ...?) blocks can stand alone, merely creating a scope. In other programming languages, blocks must follow a certain statement.
In lua, blocks end with `end` (outside of repeat...until). They are begun by `do` when standing alone, or when after a loop, by `then` after an if condition, and by nothing after a function signature
In bash, blocks for if are delimited by then ... (possible else etc.) fi, for for and while by do ... done, for case by in ... esac
In ruby, blocks end with `end`. begin begins a dedicated block statement (and is the keyword for the error handling statement), but no other blocks
In python, pretty much anything (control structure, function, etc) that precedes a block ends with `:`. In Ruby by contrast (which otherwise may look pretty similar), nothing ends with `:`
In some languages, notably Ruby and Rust, block expression return the value of the last statement

liquid|{% keyword %} ... {% endkeyword %}
python|Sass|indentation

### control structures

The default control flow is linear from top to bottom, this is called sequencing.
A thing that modifies control flow is a control structure. 

A control structure takes the normally linear flow of code and makes it somehow nonlinear.

Programming languages that use control structures outside of GOTO are structured programming languages.
Programming languages that do not use control structures or only use GOTO are non-structured programming languages, which are today quite rare.

Control structures are typically statements, however in Ruby and Rust, they are expressions.
In javascript or JS, most control structures take one statement after it, which can either be a normal statement or a block statement. A statement that does nothing is an empty statement
If control structures have conditions, they are delimited by...

()|C|JS|Java|C#|Perl
nothing|Python|Ruby|Rust|Lua
is complicated|shell

Conditions for control structures in ba(sh) are actually (a) command(s)
If the command(s) that make up the condition for a control structure return a zero exit code, they will be treated as true, and false otherwise.
Ergo, one can use the `test` command in the condition of a (ba)sh control structure, but one can also use any other command and rely on its exit status.
test is also available under the name `[` but requires a closing `]` in this case.
(ba)sh requires all operators and the [] themselves to be separated by spaces, since [ is actually just a symlink for test, and thus all of these are actually arguments for a command.

#### choice/selection control structures

choice/selection control structures allows choosing between several alternatives based one or more conditons.
choice/selection control structures constructs are also just called conditionals.
In conditionals, any of the possible paths is called a branch.

##### if

The most common conditional is if/then/else. 
  
the if/then/(else) conditional is typically a statement (in rust, it's an expression).
An if/then(else) conditional is started by `if` in nearly all programming languages
the else arm of an if/then(else) conditional is started by `else` in nearly all programming languages

else if|C#|Java|JS|SCSS/Sass
elseif|lua
elsif|liquid|perl|ruby
elif|Python|(ba)sh
  
Anki has a if-like conditional to show something only if a field has content, indicated like: 
```lang=text;
⟮c1;{​{⟯⟮c2;#FieldName⟯⟮c1;}​⟯}
	Lorem Ipsum
⟮c1;{​{⟯⟮c3;/FieldName⟯⟮c1;}​⟯}
```

##### conditional operator

The ternary operator is a conditional which is typically an expression. 
The ternary operator is more properly called conditional operator. 
The conditional operator typically has the syntax &lt;condition&gt; ? &lt;iftrue&gt; : &lt;iffalse&gt;. 
The conditional operator comes from C (more properly an early ancestor of C), thus most programming languages that are inspired by C have it. 
Example in JS:
`let attack = enemy.isFireType() ? this.attacks.thundershock : this.attacks.inferno;`
Languages that I can write that ⁑don't⁑ have a ternary/conditional operator with the typical syntax are Bash (more precisely, only exists for arithmetic expressions), Lua, Python, and Rust.

##### others

An if statement/expression, but reversed in its truth value, is an unless statement/expression.
unless statements/expressions use the keyword unless.
unless statements exist in liquid, perl, ruby


Some languages (Perl, Ruby), allow a one-line conditional, where the syntax is &lt;expression&gt; &lt;conditional&gt; (we might term this a postfix notation)
for the postfix conditionals in perl, ruby


in rust, `if let` instead of `if` allows for an if with pattern matching

##### switch

switch is a type of conditional.
the switch conditional is generally a statement.
the switch conditional generally has one condition, and then n branches for possible values.
Besides the branches for possible values of the conditional, the switch conditional generally also allows for a default case.
The default for switch statements is optional in JS
In many languages switch conditionals feature fallthrough, which is where it will continue even after the case ends, until it hits a break/return statement.
switch conditioals are generally started by the `case` keyword.
Different cases for a switch conditional are started by `switch` in Java, JS and by `when` in liquid, ruby.
In liquid, ruby, multiple cases are separated by commas.
The default case for a switch conditional is `default`  in Java, JS, and `else` in liquid, ruby.
Bash has a fucked-up syntax: case &lt;expression&gt; in {&lt;case&gt;) &lt;command&gt; ;;} esac
In C-family languages, switch cases are generally syntactically equivalent to labels, and thus don't themselves create a new scope by default.

JS Syntax examples:

```
switch (expression) {
  ⟮c1;case⟯ ⟮c2;⟯value1⟮c2;⟯⟮c3;:⟯
   //Statements;
   ⟮c4;default:⟯
}
```

##### guards

guardss are additional boolean expressions specified on branches of conditionals that must also evaluate to true if the program is to continue.
Of the languages I know, Rust has guards, introduced by `if`.

#### Iteration/Loop control structure 

Control flow that repeats the code a number of times is called iteration/looping


##### Count-controlled loops

Count-controlled loops are loops that repeat a piece of code a certain number of times.
Count-controlled loops are often started with the keyword for.
Count-controlled loops are often called for-loops.
The typical syntax for count-controlled loops inheriting from C (e.g. C#, Java, JS, Perl) is 
for <delimiter>[<counter-initialization>];[<counter-end-condition>];[<counter-change-per-loop>]<delimiter><block>
for (;;) ends up just being an infinite loop
SCSS/Sass instead has the syntax @for <variable> from <lowerbound> to (excl)/through (incl) <upperbound>


##### Condition-controlled loops


A condition-controlled loop is aloop that repeats until a condition changes.
condition-controlled loops can begin or end with their condtion, in which case they will run at least 0 or at least 1 time.
condition-controlled loops that test at the beginning of the loop are often started with the keyword `while` and are often called while-loops. 
condition-controlled loops that test at the end of the loop are often started with the keyword do, then a block, then end with the keyword while followed by the condition and are often called do-while-loops.
Most programming languages I know have while and do-while loops, in fact I don't think I know a programming language that doesn't have a while loop.
Perl and bash have an until loop: a while loop with an inverted condition (analogous to unless).
Lua also has a while loop with an inverted condition that tests at the end of the loop with the syntax repeat ... until
in rust, `while let` instead of `while` allows for a while with pattern matching


##### Collection-controlled loops 


A collection-controlled loop is a loop that loops over all elements of a thing.
Collection-controlled loops are commonly called foreach loops.
  Collection-controlled loops most commonly start with the keyword `for`, but then feature a different syntax than count-controlled loops. In perl, they instead start `foreach`.
  Collection-controlled loops generally work on iterators, or by transforming the thing into an iterator implicitly.
  Lua: for &lt;expression&gt; do
  bash, Liquid, Python, Ruby, Rust: for <expression> in <iterable> ...
  Java: for (<type> <element> : <iterable>) ...
  JS: for (<variable> in <object>) ... (only used to iterate over all key-value pairs of an assoc array)
  In a JS forin loop, the thing assigned to the variable is the key, not the value.
  for (<variable> of <iterable>) ...
  SCSS: @each <variable> in  <iterable>
Some languages have collection-controlled loops that are called as methods on a collection or iterable (these are higher-order fucntions)
iterable/enumerable.each(block)|Ruby
somearr.forEach(anonFunc)|JS

When iterating through something that returns multiple values, the expression may need to destructure the values out, or may just list n variables with commas, depending on the language

bash for in is actually the only loop using for that it has. It's also weird in that what it loops through is an $IFS separated list

Infinite loop

loop|Ruby|Rust

takes a block in ruby




Many languages provide a statement which allows skipping the current (continuing with the next) iteration of a loop.
Most languages use the continue statement to continue with the next loop, Perl and Ruby use the next statement.
Many languages provide a statement which allows ending/exiting the loop.
Most languages use the break statement to end/exit the loop, Perl uses the last statement.
In Rust, you can pass an argument to the break thing (break <something>) to have that be the return value of the block expression


Sometimes, loops have an else clause. In python, this runs at the end if we never break out of the loop. In liquid, this runs if the loop is empty

(loops with reversed condition do not count as separate kinds of loops)
lang|count-cont|cond-cont|col-cont|infinite
lua|1|2|1|0
liquid|0|0|1|0
Python|0|1|1|0
JS|1|1|2|0
SCSS|1|1|1|0
Rust|0|1|1|1

### Labels

A label in a programming language is a sequence of characters that identifies a location within source code. In most languages labels take the form of an identifier, often followed by a punctuation character (e.g., a colon). 
JS and C have labels.
JS label syntax: <name>:
Labels can be used to break out of a loop that is not the enclosing one.

### other statements

Empty statements are useful if a statement is required syntactically, but there is nothing to do, e.g. when writing outlines

;|JS|C#
pass|Python
:|(ba)sh

: is actually more complicated. It is kinda similar to true, and is therefore used as a condition for an infinite while loop.

## Polymorphism

something is monomorphic if it works for one type
something is polymorphic if it works for several different types
monomorphization is a compile-time process in which polymorphic code is transformed into n monomorphic variants

ad-hoc polymorphism is polymorphism where different implementations are selected based on the type of the argument(s)
-> callable unit overloading, operator overloading

### dispatch

dispatch is choosing which method should be invoked in response to a method call.
displatch is based on the type of the thing
dispatch is only relevant if there are multiple implementations of a thing.

#### static dispatch

static dispatch is choosing an implementation of a polymorphic operation at compile time
callable unit overloading and operator overloading are forms of static dispatch, since the implementation is chosen based on the declared type of the parameters

##### Overloading

###### callable unit

Overloading of callable units is creating multiple callable units with different callable unit signatures.
Languages I know that support overloading are C#, Java, TS.
When overloading, each signature generally has its own implementation, exept in TS.
In TS, function '⟮c1;overloading⟯' exists, but you specify ⟮c2;all possible signatures⟯ ⟮c3;first⟯, and then the ⟮c4;implementation⟯ with a ⟮c5;signature⟯ that is ⟮c6;compatible with all the specified signature⟯ (e.g. using ⟮c7;optional parameters⟯), and not compatible with ⟮c8;non-specified signatures⟯
For TS ⟮c+;overloaded⟯ functions, ⟮c+;all but the last⟯ signature(s), which ⟮c+;do(es)n't have any body⟯, is/are called ⟮c+;overload signatures⟯
For TS ⟮c+;overloaded⟯ functions, ⟮c+;the last⟯ signature(s), which ⟮c+;has the body and thus the implementation⟯, is/are called ⟮c+;the implementation signature⟯
In TS, in general: prefer ⟮c1;union types⟯ over ⟮c2;overloads⟯
In TS, things that can be overloaded anything that is callable: functions, callable objects, methods (whether in object types, interfaces or classes), constructors/newables.

Operator overloading is where different operators have different implementations based on their operands.

#### dynamic dispatch

dynamic dispatch is choosing an implementation of a polymorphic operation at runtime.
dynamic dispatch is accomplished by means of virtual methods/functions.
both single dispatch and multiple dispatch are forms of dynamic dispatch.

##### single & multiple dispatch

single dispatch is where only the type of one parameter (the reciever of the message = the thing it was called on, mostly) is used to choose the implementation

multiple dispatch is where the type of multiple parameters (the reciever of the message = the thing it was called on as well as the method parameters) is used to choose the implementation
Overloading would be multiple dispatch if it was performed at runtime, but it isn't, so it isn't.

##### virtual method table

VMT = virtual method table
virtual method table is also called (virtual) function/call/dispatch table
virtual method/function/call table is sometimes abbreviated vftable or vtable.
A vtable contains all relevant virtual functions.

##### rust

In rust, `dyn <trait-bound>` is the type of a trait object.
A trait object is an opaque type of another type that implements a set of traits.
A trait object uses dynamic dispatch to select the implementation at runtime (in contrast to rusts' parametric polymorphism, which ofc uses static dispatch)
A trait object is a dynamically sized type, and thus we need a pointer to it such as & or Box<>.
For something to be object safe, the return type may not be `Self` and there may not be any generic type parameters.
A trait object must be object safe.
The reason a trait object may not have any gemeric type parameters is that these will already be monomorphosized away by compile-time.
The reason a method of a trait used in a trait object may not return `Self` is that we don't known `Self` at compile-time, thus we can't reason about its size and can't guarantee safety.
In rust, we can specify that we want dynamic dispatch where we chose an implementation of a trait at runtime by having a pointer (e.g. Box) to `dyn <trait-list>`

### parametric polymorphism

Parametric polymorphism is polymorphism that only uses one implementation, instead taking a generic (that is perhaps subject to some contraints) and performing one's operatons based on that.
A generic is a stand-in for a type that is not yet specified or unknown. 

#### type parameters & generics

A type parameter is a specifier of one or more types that a thing (callable unit, object, ...) is defined over.
Type parameters go in angle brackets.
Type parameters are generally written in UpperCamelCase
Within type parameters, multiple type specifiers are separated by `, `.
Generics are specified within type parameters.
Names of generics are typically single characters.
A generic of any type is typically indicated T

##### binding generics

Once the name of a generic is bound, any reference to that name refers to that generic.
Two generics of different names are independent, even if they may be filled by the same concrete type at runtime.
It may sometimes seem like a generic is being bound twice when it's actually being used the second time.
E.g. impl<T> SomeStruct<T> is saying that you're implementing SomeStruct such that SomeStruct's generic <T> (second mention) satisfies being any type <T> (first mention), which is of course not particularly informative, and would be equivalent to impl SomeStruct<T>, if that were possible.
Binding <T> via the `impl` already allows one to do more interesting things.
e.g. `impl<T: Copy> SomeStruct<T, T>` for a `SomeStruct<T, U>` is saying that you're implementing this for all SomeStructs whose type parameters are of the same type which implements copy.

#### constrainment

Many languages have a way to specify contraints a generic should satisfy.
Rust specifies a set of traits as constraints for generics, these are called »trait bounds«.
Trait bounds are a set of traits that a generic must satisfy.
In rust, we may specify trait bounds by indicating it within a type parameter as \<<generic>: <trait-bound>\>, with a 'where clause', or by not using generics at all and instead writing the type as `impl <trait-list>`
trait-bound ::= <trait-name>{ + <trait-name>}
where-clause-syntax ::= where {<generic>: <trait-list><newline>}
TS allows specifying constraints for generics via the `extends` keyword.
The TS `extends` keyword in type parameter contexts takes a type specifier to specify the constraints of the generic.

#### implementation & monomorphization

Javas ArrayList, C# List and Rusts vec are dynamic arrays defined over a generic, and are thus parametrically polymorphic.
C# List and rusts vec are monomorphosized for each type usedas a generic; Javas ArrayList instead only generates a single implementation for ArrayList<Object> - therefore in Java all values in an ArrayList must be boxed.
In Rust, parametric polymorphism using generics is monomorphizised, so that Option<T> with e.g. i32 and f64 produces the relaizations Option_i32 and Option_f64.

Interfaces/traits often enable parametric polymorphism.

### subtyping

## Identifiers

In a wide sense, "name" is synonymous to identifier, in a narrow sense it is an identifier
An identifier is a thing that refers to/labels an object or class/set/collection of objects.
a unique identifier is an identifier that labels a thing uniquely in a given context.
UID   unique identifier
An identifier is opaque if it provides no information about the thing it identifies
A transparent identifier provides information about the thing it identifies.

Aliasing is referring to the same location in memory by multiple different identifiers.

UUIDs/GUIDs are formats for unique identifiers that make it very likely for them to be unique.
UUID|Universally Unique Identifier
GUID|Globally Unique Identifier
UUID=GUID
UUIDs/GUIDs are 128 bit long, which makes it very likely for them to be unique.

### name resolution

name resolution is the associating of identifiers with the correct things (e.g. variables)

#### Name binding

Name binding is the association of entities with identifiers.
For an identifier to reference something is to the identifier bound to that thing.
Binding is intimately connected with scoping, as scope determines which names bind to which objects.
static = early binding is name binding during compile-time
dynamic = late binding is name binding during runtime
dynamic/late binding enables duck typing
duck typing is calling a method without caring about its type, and seeing if it works.

#### namespaces

a namespace is a context in which names are unique.
Names within a namespace are sometimes called local names.
a namespace itself generally has a name.
Within a namespace, only the local name is needed to refer to a thing.
Outside of the namespace, the namespace and the local name are needed to refer to the thing.
In hierarchical namespaces, namespaces are nested.

### Scope

the scope of a name binding is the part of a program where the name binding is valid.
for something to have x-scope is to only have the name binding be valid within x.
a variable with foo-scope is often called an foo-variable

#### Lexical & dynamic

Static scope is another name for lexical scope.
Lexical scope is where scope is determined by where in the source code (a reference to) a name binding is.
Lexical/static scope is contrasted with dynamic scope
Dynamic scope is where scope is determined by where on the stack something is.
Pretty much all programming languages today use lexcial scope. Bash is the example, using dynamic scope.

#### global/local scope

The scope that is the entire program is global scope.
A variable that does not have global scope has local scope.

Local scope is often either block or function scope.

In some languages, things that live within global scope are properties of an object called a global object.
In JS in browsers, generally, the global object is Window.
within ⟮c2;workers⟯, the ⟮c3;global scope⟯ is `⟮c1;WorkerGlobalScope⟯`
within ⟮c2;service workers⟯, the ⟮c3;global scope⟯ is `⟮c1;ServiceWorkerGlobalScope⟯`
The mixin `⟮c1;WindowOrWorkerGlobalScope⟯` describes ⟮c3;the common features⟯ of `⟮c2;Window⟯` and `⟮c2;WorkerGlobalScope⟯`
The `self` property of a WorkerGlobalScope returns a reference to the WorkerGlobalScope itself.

Without ⟮c3;crates/unsafe code/etc.⟯, ⟮c2;globals⟯ in Rust can only be ⟮c1;constants⟯.

##### Variable scope

In general, if you declare block- or function-scoped variables on the top level, these will be global or at the least, global to the module.

Block-scoped variables
my|perl
local|lua
let|JS
ø|Ruby
ones defined within a block|C#|Java|Python

Function-scoped variables
var|JS

Global variables
ø|lua|perl
$|Ruby

Variable scope in python is not determined by keyword but by context.
In JS, variables declared without a keyword become properties of the global object

#### shell scope

In (ba)sh, the thing that determines scope is the shell.

running a script spawns a new subshell, unless you source it.
Sourcing a thing is done by `source` or by `.`
environment variables have a scope that allows access in current shells and subshells.
shell variables have a scope of the current shell only.
Variables are shell variables by default.
Exporting a variable turns it from a shell variable to a environment variables.

env|show all environment variables

export|export a variable
export -n|unexport a variable

#### Shadowing

Masking = shadowing
Name masking/shadowing is when a name in a inner scope overrides that same name in an outer scope
Variable masking/shadowing is name shadowing involving variables
In rust, shadowing allows for 'changing' tye type of the variable (really merely declaring a new variable)


#### Hoisting

Hoisting moves declarations but not initializations to the top of the scope.
Hoisting is mainly a JS concept.
in JS, var variables and function declarations (but not function expressions) and hoisted.

### Case

snake_case|variables, methods (, symbols)|ruby|python (use underscores sparingly)
UpperCamelCase|classes|C#|Javaruby
SCREAMING_SNAKE_CASE|constants|ruby
camelCase
snake_case|shell variables|(ba)sh
SCREAMING_SNAKE_CASE|environment variables|(ba)sh
_leading_underscore_snake_case|fake private variables|(ba)sh

most programming languages are case-sensitive as regards identifiers.

### Naming

While there is variety in what is allowed in a identifier name, most commonly it is [a-zA-Z0-9_]
JS also allow $ in a non-sigil way in identifier names.
JS identifiers may not start with a number, but with any other allowed character.
In general, identifiers may not be keywords.

## Values

A literal is a value which is written into the source code as-is and therefore is fixed.

### Memory-management

#### Ownership

In rust, eveary value has exactly one owner.
Owners are variables(/constants).
Moving happens when we assign a value to a different owner and thus the first owner is invalidated.
Assigning a value to a second owner produces a move unless the type implements Copy, in which case it instead calls copy.
Rust says values that are moved when reassigned (= which don't implement Copy) have move semantics, values that are copied (= which implement Copy) implement copy semantics.
A type can implement Copy if all of its components (parts) implement Copy.
In rust, all primitves implement Copy
Assigning as an operation that forces moving includes passing to a function and returning from a function.
When a owner goes out of scope, a value is dropped.

to allow cloning(), implement the Trait `Clone`. This does not change the semantics, since clone() must be called manually

## Variables

A variable is an identifier which is associated with a storage location which contains a value.

### Declaration and initialization

Declaring something is saying what an identifier means.
In most languages, but not in JS and Python, declaration at the very least fixes the kind of entity the identifier refers to. 
In statically typed languages, declaration generally fixes the data type of an identifier.
To initialize something is to assign a value for the first time.

declaring: var bla;
initializing: bla = 5;
declaring and initializing: var bla = 5;

Trying to read from something undeclared in general produces an error in most programming languages, in sh however it merely produces an empty string.
In JS, a declared but unitialized variable has the value undefined. In most other languages, reading from an unitialized variable produces an error.
In python there is no such thing as variable declaration (however, using a name you haven't used before still creates an error)
Redeclaration may or may not produce an error. In JS, it does not produce an error for var, but does for const and let.

### assignment

Setting a variable/constant to a value is known as assignment.
= is used as the assignment operator in most programming languages
sh is special in its assignment operator, since it does not allows spaces on either side
SCSS/Sass uses : as the assignment operator.
In most languages, assignment expressions evaluate to the value assigned.
Many languages have combinations of their math/string concat and assignment operators to combine these two operations (e.g. +=)

#### Destructuring

Destructuring is binding variables to values in a way that does not correspond to the 1 variable - 1 value pattern

In many languages, the comma can be used for multiple assignment, most commonly like so:
a, b = 1, 2|Python|Ruby
This is often a form of destructuring under the hood.

[var1, var2] = [value1, value2] or preexisting array|JS|Python|Rust
var1, var2 = [value1, value2] or preexisting array |Python|Ruby
(var1, var2) = (value1, value2) or preexisting tuple|Rust

In general, you can destructure that language's linear collections (esp. if primitive) and iterables.
In JS you can also destructure the assoc array structure.

Destructuring an array(like) requires array delimiters ([]) in JS, python doesn't want any delimiters, and python wants a tuple, which may mean no delimiters or () if needed for nesting etc.
use normal default value syntax to assign default values in array destructuring|JS only
combine spread syntax/splat operator w/ destructuring|JS|Ruby|Python
var1, *var2 = [1,2,3]
[var1, ...var2] = [1, 2, 3];
=> var2 = [2, 3]
Ignore a single value in destructuring
, (e.g. var1,,var2)|JS
_, (e.g. var1,_,var2)|Python|Ruby|Rust

Ignore multiple values in destructuring
*_, (e.g. var1,_*,var2 )|Python|ruby
.. (e.g. var1, .., var2)|Rust
Not possible|JS

nested destructuring
((target, _), _) = [["foo", "bar"], "baz"]|Python
[[target]] = [["foo", "bar"], "baz"] |JS
not possible|ruby

Destructuring can be a cheeky way to swap variables

When destructuring out of assoc arrays in js, this looks like

{nameofkey: nameofvariableyouwantthevaluetoendupin} = {nameofkey: value}
If the nameofkey and the nameovariableyouwantthevariabletoendupin are the same, you can do:
{nameofkey} = {nameofkey:value}

In rust, there is a set of destructuring/pattern matching constructs that can only be used in enums or if let statements.

putting an enum or struct with variable names inside in a match or on the left of an if-let will assign the variables to the values contained within.
e.g. `match { Some(foo) => ... }` will match Some() containing some value and assign that to foo
e.g. `match { Run{ distance: dist, direction: dir } => ... }` will match a `Run` and assign its distance field to dist and its direction field to dir.

pattern matching checks if a thing matches a pattern.
In rust, the destructuring syntax is part of the larger idea of pattern matching. (and the syntax that we use for destructuring is a subset of the syntax of patterns)
Many pattern matching things can be used for destructuring (and are the equivalents of the destructuring constructs of other languages).
Beyond or at the same time as destructuring, pattern matching is used for match and if let conditions. 
In rust, patterns can either be
refutable|pattern can fail to match|Some(x) (does not match if value is not Some)
irrefutable|pattern cannot fail to match

match is a conditional that uses pattern matching for its conditions, and forces checking to be exhaustive.
Rust of the languages that I know has a match conditional (using the keyword match). Of the languages I don't know, the ML family and functional languages have match conditionals.
in rusts's match, condition and expression are separated =>

pattern1 bar pattern2|pattern 1 or pattern 2

Within rust pattern matching/destructuring, we even can destructure a thing out of a reference: let &foo = somereference

### Sigils

In programming, a sigil is a symbol(s) affixed to a variable name.
Sigils are generally used to show that something is a variable, show its type, or ts scope.
In perl
\$|Scalars
@|Arrays
%|Associative Arrays (Perl calls them Hash)

In ruby
\$|global variables
@|instance variables
@@|class variables

In sh, $ is a sigil-like used for various kinds of expansion
In SCSS/Sass, any variable requires teh $ sigil
 

### Declaring multiple variables

a, b = 1, 2 (or e.g. returnTwoValues()) (lua, python)

### Constants (and not)

Mutability is whether something can be changed after inital creation. Something is mutable if it can be changed, and immutable if it can't.
Different things can have mutability: Objects, variables, (though generally not primitves).
Some languages make a difference in which keywords are used to declare constants and variables.
Constants are immutable, while variables are mutable.
In most languages, constants are written in all upper case.

Keyword for constants:
const|JS|Rust
final|Java

Keyword for variables:
let|Rust

In rust, even variables are immutable by default, and the keyword mut makes them mutable, the difference to consts being that consts cannot be declared mutable.
Rust requires its consts to always be type annotated.
In JS, consts are always block-scoped.
In some languages (JS), consts must be initialized in the same statement as they are declared.

The term magic number or magic constant refers to the anti-pattern of using numbers directly in source code. 
Instead of magic numbers (the antipattern), one should instead use constants.

### Default variables

In Perl there is a special variable $_. There are many places in programming language Perl where if you do not explicitly specify a variable, the variable will be used $_. There are key words that read the values from this variable, and there are those which set of values in this variable. (also sometimes exists as @_ and %_)

## (Data) types

An abstract data type is defined in terms of its behavior or more specifically its semantics, instead of in terms of its syntax.
If an abstract data type is a description of what something does, a data structure is how something does it.

A null pointer/reference/type/value indicates that we're not referring to a valid thing
Datatypes implemented in a programming language can either be scalar or compound/composite
Bash is fun in that it does not have data types at all, in truth all values are strings

To clamp a value is to specify an upper and a lower bound, and keep the number within those values.

### primitives and composites

Primitive may refer to a data type that is provided in a programming language as a basic building block.
Composite data types are built from primitive data types. 
Primitive may also refer to a type that has built-in language support.

##### primitive types in different languages

C#: int, float, bool, string, char, double
Java: byte, short, int, long, float, double, char, String, boolean
JS: Number, boolean, null, undefined, string, object, array
Rust: 
  scalar: integer, floating-point numbers, booleans, chars
  nonscalar: tuple, array
Python: integers, floats, complex numbers



### Type Systems

A (data) type consists of a set of values that something with that type can assume.
In implementation, each value of a type has a unique (within the type) binary representation.
Typing can also be understood as how to interpret a series of bits.
A datatype T1 whose set of values is a subset of a datatype T2 is a subtype of T2.
A datatype T1 whose set of values is a superset of a datatype T2 is a supertype of T2.
A language may also be untyped: neither variables nor values have type.
An example of an untyped language is bourne shell, which is completely untyped.
Bash supports a very mediocre type of typing via builtins such as declare.

#### Dynamic vs Static typing

Dynamic typigng: type checking at runtime ≈ values have type
Static typing: type checking at compile time ≈ variables have type

Dynamically typed languages I know: JavaScript, Lua, Python, Ruby
Statically typed languages I know: C#, Java, Perl (with regards to the scalar, array, hash distinction), Rust, TS
TS makes the normally dynamically typed JS statically typed

#### Type inference/manifest

Explicit/manifest typing is a feature of a type system where the type has to be explicitly declared.
Implicit/latent typing is a feature of a type system where the type is not explicitly declared.
Implicit/latent typing  <-> Explicit/manifest typing 
Type inference is a rough synonym for implict/latent typing, but is often used in contexts where the language is otherwise generally explicitly/manifestly typed.
Only statically typed languages can usefully be explicitly/manifestly typed
Type inference in C#: var 
in TS and Rust, often type inference is possible automatically 
Type inference in TS/Rust is more likely to work for anonymous functions
In languages with manifest typing, variable declarations require typea annotation.

On the negative side, manifestly and statically typed languages can be more effort to write. 
On the positive side, manifestly and statically typed languages 1) dramatically lower the chance of bugs, especially type errors (logic type), 2) provide better linting 3) provide better IDE code completion and similar.

(literal) type widening is the fact that TS will infer a primitive type and not a literal type for literal values.

Often, when rust can't infer the type, we need to use turbofish notation ( :​:&lt;type&gt;)

##### const assertions

In TS, const assertions are a special case of type assertions that influence type inference rather than specifying a specific type to cast to.
const-assertion ::= <type> as const;
Const assertions make TS infer the narrowest possible type. 
Specifically, const assertions make three things happen:
1. type widening.
2. object literals get readonly properties.
3. arrays become readonly tuples.

##### type narrowing

Type narrowing is a form of implicity type change where the type of a thing is made more precise based on which types could possibly exist in that context.
In TS, pretty much anything that could be reasonably assumed to narrow does.
Assigning to a variable with something of a more loose type undoes the narrowing performed that is narrower than that loose type.
Narrowing can produce the never type if the thing was narrowed to impossibility
A type guard is any check that narrows the type of a thing.
In TS, type guards for basic types uses typeof.
in TS, a type predicate is a function that returns a boolean value. The boolean value determines if the thing is the specified type.
A type predicate is specified by adding ` is <type>` to the end of the return type.
In effect, using a type predicate acts as a custom type guard.

##### Type annotation

Specifying the type of a thing (esp. a variable/constant) by writing the type into the code is known as type annotation.
Languages with manifest typing generally require type annotation for variable/constant declarations, parameters as well as return types.
In most (esp. C-family) languages, type annotation goes before the variable/constant.
In Python, Rust and TS, type annotation looks like so `: type`
Python supports type annotation since Python 3.5

###### Type aliasees

Type aliases are names for types thsat abbreviate longer type descriptions.
Where type aliases exist, they generally use the type keyword.
Type aliases exist in TS, Rust
`type <name> = <type-expression>`

###### Interesting keywords

#### Type errors

Type safety is the dgree to which a programming language prevents logic-type type errors in favor of static-semantic type errors.
A logic-type type error is caused by treating a value as the wrong type.
A type-safe language is a language that throws more static semantic type type errors instead of logic errors.

#### Conversion, coercion, casting and context (plus truthy/falsiness)

Context is a term usely used in programming, and with much variation.
We can think of context related to types as creating a situation in which things will be coerced to certain types automatically.
In python, bool() is said to create a boolean context = convert a value to true or false depending on their truthy/falsiness.
Something is falsy if it evaluates to false in a boolean context, and truthy if it evaluates to true in a boolean context.
Most langauges treat at least their null type(s) and their false type as falsy.
JS additionally treats empty strings, 0 and NaN as falsy.
Languages like JS or Python establish a boolean context (coerce to boolean) within their conditions for loops, conditionals, etc. Other languages (C#, Java, Rust) treat using non-booleans in these situations as an error, i.e. not create a boolean context.
In perl, context is most often used with the scalar/list distinction.
scalar() generates a scalar context
Since (ba)sh doesn't have any types but strings, it needs specific contexts to do certain tings
math context is required to do math
math context|$(()), (()) and the command let

###### Type annotation keywords

In general, certain types are generally indicated similarly across programming languages (though there is variation)
Integers|int|not Rust
Floating-point numbers|float|not Rust
Booleans|bool|C#, Rust
Booleans|boolean|Java
Characters|char|C#, Java, Rust
Double-precision floating-point numbers|double|C#, Java

##### Conversion

Type conversion is explicitly using a function or the like to change the datatype of something.
All pythons types, called as a function, convert to that type (e.g. list(), bool(), int())
Ruby has a set of methods that have the syntax foo.to_&lt;char&gt; that convert to that type (e.g. to_i, to_f, to_s, to_sym)

##### Coercion

Type coercion is implicitly forcing a value to be treated as of a different datatype.
JS will coerce extensively in the case of operations w/ mismatched types.
Concatenation of non-string w/ string|coerces non-string to string
use of booleans w/ math operators|coerce to 0/1
In contrast, pythons operators rarely coerce.

##### Casting

Type casting is asking the programming language implementation to treat a value as a certain datatype temporarily.
Casting will go wrong if the vlaue cannot be treated as teh casted type.

!!type value|YAML
(type) value|C#|Java

Type assertions in TS are the equivalent of type casting in other languages.
In TS, if ⟮c2;you know something about a type that TS doesn't⟯, you can use ⟮c1;type assertions⟯
TS type assertion syntax: prepending ⟮c2;&lt;some_type&gt;⟯ or appending ⟮c1;as some_type⟯


#### Firstclassness

An entity is said to be first-class in programming if you can ⟮c1;Do most other things you can do with objects/values⟯
typical features of entities that are first-class in a certain language are e.g. ⟮c1;Can be stored in variables/data structures, can be passed as a parameter to callable units, can be returned, tec.⟯
An entity that is first-class is called a first-class citizen.
Lua: all values

### bottom type

A bottom type is the subtype of every other type.
A variable with bottom type can take no value. (there is no value that can be assigned to a variable with the bottom type.)
A thing with bottom type can be assigned to anything at all.

A bottom type is used to indicate noncomputability.

no bottom type|most languages
! (called the never type)|Rust
never|TS

### unit type

A unit type is a type that only allows a single value.
A variable with unit type only ever takes things of the unit type or the bottom type.
A thing with unit type is only assignable to other things with unit type or the top type.

()|Rust

Rust's () for the unit type is abstracted from the idea of a tuple with no elements.
In Rust, things without a return value implicitly return ()
In rust, a struct without fields is also an unit type, called the unit-like strct.

in TS, there are three unit-like types: `null`, `undefined` and `void`
in TS, `null` is the only proper unit type: only things of type `null` plus `never` and `any` (of course) are assignable assignable to `null`, and `null` can only be assinged to `null` plus `unknown` and `any`.
in TS, `undefined` is only unit-like, since besides the proper relationships one may also assing things of type `undefined` to variables of type `void`.
in TS `void` is only unit-like, since besides the proper relationships things of type `undefined` are assignable to variables of type `void`.
in TS, if `strictNullChecks` is enabled (which is not the default behavior, but my default assumption otherwise the type system becomes a mess) `null`, `undefined` and `void` act like unit types, such that nullable types need to be literally declared as option types.
in TS, if `strictNullChecks` are disabled, all types are nullable.

#### Literal types

A literal type is unit type whose value is specified via the literal of another type (e.g. 4 or true or "ara ara")
in TS, the types of constants are a literal type of thier value.

### combination of other types

#### intersection types

An intersection type specifies a type which must satisfy all constraints that individual types satisfy.
While it would be technically possible to create intersection types of primitive types, it is pointless: There is no value that could possibly satisfy the constraints e.g. 'is a string' and 'is a number' at the same time, since they are disjoint.
intersection-type ::= <type> & <type>

#### Union type

A union type specifies a number of types that anything with the union type as type may take.
A union type can hold a value that could take on several different but fixed types.
A union type can be thought of as a type that has several "cases", each of which should be handled correctly when that type is manipulated.

with ⟮c1;union⟯ types, you can only use things that ⟮c2;all of the relevent types can do⟯, unless you ⟮c3;narrow them down⟯
Common syntax: type1 | type2 ...
Syntax for creating arbitrary union types exist in Python and TS

In type theory, a union type is a sum type.

##### Tagged unions

A tagged union type is a union type where each of the types has a tag, which is used to determine which type is currently in used.
What rust calls enums is more properly a tagged union.
in TS, a thing similar to tagged unions is called a discriminated union.
in TS, discriminated unions are implemented by a union type of other types with a shared field.
In a discriminated union, TS can narrow based on checking a shared field.

###### Rust

in rust, tagged unions implements the tag by means of the name of the enum.
in rust, tagged union variants may be tuples, structs, or unit-like

####### strum

strum|enum &lt;-&gt; string manipulation

to make enums ready for use with strum, one needs to derive the relevant trait onto it, and also use attributes on the enum or the variants.
Strum attributes use strum()

Enum -> str|derive strum_macros::ToString
Enum -> str message|derive strum::EnumMessage|Enum.get_message() & Enum.get_detailed_message() (return options)
str -> Enum|derive strum::EnumString|Enum::from_str()

###### Types with two possible states

####### Option type

An option type is a type that represents an optional value.
An option type can generally take on a state representing it is empty, or a state representing it is full, and wrapping around another value.
In rust, the option type is its alternative for null, which it does not have.
In rust, the option type is implemented as an enum.
In rust, the option type is 
pub enum Option<T> {
  None,
  Some(T),
}

In general, either option types or nullable types will be used to represent the absence of a value in a given language, but no both.

####### Result type 

A result type is a type which can be either of two variants/states, a success type holding the result, or an error type holding the error message.
in rust, the result type is `Result`, looking like enum Result<T, E> { Ok(T), Err(E)}

####### Commonalities

######## logic with methods

|if None|if Some
<OptionOrResult>.and(<AnotherOptionOrResult>)|None/Err|<AnotherOptionOrResult>
<OptionOrResult>.and_then(<callback>)|None/Err|<callback>(<OptionOrResult>)
<OptionOrResult>.or(<AnotherOptionOrResult>)|<AnotherOptionOrResult>|None/Err
<OptionOrResult>.or_else(<callback>)|<callback>|None/Err
<OptionOrResult>.map(<callback>)|None|call callback with contained value and return option with returned value
<OptionOrResult>.map_or(<default>, <callback>)|<default>|call callback with contained value and return option with returned value

######## cloning and copying

the cloned/copied methods of Options/Results takes an Option<&T> or <&mut T> or a Result<&T, E> or <&mut T, E> and returns an Option<T> or Result<T, E> by cloning/copying

######## conversion

Result<T, E>.ok() -> Option<T>

######## ? operator

In rust, the ? operator takes a `Result` or `Option`
In rust, the ? makes a `Result` evaluate to the value inside the `Ok` if `Ok` or exit out of the nearest function, returning an `Err`.
In rust, the ? makes a `Option` evaluate to the value inside the `Some` if `Some` or exit out of the nearest function, returning a `None`.
The ? is implemented via the trait std::ops::Try

######## unwrap & expect

unwrap and expect can be called on options and results.
unwrap and expect are similar that they return the value if the type is Ok/Some, and panic otherwise.
the difference between unwrap and expect is that expect allows us to choose our error message.

##### Nullable types

Null is not typically its own type (since it would be a useless unit type), instead other types are generally nullable.
A type being nullable means it can take a special value null/nil/undefined instead of the usual possible values.
We can understand nullable types as an union type between usual type | null type

nil|lua|liquid|ruby
null|C#|Java|JS (secondary)
undefined|JS (primary)
None|Python
there isn't one|Rust

Liquid has a special null-like type that is returned when accessing a deleted object called EmptyDrop
In JS a type is nullish if it is null or undefined.


#### type manipulation

in most languages, types are limited in how they can be used:
contain predefined primitive types|all statically typed languages
new data structures create corresponding types|all statically typed languages (I know)
new records create new corresponding types|all statically typed languages (I know)
can create type aliases|Python, Rust, TS
can create types that are combinations of other types|TS
can create new types by reasoning about other types|TS

type manipulation is a not-so-common cover term for creating new types by reasoning about other types

the `keyof` operator takes an object type and returns a union type of its keys.
the TS-specific `typeof` operator returns the type of a non-type thing.
the TS type `ReturnType<T>` corresponnds to the return type of T (T must be a function ＊type＊)
An indexed access type, given a key of a field, allows us to get the type of the value of a field of another type, much as indexing an assoc array with a key returns its value.
Indexed access types use the same [] syntax as normal accessing.
Conditional types evaluate to different types depending on an expression.
conditonal-type-specifier ::= <generic> extends <type> ? <type> : <type>;
the generic which is the first thing conditional type can be used in the true branch for further manipulation/selection.
in the <generic> extends <type> of a conditional type, within the <type> one may declare an additional generic via `infer <generic>`, which we than can use in the true branch
A mapped type maps all keys of another type to a certain type.
mapped-type-specifier ::= \[<type> in keyof <type>\]: <type>;
more on mapped types: https://www.typescriptlang.org/docs/handbook/2/mapped-types.html
Template literal types use JS template literal syntax to expand to all possible string literal types that this could assume.

mapped types

#### TS Utility types

TypeScript provides several utility types to facilitate common type transformations.

### top type

A top type is the supertype of every other type.
A variable with top type can take any possible value. (any possible thing can be assigned to a variable with top type)
A thing with top type can only be assigned to another variable with top type (in languages that have static typing).

A top type is often also the type that is at the top of the class hierarchy, in languages where such a thing exists

object|Python
unknown|TS
UNIVERSAL|Perl
java.lang.Object|Java
System.Object|C#
BasicObject|Ruby

In ruby Object inherits from BasicObject and generally acts as the top type for most purposes.

In TS, `any` is like a top type in that any value can be assigned to variables of type `any`.
in TS, `any` is like a bottom type in that things of type `any` can be assigned to anything.
Most languages with dynamic typing act as if everything had type `any`.
in TS, unless `noImplicitAny` is enabled, TS will often fall back to `any`, acting like default JS in these cases.
in TS, `{}`, `Object` are the same type.
in TS, `{}`/`Object` are nearly top types, you can assign everything but `null`, `undefined`, or of course `unknown` to `{}`/`Object`.
by contrast, `object` (notice the case) is any non-primitive type, and thus not even nearly a top type.

### object types, interfaces and classes in TS

object type = objects literals as types, generally declared with the type keyword if not inline.
in TS, object types, interfaces and to a certain extent classes share a lot of syntactic similarities.
object types, interfaces (and to a certain extent classes) both fundamentally a similar syntax to js objects.

type|keyword
object type|type
interface|interface
class|class

basic field|<fieldname>: <value>,|object type, interface, class
optional field|<fieldname>?: <value>,|object type, interface, class
methods|<fieldname>: (<ts-param-list>) => <return-type>, (syntax 1/2)|object type, inteface
methods|<fieldname>(<ts-param-list>): <return-type>, (syntax 2/2)|object type, inteface
make thing itself callable (i.e. a function)|(<ts-param-list>): <return-type>,|object type, interface
make thing itsef newable|new(<ts-param-list>): <return-type>,|object type, interface

TS object types, interfaces and classes can all be defined over n generics.
prefixing a field of a object type or interface with `readonly` makes it a constant field.
in TS, object types, interfaces and classes all can have getters & setters.

in TS, multiple interfaces with the same name will be merged into one, multiple object types or classees with the same name will throw an error
in TS, while interfaces can do many more things, interfaces can be implemented by classes just as in languages such as Java.
in TS, interfaces can be `extend`ed with other interfaces.
(TS) The main difference of using interfaces and extends vs intersections is that interfaces w/ extends will overwrite if there are properties with the same names but different signatures, while intersections will merge them.

(TS) An index signature specifies that for all keys of a specific type (in theory, but in fact I think they can only be string or int in ts anyway), the value will be of the specified type
Syntax of an index signature: [foo: sometype]: sometype2
The ⟮c+;name⟯ of an index signature ⟮c+;does not matter⟯.
^source: https://basarat.gitbook.io/typescript/type-system/index-signatures

Partial<T>|Returns T where all keys have been set to optional
Required<T>|Returns T where all keys have been set to required.
Readonly<T>|Retunrs T where all keys have been set to readonly

### boolean

A boolean data type is a type that has one of two possible values, indicating
truth values.

true/false|C#|Java|JavaScript|Lua|Ruby|Rust|TOML|YAML
True/False|Python|(YAML)
yes/no|YAML
no boolean type, only truthy/falsiness|Python

YAML is not boolean keyword case sensitive

### Symbols

Symbols as a datatype are guaranteed to be unique, and generally have a human-readable representation.
The fact that symbols are guaranteed to be uniqe mean that they are equal only to themselves.
In some languages, two symbol literals with the same name are equal to each other, for example in Ruby (:foo == :foo # true)
In some languages, two symbol literals with the same name are not equal to each other, for example in JS (Symbol("foo") === Symbol("foo") // false). Even in those languages, the same instance of a symbol is always equal to itself
Often, the main use of symbols is as object keys to avoid key collisons, or to act as alternatives to enums
Internally, symbols are often represented by a number.

:name|Ruby
Symbol("name")|JS

### references

A reference is a value that allows indirect access to another value.
A pointer is a type of reference that allows indirect access to a thing by storing its memory address.
Handle is an ambiguous concept, but is most commonly seem as a synonym to reference.
dangling reference/pointer = wild reference/pointer
A dangling/wild reference/pointer is a reference that doesn't reference/point to something valid
Link rot is the process of links becoming dangling/wild references.
Multiple indirection is having references to references (and so on).

A smart pointer is a pointer with some other features (e.g. automatic memory management or bounds checking).
A fat pointer is a pointer that stores some extra data besides the address.

What Rust and C++ call references are probably more like pointers.
In Rust and C++ the & operator takes a reference of something.
In Rust, any references of a type have the type &<type>, while in C++ they have the type <type>&.
In Rust, to take a reference, one must prefix the thing one is taking a reference of with &, while in C++ reference-taking is implied if one assigns to a reference-type variable.
In Rust, a reference to an element in a data structure counts as a reference to the whole data structure for the purposes of borrow semantics.
In Rust, references are immutable by default, and must explicitly be declared mutable with &mut.
In Rust, the act of taking a reference is known as borrowing, since implements specific semantics/rules.
In Rust, correct use of borrow semantics are checked at compile time by the borrow checker.
Borrow rules:
1) borrows cannot last for a larger scope than the owner
2) you may only have n references to a resource or exactly one mutable reference to a resource, but not both at the same time.
Only having either n references or exactly mutable reference to a resource implies that you cannot assign to a variable borrowed elsewhere, since assigning requires an implicit mutable borrow (!).
x = 22 is equivalent to *(&mut x) = 22
Dereferencing takes a thing that is a reference and returns the referenced thing, allowing you access to the value behind the reference.
you can also dereference on the left-hand side of an assignment to assign to the referenced piece of memory.
In most C-family languages (of the ones I can write, C# and Rust) to dereference you use the dereference operator *.
In Rust, the Trait that controls the behavior of the dereference operator is Deref, which has a method deref implementing dereferencing.

In Rust, a slice is a view into a block of memory by means of a pointer that also stores a length.
In Rust, any linear collection type can be sliced.
In Rust, slices are considered a reference and have the same semantics as references do.
Rust slices can bu used for the same reasons one would use slices in e.g. Python (though without the ability to step or reverse), but they are not copies, but fundamentally just views.
getting a slice: &[mut] <thing-being-sliced>\[<n>(..|..=)<m>\]
slices can be indexed just like anything else.
Slices' length may not be known at compile time, and so rust can't guarantee that indexing into a slice will not produce an error.

when cloning a reference &T, rust will return T.
to_owned() is part of the Trait ToOwned.
there is a blanket implementation for ToOwned for anything that implements Clone.
the reason to use to_owned() is for types where returning T of &T is not desirable, namely &str, hence to_owned() returns a String for str.

In rust, string literals are slices, specifically they are slices into the rodata section of the object file.
this means that instead of being &str, string literals are in fact &'static str
In rust, `String` and `str` are both UTF-8 byte sequences.
Since `String`/`str` are UTF-8 byte sequences, they cannot be indexed, as they could be indexed on a non character boundary (does allow slicing however, slices always have this problem potentially).
To get an iterator of the UTF-8 bytes of a String, use bytes().
In rust `String` represents string data allocated on the heap, while `str` represents string data somewhere in memory.
since rust's `String` is stored on the heap, it can be grown and shrunk.
Since we don't know where the string data of `str` will be and what size it can or cannot have, `str` itself cannot be owned, but instead can only be referred to as a reference.
A 'reference' &str is actually a slice, not just a mere reference. I presume that's because we need the feature of slices indicating the length, sice we need some way to know where the str stops (since `str`s can have any length, in contrast to other things like an array which we don't need to slice to reference it since we know where it ends at compile time)
Rusts treats references to strings &String and &str as the same in most cases, since there is not much difference between a reference to a string stored on the heap whose length we know, and a slice to a string stored somewhere whose length we know by virtue of it being a slice.
string.as_str returns a string slice &str of a string.
String slices &str and &String are type-compatible with &'static str, but of course work differently: they can't last longer than the original value.

String.from() gets a String from an &str.
String.new() creates a new empty string.
the + operator for strings requres a `String` on the left and a `&str` on the right

### Numeric types

Languages generally have at least a type for Integers and a type for numbers with fractional parts, most commonly floats. JS combines these into a single type Number.
C#, Java, Perl, Python, Ruby, Rust, TOML allow inserting underscores in numeric literals for readability.
In some languages, multiples subsequent underscores within a numeric literals, or underscores at the beginning or end of literals are not allowed]
Some languages have specific keywords for Infinity (JS, Ruby) or NaN (JS). More commonly, values such as these exist as constants on the Number/relevant numberic type class/object/whatever.
In some languages (JS, Ruby), you can recieve values such as Infinity or NaN via certain operations, e.g. dividing by zero. Other languages will throw errors in this case.
In JS, you can generate NaN by trying to do math with a non-number and non-boolean (unless using +, which will concatenate), multiplying Infinity * 0 or * Infinity, using unary plus on a non-number and non-boolean.
In JS, you can generate Infinity by dividing by zero
checking for NaN
Number.isNaN(num)|JS (true only for NaN)
checking for finity
Number.isFinite(num)|JS (false for all non-numbers and NaN/Infinity)
In CSS, the general numeric type is <number>, which supports decimal numbers also. <integer> is a speialization for integers.
In CSS, percentages are a special type, <percentage>. 
In CSS, <percentage> consists of a <number> followed by a %

#### Overflow

If a numeric type has arbitrary precision, it can store (nearly) infinitely large numbers (it will in practice be limited by the memory the application can get from the OS)
overflow/underflow occurs when a numeric value is to large/small for its container.
Numeric types either have arbitrary precsion, are subject to overflow/underflow, or need to throw an error if a calculation exeeds the size limit of a numeric type.
Rust throws an error in overflow/underflow scenarios when debugging, and wrap otherwise.

#### size (not arbitrary precision)

In rust:
Numeric types: &lt;type&gt;&lt;size&gt;
signed integer|i|i16, i128, isize,...
unsigned integer|u|u32, u64, usize,...
floating-point|f|f32, f64
size as part of the type annotation (usize, isize) indicates the system word size 

⟮c2;ES2020⟯ introduces the ⟮c1;BigInt⟯ datatype for numbers ⟮c3;larger than the previous maximum size⟯
BigInt literal is indicated by ends in n

#### Integers

Integer literals generally not overtly marked

#### float and double

In Java and C#, to indicate a float literal you must add f as a suffix. any number containing a decimal point not explicitly indicated as a float will be a double
Most other languages don't distinguish between floats and doubles on a keyword level, merely by size (rust) or automatically
TODO: Check the above sentence and add more understanding on the difference between a float and a double-precision float on a conceptual level as distinct from how programming languages call them.

#### methods

Object/Struct/whatever for standard math operations
Math|JS
math|Python

get a random number
&lt;mathobj&gt;.random()|JS

floor/ceiling function
&lt;mathobj&gt;.floor()/.ceil()|Python|JS
&lt;thingItself&gt;.floor()/.ceil()|Ruby

Is a thing an integer?
Number.isInteger(foo)|JS

Truncate decimal places (not rounding)
&lt;mathobj&gt;.trunc(num)|JS

Round to fixed amount of decimal places
somenumber.toFixed(num)|JS

Round a number
&lt;mathobj&gt;.round()|JS|Python

Get absolute value of something
&lt;mathobj&gt;.abs()|JS
abs()|Python (y, it's not on the math obj)

Square root
&lt;mathobj&gt;.sqrt()|JS|Python

Is the thing an Integer?
Number.isInteger(foo)|JS

### enums

Enum is short for enumeration or enumerated datatype.
An enum is a datatype that can take on one of a finite set of values.
In stats terms, an enum is a categorical variable.
We may want to consider the boolean type an enum of {true, false}
Of the languages I know, C#, Java and TS allow creation of enums via the enum keyword.
Rust also uses the enum keyword, but for things more like tagged unions.
Python allows using enums via an external module
C#, Java enum syntax: enum &lt;name> {
  &lt;variant>,
  &lt;variant2>,
  ...
}
In C# the syntax &lt;variant> = &lt;value> exists to apply values to enum variants
We may want to consider enums a special case of tagged unions, where enums can only stand for simple values.


### Collections

Collections are an abstract data type that hold a number of data items.
Python calls its data structures that represent collection ADTs, well, collections.
Associative collections map keys to values. 
Js sets and maps use .size instead of .length
Java has the Collections Framework for collections 
Collections may be implemented in the language as primitives, but many are either transparently records or some syntactic sugar made up of literals over records; in some language everything is an object anyway and thus this distinction doesn't apply.

Rust only calls its non-primitive collections collections, which are stored in std::collections.
Rust collections (as in non-primitve collections) are stored on the heap and are variable size, primitive data structures are stored on the stack and are fixed-size.

#### Access

Random access might be clearer if it was called direct access.
Random access allows access to arbitrary elements at will.
Sequential access only allows access in a certain sort of order.

flex-container:<img src="sm_rand_seq_acc.svg">
book|random access (to pages)
scroll|sequential access

#### Collection methods

Clear a mutable collection
foo.clear()|not JS|Python|Ruby

Flatten a nested thing ([[1]].flat() => [1])
foo.flat(depth)|JS
foo.flatten(dept)|Ruby
nothing in py

#### Non-linear collections

Python: dictionary, set (and frozenset)

##### Sets

ADT similar to sets in math = unique members, don't have order.
Python data structure: set (mutable), indicated by {}, frozenset (immutable).
JS: class Set, create via new Set(), add(), has()

###### Set operations

Many languages/libraries have generalized set operations to something you can do to most/all collection types.
Python has set methods, but only allows them on sets.
JS has a Set class, which does not support set method

xor/union/intersection/difference(things...)|lodash/underscore(JS)

##### Associative collections

###### Associative array

####### General

An associative array is an abstract datatype composed of a collection of (key, value) pairs so that each possible key appears only once (as a key) = keys are unique.
Different programming language's implementations limit keys to only strings, strings or integers, all values, or something inbetween.
In programming languages, string assoc arr keys are generally quoted. In TOML they may be unquoted for simple alphabetic keys.
across programing languages, a mapping is generally a a key-value set.
Associative arrays are implemented as primitives in some languages, as records in others, or sometimes as both.
Languages with no associative array primitives: C#, Java, Rust
If languages implement assoc arr via records, you then interact with them as you would with records.
If languages implement assoc arr as primitives, these then often have their own syntax for interaction.

####### JS

JS implements associative arrays via the `Map` and `WeakMap` classes. 
In JS objects (esp. object literals) also perform many of the operations we would expect of associative arrays. 
Specifically, Maps maintain insertion order, and support any key type, while Object coerces any key to a string (except Symbols). 
Objects are primitives, Maps need to be created with the new Map() constructor. 

####### Literals

no literals|C#|TOML
{}|JS (objects)|Lua|Perl (1 of 2)|Python|Ruby|YAML
()|Perl (1 of 2)|SCSS/Sass (same as arrays)
newlines & indentation|YAML

In associative array literals, the separator between 2 mappings is generally ,

key-value separator
=|lua|TOML
:|python|Ruby (symbols)|YAML
=>|Perl (1 of 2)|Ruby (non-symbols)
, (yes, really)|Perl (1 of 2)

names (only if literals)
table|lua|TOML
hash|perl
dictionary|python
hash table|Ruby
map|SCSS/Sass

In most languages with primitive associative arrays, accessing and assigning are handled by the usual indexing syntax also used for their primitive array type etc.

####### Objects

Dictionary<K, V>|C#
HashMap<K, V>|Rust
BTreeMap<K, V>|Rust
Map<K, V> interface, e.g. HashMap<K, V>|Java

######## assigning & Accessing

adding a key, value pair
.Add(<key>, <value>)|C#
.set(<key>, <value>)|JS (map only)
.put(<key>, <value>)|Java
.insert(<key>, <value>)|Rust

Retrieval function
get(<key>)|Java|JS(map only)|Rust
[] indexing notation despite not being a primitive|C#

####### Insertion order

There are both languages that do and do not guarantee insertion order to be maintained for their associative arrays.
In Rust, you need to use the `indexmap` crate to get an associative array that keeps insertion order.

####### methods


deleting key
set it to null type|lua

Has key? 
key?|Ruby

Has value?
value?|Ruby

get array/iterator of key, value tuple/array/whatever:
pairs()|lua
items()|Python
entries()|JS (map only)

get array/iterator of keys
keys()|JS(only Map)|perl|Ruby|Rust|Python (returns a dict_keys object)
Object.keys(someobj)|JS

get array/iterator of values

values()|JS(only Map)|perl|Ruby|Rust|Python (returns a dict_values object)
Object.values(someObj)|JS

Amusingly, JS doesn't have the keys(), values(), entries()... functions for its assoc array type (objects), but does have them for arrays

merge two assoc. arrays
map-merge(foo, bar)|SCSS/Sass

Computed property names allows you to put any expression on the left-hand side of a property within an object literal, if you wrap that thing in []

######## entries

An entry is a view into one item in a assoc array.
In rust, an `Entry` is an Enum with possible variants `Occupied`, `Bacant`
in rust `Entry.or_insert` insets the key into the map if map is empty.
Rust: Has the entry() function go get a Entry

####### assoc-array files

typically, most languages have modules/libraries called json/yaml for json/yaml processing.
JS and thus node calles its json/yaml libraries JSON/YAML.
<j-or-y-library-object-name>.load()|parse as JSON/YAML into assoc array structure|Python
<j-or-y-library-object-name>.parse()|parse as JSON/YAML into assoc array structure|JS (incl node)
<j-or-y-library-object-name>.dump(<assoc-arr>, <file>)|write assoc array as JSON/YAML|Python

to make sure that Python's JSON/YAML libraries insert newlines and indentation, pass the load method the named parameter indent with the relevant indent.

######## Rust serde

serde is a rust crate for serializing/deserializing data structures from/to common formats.
serde uses additional crates to add support for formats, e.g. serde_json for json and serde_yaml for yaml.
trying to use serde-related features with indexmap will fail if you haven't specified the feature "serde"
you can make `ureq` support conversion to json via serde directly via the `json` feature.
serde represents anything with the `Value` enum
the `Value` enum has variants for each type supported by the file format. 
serde_yaml represents mappings as `Value::Mapping<Value, Value>`
serde_json represents Objects as `Value::Map<String, Value>`

`Value.as_<type>` returns Option<<type>>
`Value.is_<type>` returns bool representing whether is <type>

using serde to parse, we may parse arbitrary data into a serde representation using from_str and then index into it as you would in JS with square bracket notation (but you may recieve `Value::Null`), or we may parse data into a predefined rust representation
to make serde support the derive macro, set the "derive" feature

####### misc

tables are actually the only data structure in lua


#### Linear collections/ADTs

Linear collections/ADTs are a sequence of items.
Python calls its data structres that are linear collections sequences.
Linear collections are the equivalents of sequences in math.
Python sequences: list, tuple, str

It seems to me that all non-array linear collections only allow sequential access.

##### Linear collection methods

sort the thing
sort()|Perl|Python (in-place!)|Ruby

reverse the thing
reverse()|JS(in-place)|Perl|Python (in-place!)|Ruby

Append a linear collection to a different linear collection 
col1 + col2|Python (also works for strings)
col1 << col2|Ruby (also works for strings)
col1.extend(col2)|Python

Repeat the contents of a linear collection n times
col1 * n|Python

append one element to end of dynamic linear collection
push()|JS|Rust
append()|Python

remove an element from a lin coll by name
somelincoll.remove(elem)|Python

insert an element at a specific position
somelincoll.insert(elem, index)|JS

Fill the thing with the specified element
somelincol.fill(element[, start[, range]])|JS|Ruby
In Ruby, fill also may take a block to calculate the element to fill it.
[element; length]|Rust (Arrays)
vec![element; length]|Rust (Vectors)

JS
Array() and Array.of() will create an array of a list of arguments.
The difference between Array.of() and Array() is in the handling of integer arguments: Array.of(7) creates an array with a single element, 7, whereas Array(7) creates an empty array with a length property of 7 (Note: this implies an array of 7 empty slots, not slots with actual undefined values).

The push() and pop() methods were borrowed from the Stack ADT to describe inserting/taking from the end of the linear collection in some languages, e.g. JS. 
Most commonly, pop/shift returns the element removed, while push/unshift returns the new length.
Shift and unshift are methods in JS, Ruby, Perl, Java that do the same as pop/push but for the beginning of the array.
Python extends the pop method to all collections, but it generally works weirdly, compared to other programming languages:
someset.pop()|a random element
someassocarray.pop(somekey)|the relevant value
somearr.pop(index)

somearray.splice(⟮c1;start⟯, numberOfElementsToDelete, element1toInsert, ...); (odd, js only, returns array of removed elements which may be empty)

###### Rust

In Rust, vectors can be indexed via the [] syntax, which will panic if the element doesn't exist, or via get(), which returns an Option<&T>

##### Strings as linear collections

TODO string as iterable
Strings are often implemented as linear collections (esp. arrays) of chars, or at least their semantics are similar enough that they work the same way.
Since strings are semantically and often also by implementation similar to linear collections, their methods often are the same.

###### methods

get (first) index of element/substring in string or linear collection
foo.index(bar, optionalStartIndex)|Python
foo.indexOf(bar, optionalStartIndex)|JS (returns -1 if ti could not be found)

get (last) index of element/substring in string or linear collection
foo.lastIndexOf(bar, optionalStartIndex)|JS

Concatenate multiple strings/ arrays at the end of an existing string/array
stringOrArray.concat(stringsOrArrays)|JS|Ruby

##### Array

An array (type) is a abstract datatype of an ordered linear collection of elemennts, selected by indices.

###### depth

no indices (one value only)|zero-dimensional array (uncommon)|scalar
one index|(one-dimensional) array|vector
two indices|two-dimensional array|matrix
n indices|multidimensional array|tensor

###### types & names

Arrays may be dynamic = have variable size, or static = have fixed size.
Dynamic arrays are sometimes called arraylists.
Arrays are generally primitives in different programming languages, though they differ on syntax and what they call them.

dynamic arrays (one type only)

Vec<T>|rust
ArrayList<T>|Java
List(yes, really)<T>|C#

dynamic arrays (of whatever types)

list|python
array|perl|JS|ruby

Rust Vectors, Java ArrayLists and C# Lists are Objects/Structs and defined over a generic

static arrays (one type only)

array|C#|Java|Rust

static arrays (of different types), the compiler therefore knows the type of each index

tuple|rust|TS

immutable static array (of whatever types)

sequence|yaml
array|liquid|TOML
tuple|Python
list|SASS/SCSS 

table|lua (though this is more properly the assoc array type, it just happens that an assoc array w/o keys will have numeric keys set up for it by lua, making it also the array type)

for rust, to have things of different types in a vector, one would have to use something like enum or box.

###### Array literals

In array literals, the invidual elements are generally separated by ',', except sh, which separates them by space

dynamic (of whatever types)
()|Perl (same as assoc. arr)|Shell
[]|JS|Python|Ruby

static, one type only
{}|C#|Java

static arrays (of diffent types), the compiler therefore knows the type of each index
()|rust
[]|TS

dynamic (of a single type)
vec![]|Rust (creation only)

immutable static array (of whatever types)

()|SASS/Scss|Python (Though in python in reality it is the comma that creates a tuple. the parentheses are just often needed for grouping)
[]|TOML|YAML (if inline)

Most languages use the same syntax for one-dimensional, two-dimensional, or multidimensionall arrays, merely nesting the literals.
In C# the type for multidimensional arrays (e.g. for a three-dimensional array) is type&lt;delimiter&gt;,,&lt;delimiter&gt; (and for the constructor type&lt;delimiter&gt;length,length,length&lt;delimiter&gt;). These are different from merely arrays of arrays, as these have a uniform size (while arrays of arrays do not) 

YAML also has indentation delimited, newline separated, individual items marked by `- ` version

In sh, referring to the whole array requires a special syntax my_array[@] which can only be used within ${}

In C# and Java, the builtin static arrays are objects, and thus must be created using the new operator. 
in languages with type annotation, the type of dynamic arrays is usually written as type[], e.g. int[] or String[]
in TS, <type>[] is syntactic sugar for Array\<<type>\>
in TS, readonly <type>[] is syntactic sugar for ReadonlyArray\<<type>\>
In rust, the type of its (static) array is annotated as [<type>, <length>]
Tuple types typically have type annotations of <delimiter><type>{, <type>}<delimiter>
When creating static arrays, the size must be given. In C# and Java, this is done in the [] of the array type in the constructor, e.g. new type[10];
In JS, one can create an array with a specfic size (and thus ergo empty slots) by using Array(n) or new Array(n)

access|O(1)
iterating|O(n)

##### Lists

Lists/Sequences are an abstract data type (specifically a collection), in which each element has a position (a first element, a second element), and that are finite.
Lists are always dynamically sized
C#: List, defined over one generic. must be created via constructor. Add to end of list .Add()

###### linked list

flex-container:<img src="sm_408px-Singly-linked-list.svg.png">
A linked list is a data structure (implementing the ADT list) in which each node/vertex holds a reference to the next element.
To access a linked list, we merely need a reference to the first element.
A linked list in which the only node/vertex is a reference to the next element is a singly-linked list

flex-container:<img src="sm_doubly_linked_list.svg">
A linked list with a backward reference too is a doubly-linked list.
access|O(n)

####### cons

cons is short for construct function, and comes from lisp. 
To ⟮c4;cons something onto something⟯ is to take a ⟮c1;container⟯, add ⟮c2;an element in front of it⟯, and ⟮c3;put this in another container⟯.
A singly linked list is functionally eqivalent to / can be modelled by a set of nested ordered pairs (foo, (bar, (quuz, nil))).
A cons list is a singly linked list constructed via nested ordered pairs.

####### blockchain

flex-container:<img src="blockchain.svg">


A ⟮c+;blockchain⟯ is a growing ⟮c+;(linked) list⟯ of records called ⟮c+;blocks⟯.
In a blockchain, each block contains ⟮c+;a hash⟯ of ⟮c+;the previous block⟯, a ⟮c+;timestamp⟯, a ⟮c+;nonce⟯, and ⟮c+;transaction data⟯ represented as ⟮c+;a merkle tree⟯.
Since ⟮c+;blocks contain hashes of previous blocks⟯, ⟮c+;changing a block⟯ would ⟮c+;also require changing subsequent blocks.⟯

###### vs arrays

slower access O(n) vs O(1)
more space consumption if no empty spaces in array due to pointers.
Re: modern processors, linked lists have the problem that they are stored non-contiguously and thus can't take advantage of processor cache as well (priniple of spatial locality)

##### Streams

Streams are an abstract data type (specifically a linear collection), in which each element has a position (a first element, a second element), and that are infinite (or at least potentially so).

##### Stack

The anaogy of a stack historically comes from spring-loaded plate dispensers (e.g. in a mensa)
In a stack, the element you remove will be ⟮c1;the one you added most recently⟯
LIFO = last in first out
A stack is a linear collection ADT with LIFO order, and the operations:
push: add to the top of the stack
pop: remove from top of the stack
peek: loop at top of stack

flex-container:<img src="sm_Data_stack.svg">

##### Queue

FIFO = first in first out
A stack is a linear collection ADT with FIFO order, and the operations:
enqueue: add to the end of the queue
dequeue: remove from the front of the queue
peek: look a the next element that would be dequeued

flex-container:<img src="sm_450px-Data_Queue.svg.png">

### intersection of iterators, strings, linear collections

#### slicing and ranges

Slice and range syntax is often similar.
For slicing, the slice syntax must generally be surrounded by the same brackets used for array indexing.
For ranges, different programming languages need them to be surrounded by () at different times.
start..end_incl|Ruby|Perl|Liquid (range only)
start..end_excl|Rust
start...end_excl|Ruby
start..=end_incl|Rust

##### Slicing

Slicing is extracting a subset of elements from a data structure.
Slicing is most commonly performed on linear collections or strings.
In most cases, omitting the start defaults to 0, and omitting the end defaults to the maximum value (last element/slength)
In general, using a negative index for step will reverse the thing.
In python you can assign to slices, delete them, etc.

[start:end_excl:step]|Python
.slice(start, end_excl)|JS
.substring(start, end_excl)|JS (only strings, will not count from back, but will swap start and end if start is larger)
[start,length]Ruby

##### ranges

Ranges may be a syntax for generating iterators/arrays, or may be their own type. They may also be both, pythons range is an interable type that as all iterables generates an iterator if needed.
Step is pretty much always optional.

range(start, stop, step)|python|lodash/underscore (js)
seq start step stop|sh

Bash calls its range syntax a <dfn>sequence expression</dfn>.
Bash also supports characters as start and stop.

#### misc

does the thing contain the thing?
include?|Ruby (Array, String, Enumerable)
includes()|JS (Array, String)

Is there a truthy value in an iterable
any(iterable)|Python

Are all the values in an iterable truthy 
all(iterable)|Python

Sum up all the elements in an iterable
sum(iterable)|Python
enumerableWhichIsJustASynonymForIterable.sum()|Ruby
Iterator.sum()|Rust


count occurrences of element
foo.count(bar)|Python|Ruby
no easy way|JS

### Iterators

An iterator is an object (or similar) whose purpose is to iterate over some data. 
An iterator has a next() method that returns the next element.
Most other functionality that an iterator offers can be derived from the next() method
An iterable is generally something that can create an iterator of itself.
Something being iterable is generally implemented as an interface.
Something being an iterator may be implemented as a type or interface

#### Iterator implementation

`Iterator` trait/interface|Rust

In rust, to implement `Iterator` you only have to implement `next()`, and Rust will automatically implement a bunch of other methods for you.

#### iterables


In ruby, iterables are called enumerables.
In most languages that have iterables, most collections are iterable, as are strings and ranges. 
Java Strings are not iterable, JS objects aren't either.

##### iterable <-> iterator

Iterables generally require explicit or implicit conversion to become/spawn iterators.
iterables are always automatically converted to iterators|
iterables are only automatically converted to iterators in loop contexts, manual conversion otherwise|rust


In rust, you call `collect` on the iterator to turn it back into a data structure.

###### rust

In rust, iterators themselves must always be mutable, since calling next() changes the iterator.

<iterable>.iter()|iterator of immutable references
<iterable>.iter_mut()|iterator of mutable references
<iterable>.into_iter()|iterator of owned values


#### next()

in JS, the next() method returns an assoc array {
  done: bool,
  value: ...
}
In JS, Array.from() transforms a given iterable into an array. (list() does the same in Python and foo.to_a does it in ruby)

#### Generators

A generator is a form of iterator. Generators are created via a generator function (thus you control what the next() method returns), but otherwise behave like any other iterator.
In JS, generators are indicated by a * after the function keyword.
In JS at least, generators continue from where they left off after the last yield.
In JS, returning or encountering an error ends the generator.
In JS, the next() function of a generator's iterator can be passed an argument that will be assined to the yield expression.
Returning the current iterator element 
yield|JS

yield another generator (JS) yield*

#### iterator methods

someIter.⟮c+;zip⟯() takes ⟮c+;two iterators⟯ and returns ⟮c+;a new iterator⟯ which will for each call to ⟮c+;next()⟯ return a ⟮c+;tuple⟯ with the values ⟮c+;the other two would have returned⟯ with ⟮c+;next()⟯
In rust, methods (most of them higher-order functions) called on iterators are known  as adapters or consumers, depending on what they do.
Iterator adapters take an iterator and return another iterator
Iterator consumers take an iterator and return something else (thus consuming the iterator)

### Strings

A string type is generally a type for an arbitrary sequence of characters.
Depending on the language, strings may be mutable or immutable.
In general, more languages lean to the immutable string direction.
Languages with mutable strings I know include Perl, Ruby.
While it may be tempting to change strings by assigning to indices, in languages with immutable strings, it does not work. However, in JS in non-strict mode it will not trow an error
If a language has immutable strings, string operations actually create a new string.
In many languages, especially those that do not have a char type, string literals can be indicated either with single or double quotes.
In languages that have a char type, the char type is generally indicated with single quotes, and the string type with double quotes. Examples: C#, Java, Rust
Some langauges that don't have a char type differentiate between string literals with single and double quotes (e.g. treating single quote string literals as raw strings, e.g. sh, Perl, Ruby), some languages (CSS, HTML, lua, liquid, python, JS) do not.
In languages that have single-quoted string literals, interpolation is generally also not allowd in them.
JS has a specific, especially featureful type of sting called a template literal, which are delimited by backticks (`foo`)
sh is a little special in that it accepts strings with no surrounding quotes in some cases.
YAML accepts unquoted strings if they don't interfere with other syntax, of which the most common case is them containing ` :`
In some languages, most notably C, strings are ended by the NULL (0x00) character, these are known as null-terminated strings.

A raw string is a string literal where character escapes have been disabled and so everything is a literal.
r or R"foo"|Python|Rust
String.raw`foo`|JS
'foo'|sh|Perl|Ruby|TOML

Multiline string delimiters
`containsnewlines`|JS
\[\[containsnewlines\]\]|Lua
"containsnewlines"|Rust (all strings are multiline)
"""containsnewlines"""|Python|TOML
|\nproper indentation|YAML

Strings that stretch over multiple lines in source code but are actually folded into a single line in the resulting thing (for source code readability)
>\nproper indentation|YAML

The type for css strings is <string>

#### chars

The datatype storing a single character is generally called char.
In rust, a char contains a single UTF-32 encoded unicode codepoint.

#### String interpolation/String formatting

String interpolation is evaluating a string with placeholders and replacing them with their values
String interpolation is a form of template processing (cf other cards)
In JS, string interpolation can only be performed within template literals.

\${expr}|JS|only in template literals
\#{expr}|Ruby|SCSS/SASS
&lt;sigil&gt;{expr}|Perl
&lt;sigil&gt;variable|Perl

sh's various $-introduced expressions are similar to string interpolation.
Python has three ways to perform string interpolation:
old-style stirng formatting: is just c-style string formatting. The whole string is followed by a % character, which itself is followed by a single value or a tuple of values to interpolate
new-style string formatting:
{} or {0}, {1} ... interpolates within the string, if calling format() on the string. Interpolated expressions are args to format method, format specifiers go within {}, if passing to format by name, refer to these things like so {name}. 
If combining w/ format specifiers \{<name>[!<conversion>][:<format_specifier>]\}
"Error code: {errno:x}".format(errno = ...
f-strings: allow arbitrary expression within {}. String must be prefixed by f
f"Hello, {name}"

rust defines its format syntax in std::fmt, which largely tracks python's str.format() specifier
rust allows its std::fmt formatting syntax in its format! and println!/eprintln! macros, with the difference being that the former returns a string and the latter prints.
specifying a ? as the final element in a rust formatting syntax specifier makes it use the trait `Debug`, otherwise it will use the trait `Display`

##### C style string formatting

(C) format strings aka printf (print formatted) format strings are names for a specific type of string formatting syntax using % and originating from C.
C format strings specify the format of a given argument with a format specifier
format specifier: % followed by a char or a few chars to indicate the format.
Which strings to interpolate where is determined positionally (the first string is interpolated )
Positional arguments to interpolate are specified after the string separated by a %
c-format-string-format-specifier ::= %[<parameter>]{<flag>}[<width>][.<precision>][<length>]<type>
parameter ::= <n>$
flag ::= -|+| |0|'|#
width ::= <positive-integer> # specifies minimum width.
precision ::= <positive-integer> # specifies maximum width

flag meaning
-|left-align output
+|prepend a + sign for positive numbers
 |prepend a space for positive numbers
0|use zeroes when padding via width
'|The integer or exponent of a decimal has the thousands grouping separator applied. 
#|

for the types in c-style format strings, if there is an uppercase variant this normally uppercases the cahracters

common types
x or X|hex (unsigned numbers only)
o|octal (unsigned numbers only)
d or i|signed int
u|unsigned int
f or F|decimal number
e or E|use exponent based notation e±dd
g or G|decide between e/E and f/F depending on maginitude
s|string
%|percentage (python .format() only)
b|binary (python .format() only)

##### python-style string formatting

python's str.format() method takes a C format string inspired but somewhat different syntax.
[[<fill>]<align>][<sign>][#][0][<width>][<group>][.<precision>][<type>]
where width, precision and type are the same as with C format strings
fill|what character to use to pad (takes a string)
align|what direction to align
sign|is a sign included for numeric values
#|causes an explicit base indicator to be shown for binary, octal, and hex
0|pads with 0
group|indicates a separator character for groups of numbers

align ::= \<|\>|^|=

<|align left
>|align right
^|center
=|place padding between number and sign

sign ::= +| |-

+|+ for positive numbers, - for negative numbers
-|nothing for positive numbers, - for negative numbers
 |space for positive numbers, - for negative numbers



#### String multiplication

x n|Perl
* n|Python (can also be used for arrays)|Ruby (can also be used for arrays)
.repeat(n)|JS|Ruby

#### String concatenation

string concatenation is joining strings together into a single string.

..|Lua
+|Java|C#|Python|Ruby|Rust|JS
.|Perl
.push_str()|Rust (for str + str)
.push()|Rust (for str + cahar)
Adjacent string literals are automatically concatenated|Python|Ruby

#### Regex matching

JS has regex literals: /<regex>/<flags> (which creates a RegExp object)
and a constructor: new RegExp("regex","flags"), often used if you need to construct the regex dynamically at runtime
In JS, you can both use methods on strings which take regexes, or methods on RegExp objects which take strings
The RegExp Object has a property lastIndex which indicates the offset that the RegExp will search for a match at next time (if the regex is global or sticky). This stays the same even if you switch the string in the meantime!

Does the string match the regex?
RegExpObject.test(string): boolean

RegExpObject.exec(string): {
  0: wholeMatch, 
  1: captureGroup1, 
  2: captureGroup2...,
  index: indexAtWhichTheMatchBegan,
  input: origialString
}

somestr.match() and .matchAll return string matches for a Regex.
somestr.replace() and .replaceAll replace the regex they got as a first arg with whatever is specified as a second arg, be that a string (using $1 etc. optionally) or a replacerFunction
The replacerFunction recieves the following arguments:
match|The matched substring.
p1, p2, ...|The nth string found by a parenthesized capture group
offset|The offset of the matched substring within the whole string being examined
string|The whole string being examined.
groups|named capture groups

the All() versions of the regex methods of strings both require the regex to be global and throw an error if it isn't.

What somestr.match(regexp) returns depend on whether the regex is global (g) or not:
If global, match() returns all matches, but no capturing groups. If not global, match() returns the same thing as RegExpObject.exec. matchAll() returns an iterator with individual things that are  the same thing as RegExpObject.exec returns.


#### common string methods

Capitalizations

convert to uppercase|.upper()|Python
convert to lowercase|.lower()|Python
convert to uppercase|.toUpperCase()|JS
convert to lowercase|.toLowerCase()|JS
convert to uppercase|text-transform: uppercase|CSS
convert to lowercase|text-transform: lowercase|CSS
switch upper and lower case chars|.swapcase()|Python
capitalize all first letters|.title()|Python
capitalize all the first letters|text-transform: capitalize|CSS
capitalize the first letter of the string|.capitalize()|Python
capitalize the first letter of the string| bar capitalize|Liquid
pad stringth to specified length by adding to the left/right|.padStart/padEnd(<length>, <pad-string>)
pad stringth to specified length by adding to the left/right|.rjust/ljust(<length>, <pad-string>)


does a string start with?/end with?|somestr.startsWith/endsWith(searchstr)|JS (accepts an optional second arg of the index to start searching)
does a string start with/end with?|somestr.startswith/endswith(searchstr)|Python
remove whitespace from beginning and end of string|trim()|JS, Ruby
remove whitespace from beginning and end of string|strip()|Python
remove whitespace from beginning of string|trimStart()/trimLeft()|JS
remove whitespace from end of string|trimStart()/trimLeft()|Ruby
split string on foo|.split(foo)|Python|JS(empty string for char array)|Rust
split string on whitespace|.split_whitespace()|Rust
split string on newlines|.lines()|Rust

to char array/iterator
chars()|Rust

parse sting to other type
<string-object>.parse()|Rust (Returns a `Result`, often requires turbofish annotation.)

SCSS/Sass
⟮c1;unquote(foo) or string.unquote(foo⟯)|⟮c2;unquote a string (so that css gets the value as the correct type, eg. when using maps⟯)
⟮c3;quote(foo) or string.quote(foo⟯)|⟮c4;return string, but quoted⟯



##### String replacement

somestr.replace(foo, bar)|JS|Python

##### Join to string

separator.join(iterable)|Python
somearray.join(separator)|JS|Ruby

separator defaults to , for JS and to nothing for Ruby

#### JS oddity: tag functions

Tag functions are functions prefixed to template literals (but not called)
Tag functions recieve a first argument an array of all constituent string parts of a template literal, and all interpolated values as following arguments.
Whatever the tag function returns will be what the string evaluates to.
Tag functions can return whatever.

## operators

overloading
In Ruby, all operators are actually just syntactic sugar for methods. that is, + 3 is .+(3), somearr[1] is somearr.[](1), !3 is 3.! etc.

### precedence

Operator precedence in programming mirrors the math concept of order of operations.
Operator precedence / order of operations is in which order to apply operations.
In most programming languages, math operations have the same operator precedence as they would in math itself.
Parentheses can modify the order of operations just as in math.
The power operator has unclear order of operations for historical reasons (in other programming languages), so JS throws an error if you use it without parentheses where it would make a difference
In liquid, the order of operatons is right to left, parentheses are forbidden.

### relational opearators

In computer science, a relational operator is an operator that tests or defines some kind of relation between two entities. These include numerical equality (e.g., 5 = 5) and inequalities (e.g., 4 ≥ 3).

~=|not equals|lua
!=|not equals|C#|Java|JS
==|equals|most programming languages
<=|less than or equals|most programming languages
&gt;=|greater than or equals|most programming languages
&gt;|greater than|most programming languages
&lt;|less than|most programming languages
<=>|returns 1 if left arg is larger, -1 if right arg is larger, and 0 if both are equal|Perl|Ruby

Python uses the `is` operator when comparing equality of location in memory

JS has versions of the equality operators with one extra =. The shorter ones coerce before comparisons. Specifically, any of the shorter ops containing < or > coerce to string or numbers (including null, but not undefined). == coercion is more complicated, but will coerce null to undefined.

For anything that is a data structure, there can be two kinds of equality (using Kotlin terminology)
structural equality = equivalent content
referential equality = same reference
JS, Java, C# use referential equality on non-scalars
Ruby and Python use structural equality on non-scalars (arrays and assoc. arrays)

since relational operators are handled by test in sh, they are actually all arguments to test.

test uses the normal equality operators for strings, but has a different set of operators for integer equality:
-ne|is not equal to
-lt|is less than
-le|less than or equal to
-gt|is greater than
-ge|greater than or equal to
-eq|is equal to
Perl uses sh-style comparison operator without the leading -

test has a number of options/operators for file existence and type

-e foo|foo exists and is a file
-d foo|foo exists and is a directory
-r foo|allowed to read foo

greater/smaller with strings is generally relative to their position in unicode, which for latin characters tracks ASCII and thus "Z" < "a"
Comparing a thing with itself is always true, except for: 
in JS, NaN

##### interfaces

Things using the ruby mixin Comparable must define <=> operator, and then gain access to the other comparison operators, as well as between? and clamp

is x between foo and bar?
x.between?(foo, bar)|Ruby

#### string relational operators

e.g. CSS attribute selectors, youtube-dl 

^=|begins with value
$=|ends with value
*=|contains value at some point

~=|attr is a whitespace-separated list of words, one of which is exactly value.
bar=|attr  is exactly value or begins with value immediately followed by a hyphen. It is often used for language subcode matches.

### boolean operators

logical and|and|python|liquid|lua|Ruby (lower precedence)
logical and|&&|C#|Java|JS|Ruby (higher precedence)|(ba)sh
logical or|or|python|liquid|lua|Ruby (lower precedence)
logical or|barbar|C#|Java|JS|Ruby (higher precedence)|(ba)sh
logical not|not|python
logical not|!|C#|Java|JS

In ruby, between and/or and &&/|| the former have lower precedence, and even have lower precedence than the equality operator.
Double not can generally be used to get the truthiness/falsiness of a thing, even outside of a boolean context.

#### short-circuiting

Short circuiting is more properly short-circuit evaluation.
Short-circuit evaluation  an expression stopping evaluating⟮c1;as soon as it's outcome is determined⟯
Short-circuit evaluation is most commonly found in the boolean operators of most programming languages
with short-circuiting of binary operators, the second argument is executed or evaluated only if the first argument does not suffice to determine the value of the expression.
specifically, expr1 LAND expr2 will not evaluate expr2 if expr1 is false/falsy
expr1 LOR expr2 will not evaluate expr2 if expr1 is true/truthy
Can be used to ensure a variable never gets assigned a falsy value by using logical/boolean or, since (only) if the first expression is falsy the second expression will be evaluated.
It is possible to create a kind of if statement using only short-circuiting operators: CONDITION && IFTRUE || IFFALSE
(ba)sh

⟮c+;??⟯ is like ⟮c+;||⟯ but ⟮c+;only returns its right-hand value on nullish values⟯

### bitwise

Bitwise operations operate on the underlying binary value (regardless of type in the programming language).
Most C-family languages support bitwise operations.

bitwise not|~
left shift|&lt;&lt; <n>
right shift|>> <n>
bitwise XOR|^
bitwise OR|bar
bitwise AND|&

when using the left shift operator, the newly created places will be filled by zero

### math

addition|+
multiplication|*
subtraction|-
division|/|Python: always returns a float, JS: it depends (but no distinction between floats and ints anyway)
floor division|//
remainder|%
power|**
increment|++
decrement|--

unary plus does different things in different languages: in some it does nothing (with numeric types) or throws an error (with non-numeric types). In JS it converts it to an number.


The increment and decrement operators do not exist in python.
The increment and decrement operators behave differently based on their position in relation to the number in some languages: 
++somevar or --somevar will crement first, and then evaluate, somevar++ or somevar-- will evaluate first, and then crement

### comma

In the C and thus in JS, Perl, the comma operator (represented by the token ,) is a binary operator that evaluates its first operand and discards the result, and then evaluates the second operand and returns this value (and type). (this is distinct from the comma e.g. in parameter lists)

A trailing comma is a comma at the end of a list of arguments, array elements, etc. 
In most programming languages (all of them I know), trailing commas are ignored (do not produce an error or empty elements).
In JS, trailing commas produced errors in some situations until recently (the newer ES versions such as 2017)

### element in collection/substring in string?

stringOrColl contains elem|liquid
elem in stringOrColl|Python|JS
stringOrColl.includes(elem, optionalSearchStartPos)

`in` in JS works amusingly if used on arrays: it will look for integer keys, and not for values, so that it will return false for "foo" in ["foo"] but true for 0 in ["foo"] (this is because arrays are objects, and thus the integer keys are actually object keys)

### remove element from collection

del|python
delete|JS

### Type of element

typeof foo|JS
type(foo)|Python
std::any::type_name(foo)|Rust

typeof in JS returns a string, and can return 'number', 'string', 'boolean', 'undefined', 'object' or 'function'

typeof...
{a: 1}|'object';
undefined|'undefined';
true|'boolean';
null|'object';
new Date()|'object';
function() {}|'function';
[1, 2, 4]|'object';
NaN|'number';
Infinity|'number';
37|'number';
3.14|'number';
/regex/|'object';
"something"|'string';
""|'string';
!!342|'boolean';
"1"|'string';

To test whether sth is an array in JS, you need to use Array.isArray()

### Length of strings, collections, etc.

foo.length|Java|JS|Ruby
foo.Length|C#
len(foo)|Python
#foo|lua|sh (must be surrounded by ${}, and followed by [@] if an array)

length() for strings in perl, merely generating a scalar context is enough for arrays

### Spread operator/Rest syntax

Both JS and Ruby have an operator that allows them to do similar things in relation to arguments and arrays.
Ruby calls this operator the splat operator, while js calls it a rest operator in the context of callable unit parameters (not arguments), and spread syntax otherwise

...|JS
*|Ruby|python

In the context of callable unit parameters, JS rest syntax and Ruby/Pythons's Splat both gather the remaining arguments into an array. the parameter so marked must be the last in the list.
funcName(1,2,3)
&lt;keyword&gt; funcName(... OR *foo)
foo will now be [1,2,3]
When not in callable unit parameters, JS spread and Ruby/Pythons splat transform an array into its constituent members, or in the case of assoc arrays into its constituent mappings.
Ruby uses a double splat operator for associative array destructuring.
[... OR *[1,2,3], 4] == [1,2,3,4]
{**{:foo => 1, :bar => 2}, :quuz => 3} == {:foo=>1, :bar=>2, :quuz=>3} and {...{foo: 1, bar:2}, quuz:3} === { foo: 1, bar: 2, quuz: 3 }
Rust's struct update syntax has some similarities to JS associative array destructuring
Rust's struct update syntax uses the oparator ..
for including all values of a struct instance into the current struct instance, use struct update sytnax.

### traits/interfaces/methods that implement math operators

Add|Rust

## Errors

Some languages distinguish between recoverable and unrecoverable errors.
recoverable errors e.g. not finding a file, unrecoverable errors e.g. stack overflow
Java and C# call recoverable errors exceptions and unrecoverable errors errors.
It can make sense to catch recoverable errors, but it is generally impossible to catch unrecoverable errors

### types

Errors can on one level be divided into ⟮c1;syntax⟯, ⟮c2;static semantic,⟯ and ⟮c3;logic errors⟯.

A syntax error is an expression which violates the syntax of the language (will be detected during syntax analysis)
forgetting a parenthesis
A static semantic error is an expression which is syntactically correct but semantically meaningless. (will be detected during semantic analysis)
3/"kawaisa"
A logic error is an error where the program runs without problems, but produces an unintended result. (will only be detected on running the program, generally)

Based on when they occur, we separate compile-time and runtime errors

### Error handling

#### Throwing errors

Generally take an expression as arg.

keywords
die|perl
throw|JS|Java|C#
error()|lua
@error|SCSS?Sass
raise|Ruby
panic!()|Rust

for rust, panicking is throwing an unrecoverable error

#### Error handling control structures

most commonly: try &lt;block&gt; catch (&lt;error-specifier&gt;) &lt;block&gt; finally &lt;block&gt;
In Ruby begin &lt;block&gt; rescue (&lt;error-specifier&gt;) &lt;block&gt; ensure &lt;block&gt;
Rust is notable for not having any error handling of this kind.
In general, having a try and either a catch or a finally block is necessary for the construct to be syntacitcally correct.
In JS, the <error-specifier> for catch was necessary until ES2019, and has been optional since

#### assert

Assertions are predicates that deliberatly crash the program if the predicate is false.
Assertions are generally used when something should be logically impossible to be false, and thus aren't handled by error handling.
Assertions are typically only used during development.
Rust implements assertions via macros.
rusts ⟮c1;assert_eq!⟯ macro tests wheter ⟮c2;two expressions are equal⟯ (using the trait ⟮c2;PartialEq⟯), and ⟮c3;panics if they are not⟯
rusts ⟮c1;assert!⟯ macro tests whether ⟮c2;something is true⟯, and ⟮c3;panics if it is not⟯

## Callable units

Callable unit is a cover term for anything that can be called, be that functions, methods, procedures...
A call is a thing that executes a callable unit.
Callable units generally can take arguments if specified.

Keyword to start a callable unit
function|JS|Lua|sh|SCSS/Sass (@function ofc)
fn|Rust
def|python|Ruby
sub|perl
no keyword|C#|Java

Callable units can generally be split into callable unit signature and callable unit body. The callable unit signature usually specifies at least return type, name, and parameters, as well as the keyword if necessary. In sh, a callable unit signature contains nothing but the keyword and name/
The body of the callablue unit contains the code to execute.
In java, the callable unit signature also specifies parameter type, access modifier, and optionally staticness/finalness/abstractness.
In JS, function keyword defined callable units generate their own this, while arrow functions do not.

### Declaration

In most languages, functions can only be declared in statements, however languages that have functions as first-class citizens often also allow declaration via expressions.
function expressions are generally assigned to variables for later usage.
JS calls function declarations that are statements function declarations, and function declarations that are expressions function expressions.
since classes in JS are merely syntactic sugar for functions, there are also class declarations and class expressions

### signatures

Languages with manifest typing typically require the returned type to be declared in callable unit signatures.
void is commonly used for no return type in languages that require a return type to be specified.
return type is indicated:
-> <type> at the end of signature|rust
: <type> at the end of signature|TS
<access-modifier> [static|abstract] <type> <callable-unit-name>|C#|Java

### returning

Across most languages, the keyword to return whatever value is the `return` keyword.
The datatype of the thing that is returned from a callable unit is known  ⟮c1;The return type⟯
In non-manifestly typed languages, the default return value of a function is the null type
In general, using the return keyword without a value returns the languages null type.
Multiple values: separated by comma|lua
In Rust, using the return keyword is frowned upon, as blocks return their final expression anyway.

#### returning and side effects

A side effect is a modification of the state of something that is outside of the local environment the operation is performed in.
A callable unit must return something or have side effects, else it does nothing.
A procedure (using a narrow definition) is a callable unit that does not return a value, instead causing side effects.
A function is a callable unit that returns a value.
A pure function is idempotent and has no side effects.


### Closures

A ⟮c1;closure⟯ is the combination of ⟮c2;a callable unit⟯ and ⟮c3;the lexical environment⟯ (= ⟮c4;any variables that were in scope⟯) within which that function was declared.
Closures are created when the functions are created.
All callable units automatically create closures in JS, lua.

#### rust

In rust, only closures create closures.
In rust, there are three traits that indicate closures: Fn, FnMut and FnOnce.
Rust decides whether our closure is fn, Fn, FnMut or FnOnce by looking at what the closure does
the keyword `move` before a closure forces the closure to become `FnOnce` (take ownership).
Rust only closes over the environment actually used
In rust, closures don't necessarily need type annotations, however once a closure has been used with a certain type, rust fixes the types and other types become impermissible.
fn|does not form closure (but still can be used as first-class value)
Fn|forms closure of immutable references
FnMut|forms closure of mutable references
FnOnce|forms closure of owned values

### Anonymous, first-class, higher-order functions and callbacks

#### distinguising

A callable unit not bound to an identifier is an anonymous function/callable unit.
First-class functions/callable units are callable units that are first-class citizens.
A higher order function is a function that takes a first-class function as an argument, or returns a function. All other functions are first-order functions.
callbacks are first-class functions passed to other callable units to be executed at some other point

#### relationships

anonymous functios are almost always first-class functions, and are thus often passed as arguments, etc.
However, often non-anonymous functions can also be first-class functions
callback functions are typically also anonymous

#### callbacks

The deep nesting of callbacks that result in unreadability is known as callback hell or the pyramid of doom
Error-first callback look like  (err, value) => ...
Node generally takes error-first callbacks.

#### first-class functions

##### which functions are first-class

In JS, lua, python, rust all functions are first-class. 
In Ruby, only functions created with a special syntax are first-class.
While in rust only closures form closures, all functions are in fact first class. Even things written with the closure syntax actually become `fn` type functions if they don't actually close over anything. (tested)

##### types of first-class functions in statically typed languages

In statically typed languages, first-class functions must have a type that describes them.
\(<ts-param-list>\) => <return-type>|TS
(fn|Fn|FnMut|FnOnce|fn)\([<param-type>]{, <param-type>}\) -> <return-type>|Rust

<ts-param-list> ::= [<param-name>: <param-type>]{, <param-name>: <param-type>}

#### anonymous functions

In JS, anonymous functions have no special syntax, you merely leave out the identifier.

#### anonymous first-class functions

##### name

In ruby, anonymous first-class functions are called blocks.
In rust, anonymous first-class functions are called closures.
In JS, there is a special type of first-class anonymous function called an arrow function.

##### syntax

In ruby and rust, parameters to blocks/closures are surrounded by |...|
In ruby and rust, blocks/closures are surrounded by {}
{|params| code...}
In ruby, blocks may also be surrounded by do ... end
In rust, one-line closures may have their curly braces left out.

##### ruby

in ruby, to call a passed block, use the yield keyword. 
Anything passed to the yield keyword will be available as arguments to the block
In ruby, the & operator converts a block to a proc object.
Calling #call on a proc object is similar to yielding a block
instead of a block with the syntax {|elem| elem.method} you can also pass &:method for the same effect

##### JS

Arrow functions function similarly to normal js functions, but have a shorter syntax: (<params>) => <block>.
Instead of a block, you may also specify a single expression, whose value will be returned. 
The parentheses are optional if there is a single param

#### IIFE

An immediately invoked function expression (IIFE) uses function scoping to create a fake block scope.
IIFEs were used for the same reasons as block scope is used generally, and preventing hoisting.
IIFEs generally use anonymous functions.
in JS IIFEs need to force an expression to be able to immediately invoke it (since a declaration cannot be immediately invoked)
The most common way to force functions to be expressions is via surrounding them in (), but other ways are possible.
With the introduction ES6 let and const, IIFEs have become mostly irrelevant.



#### common higher-order functions

There are many built-in higher order functions, generally as methods on data structure types.
since higher-order functions must take first-class functions as arguments, in languages that only have a special type of anonymous function as a first-class function, a higher-order function must take these.


language|higher-order functions are called on
JS|Arrays
Rust|Iterators


language|higher-order function recieves arguments
JS|value, index wholeArray


In JS, any higher-order function can take a thisArg, which is then the final argument. This argument will be what the passed fucntion recieves as this.

##### map

In many programming languages, map is the name of a higher-order function that applies a given function to each element of a collection, e.g. a list, returning a list of results in the same order. 
thing.map(func)|Java|JS|Ruby|Rust
map(func, iterator)|Perl (is list not iterator though)|Python
Select(func)|C#
no map function|sh|SCSS/Sass

Thing map is called on
arrays (or ggf. other iterables), not iterators|JS|Ruby|C#
iterators, not arrays|Rust
streams (whatever that is, but not the same as an iterator)|Java
globally|Perl|Python

###### flatmap

A flatmap function is a map function which may return an array and which flattens all elements of the array into the resulting thing.
effectively, flatmap is merely map with flat called on the array returned.
Most languages that have map function have a flatmap (flatMap) version of it, except for Python,. C# calls it SelectMany. Perls ordinary map is actually a flatmap, so really perl doesn't have a map.

##### sort

Sort is a higher-order function that takes a function which itself takes two arguments. Depending on the language, return values are handled differently.
JS function must return value smaller 0 if the first argument is to be first, larger 0 if the second argument is to be first, and 0 if it should not reorder.
The sort function passed must be deterministic.
In many languages, sort sorts with a predefined sorting algorithm if no sorting function is provided
In some languages sort does not take a sorting function, instead only using the predefined sorting algorithm, in those languages sort is not a higher-order function.

sorted(foo)|Python (takes an iterable)
foo.sort()|JS (takes an optional sort function, only Arrays)

##### filter

Filter in a narrow sense is a higher-order function that processes a data structure to produce a new data structure containing exactly those elements which the passed function returns true.
filter()|JS|Rust

##### reduce

The reduce function/method takes a function known as the reducer function
The reducer function recieves the return value of the last execution of the reducer function, and the current element of the collection. 
The reducer function return a single value.
In effect, the reducer function applies an operation to the current element, and the accumulated result of all other elements.
Many languages allow specifying a 'previous result' element for the first time the reducer function runs, as there will not be one.
js has the variant reduceRight that starts from the end
reduce()|JS|Ruby|Python

##### some/every/

some is a higher order-function that takes a function and returns true if the passed function returns true even once.
every is a higher order-function that takes a function and returns true if the passed function returns true for all elements.
JS

python has the functions any(iterable) and all(iterable), that merely return the result of calling bool() on each item, not taking any higher-order function

##### find

find is a higher-order function that takes a function and returns the first element for which the passed function returns true. findIndex instead returns the index.
find()|JS|Ruby
findIndex()|JS
find_index()|Ruby



### Arguments

How are parameters and arguments are often used synonymously, although they are more properly not synonyms
for a callable unit,  ⟮c1;parameters⟯ are the values you specify the function will be passed, most commonly in its signature.
for a calllable unit, arguments are the values/variables you actually pass.
When passing things, using a car metaphor, you can think of the ⟮c1;parameter⟯ as a ⟮c2;parking space⟯ and the ⟮c1;argument⟯ as an ⟮c2;automobile⟯
function foo(a, b){...
foo(12, "whistles") 
a, b are parameters, 12, "whistles" are arguments

most languages require the possible parameters defined in a callable unit definition to be wrapped in parantheses.
sh doesn't allow specifying parameters at all
most languages require the arguments to a function call to be wrapped in parentheses.
sh does not wrap arguments at all
most languages separate both the parameteres and arguments with commas.
sh separates arguments with space

Exceptions:
1 arg doesn't need parens|lua
always optional|ruby|perl
never|sh

refer to all passed arguments as an array
$@|(ba)sh
arguments|JS (not arrow functions)

In sh, instead of parameters having names, you refer to them positionally via $0...$9. 
$# gets the amount of arguments passed. # $ for sytax normalization for the md document

#### Positional and named

A positional argument is one where the language knows which parameter to assign it to based on its position in the argument list.
A named argument is one where the language knows which parameter to assign it to because it directly refers to the name of the parameter.
Named arguments usually use normal assignment syntax

named parameters|Python|JS|SCSS/Sass @mixin, @function
positional parameters|pretty much all languages

Move remove the first positional argument and shift all arguments one to the left
shift|Perl|sh

#### Default parameters

A default parameter is one which will take on a default value if no argument for it is specified in the call.
In general, default parameters will also take on the default value if the argument passed is the language's null type. 
In JS, the default parameter will take on the default value if undefined is passed as an argument, but not if null is passed.
the general syntax is `paramname = defaultval` (within the parameter list)
Python, JS, SCSS/Sass @mixin, @function have default parameters TODO Check other languages

#### Optional

In most languages, callable units must be recieve the exact amount of arguments specified as parameters, unless things like the splat operator or default parameters are used.
JS does not require the same number of arguments as parameters, it will assign unpassed parameters `undefined`, and put all arguments into the array-like `arguments`, allowing for retrieval of extra arguments.
TS moves JS in line with other programming languages, requiring arguments for parameters by default, and only accepting the not-passing of arguments if the parameter is optional.
in TS, optional parameters and optional fields are marked with a ? after the name, which changes their type to be whatever | undefined

#### evaluation strategy

An evaluation strategy is a set of rules for evaluating expressions.
Evaluation is equivalent to reduction in math.
The concern most of interest within the evaluation strategy is the parameter-passing strategy.
The fundamental parameter passing strategy distinction is between strict/eager evaluation/applicative order and non-strict/lazy evaluation/normal order.
The parameter passing strategy may be the same for all constructs in a language, there may be keywords or other constructs to indicate the parameter passing strategy, or the strategy may differ by context/value.
Different implementations of parameter-passing strategies are often called call by x or pass by x.

Arguments are generally bound to parameters. 

A function is strict if it evaluates to ⊥ if one of its arguments evaluates to ⊥
= A function is strict if it fails to evaluate/terminate if one of its arguments also fails to evaluate/terminate.
Strict evaluation is evaluation that guarantees a function is stict.
Applicative order makes sure a function is strict by evaluating its arguments before the function is applied.
A function is non-strict if does not necessarily evaluate to ⊥ if one of its arguments evaluates to ⊥
A function is non-strict if it does not necessarily fail to evaluate/terminate if one of its arguments also fails to evaluate/terminate.
Non-strict evaluation is evaluation that does not guarantee that a function is strict
Normal order implements non-strictness by evaluating its arguments only once they are used within the function.
In math, strict reduction proceeds from the inside out, so that hitting a bottom type will always be encountered.
In math, non-strict reduction proceeds from the outside in, so that something containing a bottom type may have already been eliminated by outer reductions.
Applicative order is a rough synonym to eager evaluation.
Normal order is a rough synonym to lazy evaluation

Call-by name implemens normal order by substituting the arguments of a function into the function body.
Call-by-need is a memoized version of call-by-name.

###### extracurricular binding

JS's bind() method has the potential to change the idea that arguments passed to a function call are bound to parameters.
JS's bind() is called on a function.
JS's bind() method binds the first argument that it is passed to the this of the function, and any following arguments to the parameters of the function it was called on.

###### applicative order

call/pass-by-value/-reference/sharing are all forms of strict evaluation.

call/pass-by-value|pass the value of the expression/variable (= copying)|changes to passed variable will be lost if not returned
call/pass-by-reference|pass the reference of variable (i.e. the loc in memory)|changes to passed variable (incl reassignments) will be preserved even if not returned
call/pass-by-sharing/object/object-reference|pass by value, but only the object reference for objects|changes to passed variables contents will be preserved even if not returned if object, reassignments will not.

Most popular languages with objects that are said to be pass-by-value are actually pass-by-sharing.
In purely functional languages, cb/pb value & reference are the same.
In purely functional languages, everything is immutable, so while the semantics are similar to pb value fron the outside, inside actually only references are passed (since it's cheaper), thus it is actually pb reference
Call by sharing is a term that is kinda rarely used.
In call-by-sharing

sharing|lua|JS|Java

moving seems like copying b/c you can't mess with it after, but in fact ofc only the reference changes hand.

###### non-strict binding

### Asynchronous callable units

Asynchrony, in computer programming, refers to the occurrence of events independent of the main program flow and ways to deal with such events.  

A process that is blocked is one that is waiting for some event, such as a resource becoming available or the completion of an I/O operation.
A blocked process cannot do anything in the meantime.
Asynchrony is a common way to deal with blocking.

A promise is a proxy for a value that will eventually become available.
In JS, a promise is an object
You react to promises by calling the then() method on them.
In JS, something you can call then() on is called a thenable.
in JS, most interfaces for promises work on any thenables.
A promise can have the states ⟮c1;pending⟯, ⟮c2;fulfilled⟯, or ⟮c3;rejected⟯.
A promise is called ⟮c1;settled⟯ if it is either ⟮c2;fulfilled⟯, or ⟮c3;rejected⟯.
Ergo a promise is either settled or pending.
We may return a rejected promise manually, additonally, if an error occurs in our async function, it will reject automatically.
Once a promise has settled, the attached thens will run as soon as possible / awaits will resolve.
If a promise is settled, and we then attach a then()/catch()/finally(), it will run immediately
While a promise is pending, thens will not yet run / awaits will not yet resolve.
A promise may have the fates resolved, unresolved.
Whether a promise is resolved depends on whether we can still resolve it: If we can still resolve a promise, it is unresolved, otherwise resolved.
A promise being resolved means that its outcome is already determined, even if we may not yet have the outcome.
Promises with the states fulfilled or rejected also have the fate resolved.
A promise with the state pending is resolved if it has been resolved to a itself pending Promise, else a promise that is pending is also unresovled.
//generally true, not jus js

In many languages, the async keyword marks the callable unit as asynchronous and allows it to call asynchronous functions.
await is a keyword/function available in many programming languages that calls an asynchronous function and then returns the value the function returns once it does.
In JS (and other languages w/ promises), await takes a promise (and is the rough equivalent of calling then() on it)
to handle errors resulting from await, use try/catch as normal.

In JS, then() takes two callbacks, one to run in case fullfilment and one to run in case rejection.
then(), catch() and finally() themselves return thenables, which allow them to be chained.
is the thing the last promise returned is what then(), catch(), and finally() get as an argument. What they get depends on if the callback running is one for rejection or one for fulfillment
In JS, catch() is a version of then() with only the callback to run in case of rejection, finally() is a version whose callback will run no matter if rejeciton or fulfillment
In JS, async functions always return promises.

you can create promises in a number of ways
create a promise that is already rejected: Promise.reject(reason)
create a promise that is already resolved: Promise.resolve(value)
If it is passed a non-promise, it will immediately be fulfilled w/ that value, if it is passed a promise it will be resolved to that promise

creating a new promise (that is not auto-rejected/resolve)is done via the promise constructor.
The promise constructor takes a callback known as the executor function.
the executor function itself takes the arguments resolutionFunc, rejectionFunc.
We do not implement resolutionFunc and rejectionFunc ourselves, the executor function will get them passed in when necessary.
The only thing we do with the executor functions argumetns resolutionFunc and rejectionFunc is call them when we want to resolve/reject.
As with the Promise.resolve and .reject, you pass the rejectionFunc the reason for rejecting, and the resolutionFunc the thing you want to fulfill with, or another promise

JS has a few methods for acting on multiple promises at once:
Promise.race() takes n promises and runs the attached callback ⁑once⁑ the first promise resolves.
Promise.all()/allResolved() runs the attached callback once all passed promises are resolved. The attached callback will recieve all returned results as an array.
⟮c1;Promise.allSettled()⟯ is like ⟮c1;Promise.all()⟯, but the ⟮c2;former⟯ will ⟮c3;continue even if one rejects⟯, the ⟮c2;latter⟯ will ⟮c3;not⟯

Pretty much all operations of the fs module in node have an ⟮c+;async⟯ and a ⟮c+;synchronous⟯ method, where if the ⟮c+;async⟯ method is called <code>⟮c+;foo⟯</code> the ⟮c+;synchronous⟯ method is called <code>⟮c+;fooSync⟯</code>
In node, asynchrony is by default implemented via callbacks.
In node, any asynchronous operation that could fail takes a error callback.
In node, any asynchronous operation that could return something useful takes a success callback.
in node, most functions are still designed for callbacks, however you can use util.promisify().
util.promisif()y takes a function following with a error-first callback as the last argument, and returns a version that returns promises.

Promisifying is making someting return a promise which wouldn't normally.

#### asynchronous techniques

hooks and event handlers are asynchronous programming techniqyes.

##### hooks

A hook is an action that is defined on a thing and is called when the thing is in a certain state, e.g. before a function call.

##### Events

Technically, an event listener watches for an event, at which point it calls the event handler to deal with it.
In casual use, event listener and event handler are synonyms.

### misc

Memoization is the form of caching that caches the return value of a deterministic callable unit

#### recursion

recursion ≈ self-inclusion

## Records

A record is a collection of fields, possibly of different data types, typically in a fixed number and sequence. 
A type that defines a record is a record type.
Most programming languages allow creation of instances of record types.

### Principles

Encapsulation refers to grouping together related things somehow, e.g. within records.
In OOP, encapsulation is often used to mean bundling the data and the methods that operate on it in one construct
Information hiding is hiding the internals of a thing from the  outside.

### Class and instance entities

A class x is a x operates on/is defined on a class rather than an instance.
An instance x operates on/is defined on an instance of a record.
A class function may also be known as an associated function.
Class x ≈ static x
generally, one mainly talks of class, instance methods, which operate on classes/instances, and class, instance variables
class variables + instance variables = fields
Members are generally all methods and fields of a record, no matter if class or instance.
ergo: members = member fields + member bariables
A piece of data on a record is called a field

In rust, a class method/associated function is called by using the :: operator

static|Java|C#|JS
does not take self as argument|Rust

### self-reference

self/this are keywords to reference the current record/other thing

#### self/this in different languages

self|Python|Ruby|Rust
this|C#|Java|JS

#### typeof self

In rust, `Self` is the type of the current record.
In rust, `self` has the type `Self` (or `&Self` if borrowed)

#### self/this binding

Many languages bind self/this automatically in methods, all others typically bind self/this explicitly by taking self/this as their first arguments.
In JS, any function binds this, even those that are not methods. Outside of a function, this refers to the global object.
to refer to the this representing the global object even within places that bind this to something else, use `globalThis`.

##### self and methods/assocated functions

In certain languages (Rust, Python), methods must take self as the first argument, else they are class methods/associated functions.
In rust, taking `self` takes ownership and thus invalidates previous references, ergo one generally wants to take &self or &mut self.
In rust, one uses :: instead of . to call associated functions

### Methods

A method is a callable unit that is a member of a record.
To make an object B do something, an object A must send a message.
in OOP, a method call is the way to send of message: The originator object is implicit, the target is specified manually, the method called is the message, and the arguments are well the arguments.
Ergo, in OOP objects generally use message passing to communicate.
In JS, methods are specified without using `function`, merely name and param list.
There is an older version of specifying methods in JS that is <name>: <anonymous-function>, this only works for object literals.

#### Getters and setters

Also called accessors and getters.
A getter returns a field of a record.
A setter changes a field of a record.
Setters are often used to perfrom some sort of validation before changing the field of a record.
Getters and setters may help enforcing information hiding.

Ruby syntax:
def name=(value)...|setter

JS & TS:
get foo()
set foo()
only within a class

You can only interact w/ ruby instance variables via getters and setters, trying to use it without those will give you a NoMethodError

### passive data structure

AKA plain old data structure (PDS)
A passive data structure is a data structure, especially a record with fields but no other object-oriented features.

### Structs

Struct is not an incredibly well-defined term, but is generally a record with the possibility for methods, but not the whole inheritance etc. stuff of classes.
In rust, struct declarations use the keyword struct.
Both struct delcarations and initializations in rust use a very assoc-array like syntax.
struct User { username: String, ...}
Tuple structs are either 'tuples with a name which can be instantiated' or 'structs with anonymous but ordered fields'.
if a variable and a struct field have the same name, you can write `foo,` instead of `foo: foo,`

### impl

Rust allows implementing methods or associated functions for structs, tagged unions (enums) and traits via the impl keyword.
when used for implementing things on structs/enums/traits, the construct used is called an impl block
the syntax for impl blocks for structs and enums is `impl <name> <block>`
the syntax for impl blocks implementing traits for structs is `impl <traitname> for <thingname> <block>`
Any thing may have as many impl blocks as you like.
For any impl block, we may indicate that we only want to implement it for something whose generics either are of a certain type or implement certain traits.
When we implement something, we can only rely on other things of the thing we're implementing existing, plus whatever trait bounds we've established.
we may `impl` a Trait without any `for` clause to provide a default implementation.
`impl <trait-list>` does not start an impl block and instead refers to a type that implements trait-list, with the advantage that this syntax can be used outside of a type parameter.

### fields 

In JS, fields themselves have properties (such as enumerable).
In JS, enumerable fields are those that will be enumerated over in a `for-in` loop.
generally, properties added 'normally' are also enumerable
<object>.propertyIsEnumerable(<name>)
properties that are not inherited (that is, they are there not because of the prototype chain, they of course then be inherited by other things) are called own properties
<object>.hasOwnProperty(<name>) 
The ⟮c+;Object⟯.⟮c+;assign⟯⟮c+;(foo, bar)⟯ method ⟮c+;copies⟯ all ⟮c+;enumerable⟯ ⟮c+;own⟯ ⟮c+;properties⟯ from ⟮c+;one or more source objects⟯ to ⟮c+;a target object.⟯ 

### Classes & objects 

An object in object-oriented language is essentially a record that contains procedures specialized to handle that record; and object types are an elaboration of record types.

Keyword to declare a class is done by the keyword `class` in pretty much all programming languages which have it.

A singleton (AKA the singleton pattern) is a class that can only have a single instance of that class. It is useful when you don't need multiple instances of a thing (the null object, a logger), or to coordinate states.

method in lua function object:method(...)

in languages with type annotation, the type annotation of an object is generally its class (e.g. MyClass myObject = new myObject();)


#### Methods ruby

In ruby, methods that will return a boolean are marked by a ?
In ruby, methods that do something destructive are marked by a !

    <tr><th colspan="2">In ⟮c5;documentation⟯, these methods are referenced...|
⟮c1;class methods⟯|⟮c2;.method or :​:method⟯
⟮c3;instance methods⟯|⟮c4;#method⟯



#### pure OO

A pure object oriented language is one where everything is treated as an object.
There is much discussion on what it means to be 'treated as an object' for pure OO languages, but most commonly, it is at least:
1) Everything you operate on is a first-class Object
2) The only thing you can do with an object is call a method on it.
Therefore, 
1) Methods may only return other objects.
2) Operators (if they exist) are syntactic sugar for methods.
It is a matter of debate which languages are sufficiently pure OO to qualify: 
Ruby, Python, and JS allow methods to be called on pretty much anything, even primitives, since all primitves are boxed.
Only Ruby (of the languages I know) is quite pure enough to be called a pure object oriented language, I think

#### Inheritance

Superclass aka base class
subclass aka derived class
In most programming languages, you refer to your superclass=base class with the keyword `super`.
In most programming languages, you specify a subclass/superclass relationship like so: Subclass extends Superclass
In ruby, you specify a subclass/superclass relationship like so: Subclass < Superclass
In C#/Java, making a class final disallows a subclass from inheriting from it.
In C#/Java, making a method/static function final disallows a subclass from overriding it it.
Most languages only support single inheritance, some languages (among those I know Perl and Python) also allow multiple inheritance

#### abstract & static classes 

Abstract classes are generally declared with the abstract keyword. 
Within abstract classes, members are also declared with the abstract keyword.
Both abstract and static classes/members are not instantiable.
Abstract classes/members are designed mainly to be inherited from.
Since abstract classes/members cannot be instantiated, they must be overriden to be used.
JS does not support abstact things, however you can simulate it by using the @abstract/@virtual JSDoc tag.

#### Constructors/object creation

Creating a new object via a constructor is done by the new operator in most languages, but not in Ruby or Python.
TS calles things that can be used to create new things `newable`.

A constructor is generally a callable unit and thus called with ()
Rust doesn't use any operator to create new Structs. In general, you use literals, some type provide a new() associated function.
In C#, Java, the constructor has the same name as the class.
In Ruby, the constructor is defined by the initialize function within the class (class SomeClass\n  def initialize(...), and called by calling the new() method on the class (SomeClass.new())
In JS, the constructor is named constructor
Many languages allow us to declare many different constructors with different arguments.
Most languages provide a default constructor if you don't provide one, which does nothing besides create the object.
In JS, you may not use arrow functions as constructors

A factory function is any callable unit which is not a class/constructor that returns a new object.
Ergo, factory functions create things without using the new keyword.
in Rust, many things are created by a factory function `new()`, which is an associated function of the struct.

#### immutable objects

an immutable object is an object which cannot be changed once it's been created.
in JS, Object.freeze(obj) makes the object an immutable object.
In TS, Readonly <T> constructs a version of T whose properties are all set to readonly, making it a immutable object.

#### Access modifier

Access modifiers (or access specifiers) are keywords in object-oriented languages that set the accessibility of classes, methods, and other members. 

default accessibility|language
default (= package)|Java
public|Python, JS
private|Rust
Most language with any kind of access modifiers have at least a public private distinction
public (most programming languages), pub (Rust)|any code
private|code within the class
Most languages with a public/private access modifier distinciton will use the public/private keyword to mark the one that is not the default anyway
JS is an exception, it marks private members with #

protected|same class and subclasses|Java
package|within the same package|Java
in java, the package access modifier is the default
JSDoc allows the simulating of the four access modifiers that Java has by using @access <access-modifier> or @<access-modifier>

A ⟮c1;private item⟯ can be accessed by ⟮c2;its immediate parent module⟯ and ⟮c3;all its child modules⟯
A public item can be accessed as a private item can, and additionally also through a chain through its ancestors.
In rust, each field of a struct has its own access modifier, which must be set to public if desired.

#### Interfaces

mixins are pretty similar concepts.
In OOP an interface is a set of methods that anything that implements that interface must also implement.
Interfaces in programming standartize behavior
If a given programming language has syntax for them, generally keyword interface.
Indicating that one follows an interface is generally done with the implements keyword.
Something conforming to an interface is generally said to implememnt it.
If something implements an interface, it generally must implement all methods of that interface.
In the past, Java did not allow variables in interfaces. as of today, they are allowed, but subject to heavy restrictions.
In interfaces in Java/C#, you most commonly merely specify method stubs. (in the past this is the only thing you could do, this is no longer true)
Method stubs are method signatures without the implementation, in Java/C#, they are followed by a ;.
In most languages, a record may implement multiple interfaces/traits.

##### Traits

Traits in Rust are broadly similar to intefaces in other programming languages.
Traits in Rust can be implemented for types you did not define.
However, the trait ∨ the thing its implemented on must be local to the crate
Traits allow for blanket implementations, that is implementing a trait for anything that implements one or more other traits.
impl<T> ToString for T where
    T: Display + ?Sized,
{ ... }
In rust, the keyword to declare a trait is `trait`
`trait <name> <block>` 
blocks of trait declarations contain method signatures.
In rust, deriving a trait is automaticallly generating trait implementations for a given thing.
In rust, derive is implemented via an annotation that takes a list of Traits.

In rust, the orphan rule says that either a trait or the thing it is being implemented on must be local to our crate.
In rust, the reason for the orphan rule is that otherwise when using multiple crates, they may end up trying to implement the same trait on the same type in different ways, creating conflicts (and dependency hell)

In rust, traits may exist in a supertrait/subtrait relationship.
A supertrait S of trait T means that any type implementing T must also implement S.
A subtrait S of trait T means that any type implementing S is also guaranteed to implement T.

syntax for declaring a trait with a supertrait: `trait <subtrait> : <trait-bound>`

#### OOP

C#, Java

#### is X an object of Y

someobj instanceof class|JS

#### Duplication/Replication

A deep copy is a copy of a data structure where things referenced in the original data structure are also copied.
A shallow copy is a copy of a data structure where references in the original data structure are merely copied, and still refer to the same thing.
Deep copying is recursive and more computationally expensive.

shallow copy
copy (module copy).copy(foo)|Python
foo.copy()|Python (only collections)|Rust

deep copy
copy (module copy).deepcopy(foo)|Python
foo.clone()|Rust

#### toString()

Most languages with objects have a tostring method to convert these to strings for debugging purposes.
It can often be useful to overwrite the default tostring implementation for more useful custom debugging.
tostring methods are often called implicitly during coercion.

<thing>.toString()|Java|JS
<thing>.ToString()|C#
<thing>.to_string()|Rust
<thing>.__str__(), called via str(<thing>)|Python
<thing>.to_s() or .to_str()|Ruby

The difference between Ruby's to_s() and to_str() is that to_s() is implemented in the (almost) top type (Object), and is called for some coercions only, while to_str() indicates that we want to treat the thing as a string in most cases, and thus allows for coercion in more circumstances.

to_string() is part of the ToString trait.

#### Boxing

A box is a minimal object wrapper around another type.
The types that are most commonly boxed are primitives, sometimes boxing is restricted to this narrower definition.
putting values into a box is called boxing, the opposite unboxing
A wrapper is any entity that encapsulates/wraps around another thing.
Implementation-wise, it may be that the whole box is stored on the heap as an object would be, and we only have a pointer to the box, or as Rust seems to do it the Box may merely contain a pointer to whatever data, which is moved to the heap. (though I wonder if these are different)
Memory-wise, since boxes are objects, boxed data will be stored on the heap.
Boxing primitives allows us to interact with them using a similar interface as other objects; this enables the Everything you operate on is a first-class Object constraint of pure OO, consequently most primitives are boxed in languages aspiring to pure OO such as Python, JS, Ruby...
Autoboxing is the conversion of primitves to boxed types when relevant.
Since boxed data will be stored on the heap, it is not necessary for it to have a constant size, thus boxed data allows more flexibility.

Rust's construct for boxing is Box<T>.

## Pragmas

In computer programming, a directive or pragma (from "pragmatic") is a language construct that specifies how a compiler (or other translator) should process its input
Perls pragmas have the syntax use &lt;name&gt;;
Perls pragma use warnings; causes the perl program to display warnings in certain circumstances.

### Strict mode

Both perl and JS have a strict mode pragma.
Strict mode pragmas cause programs to fail in certain cases.
Start strict mode in JS: "use strict";
in JS, non-strict mode code is called sloppy mode
In JS, modules and classes are strict by default
In JS, strict mode applies to the whole file if it's the first statement if the file, and to the whole function if it's the first statement in the function

Strict mode in JS:
- reserves certain keywords (for future proofing)

### shebangs

An interpreter directive is a type of pragma that specifies which interpreter to use for a thing.
On a unix-like OS, if a script starts with the shebang, followed by a path, this is an interpreter directive, and specifies with which binary to execute the script.
The shebang consists of the characters #!.

### attributes

Attributes are pragmas (mostly) for rust.
attribute begins|applies to
#!|whole crate
#|next item

attributes have four forms for taking arguments (or none)
ø|no arg
= "<value>"|one arg
\(<value>{, <value>}\)|one or more unnamed args
\(<key> = "<value>"{, <key> = "<value>"}\)|one or more named args

rust-attribute ::= #[!]\[<rust-attribute-name><rust-attribute-arguments>\]
rust-attribute-arguments ::= ø|(= "<value>")|(\(<value>{, <value>}\))|\(<key> = "<value>"{, <key> = "<value>"}\)

## Formatting

Official style guide/best practices
PEP 8|Python

## modules

The main purpose of modules is encapsulation.
A module is as self-contained set of code.
Most commonly, a module is defined by each code file.
In Rust, modules are instead defined manually via mod <name> { ... }, or via `mod <filename>`
Packages and modules are sometimes synonyms.
conta
In python, a package is a collection of modules (and perhaps other packages).
In python, each .py file is a module.
A package must contain a __init__.py file

If you want to import/export multiple members, most languages have the syntax {member1 [as name1], member2 [as name2], ...}
In some languages, when you're importin multiple members and want to bring the module itself into scope, you can include the keyword for self-reference (this or self) in the list of things to im-/export.
Import/export anything uses * in most languages
in JS, you can only import/export within modules.

### prelude

Most languages have a number of things that are automatically imported. Rust (and haskell) calls this prelude.

### module systems

#### Rust

Rust allows nesting of modules in a module tree.
In rust, the root node of the module tree is `crate`, sometimes called the crate root.
The crate root serves as the entry point for the rust compiler.
rust allows for both `use`ing/referring absolute and relative paths for the module tree, where absolute paths start at the crate root, and relative paths start at the current module.
Rust's module nesting is defined either directly by nesting `mod <name> {...}`s or by a combination of file hierarch and `mod <filename>`
calling `mod <filename>` without a block argument integrates an existing rust file as a child of the module we're currently in in the module tree, however the file structure must also reflect this.

Rust also allows having multiple crates with independent module trees in the same package.
In rust, there are two types of crates, binary and library.
A package can contain 0-1 library crates and 0-∞ binary crates.
the crate root for binary crates is called main.rs.
the crate root for library crates is called lib.rs

#### JS

##### CommonJS

CommonJS is ⟮c1;a module ecosystem⟯ mainly used by node

let/var/const <name> = require(<path>)

##### ES Modules

To contrast with module systems such as CommonJS, the official implementation of modules in JS are known as ES Modules.
In JS, ES Module import/export statements can only be used within a module.
Modules are declared in script tags by adding type="module".

### importing

Import statements tell whatever's executing the program to act as if the specified entities were part of the file, potentially renaming them.
In most languages, you can only import things that were first exported.
In most languages, import statements must be in the beginning of the file.
In most languages, you may only export top-level items.
Import statements have the general syntax

import <members> [as <name>] from <path>
in JS you can leave out `<members> from` if you only want the side effects

Python instead has the order from <path> import <members> [as <name>]

In vanilla CSS, you can import other stylesheets via the non-nested at rule @import.
@import syntax: @import <path> (<media-query>|<feature-query>);
For CSS, the <path> may be an <url> or a <string>

JS supports an import() function that allows dynamic runtime imports.
import() returns a promise.

Rust uses `use` instead of import.

#### SCSS/Sass 

Three keywords: @use, @import, @forward (@include is not an import statement!)
Syntax alwas keyword <path> [as <name>]
@forward foo doesn't allow the current stylesheet bar to access the things in foo, but ⟮c1;allows anything @using bar to access them.⟯

#### latex

⟮c1;\input⟯ and ⟮c2;\include⟯ both ⟮c2;import latex code into the current file⟯. 
⟮c3;\input, \include⟯ are useful if ⟮c4;you want to split up you latex into multiple files⟯. 
both ⟮c5;\input⟯ and ⟮c5;\include⟯ take ⟮c6;a path of the file to import⟯. 
⟮c7;\include⟯ but not ⟮c7;\import⟯ ⟮c8;adds a \clearpage when importing⟯, and thus ⟮c9;can't be used in the preamble⟯ 
using ⟮c10;\include⟯ allows you to use ⟮c11;\includeonly⟯, which takes ⟮c12;an argument⟯ of ⟮c13;a list⟯ and will ⟮c14;only import the \includes listed within⟯, cutting down on ⟮c15;compile time⟯. 

### exporting

Exporting is selecting entities for potential import.
In most languages, exporting is required so they can then be imported.
General syntax: export <members> [as <name>] [from <path>]
re-exporting members is exporting members from a different (generally child) module.

JS allows one default export per module. The default export is the only thing that may be imported without curly braces, and can be renamed without `as`.
JS default exports are funtionality-wise not super useful, but be useful in indicating that it is the most important export / only relevant export.
In JS, non-default exports are known as normal/named exports.
In JS, using the from <path> component of exports allows for re-exporting.
JS re-exporting allows aggregating exports in a single file.

In rust, re-exporting works by making a `use` itself public.

#### default exports

## lifecycle

### Entry point

In computer programming, an entry point is a point in a program where the execution of a program begins, and where the program has access to command line arguments. 
The entry point of many programming languages is the main function:
public static void main(String[] args)|Java
main()|rust

## communication

To share data between entities, one can use message passing or shared memory.
Shared memory is having a fixed storage location which both entities can access to read/write the data.

### messages

Message passing is communicating between two things by sending messages.
A message consists of the source thing, the target thing, the message, and potentially the  arguments passed.
IPC is just message passing between two processes.

## Memory 

Memory allocation is setting aside memory for a purpose, e.g. to store entities of a programming language.
Memory deallocation is releasing previously allocated memory.

### The stack and the heap

The call stack is often only called the stack.
The call stack implements the stack ADT
The call stack is made up of stack frames.
The stack frame usually includes at least ⟮c1;the arguments⟯, the ⟮c2;return address⟯, and ⟮c3;local variables⟯.
When we call a callable unit, a new stack frame is pushed on the stack, and the stack pointer is updated.
When we return from a callable unit, the stack frame at the top of the stack is popped, and the stack pointer is updated.
The stack frame at the top of the stack is the stack frame of the currently executing callable unit.
The stack pointer points at the most recently referenced location on the stack.
The memory address at which the stack starts out when it is size 0 is the stack origin.
If the stack has size 0, the stack pointer is (or better be :P) at the stack origin.
The stack may grow upwards = larger memory addresses or downwards = smaller memory addresses (however this needs to be fixed in advanced)
stack grows upwards|stack overflow|address > stack_origin_addr+ max_stack_size
stack grows upwards|stack underflow|address < stack_origin_addr
stack grows downwards|stack overflow|address < stack_origin_addr-max_stack_size
stack grows downwards|stack underflow|address > stack_origin_addr
Since each call to a callable unit adds a stack frame, infinite recursion causes a stack overflow (unless the compiler optimizes the recursion away)
The stack is significantly faster than the heap, since it's implementation is far simpler.
The heap can become fragmented.
The heap is managed much less strictly than the stack.

In general, there is one stack per thread and one heap per process (instance of a program)


### stack trace

A stack trace is a report of the active stack frames during the execution of a program.
Stack traces are often automatically printed in the case of unrecoverable errors
to show a stack trace on error in rust, set the env variable `RUST_BACKTRACE=1`

### static and dynamic as size

static types/statically sized types (!= static variables) have a size that can be known at compile time.
dynamic types/dynamically sized types have a size that cannot be known at compile time. 
One of the main cases for static arrays is that they are static(ally sized) types.
Only statically sized types can be stored on the stack (= in automatic variables).
Dynamically sized types are stored on the heap. 
To store dynamically sized types on the stack, one typically has a pointer.
Most record types are dynamically sized types.
In rust, statically sized types implement `Sized`, dynamically sized types implement `?Sized`
In rust, pointers to dynamically sized types are fat pointers.
In rust, the most common dynamically sized types are trait objects and slices.
Pointers to slices are fat pointers because they also store a length of the slice.
trait objects are fat pointers because they also store a virtual method table.

### static, automatic and dynamic variables

The lifetime of a variable is the time where it is in a valid state, which generally coincides with when it has memory.
The lifetime of a value is the time where it occupies a certain region of memory.
The lifetime of a variable cannot outlive the the lifetime of its value.

A static variable is allocated for the entire lifetime of the program.
Static variables fall outside of the clear stack heap distincition, as they are stored in a data segment.
A data segment is a part of the object file (file of object code = compiler output, see compilers) that contains static variables.
The read-only data segment is the part of the data segment (or an extra data segment) that contains read-only static variables (ergo static consonants)
the read-only data segment may be called rodata.

#### automatic and dynamic variables

The terms automatic and dynamic variables/memory allocation are mainly used in C-style languages.

An automatic variable is a variable that has its memory allocated and deallocated automatically when the program enters and leaves the variables scope.
Automatic variables have a lifetime of the variables scope.
In general, automatic variables genrally must be statically sized.
Any automatic variable can go out of scope.

Dynamic memory allocation creates lifetimes of your choosing: their memory is allocated and deallocated by you or a memory management system.
(dynamic variable isn't a real term, I've introduced it here for terminological parallelism)
Def: Automatic/static variables use automatic/static memory allocation.

Use-after-free is a vulnerability where memory is used after it has been deallocated.
Use-after-free can generally only occur to dynamically allocated memory.

#### lexical and nonlexical lifetimes

In lexical lifetimes, the lifetime of a value is until the end of its lexical scope
In non-lexical lifetimes, the lifetime of a value is until it is last used within its lexical scope.
In general, the difference between lexical and non-lexical lifetimes does not matter, however if the value is a reference Rust's borrow checker cares about if you're holding on to it. Hence, rust implements non-lexical lifetimes for references.

lifetime-annotation ::= '<name>
lifetime-annotations specify named lifetimes
You must specify all lifetimes you are gonna use as type parameters.
In rust, in theory all references used in callable units require a lifetime annotation, though in most cases it can be left out due to lifetime elision.
lifetime annotations cannot be elided in cases where the compiler cannot figure out how parameters and return value relate.
ergo, lifetimes cannot be elided if the function returns a reference, the function takes more than one reference as a input parameter, and the function is not a method.
Importantly, lifetime annotations beside 'static do not change lifetimes, merely indicate how lifetimes of references relate (specifically, "treat all these lifetimes as the lifetime of the shortest one")
Rust indicated static variables with a 'static lifetime annotation

### memory management

Memory management is managing the memory of an application.
One of the main jobs of memory management is memory allocation and deallocation.
Memory management may be manual = performed by the programmer or automatic = performed by the programming language automatically.
Dynamic memory allocation can be handled by manual memory management or by automatic memory management.
Automatic variables are handled by automatic memory management.
static variables are not subject to memory management.
Most higher-level programming languages have no manual memory management at all.

A destructor is a method which is envoked just before the memory of a thing is released.


#### types of data

Garbage data is data that cannot be used anymore (e.g. reference out of scope)
The opposite of garbage data is live data.
Outside of programming, garbage data is sometimes used for data that is unusable in some way (e.g. corrputed, garbled)

#### manual memory management

In C, dynamic memory allocation is done by manual memory allocation.
malloc() allocates the specified number of bytes
calloc() allocates the specified number of bytes, and sets them to 0
free() releases teh specified block of memory back to the system.

#### automatic memory management

The three most common types of automatic memory management are garbage collection, automatic reference counting, and RAII.

##### garbage collection

Garbage collection is a form of automatic memory management in which a garbage collector deallocates garbage memory.

##### reference counting

(manual) reference counting is a form of manual memory management
automatic reference counting is a form of automatic memory management
In reference counting, when no more references to a certain value exist, then it is destroyed
In reference counting, a value (most commonly an object) as some kind of field indicating how many references to it exists.
In manual reference counting, we call increment and decrement methods to indicate how many references there are.
In automatic reference counting, increment/decrement methods for refrences are called automatically. 
Circular set of references are called reference circles.
reference circles can allow things in refrence counting to never reach reference count 0 and thus be destroyed.

In rust, reference counting is implemented by Rc<T>.
Rc<T> allows multiple owners, where each call to clone() increases the reference count.
In rusts implementation of reference counting, dropping Rc<T> decreases the reference count.

##### RAII

RAII = resource acquisition is initialization
In RAII, memory for a value is allocated by its constructor and deallocated by its destructor.
In rust, the destructor for RAII is drop() of the Drop Trait.
In rust, when a variable goes out of scope, the value it owns is dropped.

## libraries


### web frameworks

A framework is a set of libraries where the framework itself has control by default, and only exposes an API.
A framework: Don't call us, we'll call you.
A web framework is a framework for use in web development.

#### commonalities

##### templating

⟮c8;a template engine/processor⟯ is something that ⟮c9;combines⟯ ⟮c10;a template⟯ and ⟮c11;data⟯ ⟮c9;into some kind of result⟯ 
⟮c12;templatees⟯ are written in ⟮c13;template languages⟯ 

####### Liquid


⟮c2;liquid⟯ is ⟮c1;a template language⟯) 
⟮c3;Liquid⟯ was develped from ⟮c7;Embedded Ruby Templates (ERB⟯) 
⟮c4;Liquid⟯ is ⟮c5;kinda similar to Ruby⟯ due to ⟮c6;it being developed from Embedded Ruby Templates (ERB⟯) 

⟮c1;Liquid⟯ ⟮c2;tags⟯ look like this ⟮c3;{% ... %⟯}. 
Liquid ⟮c4;tags⟯ ⟮c5;surround⟯ ⟮c6;logic/control flow⟯. 
In liquid, ⟮c7;outputting⟯ is generally done ⟮c8;within double curly braces {{ ... ⟯}} 
```
{% if user %} 
Hello {{ user.name }}! 
{% endif %}
``` 
⟮c9;adding a -⟯ ⟮c10;to {{ or {%⟯ ⟮h9,10;like {{-, {%-⟯ ⟮c11;strips whitespace from the relevant side⟯ 


⟮c9;Liquids⟯ ⟮c10;loops⟯ are odd in that the⟮c11;y accept a number of additional parameters⟯ ⟮c12;after the main condition⟯, in the format ⟮c13;key:value⟯ and separated by ⟮c14;spaces⟯ 


span:2;Liquid loop parameters
⟮c1;start where the previous loop of the same iterator left off⟯|⟮c2;offset:continue⟯
⟮c3;start at the offset/index n⟯|⟮c4;offset:n⟯
⟮c6;iterate through the array in reverse⟯|⟮c5;reversed⟯
⟮c7;only do n iterations⟯|⟮c8;limit:n⟯


```
{% for item in array foo:bar foo2:bar2 %}
  {{ item }}
{% endfor %}
```


⟮c1;cycle⟯ ⟮c2;takes n arguments⟯ and ⟮c3;prints the next one (from the last time this  was called⟯). 


```
{% cycle item1, item2... %}
``` 


⟮c4;Cycle⟯ can be used to apply classes for ⟮c5;even/odd elements⟯ or ⟮c6;to any nth elements⟯. 
⟮c7;Without the cycle group paramter⟯, ⟮c8;all cycles in the document⟯ ⟮c9;cycle the same thing⟯ 
⟮c10;if you want to cycle multiple things⟯ in ⟮c11;the same document⟯, you need to ⟮c12;use cycle group paramters⟯. 
The syntax for the cycle ⟮c13;group parameter⟯ is ` ⟮c14;"name":⟯`. 
```
{% cycle "name": item1, item2... %}
```

⟮c1;{% liquid ... %}⟯|⟮c2;write liquid logic in a single block⟯
⟮c3;{% raw %} ... {% endraw %}⟯|⟮c4;disable tag processing (different from comments in that non-liquid stuff will be rendered⟯)
⟮c5;{% render "foo" %}⟯|⟮c6;render another template foo⟯
⟮c7;{% tablerow foo in bar ...⟯|⟮c8;generate html tables⟯


```
{% liquid
case section.blocks.size
when 1
  assign column_size = ''
when 2
  assign column_size = 'one-half'
when 3
  assign column_size = 'one-third'
else
  assign column_size = 'one-quarter'
endcase %}
```

There are ⟮c1;two different namespaces⟯ for ⟮c2;variables⟯ in ⟮c3;liquid⟯: one for ⟮c4;assign/capture⟯ and one for ⟮c5;increment/decrement⟯ 
⟮c6;Normal variable assignment⟯ uses the ⟮c7;assign⟯ keyword 
```
{% assign my_variable = false %}
```
⟮c8;{% increment / decrement foo %⟯} ⟮c9;increments/decrements⟯ a variable foo ⟮c10;increment⟯ ⟮c12;variables⟯ start at ⟮c11;0⟯ and ⟮c10;decrement⟯ ⟮c12;variables⟯ starts at ⟮c11;-1⟯ 
⟮c13;everything within⟯ ⟮c14;a capture block⟯ is ⟮c15;assigned to the specified variable⟯ 
⟮c17;capture⟯ captures ⟮c16;a whole string⟯ into ⟮c18;a new variable⟯, allowing ⟮c19;string interpolation⟯ or ⟮c20;other complex logic⟯ to generate the variable 
```
{% capture my_variable %}あっ！いやだ！{{page.author}}によってバリアブルに入れられてしまいました。！{% endcapture %}
``` 

#### front-end frameworks

##### types of web pages and their generation

Fundamentally, a ⟮c16;web page⟯ may either be ⟮c17;static⟯ or ⟮c17;dynamic⟯. 
A ⟮c18;static⟯ web page is ⟮c19;delivered to the web browser⟯ ⟮c20;exactly as stored on the web server⟯. 
A ⟮c21;dynamic⟯ web page is ⟮c22;generated in some way⟯. 
⟮c23;Static generation⟯ merely creates ⟮c24;static web pages⟯. However, since ⟮c25;they are often generated in a manner similar to dynamic web page⟯, ⟮c23;static generation⟯ is often seen as ⟮c26;something inbetween dynamic and static web pages⟯. 
A ⟮c27;dynamic web page⟯ may be generated ⟮c28;client-side⟯ or ⟮c28;server-side⟯. 
A ⟮c29;dynamic webpage⟯ ⟮c30;generated client-side/server-side⟯ is said to use ⟮c31;client-side/server-side rendering⟯. 


⟮c4;Client-side rendering⟯ ⟮(c:34;s4;CSR⟯) generally involves only having ⟮c5;a minimal HTML page⟯ and ⟮c5;a JS bundle⟯, which then ⟮c6;handles everything elsee.⟯ 
The pages ⟮c32;CSR⟯ produces are generally called ⟮c33;single-page applications⟯. 
⟮c35;Server-side rendering⟯ ⟮(c:36;s35;SSR⟯) has ⟮c37;a server generate the web page⟯, generally using ⟮c38;a server-side programming language (in the past most commmonly PHP⟯), which is then ⟮c39;served to the user fully baked⟯. 
⟮c40;CSR⟯ only ⟮c41;needs to communicate w/ the server⟯ if ⟮c42;new data is needed⟯. 
Whenever ⟮c43;the user navigates to a different page⟯, ⟮c44;CSR⟯ ⟮c45;can usually handle it internally⟯, while ⟮c44;SSR⟯ ⟮c45;needs to make a new request for a new page⟯. 
⟮c1;Client-side rendering⟯ has ⟮c3;longer⟯ ⟮c2;initial load times⟯ and ⟮c3;shorter⟯ ⟮c2;subsequent load times⟯ than ⟮c1;server-side rendering⟯ 

⟮c7;Client-side rendering⟯ often has ⟮c8;problems with SEO⟯, as ⟮c9;the original HTML basically contains nothing⟯ 
The difference between ⟮c10;static generation⟯ and ⟮c10;server-side rendering⟯ is that ⟮c10;static generation⟯ ⟮c12;generates the HTML⟯ ⟮c11;at build time⟯, while ⟮c10;server-side rendering⟯ ⟮c12;generates the HTML⟯ ⟮c11;on each request⟯ 

⟮c13;Static-site generator⟯ by ⟮c14;github⟯: ⟮c15;Jekyll⟯ 

##### different products

Express is the most popular server-side web framework for node.
Angular is the successor to AngularJS
Angular is sometimes called Angular 2
While AngularJS was written in JS, Angular (2) was written in typescript.
Angular and Vue.js are the two most popular front-end frameworks that are clearly frameworks.
React is often called a framework and would be the most popular front-end framework if it was, but is more like a library.
Svelte works like a front-end framework, but actually compiles in advance.

##### react 

###### core react

####### using JSX

JSX is syntactic sugar for React.createElement(/*args*/)
Using JSX with React is optional.

####### components and elements

React components accept arbitrary inputs as `prop`s and return react elements.
Elements are either components or native DOM tags.
Typcially, the ⟮c+;top-most⟯ react component is called ⟮c+;App⟯
React components are UpperCamelCase'd

######## attributes of components

######### props

all attributes that a react component recieves are gathered together and passed to the render logic as `props`

######### state

state is by default encapsulated in a component.
Passing state down is passing state to a child via props.

######## implementation

Components can be implemented via functions + hooks or classes.
function components = components implemented with a function
class components = components implemented with a class.
The thing implementing the render logic is the function for function components, and the render method for class components.
The thing implementing the render logic of a component must be a pure function, side effects may only be performed in the class methods or relevant hooks.
the thing implementing the render logic recieves props.
to make a component hide itself, return null from tthe render logic.

react class components always extend React.Component. 
in the render() method of class components, you access most things via `this`

the function implementing a function component takes props as a parameter
For anything besides rendering based on props, react function components require hooks

table:action|function|class
referring to props|props (is parameter)|this.props
referring to state||this.state

####### the tree

React maintains a component tree called »the virtual DOM«, which is an in-memory JS representation.
Because React maintains the virtual DOM as an in-memory JS representation, creating react elements is far cheaper than browser DOM elements.
Eventhough react's component tree is called 'the virtual DOM', it can be outputted to many things, including but not limited to the DOM.
`ReactDOM` is an inteface to the output DOM.
ReactDOM.render(<root-element>, <DOM-container>[, <callback>]) 
calling ReactDOM.render() is most commoly done to render the initial the virtual DOM into the output DOM once, where subsequent changes are handled by the render() method of components.

####### changes

The render logic of a given component is called when state or props change, initating the render phase.
Calling ReactDOM.render() also initiates the render phase for everything.
For any change, react has two phases (with a rare inbetween phase): Render phase, commit phase (and pre-commit phase)
The render phase is pure and has no side effects, may be paused aborted or restarted by react.
The render phase involves react calling a constructor for newly mounted components, and the render logic for any component.
The render logic of React components creates a tree of React elements.
In the commit phase, we figure out how to output the tree of React elements to the output (e.g. the DOM)
In an performance-unlimited word, react would just completely output the virtual DOM tree to the DOM.
Since performance is limited, react needds to figure out what has changed between the new and old virtual DOM trees and how to change the DOM based on that as little as possible, which is called »reconciliation«.
Since complete tree diffs are O(n^{3}), reconciliation uses certain heuristics.

######## component lifecycle

In react, a component may change in three lifecycles, mounting, updating and unmounting.
Mounting is outputting the virtual DOM representation of a component to its output representation (i.e. creating the output representation).
Updating is changing the component's state or props.
Unmounting is removing the virtual DOM representation of a component from its output representation (i.e. destroying the output representation).
For each stage in the component lifecycle, react has a method.
For the mounting and updating stages, the methods are called after the DOM representation has changed.
For the unmounting stage, the method is called before the DOM representation changes.

mounting|componentDidMount()
updating|componentDidUpdate()
unmounting|componentWillUnmount()

######## reconciliation

If react hits an element in its tree that has a different type (e.g. from <Article> to <Comment>), it will destroy (unmount) and rebuild (mount) the whole subtree.
when a DOM subtree is destroyed, all components of that subtree recieve `componentWillUnmount()`
when a DOM subtree is rebuilt, all components of that subtree recieve `componentDidMount()`

If react hits an element that has the same type, it will look at the attributes of both, kees the same underlying DOM node, and only updates the changed attributes.
When updating style, React also knows to update only the properties that changed. 
when a component's attribute change, it recieves `componentDidUpdate()`

```
<div className="before" title="stuff" />
<div className="after" title="stuff" />
```
```
<div style={{color: 'red', fontWeight: 'bold'}} />
<div style={{color: 'green', fontWeight: 'bold'}} />
```

However, if the DOM nodes are out of order compared to the last rerender, react is forced to assume that the children are different and destroy the subtrees.
To prevent a reorder of DOM nodes destroying the subtree, react offers the `key` property, where it can assume that elements with the same key property are the same.
`key`s should be stable over time, e.g. IDs or hashes of some description.
`key`s should not be abstracted into subcomponents, as react cannot use them for element identity assertions form there.

####### events

React wraps browser events in `SyntheticEvent`s, which generally have the same interface but prevent browser inconsistencies.
In react, you can't return false to prevent the browser default for an event, you actually have to call preventDefault

###### react native

⟮c1;React Native⟯ is a ⟮c2;framework⟯ for building native applications using ⟮c4;React⟯ and ⟮c4;the platforms native capabilities⟯
The most common targets for react native are android and iOS, but you can also target desktop OSs, qt, TVs and even the web.
You can use react native for your ⟮c1;whole app⟯, but you can also ⟮c2;integrate it into an existing project⟯
React Native implements a polyfill for WebSockets, initialized via importing React. Other modules using WebSockets therefore need to be imported after React.

####### components

Native Components: React Components transformed into native views
Core components: Native Components that are part of React Natives standard library
React Native|HTML
&lt;View&gt;|a non-scrolling &lt;div&gt;
&lt;TextInput&gt;|&lt;input type="text"&gt;
&lt;Text&gt;|&lt;p&gt;
&lt;ScrollView&gt;|a scrolling &lt;div&gt;
&lt;Image&gt;|&lt;img&gt;

&lt;TextInput&gt; is a Core Component that allows the user to enter text.
onChangeText|event when text is changed
onSubmitEditing|event when text is submitted

⟮h∞;<img src="sm_2021-09-16--16-10-01-screenshot.png">⟯
⟮h∞;<img src="sm_2021-09-16--16-08-57-screenshot.png">⟯
A list with ⟮c1;sections/headings⟯ should probably use the ⟮c2;&lt;SectionList&gt;⟯ component
A list with ⟮c1;no sections/headings⟯ should probably use the ⟮c2;&lt;FlatList&gt;⟯ component

All the elements and views of a ScrollView are rendered, even if they are not currently shown
&lt;ScrollViews&gt; can be configured to allow paging through views using swiping gestures by using the pagingEnabled props. 
The &lt;ScrollView&gt; Core Component can scroll in y-direction and, if `horizontal` is specified, in x-direction.
On iOS a ScrollView with a single item can be used to allow the user to zoom content. Set up the maximumZoomScale and minimumZoomScale props for that.

####### switching based on platform

Platform.version returns the os version (e.g. 10.1) on iOS and the API level on android
Platform.OS returns the current os
React Native supports two ways of generating plaform-specific code, the Platform module and platform-specific file extensions
to target React Native files specifically to android or to iOS, use the file extensions .android.js and .ios.js respectively
Platform.select takes an object with keys "ios", "android", "native", and "default", and runs the code contained in the relevant value
As far as I can see, for Platform.select "native" will trigger on native targets, while "default" will trigger on all targets, including web

#### server

Web servers provide web pages.
CMS|Content Management System
SSR|Server-side Rendering
⟮c3;Routing⟯ is relating ⟮c1;paths⟯ to ⟮c2;what should be shown⟯
while ⟮c5;react⟯ is by default a ⟮c1;client-side-rendered⟯ thing, using ⟮c2;next.js⟯, ⟮c3;gatsbyjs⟯ or ⟮c4;other custom tools⟯, you can make it ⟮c1;SSR⟯

##### JS

Node.js was created in 2009.
Node.js uses V8 as its JS engine/interpreter.
⟮c1;Deno⟯ is a ⟮c2;perhaps-sucessor⟯ to ⟮c3;node⟯ by ⟮c4;the same creator⟯.
⟮c5;Deno⟯ is wrtten in ⟮c1;rust⟯, provides native ⟮c2;TS⟯ support, uses ⟮c3;ES⟯ modules, and ⟮c4;URLs⟯ for the location of dependencies

##### Python

Flask and Django are the most popular web frameworks for Python.

#### both (Static generation / hybrid between CSR and SSR)

##### jekyll

Jekyll|Ruby
⟮c4;Jekyll⟯ uses ⟮c5;liquid⟯ as its ⟮c6;template language⟯ 
You can write ⟮c16;Jekyll⟯ pages in ⟮c7;HTML⟯ or ⟮c8;Markdown⟯ 
Jekyll pages/layouts/includes can have ⟮c9;metadata⟯ associated with them, which is specified in ⟮c10;the front matter⟯ 
⟮c11;Front matter⟯ in Jekyll ⟮c12;starts and ends⟯ with ⟮c13;three dashes ---⟯ 
⟮c14;Front matter⟯ in Jekyll is written in ⟮c15;YAML⟯ 


for any page, the `⟮c17;page⟯` assoc array contains ⟮c18;the keys of that pages front matter⟯ 
the `⟮c19;page⟯` assoc array is ⟮c20;autopopulated with certain keys⟯ beyond ⟮c21;the ones specified in the front matter⟯, amongst others the key ⟮c22;`url`⟯ 

⟮c23;Layouts⟯ ⟮c24;wrap around⟯ your content. 
⟮c25;Layouts⟯ are stored in the ⟮c26;_layouts directory⟯. 
For a given post or other page, you specify ⟮c28;which layout it's using⟯ by using ⟮c27;the `layout` front matter key⟯. 
Layouts can ⟮c29;inherit⟯ - you do this by ⟮c30;referring to the parent layout⟯ ⟮c31;within the child layout⟯ using ⟮c32;the `layout` front matter key.⟯&nbsp;
Within a layout, ⟮c33;`{{content⟯`}} refers to ⟮c34;the content of the post using⟯ the layout, or ⟮c34;the next-deeper child layout.⟯ 
As a convention, ⟮c35;the root level layout⟯ is called ⟮c36;default.html⟯. 
the `⟮c37;layout⟯` assoc arr contains ⟮c38;all metadata of the current layout⟯. 
⟮c39;`layout.foo`⟯ allows you to ⟮c40;access key foo of layout front matter⟯ 


⟮c41;Includes⟯ are basically ⟮c42;components⟯, you can ⟮c43;refer to and include from anywhere you like⟯. 
⟮c44;Includes⟯ are stored in ⟮c45;the _includes directory.⟯ 
⟮c46;Includes⟯ may take ⟮c48;arguments⟯ as ⟮c47;key=value⟯. 
Within an include⟮c49;, a parameter foo⟯ is referred to as `⟮c50;include.foo⟯` 
Include syntax: `⟮c1;{%⟯ ⟮c2;include⟯ ⟮c3;include-name.html⟯ ⟮c1;%}⟯` 

the `⟮c51;site⟯` assoc arr contains ⟮c52;all global data⟯. 

Syntax for jekyll ⟮c53;post⟯ ⟮c54;file names⟯: ⟮c55;YYYY-MM-DD⟯⟮c56;-title⟯⟮c57;.extension⟯ 
Jekyll will ⟮c62;auto-generate⟯ ⟮c58;a `post.title`⟯&nbsp;from ⟮c59;the URL = file name⟯ if not specified 
Jekyll will ⟮c63;auto generate⟯ ⟮c60;a `post.excerpt`⟯&nbsp;from ⟮c61;the first paragraph⟯ if not specified 
⟮c64;Posts⟯ are specified in ⟮c65;./_posts⟯ 
`⟮c66;site.posts⟯` contains ⟮c67;an array⟯ of ⟮c68;all the posts in ./_posts⟯ 


Jekylls supports keeping data stored in ⟮c69;./_data⟯ for ⟮c70;global use⟯ 
Jekyll ⟮c71;data files⟯ may be specified in ⟮c72;yaml, json::2 similar ones⟯, ⟮c73;csv or tsv::2 similar ones⟯. 
Jekyll ⟮c74;data files⟯ can be accessed via ⟮c75;`site.data.filename` (no extension⟯)&nbsp;
Jekyll supports keeping ⟮c76;small mini-posts⟯ in so-called ⟮c77;collections⟯. 
⟮c78;Any directory in the root folder⟯ ⟮c79;starting with _⟯, but not ⟮c80;being one of the predefined directory names (such as _data, _posts⟯) is considered ⟮c81;a collection⟯ of ⟮c82;the same name⟯. 
Jekyll supports ⟮c83;designating a directory for collections⟯ instead o⟮c84;f specifying them in the project root in the config⟯, but this must then ⟮c85;also contain _drafts and _posts, if extant⟯. 
Besides ⟮c86;creating a directory⟯, ⟮c87;collections⟯ must also be ⟮c88;referenced in the collections array in the config⟯. 
⟮c89;collections⟯ are ⟮c90;arrays⟯ available via ⟮c91;the `site.collectionname` propert⟯y 


###### themes

Jekyll ⟮c2;themes⟯ are often ⟮c1;gems⟯. 
By default, if you use a ⟮c3;gem theme⟯, ⟮c4;some of the directories of your site⟯ are ⟮c5;in the gem itself⟯. 
If you want to ⟮c6;edit things⟯ ⟮c7;in gem themes⟯, you need to ⟮c8;copy then out of the gem itself⟯, and ⟮c9;reference the gem's dependencies in your gemfile/config⟯. 

###### plugins

⟮c9;Jekyll plugins⟯ are specified within ⟮c10;the _config.yml⟯ and within ⟮c11;the gemfile⟯. 
In the ⟮c12;gemfile⟯, ⟮c13;jekyll_plugin⟯s are specified within ⟮c14;the `group :jekyll_plugins`⟯ 


    <tr><th colspan="2">Jekyll Plugins|
⟮c1;jekyll-feed⟯|⟮c2;Generating an RSS feed (jekyll⟯)
⟮c3;jekyll-seo-tag⟯|⟮c4;Generating a few SEO tags (jekyll⟯)
⟮c5;jekyll-sitemap⟯|⟮c6;Generating a sitemap⟯
⟮c7;jekyll-paginate⟯|⟮c8;allow pagination⟯


###### config
⟮c1;defaults⟯|⟮c2;default front matter⟯
⟮c3;paginate: n⟯|⟮c4;paginate with n pages⟯



##### next.js

Each page is defined by a react component.

###### globals

The global component acts as a globabl template for all pages.
The global component is stored in `pages/_app.js`
For rare cases, there is a higer global template `Document`, which is only rendered on the server and does not support data fetching methods.
Overriding the global component is often doe to create global components, styles or state.
Stylesheets are imported by JS's `import` (as in webpack, which next.js uses in the background).
Stylesheets may only be imported from the global component.

###### layouts

Defining layouts for pages allows react to easily perform reconcilliation between the pages.

###### ways to serve content

Next.js allows you to mix and match static generation, SSR and CSR for each page.
Next.js distinguishes between static generation, SSR and CSR by how the components implementing the page will recieve props.
Next.js's »data fetching methods« are getStaticProps/getStaticPaths/getServerSideProps.
Next.js's data fetching methods are all async.
To use the data fetching methods, you need to `export` them


### IO

#### shell environment

Modules which contain most of the environment stuff, though they may contain other stuff


rust
std::env|env & argv
std::io|stdin, stdout, stderr and reading input lines
std::process|run a system command
no module (just std)|printing


python
sys|stdin, stdout, stderr, argv
os|env, run a system command
no module|printing


node
process|stdin, stdout, stderr, argv, env
console|printing
child_processes|run a system command


ruby
no module|stdin, stdout, stderr, argv, env, printing, run a system command 

##### stdin/stout

<relevant-module-if-any>.stdin/stdout/stderr generally gets a streamlike io object referring to stdin/stdout/stderr

std::io::stdin/stdout/stderr|Rust (returns a handle of std::io::Stdin/Stdout/Stderr)

##### environment variables & command-line arguments

argv = argument vector
Command-line arguments
@ARGV|Perl
process.argv|node
sys.argv|python
std::env::args()|Rust

Environment variables
%ENV|Perl
process.env|Node
os.environ|python
std::env::vars()|Rust

A signle environment variable
std::env::var(<name>)|Rust

###### parsing

for any kind of involved CLI argument parsing in Rust, use `clap`.

##### print to & read from console

Print functions in different languages
the JS console library works both in the browser and in node.js

print()|lua|perl (no final newline)|python|Ruby (no final newline)
say()|perl (final newline)
puts|Ruby (final newline)
console.log()|JS
@debug|SCSS/Sass
System.out.prinln()|Java
Console.WriteLine|C#
echo|liquid (within liquid block)|(ba)sh
println!|Rust

echo options
-n|no trailing newline

Print functions using C format strings
printf|(ba)sh, but it doesn't take format strings any more than echo|C (ofc)|Perl|Ruby
string.format|Lua
% syntax|Python

Print an error to console (but don't throw one)
console.error()|JS
@warn|SCSS/Sass
eprintln!|Rust

clear the console/terminal window
clear|sh
console.clear()|js
ø (no easy native solution)|python|ruby

console.count(foo)   count how many times a string foo has been printed

the sh printing commands all don't read from STDIN
besides taking more options, printf has exit codes other than 0 (echo always exits 0), echo adds a "\n" at the end while printf doesn't
printf options
-v foo|save the output in a variable foo

##### run commands in system shell

system()|ruby
<system-module>.system()|python

#### file system

##### current working directory

process.cwd()|node
__dirname|Node

##### paths

module for working with paths
path|node

<path-module>.resolve({<items>})|glue passed things together into an absolute path (glues the path of the working directory onto the beginning if necessary)

#### files & streams

##### relevant modues

std::io, std::fs|Rust

##### non-stream based file interaction

Many programming languages feature utility functions to read an entire file to a string/write an entire file to a string, without having to use streamlike I/O.
The functions to instantly write a file typicallly take at least a path and the contents plus named arguments or an assoc arr for options.
The functions to instantly read a file take at least a path.
Most functions to read a file instantly, but not Rust, also take named arguments or an assoc arr for options.
the node async instant read/write file function also takes an error callback, as usual
readFile(Sync)/writeFile(Sync)|Node
std::fs::read_to_string|Rust

##### interaction

Once aquired, files and other streams such as stdin, stdout, stderr are often generalized in their functionality to a common interface, often called a stream, though sometimes called a file object.
Streams may be distinguished by if they support input, output, or both, or if they represent text, binary or something else (but not necessarily the case).
Streams often work similar to iterators, consuming input gradually.
Streams as the programming-centric I/O concept get their name and basic idea from the stream ADT.
Sometimes, instead of conceptualizing inputs as streams, programming languages instead conceptualize the way of consuming input streams, and thus call their interface for consuming streams `Reader` or similar.
For languages that have separate readers, getting the reader typically locks the stream to the given reader.

###### implementation of streamslike IO in different languages

Pythons streamlike I/O class/interface is `File`, even for things we wouldn't typically call files.
Ruby's streamlike I/O class/interface is `IO`.
Node's streamlike I/O class/interface is `Stream`.
In node, `Stream`s that can be read/written/both implement `Readable`/`Writable`/`Duplex`
JS has `ReadableStream` and `WritableStream` for streamlike I/O class/intefaces.
Rust doesn't have one class/struct for working with streams, but things that are readable implement the traits `Read` andor `BufRead`.
For some things, Rust only returns things implementing `Read` andor `BufRead` after calling `.lock()`
For files, rust's struct implementing `Read` is `File`.
JS returns the actual reader `ReadableStreamDefaultReader` after calling `.getReader()` on the stream, which locks the stream.

####### streamlike IO that can be read

read(<integer>)|return next <integer> bytes/characters
read()|return whole file
readline()|return next line

Ruby doesn't support `readline()` for its streamlike object, but does support `readlines`, which returns all lines as an array.
Node doesn't support `readline()` on `Stream`, however it offers a whole library `Readline` to consume `Readable` `Stream`s line by line.

####### streamlike IO that can be written

write(<content>)|write the content to the string

##### aquisiton and holding

###### not quite dispose

createReadStream/createWriteStream|node

###### dispose

The dispose pattern is a pattern for resource management.
In the dispose pattern, a resource is held by an object.
In the dispose pattern, a resource is typically aquired by calling a global function.
In the dispose pattern, a resource is used by calling methods on it.
In the dispose pattern, a resource is released by calling a method on the object.
The dispose pattern is common for interacting with files, in which case the resource is a file handle.

####### aquisition

to aquire files for the dispose pattern, most languages use a open() function, taking the path and returning a streamlike io thing.
Most languages have a positional or named parameter for `open()` allowing the specification of the encoding.

######## mode letters

Established by *nix/C, many functions to open/create new files/file handles across languages take a certain set of letters with certain meanings

r|read
w|create/clobber (eqiv to > in shell)
x|try create and fail if exists
a|create/append (equiv to >> in shell)

####### releasing

<resource>.close()|release the file handle

####### language constructs

some languages have language constructs for the dispose pattern: 
with|Python
using|C#
Languages that have language constructs for the dispose pattern typically require the things they act on to implement a certain inteface with methods for aquiring and releasing the resources, which will then be called automatically.
The language constructs for the dispose pattern typically assign the resource to a local variable.
The language constructs for the dispose pattern typically only execute their code if the resource could be successfully aquired.
In python, the interface for the dispose pattern is a context manager object, which must have __enter__ and __exit__ methods.
python-construct-for-dispose-pattern ::= with <context-manager> as <variable-name>:
c#-construct-for-dispose-pattern ::= using(<type> <variable-name> = <thing-implementing-IDisposable>){...

### fancy IO

#### visual

##### UI

widget tookit   library for creating UIs
gtk   GNU widget toolkit
qt (read cute)   cross-platform widget toolkit

##### Data visualization

d3 is a JS library for mainipulating/visualizing data

#### web 

table:span=2;web IO library
requests|python|requests only
ureq|Rust|requests only
`http`/`https`|node|requests & server=responses
none|native js|requests only
axios|node & native js|requests (promise-based)

##### requests

table:span=2;requests
<request-library>.get()|GET request|python, node
<request-librar>.request()|any request|python, node
fetch()|any request|native JS

Most web request libraries take an object of type `Request` as an argument.
Node instead gets a OutgoingMessage object, which is also the same object the callback to createServer sends.
Most web request libraries return an object of type `Response`.
Node instead returns a IncomingMessage object, which is also the same object the callback to createServer gets.
Most async web request libraries return a promise or equivalent which resolves to a `Response`, or else take a callback that recieves a `Response`


<reqres-object>.headers|HTTP headers|node, js, python
<response-object>.url|url of request or final url of document|js, python, node


<request-object>


<response-object>.status_code/statusCode|HTTP status code|python, node
<response-object>.status|HTTP status code|js
<response-object>.reason|HTTP status message|python
<response-object>.statusText|HTTP status message|js
<response-object>.statusMessage|HTTP status message|node
<response-object>.ok|is success status code (200-299)|js, python
<response-object>.content|Returned thing as binary|python
<response-object>.encoding|Page encoding|python
<response-object>.text|Returned unicode text|python
<response-object>.body|Returned body as stream|js


If the response object is going to be sent, as e.g. in node, it supports additional methods/fields:


<response-object>.setHeader(<key>, <val>)|set HTTP header to value
<response-object>.end()|finish the message


###### XHR

XHR|XMLHttpRequest
Ajax|Asynchronous JavaScript And XML

###### fetch

the Fetch API features fetch() as its main method 
The Fetch API is the new, modern method to fetch data via the interfet after a site has loaded.
fetch(<resource-to-get>, [<options-object>])
fetch() returns a Promise which itself resoves to a `Response`
Response
.json()|return promise with contents of response as parsed json

Node doesn't have the Fetch API natively, but you can install it via a package, and Next.js polyfills it automatically

##### sending responses

to send a response to requests, you generally first need to create a server

table:span=2;method to create new servers
<server-library>.createServer|create new server

createServer takes a callback to then respondd to requests

### scientific computing

pandas|python

### performance monitoring

time|measure elapsed time in executing a command|sh
console.time(), console.timeLog() & console.timeEnd()|measure elapsed time in running code.

### dates

most languages have a date object (or multiple different ones) that allows convenient manipulation of datetimes

#### js

In js, ⟮c2;Unix time⟯ is almost always interacted with in ⟮c1;milliseconds⟯, 
as opposed seconds, which is more standard
the `⟮c1;Date.parse()⟯` method takes ⟮c2;a date in a few common formats⟯ and outputs ⟮c3;Unix time (in millis, as is common in JS)⟯
`⟮c1;new Date()⟯` takes ⟮c2;Unix time milliseconds⟯ and returns ⟮c3;a `Date`⟯
`⟮c1;someDate.toISOString()⟯ ` returns the datetime ⟮c2;as ISO 8601⟯

#### rust

In rust, the most featureful library to use to interact with dates is chrono.
chrono has `Date` and `DateTime` to represents dates and datetimes, which both take a type parameter of the `TimeZone`.
chrono also has `NaiveDate`, `NaiveDateTime` and `NaiveTime` to represents dates, datetimes and times without timezone awareness.
In generaly chrono structs implement traits in such a way that you can use standard arithmetic operators for them.
In general, using arithmetic operations in chrono calls the underlying `checked_<operation>_signed` method
chrono has three `TimeZone`s, `Utc`, `Local` and `FixedOffset`
`Local` or `Utc` (but not `FixedOffset`) :: `today()` or `now()` produce a new `Date` or `DateTime` with the speciied timezone.
Behavior of things that work ⟮c+;like dates⟯ / ⟮c+;like times⟯ is standartized in the ⟮c+;traits⟯ ⟮c+;Datelike⟯ and ⟮c+;Timelike⟯
you can get ⟮c+;the time components⟯ of ⟮c+;Timelike⟯ using ⟮c+;the length you want as a method⟯ (e.g. hours -&gt; ⟮c+;sometimelike:​:hours()⟯)
you can get ⟮c+;the date components⟯ of ⟮c+;Datelike⟯ using ⟮c+;the date component you want as a method⟯ (e.g. months -&gt; ⟮c+;somedatelike:​:month()⟯)
chrono represents durations with `Duration`
for chrono `Duration`s there are a bunch of constructors for different amounts of time such as `::weeks()`, `::hours()` etc.
For rust, if you only need simple duration handling, chrono might be overkill, and the things in `std::time` might be more appropriate.
Weekdays in chrono are implemented by the enum chrono:&#8203;:Weekday and the variants( :&#8203;:Mon,  :&#8203;:Tue,...)

### Standard library

A software solution that has everything that it needs to run out of the box is said to be batteries included.
A programming language that has a large standard library is said to be batteries included.

the standard library is often indicated by fs

get list of all functions a module/package supports
dir(foo)|Python

get the smallest/largest of an amount of arguments
min()/max()|Python (also accepts an iterable as an argument)
Math.min()/Math.max()|JS

Get documentation information on the thing
help(foo)|Python

Show an output popup
window.alert("mesg")

#### Modules/Objects/Namespaces

Filesystem handling
fs|node|Rust

#### Query for input

Generally, show a message, have a text input field, return the inputted text.

input(mesg)|Python
window.prompt(mesg, default)

### other libraries

#### utility libraries

An utility library is a library that adds a bunch of syntactic sugar methods for doing things.
in JS, there is the tradition of importing the main utility library as `_`.
As of 2021 the main js utility is lodash, before that it was underscore.

#### presentations

complexity|write in|name|converts to
fancy|js|reveal.js
simple|md|remarkjs
simple|own markdown syntax|pandoc|5 html-based formats incl. reveal.js, latex beamer, ms powerpoint, pdf


## programming language categorization & history

### names

Name|Prononciation
⟮c1;C#⟯|⟮c2;C sharp⟯


thing|slang
⟮c1;Rust users⟯|⟮c2;rustaceans⟯


### Programming paradigms

Functional programming languages: {Haskell}

### Programming languages I don't know

COBOL is a programming language introduced in 1959 with an englisy-like syntax that is as of 2021 mainly used on ⟮c1;legacy mainframe computers⟯
C was created in 1972.
*nix OSs are famously written in C.
tcl is a programming language where everything is a command.
tcl has a well-known widgeting toolkit known as tk.
wish is a tcl interpreter including its widgeting toolkit tk.

### programming language relationships

#### versions over time

Python ⟮c1;2⟯ and ⟮c1;3⟯ have ⟮c2;some syntactic differences.⟯ 
ES2015|ES6
The rust development cycle has the three release channels ⟮c1;Nightly⟯, ⟮c2;Beta⟯ and ⟮c3;Stable::S...⟯. ⟮sb;⟮c4;Every six weeks⟯ ( = ⟮c5;1 cycle⟯), ⟮c6; a release moves up one (beta -&gt; stable, nightly -&gt; beta) ⟯. ⟯ 
Therefore, ⟮s10-12;⟮c7;what is beta now⟯ will be ⟮c8;stable⟯ in ⟮c9;a maximum of 6 weeks⟯⟯, and ⟮s7-9;⟮c10;what is nightly now⟯ will be ⟮c11;stable⟯ in ⟮c12;at most 12 weeks⟯.⟯ 
⟮c17;Breaking changes (such as reserving new features⟯) can only happen on ⟮c18;the highest rust versioning level⟯, which are ⟮c19;editions⟯. ⟮sb;these are released ⟮c20;about every three years⟯, with the ones in existence as of writing being ⟮c21;2015, 2018, and 2021⟯⟯ 

#### dialects, influence, etc.

##### ECMA

JS = Javascript
ES = ECMAScript
JavaScript is a dialect/language that coforms to of the ECMAScript standard
others languages that conform to the ECMAScript standard are ActionScript / JScript. 
However, this distincition is often not made, and JavaScript and ECMAScript are often treated as synonyms. 
CoffeeScript is similar to and compiles down to JavaScript, but has more syntactic sugar/cleaner syntax.
TypeScript is a superset of javascript.

### Things programming languages do especially well

performance|rust

### language governance

After being dropped by mozilla, the rust foundation has taken over the governance of Rust (as of 2021)
The rust foundation is made up of major industry players like microsoft, google, huawei, mozilla.

# CompSci

## abstraction

abstraction is hiding implementation details in favor of a clear, semantic and elegant interface.
A high-level programming language is a programming language with high levels of abstraction.
A low-level programming language is a programming language with low levels of abstraction.
Often, abstraction has runtime overhead/costs.
Zero-cost abstractions are abstractions that have no runtime, only compile-time overhead.
Rust touts that it has many zero-cost abstractions.

## concurrency

Concurrency is executing multiple things at the same time.

### multithreading

A thread is the smallest sequence of instructions that can be independently managed by a scheduler.
Threads can be divided into kernel and green/virtual/user threads.
green thread = virtual thread = user thread.
kernel threads are those managed by the kernel to be scheduled for some CPU time.
user threads are those threads managed by a user process.
N:1 Threading   all threads of the program map onto one kernel thread
M:N Threading   some amount of threads of the program corresponds to some amount of threads of the os/kernel 
1:1 Threading   1 thread of the program corresponds to 1 thread of the os/kernel

#### thread pools

A thread pool is a group of pre-instantiated, idle threads which stand ready to be given work. These are preferred over instantiating new threads for each task when there is a large number of short tasks to be done rather than a small number of long ones. This prevents having to incur the overhead of creating a thread a large number of times.
A thread pool typically processes a queue of tasks waiting for processing.

#### workers

Web Workers are threadlike things in JS.
Web Workers come in two flavors, dedicated workers and shared workers.
While a ⟮c2;dedicated worker⟯ is accessible from ⟮c3;a single script only⟯, a ⟮c2;shared worker⟯ is accessible from ⟮c4;multiple scripts⟯, even if ⟮c1;within different windows or frames⟯
Because many JS APIs are not ⟮c2;threadsafe⟯, ⟮c3;Web Workers⟯ have access to ⟮c1; only a limited subset⟯

Web Workers are created by using the Worker/SharedWorker constructor taking the JS file that implements the worker.
Web Workers as well as the main thread communicate via message passing.
For Web Workers, messages are sent by using the method postMessage and recieved via the message event.
For Web Workers, messages always send a copy of the data.
To handle events in Web Workers, use the error event.
To stop a Web Worker, call the terminate() method on it.

#### thread-safety

Thread-safe code is code that will work even if many Threads are executing it simultaneously. 

### concurrency control

concurrency control ensures that correct results for concurrent operations are generated.
Mutual exclusion is the requirement in concurrency control that no thing may access the critical section while another thing is already accessing the critical section.
lock = mutex
A lock or mutex is a thing that enforces mutual exclusion.

### classic problems

#### race condition

A race condition is the condition of a system where the behavior of a system depends on the sequence/timing of uncontrollable events.
A race condition is often a flaw that may cause bugs.

#### deadlock

<img src="1280px-Process_deadlock.svg.png"><img src="220px-Gridlock.svg.png">
A ⟮c2;deadlock⟯ is a situation where ⟮c3;each member of  a group⟯ is ⟮c4;waiting on another member to do something⟯, and therefore ⟮c1;the system is stuck⟯
⟮c5;Gridlock⟯ is a specific type of ⟮c6;deadlock⟯ that occurs ⟮c7;in a street network⟯

## metaprogramming

metapgrogramming is programming that operates on other programs
An eval is a keyword/function/which executes a passed string as if it had been an expression in the language.
Using eval with data from an untrusted source is a huge security risk.
eval is a function in bash, JS, Perl, Python, Ruby. a similar function load is availabe in lua

### reflexion

reflective programming is metaprogramming where the program operates on itself
reflective programming is sometimes shortened to reflexion.

### macros

a macro is something that maps a input to a replacement output.
Rust supports macros as its main form of metaprogramming.
Rust macros end in an !.


## Programming language implementation

A programming language implementation is a system for executing computer programs written in a given programming language (s). 
There are two general approaches to programming language implementation: interpretation and compilation
While we might talk about ⟮c2;programming languages⟯ being ⟮c1;compiled or interpreted⟯, but actually it's ⟮c3;the relevant implementation⟯ that is ⟮c1;a compiler or an interpreter⟯.
A ⟮c1;reference implementation⟯ is an ⟮c2;implementation⟯ of a ⟮c2;specification⟯ generally written by ⟮c3;the creators⟯ of ⟮c5;the API/programming language/whatever⟯ to be ⟮c4;an example for other implementations⟯

TS compiles to JS via the compiler, interfaced with the cli tsc.

$Something that happens during execution   runtime $something
$Something that happens during compiling   compile-time $something

### Types

A compiler translates one programming language into another in one step before execution.
Most commonly, a compiler translates a programming language into machine code/assembler.
An interpreter translates the code into another language (most commonly machine code/assembler) as it goes along.
JIT = Just in time (compilation)
frequently when using JIT as a first step the code is compiled to bytecode
when using JIT, the code(/bytecode) is initially executed by an interpreter, but there is a monitor/profiler that constantly analyizes the code being executed and identifies parts of the code where the speedup gained from compilation or recompilation would outweigh the overhead of compiling that code, and then compiles this on the fly.

#### Transpiling

Source-to-source translator/compiler    trans(com)piler
A transpiler compiles one (programming) language into another (programming) language, though the target language is generally not assemly.
A preprocessor most typically takes some input and transforms it into some output, often for further use of compilers.
While preprocessors generally don't transform the language, sometimes transpilers are called preprocessors, e.g. in the case of sass.
Babel is a transpiler that transpiles ⟮c1;newer JS (e.g. ES 2017, ES 2020) to older JS (e.g. ES5)⟯

#### compilers

Object code is the code that the compiler produces, generally machine code.
The object file is the file containing object code.

##### compiler options

A compiler option is a setting that changes what a compiler does.
Compiler options may be set via pragmas, via a config file, via CLI options, or via a combination.
TS|config, CLI

Release profiles are sets of compiler options for certain scenarios, e.g. dev, release, ...
Rust allows customization of its release profiles via the Cargo.toml [profile.*] headers

###### TS

compiler option|function
strict|activate a bunch of other options, amongst others noImplicitAny and strictNullChecks

###### Rust

rust has a set of compiler options that allow the conditional compilation of code.
In rust, a compile-time feature flag is a compiler option that allows conditional inclusion or exclusion of code.
rust allows the creation of custom compile-time feature flags that may be used in the conditional compilaton of code via compiler options.
rust has two types of pragmas to specify a set of compiler conditions that must be met: attributes and macros, both indicated by cfg.
in rust, you specify custom compile-time feature flags in a [features] section of your Cargo.toml
in the [features] section of your Cargo.toml, each key specifies a feature, and takes an array of crates or other features to optionally require.
you can activate a feature for an external crate by referring to it within the features array that is part of the table defining the dependency.
custom compile-time feature flags are refered to in `cfg` by the <cfg-name> feature
compile-time feature flags are enabled by cargo build --features "<featurename>" 
any cfg condition is enabled by --cfg "featurename"
cfg-attribute-sytnax ::= #\[cfg(<cfg-predicate>)\]
cfg-predicate ::= <cfg-option>|<cfg-logic-function-multiple>|<cfg-not>
cfg-option ::= <cfg-name> = "<cfg-value>"
cfg-logic-function ::= (all|any)\(<cfg-predicate-list>\)
cfg-not ::= not\(<cfg-predicate>\)
cfg-predicate-list ::= <cfg-predicate>{, <cfg-predicate>}

### Steps involved

1. lexical analiysis/tokenization/lexing
2. sytax analysis = parsing
3. semantic analysis

#### lexical analysis

lexical analiysis = tokenization = lexing
Terminology around tokenization/lexical analysis is not always consistent.
Lexical analysis is converting a sequence of characteres into a sequence of lexical tokens.
Lexical tokens have some kind of meaning, relative to the language.
Lexical token is often shortened to just token
Tokens are lexical units/items in linguistic terms.
Tokens have a certain value (a string), and a certain type.
Token types that are common across programming languages are identifier, keywords, operator, literal ...
The analogue of token type in linguistics might be word class/syntactic category/part of speech
Compilers/interpeters store all the identifiers/symbols and info about them in the symbol table.
In the context of compiling/interpreting, identifier/name is a synonym for symbol.

#### syntax analysis

#### semantic analysis

#### compiler optimizations

A compiler optmization is a feature of a compiler that tries to minimize or maximize some attributes of an executable computer program.
Optimization levels are compiler options specifying how much compiler optimizations to apply.
In the GCC C compiler and in Rust, there are four optimization levels, 0-3.
In rust, optimization levels are set via `opt-level'.

##### dead code

Dead code is code which is never or not usefully used.
Unreachable code is dead code which is dead because there is no control flow path that would lead to it.
Dead code elimination is a compiler optimization involving the removal of dead code.
In js, dead code elimination is kown as tree shaking.
unused variables are a type of dead code.
compilers and linters will typically warn about unused variables.
unused variables may be a code smell in that they are mistakenly not used.
in rust, to turn off warnings about unused variables for a certain variable, prefix it with a _.

##### call sites

A call site is the place where a callable unit is called.
Inlining is a compiler optimization that replaces a function call site with the body of the called function.

### interfaces for implementation

#### Language CLI

most languages have a CLI tool to interface with them, esp. with implementations

interpreters/hybrid

lua|lua
node|JS (using node)
python, python3|python
perl|perl

compilers

sass|sass/scss
rustc|rust
tsc|ts

-c STRING|read program from string|python
-e STRING|read program from string|perl

npx <name> allows execuution of a binary <name> within an npm project without having to specify a path (e.g. a local version of a build tool or sth.)

by default, TS will ⟮c+;compile⟯ even ⟮c+;if there are compiler errors⟯, since it assumes ⟮c+;you might have a good reason⟯, use --noEmitOnError to disable this.
by default, TS compiles down to ⟮c+;ES3⟯, but you can change that with the ⟮c+;--target⟯ flag

##### REPL

REPL is short for read-eval-print loop
⟮c3;REPLs⟯ are also called ⟮c1;interactive toplevel⟯ or ⟮c2;language shell⟯

For most languages, invoking their CLI tool without arguments will open a REPL, if not
irb|ruby
tss-node|TS
is none|perl
jshell|java
csharp|C# (provided by mono)

Python calls being in the repl interactive mode
the value of the last expression
_|Python

#### Shebangs

env (/usr/bin/env) can be passed a comand, in which case it will populate the environment variables (including PATH) and then run command with this environment. 
Using env in the shebang is to get the relevant executable on the path
so in general, you can specify the language of a script by doing 
#!/usr/bin/env language-command

### specific languages

#### Python

CPython is the most common and reference implementation for Python.
CPython implicitly compiles Python to bytecode, and then runs the bytecode via an interpeter.
Python bytecode files produced by CPython are .pyc files.

#### JS

JavaScript is run by a JavaScript engine (e.g. V8, SpiderMonkey), which may differ by browser.chromium|v8
firefox|spidermonkey
d8 is the developer shell for v8

### document start/end indicators

--- the file ... |YAML (but optional, merely allow multiple documents per file)

## algorithms

⟮c1;An algorithm⟯ is a ⟮c2;finite⟯ ⟮c3;sequence⟯ (in the math sense) of ⟮c4;steps⟯ that ⟮c5;precisely defines an operation⟯. 

### pseudocode

⟮c6;pseudocode⟯ is ⟮c7;a plain-language description⟯ of ⟮c8;an algorithm⟯. 
⟮c9;Pseudocode⟯ generally ⟮c10;uses (structural) conventions of⟯ ⟮c11;programming languages⟯, but not ⟮c10;specific syntax⟯. 

```lang=text;
When a button is pressed:
  Get some memory, which will be used to remember the floor number
  Put the floor number into the memory
  Are we already on the target floor?
    If so, we have nothing to do: finished
    Otherwise:
      Wait until the lift is idle
      Go to the required floor
      Release the memory we used to remember the floor number
```

### properties

#### determinism

a deterministic algorithim/callable unit will, given a particular input ⟮c1;always produce the same output⟯

### for

#### search

##### binary


flex-container:<img src="sm_1280px-Binary_Search_Depiction.svg.png">
⟮c1;Binary search⟯ 
```
⟮c2;take middle element⟯ 
⟮c3;if equal, done⟯ 
⟮c4;else take relevant half and repeat⟯ 
``` 
⟮c5;binary search⟯ has a ⟮c7;worst-case time complexity⟯ of ⟮c6;O(log n⟯) 
⟮c8;Binary⟯ search can only be done on something that is ⟮c9;sorted⟯. 

#### sorting

A sorting algorithm is an algorithm that sorts a linear collection.

##### bubble


flex-container:<img src="sm_Bubble-sort-example-300px.gif">
Bubble sort is called that because the largest elements will bubble to the right in a single pass.
while true:
  for all elements in the list: 
    if currentElement > nextElement, swap them
  if no swap occurred in the loop, stop.

### complexity

Computational complexity is the amount of resources necessary to run an algorithm.
Computational complexity assumes the amount of resources to perform each operation are similar / average out.
there are two types of computational complexity commonly used, depending on the case: worst-case and average-case.
In general, if we only say 'complexity', worst case complexity is assumed.
there are two types of computational complexity commonly used, depending on the resource: time and space
Computational complexity is generally specified in Big O notation.
Computational complexity is generally specified as a function of the input size n.
Computational complexity/Big O notation only indicates orders of magnitude.

O(1)   constant complexity/time|Accessing an element in an array
O(n)   linear complexity/time|Iteratering over a one-dimensional array
O(log n)   logarithmic time
O(n<sup>2</sup>)   quadratic time

### static program analysis

static program analysis is reasoning about/analyzing the behavior of computer programs without actually running them
Linting is probably the most common form of static program analysis.

## information theory

### symbol rate

baud   Bd
baud   symbol rate (AKA baud rate, modulation rate)
symbol rate   symbol changes per second

## coding theory

The Hamming weight of a string is the number of symbols that are different from the zero-symbol (of the alphabet used).
This means that the hammming weight of a binary number is its digit sum. 
The hamming weight of 11101 is 4, the hamming weight of 60801 is 3

## AI

### Computer vision

⟮c1;Computer vision (CV)⟯ is a field of study that aims to get ⟮c2;artificial systems / AI⟯ to get ⟮c3;meaningful information / understanding⟯ from ⟮c4;digital images/videos/whatever⟯.

#### depth

⟮c1;Stereopsis}/{{c2::stereo(scopic) vision⟯ is ⟮c3;the ability to percieve depth⟯ from ⟮c4;only two eyes/optical sensors⟯.
binocular disparity is the difference between the images that the optical sensors involved in stereopsis recieve due to them being positioned somewhat apart.
stereo matching is matching the two images produced by stereopsis.
After stereo matching, one can calculate the distance via trangulation.
stereo matching is more difficult (esp. for computer sensors) if the thing is featureless (since it then has a harder time matching the relevant pixels)
To improve stereo matching on featureless things, a device intended for depth calculation via stereopsis often will project a IR dot pattern, which is a pseudorandom but known pattern of dots in the infrared spectrum, which it then can use as the things to match.

#### triangulation

⟮c1;Triangulation⟯ in surveying / computer vision / etc. is ⟮c2;determining the location⟯ of ⟮c3;a point C⟯ from ⟮c4;two points A and B⟯ by ⟮c5;forming a triangle⟯.
By knowing the ⟮c6;distance between A and B⟯ as well as ⟮c7;the angles at A and B⟯, we can ⟮c8;reconstruct the distance.⟯

### safety

#### technological singularity

The technological singularity is a hypothetical point at which technological progress reaches critical mass and becomes uncontrollable, causing severe but unpredictable changes.
Most commonly, the technological singularity is cashed out in terms of a intelligence explosion.
An intelligence explosion posits that there willl be a runaway reaction of self-improvement cycles of an AI, thereby bringing about the technological singularity.

# software engineering

Software engineering is term where the definition is often fought over.
Software engineering (roughly) is different from software development/programming in that it emphasizes a more holistic view including tools and processes used for development, and temporally not just the time writing code, but the time before and after too.

## software design

### decomposition

Decomposition is breaking down the problem into smaller parts.

### software architecture

Software architecture refers to the fundamental structures of software/development and creating those structures.

#### properties

##### coupling & cohesion

https://upload.wikimedia.org/wikipedia/commons/0/09/CouplingVsCohesion.svg
cohesion is the degree to which the elements inside a module belong together.
coupling is the degree of interdependence between software modules.
In general, cohesion is good and coupling is bad.
high coupling generally implies loose cohesion and v.v. 

A god object is an object that violates the single-responsibility principle by knowing too much or doing too much.
The single-responsibility priinciple states that (the implementation of) a thing should only change for one reason.

#### solution stack

A software/solution stack is the set of technologies that are layered/combined to run something (most often an application)
A developer than can work with all layers in a solution stack is a full-stack developer

ME?N = MongoDB, Express.js, ?, Node.js
MEAN includes Angular
MERN includes React
MEVN includes Vue.js

#### design patterns

##### MVC

MVC = Model View Controller

        ┌─────────────┐
      ┌─┤    Model    │◄┐
      │ └─────────────┘ │
  Updates           Manipulates
      ▼                 │
┌─────────────┐ ┌───────┴─────┐
│    View     │ │ Controller  │
└──────┬──────┘ └─────────────┘
       │              ▲
       │              │
     Sees           Uses
       │   ┌──────┐   │
       └──►│ User ├───┘
           └──────┘

## development practices

Rubber-duck debugging is problem-solving by explaining it out loud to an object or naive human.
functional requirement|function (relation between input and output)|system must do x
non-functional requirement|criteria of judgement, not specific behavior|system shall be x

### development paradigms

#### Agile

##### lean

###### kanban

Kanban board tools: trello, github projects

#### Scrum

### CI/CD2

CD|Continuous delivery OR deployment
CI|Continuous Integration

Before CI, integration would only happen once every few weeks or months
Continuous Integration is a software development practice where members of a team integrate their work frequently, at least once a day
The two main goals of CI are to reduce the pain of any integration, and to be able to deliver a product version at any moment

If a build failure happens in CI, the build should be fixed before work continues.

continuous delivery|software can be deployed on any commit
continuous deployment|software is deployed on any commit
⟮c1;Continous deployment⟯ ⟮c3;relies on⟯ ⟮c2;continous delivery⟯
A nightly build is one that is built every night, generally automatically

CI/CD requires certain steps such as testing to happen on any integration.
A CI/CD pipeline specifies the set of steps to happen on each integration.
The most common tools to implement a CD/CI pipeline are Jenkins, CircleCI, Travis CI or github actions.


### code writing enviroments

Integrated development environment   IDE
An IDE is a software development tool that aims to include everything relevant to progragramming in a ceratin language.

The ⟮c1;standard length⟯ of ⟮c2;a line of code⟯ is ⟮c3;80 characters⟯. 
⟮c6;The standard length of a line of code being 80 characters⟯ originated ⟮c4;with IBM punch cards⟯ in ⟮c4;1928⟯, and later was ⟮c5;the standard width of a terminal⟯ 
The default size in many cases for ⟮c3;terminals⟯ is ⟮c1;80 characters⟯ wide, and ⟮c2;24/25 lines⟯ high

#### code editor

A (source-)code editor is a text editor designed for writing source code.

##### keyboard shortcuts

###### vscode

rename a symbol|⟦f2⟧
see code actions (available refactorings and quick fixes)|⟦⌘⟧⟦.⟧
change (programming) language of current document|⟦⌘⟧⟦k⟧&nbsp;&nbsp;⟦m⟧
show integrated terminal|⟦⌃⟧ (even on mac) ⟦`⟧
fast scrolling|⟦⌥⟧ ⟦scroll⟧


Action|Shortcut
⟮c1;Open IntelliSense⟯|⟮c2;⟦⌃⟧ <kbd class="key space"></kbd>⟯


######## lines

Shortcut|Action
⟮c1;⟦⌃⟧ ⟦j⟧⟯|⟮c2;join lines⟯
⟮c3;⟦⌘⟧ ⟦⇧⟧ ⟦k⟧⟯|⟮c4;delete line⟯
⟦⌘⟧ ⟦enter⟧|insert a line below
⟦⌘⟧ ⟦⇧⟧ ⟦enter⟧|insert a line above


when focused on a line but not selecting a word, ⟦⌘⟧ ⟦c⟧ and ⟦⌘⟧ ⟦x⟧ act on the line itself


copy line up/down|⟦⇧⟧ ⟦⌥⟧ ⟦up/down⟧
move line up/down|⟦⌥⟧ ⟦up/down⟧


indent/outent a line|⟦⌘⟧ ⟦]⟧/⟦[⟧


##### UI 

###### vscode elements

####### groups

In vscode, a editor group is a group of one or more open editors

split current editor into two editor groups|⟦⌘⟧ ⟦\⟧
switch to left/right editor group|⟦⌘⟧ ⟦k⟧ ⟦←/→⟧
move editor group left/right/up/down|⟦⌘⟧ ⟦k⟧ ⟦←/→/↑/↓⟧
close editor group|⟦⌘⟧ ⟦k⟧ ⟦w⟧

####### tabs

In vscode, by default a tab contains one editor.

move current editor tab left/right|⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦⇧⟧ ⟦←/→⟧
switch to left/right tab|⟦⌘⟧ ⟦⌥⟧ ⟦←/→⟧
cycle through tabs|⟦⌃⟧ ⟦tab⟧
close all editors = tabs|⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦w⟧

####### single editor

######## navigation

symbol chooser popup (shorter version for mode of command palette)|⟦⌘⟧ ⟦T⟧
go to line (shorter version for mode of command palette)|⟦⌃⟧ ⟦g⟧
go to symbol  (shorter version for mode of command palette)|⟦⌘⟧ ⟦⇧⟧ ⟦O⟧
go back in location history|⟦⌃⟧ ⟦-⟧
go forward in location history|⟦⌃⟧ ⟦⇧⟧ ⟦-⟧

######## region

in vscode, a region is a block of code you can collapse or expand (e.g. defined by a {} in curly brace languages)

fold/unfold current region|⟦⌥⟧ ⟦⌘⟧ ⟦[/]⟧
fold/unfold current regions recursively|⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦[/]⟧
fold all regions|⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦O⟧
unfold all regions|⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦J⟧

######## editing

autoformat file|⟦⌘⟧ ⟦⌥⟧ ⟦f⟧

######### bookmarks

The vscode extension Numbered Bookmarks adds numbered bookmarks for lines which can be navigated to and from via keyboard shortcut

set numbered bookmark <n>|⟦⌘⟧ ⟦<n>⟧
navigate to shift bookmark <n>|⟦⌘⟧ ⟦⇧⟧ ⟦<n>⟧

######## select/search

add cursors to all search results|⟦⌥⟧ ⟦enter⟧

⟦⌘⟧ ⟦d⟧ uses the search widget to search for the word under the cursor, and adds a cursor for the first find match. every subsequent press adds a cursor to the next find match.
⟦⌘⟧ ⟦k⟧ ⟦⌘⟧ ⟦d⟧ is just like ⟦⌘⟧ ⟦d⟧, except that it doesn't add more than one cursor
⟦⌘⟧ ⟦l⟧|select a line (multiple presses select more)
In vscode, one can resize the search widget by dragging its left edge.

######## comments

⟮c1;add line comment⟯|⟮c2;⟦⌘⟧ ⟦k⟧⟦⌘⟧ ⟦c⟧⟯
⟮c3;toggle line comment⟯|⟮c4;⟦⌘⟧ ⟦/⟧⟯
⟮c5;toggle block comment⟯|⟮c6;⟦⇧⟧ ⟦⌥⟧ ⟦a⟧⟯

######## vscode jupyter

⟮c1;⟦f10⟧⟯|⟮c2;execute next line of code⟯
⟮c3;⟦⌃⟧ ⟦enter⟧⟯|⟮c4;finish editing a cell/run a code block⟯


####### bars and panels

show/hide side panel|⟦⌘⟧ ⟦b⟧

######## bottom panel

show problems|⟦⌘⟧ ⟦⇧⟧ ⟦M⟧
open new terminal if terminal tab is focused|⟦⌃⟧ ⟦⇧⟧ ⟦5⟧
split terminal right|⟦⌘⟧ ⟦\⟧

###### increment/decrement via arrow keys

Arrow up/down plus..|Increments by... (assumes base 10)
⟮c1;alt⟯|⟮c2;0.1⟯
⟮c3;ø⟯|⟮c4;1⟯
⟮c5;shift⟯|⟮c6;10⟯
⟮c7;command/ctrl⟯|⟮c8;100+⟯

##### code snippets

code snippets feature in many different code editors 
code snippets are templates that are triggered by selecting it from code completion or typing the name and then tabbing.
vscode features some built in code snippets and allows both extensions and the user to define new ones.
vscode follows textmates syntax for defining user snippets.
vscode snippets all live in the `snippets/` directory
snippets for a given language are set in a <languagename>.json file.
global snippets are set in a whatever.code-snippets file.
user snippets for vscode are defined in a json file.
any top-level json object within the snippets file defines a snippet.


key|function
prefix|what triggers the snippet
body|what happens when the snipped is triggered
description|What details IntelliSense provides for the snippet


code snippets can contain tabstops, places where values can be filled in easily.
when defining a code snippet, plain tabstops look like $1, $2...
$0 as a tabstop defines the final cursor position.
the transform part of code snippets takes a regex in the usual slash-based form, though instead of the replace part it may also take specifiers like `upcase`, `downcase`, etc.
the choice specifier of code snippets specifies a choice similar to the shell syntax
```
snippet-tabstop-specifier ::= $(<tabstop>|<variable>)
tabstop ::= <integer>|\{<integer>(<complex-specifier>|<choice>)\}
choice ::= \|<string>{, <string>}\|
variable ::= <string>|\{<string><complex-specifier>\}
complex-specifier ::= (:(<snippet-tabstop-specifier>|<string>)|<transform>)
```
you can jump between tabstops with tabs.

## QA

QA = Quality assurance
QA are the activities done to make sure that the product meets certain standards.

⟮c1;wave a dead chicken (over it)⟯: To perform a ritual over ⟮c4;crashed software or hardware⟯ which one ⟮c2;believes to be futile⟯ but is ⟮c3;nonetheless obligatory so that others may be satisfied that an appropriate degree of effort has been expended.⟯

### debugging

#### devtools (webkit)

##### elements tab

⟮c1;press del⟯ in the dom view of devtools to ⟮c2;delete the node⟯ 
⟮c3;⟦⌘⟧ ⟦⌥⟧ ⟦click⟧⟯ one of those ⟮c4;triangle arrows⟯ in devtools to ⟮c5;expand/collapse all children⟯ 
⟮c6;Expand and collapse⟯ DOM nodes in Chrome's devtools via the ⟮c7;right and left arrow ⟯ keys. 
to ⟮c8;search the DOM⟯ via ⟮c9;string⟯, ⟮c10;css selector⟯ or ⟮c11;xpath selector⟯, ⟮c12;ctrl/cmd+f⟯ in the DOM view in devtools 
to ⟮c13;hide the DOM node you have focused⟯ in devtools, press ⟮c14;h⟯ 
to edit the ⟮c15;attributes⟯/⟮c16;node type⟯ of a node while in devtools, press ⟮c17;enter⟯ and then ⟮c18;tab/shift tab around⟯ 
Chrome's devtools feature an ⟮c19;element picker⟯, which can be toggled with ⟮c20;⟦⌘⟧ ⟦⇧⟧ ⟦C⟧⟯ 
to have an ⟮c21;element that you select in your devtools be visible in your browser window⟯, ⟮c22;right-click⟯ and then ⟮c23;click <q>scroll into view</q>⟯ 
⟮h∞;<img src="FBb3y3CzDXA5P0sNEuyd.png">⟯

##### styles tab

⟮c3;navigate through⟯ ⟮c1;style declarations⟯ and ⟮c1;selectors⟯ in the styles panel with ⟮c2;tab/shift-tab⟯ 
⟮c4;control-clicking⟯ a ⟮c5;style declaration (e.g. margin: 0.5em⟯) in the styles panel devtools ⟮c6;goes to the line where it was declared⟯ 
⟮c7;shift-clicking⟯ ⟮c8;the box next to a color⟯ in the styles panel devtools ⟮c9;changes its color representation (RGB, HSLA, etc.⟯) 
⟮h∞;<img src="sm_2021-09-16--17-43-33-screenshot.jpg">⟯

##### elements+styles tab

You can ⟮c1;force element state (such as hover, focus⟯) either by ⟮c2;right-clicking the DOM node &gt; force state⟯ and then choosing the state, or by ⟮c3;clicking the :hov button⟯ in the ⟮c3;styles panel⟯ and choosing the state 

###### box model

flex-container:⟮h∞;<img src="sm_2021-09-16--18-04-22-screenshot.jpg">⟯⟮h∞;<img src="sm_2021-09-16--18-03-06-screenshot.jpg">⟯
Hovering over ⟮c1;a part of the box model⟯ in the styles tab will ⟮c2;higlight that relevant thing in the page⟯ 
Besides by normal CSS declaration, you can ⟮c3;change any part⟯ of the CSS box model in devtools by ⟮c4;clicking on the relevant number and setting it⟯ 

##### console

You can access ⟮c2;the currently selected node in the elements inspector⟯ as ⟮c1;$0⟯ in the console in devtools. 
If you ⟮c3;right-click &gt; store as global variable⟯, the DOM element becomes available ⟮c4;as temp1, temp2, etc.⟯ ⟮c5;in the console⟯ 

##### other tabs/panels

Use the ⟮c1;Media⟯ Panel in Chrome DevTools to view information and debug the ⟮c2;media players⟯ per browser tab. 
The ⟮c3;Issues⟯ tab in Chrome DevTools moves the ⟮c4;issues messages⟯ that used to ⟮c5;appear in the console⟯ into their own tab 
The ⟮c6;Coverage⟯ tab in Chrome DevTools can ⟮c5;help you find unused JavaScript and CSS code⟯. 
to use the ⟮c1;Coverage⟯ / ⟮c2;Network⟯ tab, click ⟮c3;the record button⟯, then ⟮c4;reload (or otherwise make network requests⟯) 

##### tab management

to ⟮c1;close a tab⟯ ⟮c2;within⟯ e.g.&nbsp; the ⟮c3;sources⟯ tab, use ⟮c4;alt+w⟯ 
next to the ⟮c5;styles⟯ tab in devtools, there are other tabs, showing you (in order) the elements ⟮c6;event listeners registered⟯, ⟮c7;DOM Breakpoints⟯,&nbsp; ⟮c8;JS properties⟯, and ⟮c9;accessibility information⟯ 
Besides the DevTools tabs ⟮c10;active by default⟯, there are ⟮c11;a bunch more⟯ tabs, which you can ⟮c12;show⟯ via ⟮c13;the command palette⟯, or via ⟮c14;the overflow menu⟯ 

##### global features

Whenever you get a ⟮c1;function⟯ in devtools, you can ⟮c2;go to the place where it's defined⟯ with ⟮c3;right click &gt; show function definition⟯ 

### code review

Code review may be by any other peer or by some authority related to the project (depending on the purpose)
Code review is when another agent analyzes  the source code for bugs/errors/code quality
Code review may be performed by human agents or automated code review tools

### bugs

A regression is something that used to work no longer working.

### solutions

Bodge ≈ kludge
A bodge/kludge is a solution to a problem that is quick to implement but inelegant and hard to maintain.

### testing

#### TDD & self-testing code

TDD|Test-driven development

⟮c1;TDD⟯ necessarily generates ⟮c2;self-testing code⟯
⟮c1;Self-Testing code⟯ is ⟮c2;having built-in tests⟯ for ⟮c3; anything in the codebase (added while writing the things)⟯.
⟮c1;Code coverage⟯ is a measurement of ⟮c2;how much of $unit (e.g. lines, blocks)⟯ are run ⟮c3;when automated tests are executed⟯
for TDD, you first write a test that describes the feature you're wanting to implement
If you want to fix a bug under TDD, first write a test exposing the defect

TDD core loop: 

1. Write unit test for feature
2. Run test, should fail (feature is not implemented
3. Write code
4. Test should now succeed
5. Refactor

#### things used

A test double is a thing that replaces a production thing in testing

#### types of tests

Unit tests test a unit of code (where that might be a module, function or record).
Unit tests are generally quite fast.
Unit tests should never require you to e.g. do special things to your environment.
Unit tests often use test doubles.
End to end testing tests that with a given input, the program will flow correctly and the correct final state will be reached
⟮c3;Integration testing⟯ is testing whether ⟮c1;separate modules⟯ ⟮c2;work together as intended⟯
Integration test can refer to testing only very few modules, the whole system in isolation, or the whole system incl externals, making it very confusing.
Unit tests may be narrowly defined as testing one unit only with test doubles, or more broadly as testing a few units, thus overlapping with the narrow definition of integration tests

## principles

GIGO   Garbage In, Garbage Out
Garbage in, garbage out claims that if the input data is somehow bad ⟮c1;the output data will be too⟯
Syntactic sugar is syntax that makes a programming language easier to use, but ⟮c1;doesn't expand it's functionality⟯
"Anything that can go wrong will go wrong"   Murphy's law
⟮c1;an anti-pattern⟯ is a pattern (intentional or not) that is ineffective/counter-productive 
YAGNI  You/ya ain't gonna need it
In computer programming, ⟮c1;code smell⟯ is a characteristic in code that indicates a deeper problem.
While code smell is often defined to mean :an indication of a problem, it often just means an actual anti-pattern/problem
DRY   Don't repeat yourself
KISS   Keep it simple stupid
"⟮c1;a camel is a horse designed/made by committee⟯" is a ⟮c2;criticism of creating something by comittee⟯, since ⟮c3;the camel symbolises incorporating too many conflicting elements⟯ 

### mech pol

the mechanism   what can be done
the policy   what should be done
separation of mechanism and policy.

## documentation

### methods

Self-documenting code is code that uses names of identifiers and strucutre (rather than comments) in such a way that it is easy for a human to understand what it is doing.
In self-documenting code, identifiers indicate what the thing they are identifying is/does.


#### Comments

Comments in programming are (generally) ignored by compilers/interpreters.
But: Conditional comments are conditional statements interpreted by Microsoft Internet Explorer versions 5 through 9 in HTML source code. They can be used to provide and hide code to and from these versions of Internet Explorer. 
Comments are written primarily for humans
Generally, single line comments go to the end of the line

Single line:
--|lua
//|C#|Java|JS|Rust|SCSS/sass ('silent', will not end up compiling to CSS)
\#|cron|gitignore|hosts|i3 config|Markdown|m3u|Perl|Python|Regex (freespacing mode)|Ruby|sh|TOML|YAML
%|Latex
(?#foo)|Regex
(* foo *)|ENBF

Multiline:
--\[\[foo]]|lua
/\*foo\*/|CSS|C#|Fountain|Java|JS|Rust
&lt;!-- foo -->|HTML
=begin foo =end|Ruby
{% comment %} ... {% endcomment %}|Liquid

Besides comments, fountain has the notion of a note, delimited [[foo]]

#### Documentation generators

A documentation generator is a tool that generates documentation from source code, most commonly taking into consideration the actual source code as well as a special documentation syntax.
Documentation generator syntax is often in the form of a special kind of comment.
Rustdoc is the built-in documentation generator syntax for Rust.
Javadoc is a documentation generator syntax for Java.
JSDoc is a documentation generator syntax based off of and very similar to JS.
ESDoc is a variant of jsdoc that tries to guess more from existing source code.
Assume whatever is true for JSDoc is probably also true for javadoc.
Generally, you can build documentation using a documentation generator using its name as a CLI command.
For rustdoc, you can also use the cargo subcommand doc.
Generally, documentation generators generate HTML websites, often using a certain template as a basis.
Documentation generator config
name|CLI|Config file
jsdoc|y|y

Of the documentation generators, jsdoc also supports a plugin ecosystem.
By default, jsdoc supports HTML in its annotation, with the markdown plugin it instead supports markdown.
JSDOc supports inline tags for annotating things within a thing, however most jsdoc tags are block tags.

jsdoc-comment ::= /** <jsdoc-comment-contents> */
jsdoc-comment-contents ::= ([<jsdoc-description>] {<jsdoc-block-tag>})|<jsdoc-inline-tag>
jsdoc-description ::= <jsdoc-text>{<newline><jsdoc-line-start><jsdoc-text>}
jsdoc-block-tag ::= <jsdoc-line-start><jsdoc-tag><newline>
jdoc-tag ::= @<jsdoc-tag-name>[ \{<jsdoc-parameter-list>\}][ - <jsdoc-description>]
jsdoc-text ::= {<char>}
jsdoc-line-start ::= * # notice the space

jsdoc-inline-tag ::= {<jsdoc-tag>}

In JSDoc, to refer to things that are not in the thing being documented, to prevent ambiguity, namepaths are used.
jsdoc-namepath ::= <entity>{(#|.|-)<entity>}
#|instance member
.|static member
~|inner member (member within an inner scope of something)

@author <name> [\<<email>\>]|identifies the author

Documentation
for the following thing|///|Rust
for the following thing|/**...*/|Java (Javadoc)
for the thing we are in right now|//!|Rust
for the thing we are in right now|"""foo"""|Python (docstring, must be first line in function, technically not a comment but performs similar function)

Rust documentation comments accept formatting in markdown. Code in code blocks there is executed as tests.

### generation

mdBook is a rust crate and command-line tool that produces books from markdown.
mdBook produces books similar to the rust book.
mdBook and docusaurus can easily be deployed to github pages.
docosaurus is a react-based solution for writing documentation via markdown


## requirements engineering

A ⟮c1;user story⟯ is the ⟮c2;explanation of a feature⟯ ⟮c3;from the perspective of the user⟯.
Hofstadter's Law: It always takes longer than you expect, even when you take into account Hofstadter's Law.
Parkinsaw's Law: Work expands to fill the available time
The law of triviality was originally developed as a corollary to parkinsons law.
Law of triviality: people within an organization/community/project typically give disproportionate weight to trivial issues.
Most common example of the law of triviality: the choice of materials for a bike shed taking up a disproportionate time during the construction of a nuclear power plant.
Bike-shedding is discussion that conforms to the law of triviality: Disproportionate discussion about relatively irrellevant issues.


### code quality

Code quality tools such as linters and code formatters often have a CLI but are more commonly used as an extension in IDEs or as some sort of hook/CI pipeline step.

#### linting

A linter flags logic errors, suspicious constructs and violated conventions.
A linter often also includes a code formatter.

yaml|yamllint
css|stylelint
js|ESLint
shell (bash/csh/ksh etc.)|shellcheck

ESLint takes its config from a .eslintrc.js/yaml/json/cjs or from the eslintConfig field in your package.json
in ESlint, to ⟮c2;inherit configs from other files⟯, specify the ⟮c1;extends⟯ key
in ESlint, to use ⟮c2;the default rules⟯, use ⟮c1;extends: eslint:recommended⟯
in ESlint, the things stored in the ⟮c2;settings⟯ key are ⟮c1;global to all ESLint rules⟯
To ⟮c2;extend⟯ ESLint, use ⟮c1;plugins⟯

To prevent eslint or stylelint conflicting with prettier, install eslint-config-prettier or stylelint-config-prettier, respectively

#### code style

nit = short for nitpick
Generally, each project has a certain code style.
A code style is a set of rules for how to format source code.
A code formatter is a program that imposes certain stylistic conventions on the code by formatting it automatically.
Prettier is a code formatter that doesn't allow config, instead imposing opinonated but mostly uncontroversial defaults, thus allowing you to move on with your life.
Prettier works for most languages relevant for web development.
A code formatter can be used together with a linter, however the code formatting functionality of a linter must typically be disabled.

## Modelling

### UML

UML  Unified Modeling Language
UML is a general modelling language most commonly used in the field of software engineering.

#### class

An UML class diagram generally consists of three parts, a class name on top, member variables in the middle, and member methods at the bottom.

flex-container:<img src="sm_220px-BankAccount1.svg.jpg">

#### sequence

⟮h∞;<img src="sm_paste-d8abaabcb6ec43ff8294b3567cb96b4fe4aa48f2.jpg">⟯

A sequencie diagram is an UML diagram showing object interactions as time flows.
In a sequene diagram, the lifelines go from the objects downwards.
In a sequence diagram, a thicker bar on the lifeline means the object is active.
In a sequence diagram, messages between objects are indicated by horizontal lines between the lifelines.
In a sequence diagram, the further down a message, the later it comes
non-filled arrowheads   Async messages
filled arrowheads   synchronous messages
request messages   solid line arrows
Answer messages   dashed arrows


#### object


flex-container:<img src="sm_paste-7a55c6f447e4be8da11b84f2d660fe36fa529dc8.jpg">
Objects in UML object diagrams at least contain a top field with the object name, the class name or both, often they also contain a field below that for instance varaibles

## automation

### misc

The Amazon Mechanical Turk is a service that allows crowdsourcing menial tasks.
The Amazon Mechanical Turk pays way below the minimum wage.
The Amazon Mechanical Turk is sometimes used for study subjects.


## toolchains

In general, a toolchain is a set of software tools used to do something.
In software development, a toolchain is a set of tools used in combination to develop and deploy software.
A task runner is used to run predefined tasks, which would otherwise be tedious or impossible.

expo is a toolchain for react native that does a bunch of toolchainy stuff.
expo is accessed via expo-cli
expo's managed workflow handles pretty much everything but writing code
expo's bare workflow allows you to pick and choose whichc parts of expo to use
to test an app using expo on a phone, you need to install the expo client app on your device
If you want to use the bare React Native workflow, you will have to set up your target's devtools

### language installation & setup

rustup is the rust installer

### dependencies

A dependency is a piece of software another piece of software relies on.

### packages & package managers

Package management is managing packages, i.e. handles installing, uninstalling, updating...
A package manager is a program that does package management.
A package manager typically can manage packages from many different developers.
A package is a file in a package format.
A package format usually is made up of an archive (format) of some kind and some metadata.
Package managers mainly for programming languages tend to do their package management for the local project by default, and only globally for the whole system if explicityly instructed with -g or --global.
Package managers mainly for OS's typically install their packages for the whole system by default, though some have the option for installation in the home directory only, e.g. by using --user.
Package managers are contrasted with installers, which usually install one piece of software only, and do not keep it updated.

#### directory structure

./node_modules|directory for installed packages|npm

#### package manager commands

update|update the package index|apt|brew|DIFFERENT MEANING: bundler, npm
update|update all dependencies/installed packages|bundler|npm
refresh|update all installed packages|snap
exec|execute a script in the current bundle|bundler
upgrade|installs all available updates|apt|brew
install PACKAGE|install a package|apt|brew|npm|DIFFERENT MEANING: bundler
install|install all dependencies in package manifest|bundler|gem
uninstall PACKAGE|uninstall a package|brew|npm
remove PACKAGE|uninstall a package|apt
ls/list|list installed packages|brew|npm
outdated|show a list of outdated packages|brew|npm|bundler
init|set up a new project/package, incl pacakge manifest|bundler|cargo|npm
show FOO|shows information about a package foo (npm); shows path to gem foo (bundle)
show FOO version|show latest version of package foo|npm
pack|create a tarball of a project/package|npm
publish|publish to offical pagckage hub/repository|cargo|npm
edit[ <name>]|open <name> in code editor, or default if none is provided|espanso

#### package manifest & language config file

A package manifest (though different languages call it different things) specifies metadata and config for your package/project as well as dependencies.
A language config file specifies config (e.g. compiler options) for the current programming language.
Package manifest and language config files are often the same thing.
In most package managers, besides the place where you specify your dependencies, there is also a lockfile.
While the package manifest or wherever is where you specify the versions of your dependencies you accept, the lockfile specifies the versions which are actually installed.

Cargo.toml|cargo
package.json|npm|yarn

tsconfig.json|TS


package manifest top-level keys
dependencies|specify dependencies|Cargo.toml|package.json
devDependencies or dev-dependencies|Cargo.toml|package.json
package|general package metadata (author, name etc)|Cargo.toml
none, are all their own top-level keys|general package metdadata (author, name etc)|package.json
main|entry point|package.json

package-lock.json|npm
Gemfile.lock|bundler


##### dependencies

The syntax for dependencies in most package manifests is as key-value pairs, where the value is a semver version.
In rust, instead of the value of a key-value dependency pair being a version, it may also be a table with version as its one of keys, and other optional keys.

###### auto-adding

Some package managers (e.g. npm) will add a package as a dependency if you install/update it, while others will instead install dependencies listed in the package manifest automatically (e.g. cargo), some will do both, and some will do neither.
npms save dependency to package manifest automatically behavior can be disabled with --no-save
Some package managers separate dependencies (for running) and dev-dependencies (for development)
Dev dependencies are usually their own area in the package manifest.
npm allows --save-dev direct installation to dev dependencies via --save-dev




##### rust

specifying features of packages
package-with-features ::= <package-name> = \{ version = "<semver-version-specifier>", features = \["<string>{, "<string>"}\]\}

#### repositories

A repository is anything that stores software.
Often, a repository either stores the code of a VCS, or packages of a certain type.

### project structure

#### rust

./src
./tests
./examples
./benches

### build tools

Build tools are the tools that create an executable application from source code.
A bundler is a tool that merges together all your JavaScript code and its dependencies into one js file, most commonly known as bundle.js
A bundler is a type of build tool.
There are more JS build tools than you can shake a stick at. The most common is webpack.
webpack-cli is the command for administering webpack
Code splitting is the splitting of code into various bundles or components which can then be loaded on demand or in parallel.


### mapping

different tools may perform one or more roles within a toolchain.

Most commonly, the CLI for a framework will also be a build tool.

#### dpkg / apt

apt is the package manager for Ubuntu.
In the past, one would have used apt-get as a way to interface with apt (but now deprecated).
PPA = Personal Package Archive
apt can interact with the four official ubuntu repositories, with PPAs, or theoretically also with third-party repositories
PPAs are repositiories in the conventional sense, but are distinguished by ubuntu from repositories proper in that they are repositories of a single developer published via launchpad (which means the dev doesn't need their own server).
The four types of offical ubuntu repositories are main, universe, restricted and multiverse.
main|canonical-supported FOSS
universe|community maintained FOSS
restricted|proprietary drivers
multiverse|Software restricted by copyright or legal issues
At least some of the repositories of ubuntu are only updated on OS updates, but I have no idea which ones.
to add/remove other repositories/ppas with apt use add-apt-repository (--remove for removing)
apt repositories/ppas are stored in /etc/apt/sources.list(.d)
aptitude is a TUI for apt
apt-cache can be used to query apt's package cache (the local record of packages)

dpkg is a package manager for .deb packages, but does not have a package repository, instead requiring you to download your packages yourself.
apt uses dpkg in the background.

#### rust

cargo is the package manager and build tool for rust.
the official package repository for cargo is crates.io
There is no official task runner for rust, but one commonly used is cargo-make.

#### JS

npm is the most common package manager for JS, followed by yarn. 
The official package hub for npm is the npm Registry.
npm scripts works as a task runner for JS.

#### python

pip is the package manager for python.
The official package hub for pip is PyPI.
The package format for python format .whl ('wheel')

#### anaconda

Anaconda is a batteries-included distribution of Python and R and a bunch of associated packages for scientific computing.
conda is the package manager for the anaconda software distribution.

#### react antive

metro is the bundler for React Native.

#### Latex

In latex the package manager is part of the tex distribution
The two most common latex distributions are ⟮c1;TeX Live⟯ and ⟮c1;MiKTeX⟯
tlmgr is the package manager for tex if you are using the TeX Live distro.
The official package hub for tex is CTAN.

#### espanso

for espanso, its package manager is under `espanso package`
for espanso, `espanso package install` and `espanso package uninstall` may be abbreviated `espanso install` and `espanso uninstall`

#### snap

snap is the package manager for snaps.
snaps are mainly used in Ubuntu, but can be used on many *nixlikes.
snap packages = snaps
snaps are containerized.
snaps are maintained by the snapd daemon.
snap calls its updates refreshes.
snap auto-refreshes four times a day by default.
snap stores most of its stuff in /snap.
snaps are stored in /snap/<snapname>
snaps variable data (such as log files) are stored in /var/snap
snap has a second linux file system in /snap/core, which it mounts in specific places at runtime.
snaps are pacakged by snapcraft.

#### homebrew

homebrew (command: brew) and macports (command: port) are package managers for macos.
homebrew can also be used on linux, and is written in ruby.
tap TAPNAME|add a repository|brew

in ⟮c11;homebrew⟯, a ⟮c1;formula⟯ ⟮c2;describes a package⟯. 
A ⟮c12;formula⟯ is a ⟮c3;ruby (.rb⟯) file. 
Each ⟮c4;tap⟯ has ⟮c5;its own list of formulae⟯, which you can find at ⟮s4-5;⟮c6;tap-name/Formula⟯.⟯ 
A ⟮c13;formula⟯ contains ⟮c7;the location of the tarball of the source⟯, and  ⟮c8;a script that knows how to build the software from the source⟯. 
A ⟮c9;precompiled formula⟯ is known as a ⟮c10;bottle⟯. 
A ⟮c14;cask⟯ is like a ⟮c15;formula⟯, but ⟮c16;it's used to installed native .dmg mac apps instead of cli packages⟯ 
In homebrew, ⟮c17;all formulae⟯ are contained in ⟮c18;taps⟯ (≈ ⟮c19;repositories⟯). 
The ⟮c20;default⟯ ⟮c21;taps⟯ are ⟮c22;homebrew-core⟯ and ⟮c23;homebrew-cask⟯ (for ⟮c24;Casks⟯), and you can ⟮c25;add further 3rd party ones⟯ 

In homebrew, according to the docs, a ⟮c1;Keg⟯ is ⟮c2;the path a formula is installed to⟯, including ⟮c3;the specific version⟯. 
since ⟮c4;Kegs⟯ are ⟮c5;always installed⟯ to ⟮c6;the Cellar⟯ (path e.g. on apple silicon ⟮s6;⟮c7;/opt/homebrew/Cellar⟯⟯), ⟮s8;a Keg has the following syntax (on apple silicon ⟮c8;/opt/homebrew/Cellar/&lt;formulaname&gt;/&lt;version&gt;⟯&nbsp;⟯ 
If something is ⟮c9;keg-only⟯, it is ⟮c10;installed into (/usr/local or /opt/homebrew/ or linux)/Cellar⟯ but ⟮c11;not symlinked anywhere else⟯, often because ⟮c4;the OS already ships with a version that this would conflict iwth⟯ 

⟮c1;homebrew⟯ installs ⟮c12;anything⟯ to ⟮c2;within its prefix⟯. 


    <tr><th colspan="2">homebrew prefixes
⟮c1;macOS Intel⟯|⟮c2;/usr/local⟯
⟮c3;Apple Silicon⟯|⟮c4;/opt/homebrew⟯
⟮c5;Linux⟯|⟮c6;/home/linuxbrew⟯


⟮c13;Where homebrew has its prefixes⟯ mean you ⟮c9;don't need to sudo anything with brew⟯, which is also ⟮c9;highly discouraged.⟯ 
If necessary, ⟮c1;homebrewbrew⟯ ⟮c10;links things⟯ ⟮c14;from its prefix⟯ ⟮c11;into directories such as /usr/local/bin, /usr/local/lib⟯ 

#### ruby

ruby has two package managers, bundler, which mostly does dependency management, and RubyGems with the command gem which mostly does installation.
In ruby, packages are called gems.
The official package hub for RubyGems is rubygems.org
bundler is kinda weird, since it is a ruby gem itself.
bundler manages the gemfile 
The gemfile contains dependencies
the gemfile is just a ruby file
In a gemfile, the first thing is a call to source, which establishes the global source
source is also a method which takes an url as the first and a block as the second argument if you want to establish additional sources
within the gemfile, gem dependencies are defined by `gem <name>, <version>`

#### tools to interact with framewokrs

interact with nextjs|next
interact with jekyll|jekyll

### build tool functionality 

build builds a production build in cargo, jekyll, next
test runs unit tests in cargo
doc builds the packages documentation in cargo
clean remove generated files in cargo, jekyll
lint runs the relevant linter on the project (Nextjs: eslint)
new foo creates a new project foo in cargo, jekyll

Hot reloading reloads a thing as you change the code etc.
serve (for jekyll and webpack) and dev (for nextjs) serve your build with hot reloading 
nextjs serves your app at port 3000 by default
You can run a build you created with build (for nextjs) with start (for nextjs)

Most of the config for frameworks is done in a global config file, which is placed in the project root.
_config.yml/.toml|Jekyll

Browserslist is a tool to define target browsers.
Browserslist is specified in a package.json key, which accepts an array of specifiers, or the keyword "default" for a sensible default.

### boilerplate

Boilerplate code is repetitive code that is reused often, often also implying that it is unneccessary and would be better if it just wasn't necessary.

To set up a default repository with boilerplate, different frameworks/languages have different tools:
react|create-react-app <name>
nextjs|create-next-app <name>
react-native|expo init <name> 
expo init creates a project using expo's managed workflow

cargo-generate is a crate that allows using a pre-existing git repository as a template.
the npm package create-wasm-app adds the command npm init wasm-app which allows us to set up an js app which consumes our rust-generated wasm

### Mobile development

Mobile development is centered around a core IDE, Android Studio for android and XCode for iOs

## deployment

### preventing undesirable experiences

#### canary

Canary release/deployment is showing an early build of an application to only a small subset of users
In canary releases/deployemnt, the users who get the early build are monitered for feedback or bugs.
In canary realeases/deployment, after we've verified that everything's all right for the subset of users, we'll release it to a larger audience eventually if okay.
Sometimes, the distinction is made between a canary release, which is a dedicated version of a program that users could choose to use (e.g. Chrome Canary), and a canary deployment, which is where it is just deployed to a group of people without their input, however, this distinction is often not made.
canary releases/deployements get their name from the canary in the coalmine metaphor

#### blue-green deployment

In a blue-green deployment, there are two environments/servers, blue and green.
blue|existing production environment
green|new version
In a blue-green deployment, initially all users are routed to the blue env. Once the green env is deployed, it undergoes a heavy set of tests. After these pass, the users are instead routed to the green env. The blue env remains on standby, and if there is a problem with the green env, users can get pushed back to the blue env.

#### feature flags 

feature flags (/toggles/switches) are options that allow you to turn functionality on and off without deploying new code, in DevOps contexts generally during runtime.
Feature flags can be used for hiding stuff for cd/ci (the way rust does experimental features), canary releases or user targeting (and thus A/B testing)
Rust hides ⟮c13;unstable/experimental⟯ ⟮c13;features⟯ behind ⟮c14;feature flags⟯, ⟮sb;which you ⟮c15;can only activate⟯ on ⟮c16;nightly⟯⟯. 

# Misc/no place yet

most languages allow an arbitrary amount of spaces and tabs as indentation, YAML however only allows spaces
hot whatever|doing whatever while the system is still running
cold whatever|doing whatever while the system is not running
hot swapping may be of components, or of software

## resource leak

A ⟮c1;resource leak⟯ occurs when a program ⟮c2;does not release resources⟯ when ⟮c3;it no longer nees them⟯. 
A ⟮c4;memory leak⟯ is ⟮c5;a resource leak⟯ involving ⟮c5;memory⟯. 

## Indexing

Most langauges I know start linear collection indices at 0, however lua starts them at 1
In most languages, providing negative indices counts from the back, with -1 being the last element.
Square bracket notation: most commonly used for array/linear collection indexing or accessing members in associative collection, esp. if primitives in language. SCSS/Sass is special in that maps are primitive in the language, but neverthelesss square bracket notation does not work, one must use map-get() (also not map.get, which its documentation still falsely refers to)
any key in a table lua, Ruby, JS, Py, Rust
In most languages, indexing a linear collection outside of its bounds produces an error, in JS it merely produces undefined
In most languages, referring to an associative array element that doesn't exist will get you an error, in Lua and JS you merely get undefined
TS changes referring to a lin col index outside of bounds or a nonextand assoc arr element to an error
JS allows indexing strings via the charAt method.

Dot notation ⟮c1;object⟯⟮c1;.⟯⟮c1;member⟯
Most languages use dot notation for accessing members of records.
Some languages also use dot notation for access of assoc arrays.
In Rust, also tuples are accessed via dot notation, but arrays are not.
dot notation: TOML also 
string keys of tables lua
members of objects in lua
but: not method calls, use : instead

Some languages have a scope resolution operator, which is typically used instead of dot notation for namespace resolution, for calling static members of classes, and for variants of enums.
The scope resolution operator is typically `::`.
The scope resolution operator comes from C++ and is used in ruby, rust.

While JS will not error if you try to access a key or index that is nonexistant, it will return undefined, and if you then try to access something of undefined, it will return an error.
TS makes referring to ⟮c+;nonexistent properties⟯ an ⟮c+;error⟯, rather than ⟮c+;returning undefined⟯
In JS, the ?. is called the optional chaining operator.
In JS, the optional chaining operator works like dot notation, except that if used on a nullish value, it will short-circuit and return undefined.
the optional chaining operator short-circuiting to undefined when after something that is nullish prevents attempted indexing of something nullish, which would otherwise cause an error.
The optional chaining operator can be used instead of dot notation, and before [] notation or method calls.

A lua table can be accessed via dot and square bracket notation. (Perhaps move this to its own thing-access section)
assoc array access []|Python|Ruby|
{}|Perl

## Project Jupyter

⟮c1;Jupyter Notebooks⟯ used to be called ⟮c2;IPython Notebooks⟯
Jupyter notebooks are multimedia documents.
Jupyter notebooks can contain code, markdown test, math, plots, media/images.
Code within Jupyter notebooks are run by kernels.
There Jupyter kernels for a bunch of different programming languages.
The python kernel for Jupyter notebooks is the ipython kernel.
Jupyter notebooks are in fact implemented via json files.
The file type of ⟮c1;jupyter notebooks⟯ is ⟮c2;.ipynb⟯
The Jupyter Notebook App is a server-based application that allows editing and running notebook documents via a web browser.
The Jupyter Notebook App can be executed locally or can be installed on a remote server and accessed through the internet.
Jupyter Notebooks can be edited using many different programs, e.g. the official Jupyter Notebook App, but also VSCode
The thing managing all the Jupyter stuff is Project Jupyter

jupyter supports magic commands starting with % that do a variety of things

%system or ! executes shell commands from jupyter


## misc

https://en.wikipedia.org/wiki/Type_theory#History

Associative arrays: names, literals, other construction methods, etc.

### Computer Ergonomics

Ideally, your ⟮c2;arm (elbow⟯) should have an angle of ⟮c1;90°⟯ while ⟮c6;touch typing⟯ 
Ideally, ⟮c3;your wrist⟯ should be ⟮c4;hovering⟯ while ⟮c5;touch typing⟯ 

## server directory structure

Jekyll & common

./assets|assets
./assets/css|css files
./assets/js|js files

## Metacharacters & escapes 

A metacharacter is a character that has a special meaning to a computer program, such as a interpreter/compiler or a regular expression (regex) engine.
A reserved character is a character that cannot be used in a certain context because it is a metacharacter and thus must be replaced with an escape sequence or a different character, or not used entirely.

An escape character is a metacharacter that invokes an alternative interpretation of the following character(s)
An escape sequence is the combination of an escape character and the subsequent characters that has a specific meaning.
Weirdly, an escape sequence (but not an escape character) is sometimes called a character escape.
In C, \ acts as a/the escape character, with many programming languages having copied this, this includes latex, at least for basic things such as % and &.
C pioneered a set of escape sequences starting with the escape character \ and certan chars/sequences afterwards, which have been widely adopted.
In HTML, & acts as a/the escape character.
Liquid is rare in that escape sequences don't exist at all.
Generally, most languages will require using an escape sequence for their metacharacters, or at least the ones that could have meaning in a given context, this is known as character quoting.
Besides character quoting, escape sequences are often used for characters that cannot (easily) be typed on a keywboard.
Escape sequences for unicode codepoints:
\u + UTF-16 escape sequence (must be a set of two \u + UTF-16 escape  sequence if surrogate pair)|JS
\<unicode-code-point>|CSS
\u<unicode-code-point>|Regex (some flavors)
\u<four-hex-digits>|C-style escape sequence
\U<eight-hex-digits>|C-style escape sequence
\x\{<unicode-code-point>\}|Regex (other flavors)
\u\{<unicode-code-point>\}|JS (ES 6 and beyond)
can be directly input|most programming languages

Escape sequences for ascii characters
octal
\0<octal-digit><octal-digit><octal-digit>|Regex (some flavors)
\<octal-digit><octal-digit><octal-digit>|C-style escape sequence, Regex (some flavors)
\o\{<octal-digit><octal-digit><octal-digit>\}|Regex (some flavors)

alphabetic
\c<character> (ASCII control character (<character>-64))|Regex (some flavors)

hexadecimal
\x<hex-digit><hex-digit>|Regex (some flavors)




HTML has ⟮c1;two ways⟯ of specifying ⟮c2;character escapes⟯. 
Both ways HTML has for specifying character escapes ⟮c3;start with an &amp;⟯ and ⟮c4;end with a semicolon ;⟯.
Of these, ⟮c6;numeric character references⟯ ⟮c7;refer to the character position within character set (most commmonly UTF-8⟯), ⟮sb;they start ⟮c8;with # (after &amp;⟯) and can be specified in decimal or hex. ⟮hb;(for example ⟮c9;&amp;#8203;⟯⟯⟯) 
⟮c10;Character entity references⟯ ⟮c11;have a short, memorable name⟯ ⟮hb;(for example ⟮c12;&amp;amp; or &amp;quot⟯⟯) 
This distinction is however often not made, and often ⟮c13;any name that is a combination of some of the name parts (e.g. HMTL entity, entity reference, character entity⟯) are used. 

to en/decode html character escapes, the npm package and concomittant CLI he is often used.

Character entity reference / Numeric character reference|Displays as / creates?
⟮c16;&amp;gt;⟯|⟮c17;&gt;⟯
⟮c14;&amp;lt;⟯|⟮c15;&lt;⟯
⟮c18;&amp;amp;⟯|⟮c19;&amp;⟯
⟮c20;&amp;shy;⟯|⟮c21;A hyphen that works as a line break, but is only displayed when necessary for wrapping.⟯
⟮c22;&amp;#8203;⟯|⟮c23;A zero-width space that allows the browser to break there, when necessary⟯


## text encoding

### theory

A character is the fundamental unit of text in computing contexts.
In practice, a character is 'anything that has an unicode code point'
A character set is a set of characters grouped for some reason.
A character encoding is a set of mappings of the characters in a character set to some sort of numeric representation.
All character encodings before Unicode mapped characters directly to the binary encoding.
Unicode is a character encoding that maps characters to an abstract unit known as a code point, and then any Unicode translation format are character encodings that map unicode code points to binary rperesentations.
Once a computer has determined which character a byte or set of bytes represents, it pulls the relevant glyph from (simplified view) a font to display it.
If your computer does not have a glyph for a character in any font its willing to use in this situation, it will display something like a box or question mark.

#### font

a computer font is a file containing a set of glyphs for certain characters.
There are two main types of computer fonts, based on how they store characters: bitmap and vector/outline, with the advantages and disadvatages you would expect.

### encodings

character encodings (simplified): Morse -(end of the 19th century)-> Baudot-Murray -(1960s)-> ASCII -2000ish-> Unicode

#### Morse

##### genealogy

The original morse code was meant for english speakers. 
The morse code used today is an overhauled version of the original morse code called international/continental morse code.

##### encoding

Morse code varies signal length to produce different units.
In morse code, a space is signal absence.
In morse code, signal presence may either be a dot or a dash.
In morse code, length is measured relative to the dot length

A dash|three dots
A space (between words)|seven dots
A space (between characters)|three dots
A space (between dots/dashes)|one dot

##### syntax

morse-code-sentence ::= <morse-code-word>{<word-space><morse-code-word>}
morse-code-word ::= <morse-code-character>{<character-space><morse-code-character>}
morse-code-character ::= (<dot>|<dash>)<dd-space>

##### common words

SOS is `. . . - - - . . .`
Notably, SOS does not have character spaces between characters, instead only the one-long necessary space.
SOS = `. . . - - - . . .` indicates that loss of life or major loss of property is imminent.
SOS was chosen because it is easy to recognize.
SOS is widely believed to stand for Save Our Souls, but this is a backronym.

#### baudot

the baudot(-murray) code was a 5-bit binary encoding.
the baudot(-murray) code was later extended to 6-bit (ish) via a FIGS (figure shift character).
With the baudot murray code came the change to punched tape.

#### ASCII

Control characters are also called non-printing characters.
ASCII (no extension) takes up 7 bit.
ASCII characters that are not control/non-printing characters are printing characters.
Control characters as a term is generally reserved for the 65 characters defined in ASCII and extended ascii, other characters such as the zero-width non-joiner may be considered semantically similar, but are called formatting characters.
the first 32 ASCII control characters are exactly 64 bit below the uppercase letters, and so may be represented by letters A-Z plus a few symbols.
In the past the control key would have lowered the sent keycode by 64 to produce the first 32 ASCII control characters; this behavior still exists (albeit emulated) in terminals.
Since the control character is often represented by a caret, and the control key plus letter was/is used to produce ASCII control characters, ASCII control characters are often indicated ^<letter>, this is called caret notation.
Caret notation is commonly used in *nix contexts.
In ASCII, the uppercase characters are 64 above their index in the alphabet.
In ASCII, the lowercase characters are 96 above their index in the alphabet/32 above the relevant uppercase character.
In ASCII the 7th bit will be set for any letter in the alphabet.
In ASCII the 6th and 7th bit will be set for any lowercase letter in the alphabet.
In ASCII the 6th and 7th bit will never be set for any control character within the 128 original characters besides DEL.
0-31|control characters
32-64|various symbols, numbers, etc.
65-90|A-Z
91-96|various symbols
97-122|a-z
123-126|various symbols
127|DEL


The most common escape sequences (not character quoting)
C escape sequence|name|short|hex|alternative meaning
\n|new line|LF|0x0A|any newline character
\r|carriage return|CR|0x0D
\f|form feed|FF|0x0C
\t|(horizontal) tab|HT|0x09
\v|(vertical) tab (may also match any vertial whitespace in some langauges)|VT|0x0B
\b|backspace|BS|0x08
\a|bell|BEL|0x08
\e|escape|ESC|0x1B
\0|null|NUL|0x00
|end of transmission|EOT|0x04

EOT is often interpreted as EOF (which doesn't exist as a control sequence) in the contexts of files.
EOF|end of file

CRLF|Windows|The Internet
LF|Unixlike (Linux and modern mac)
CR|older macs

The bell character is sometimes used in command-line utilities for a notiification sound

#### ISO/IEC 8859

The ISO/IEC 8859 encodings are based on ASCII but take up 8 bits instead of 7, with the extra 128 characters occupied by code pages for different languages

Garbled text due to character encoding errors is called 　文字化（もじば）け, which was common in japanese due to a number of incompatible encodings existing.

#### Unicode

Unicode is goverened by the unicode consortium.

##### Codepoint subdivision 

While in encodings such as ASCII, a character is equivalent to a series of bits, in Unicode a codepoint is an abstract unit that can be realized in different encodings.
The fundamental unit in unicode is a codepoint.
Unicode codepoints are frequently written U+{<hex-digit>}
All unicode codepoints are contained in the unicode codespace.
Currently, about 12% of the unicode codespace is used.
The unicode codespace consists of 17 planes. 
A unicode plane contains 2^16 = 65536 codepoints.
A plane in unicode consists of one or more blocks.
Since unicode blocks are contained within planes, they at most can be the size of a plane, i.e. 2^16=65536
Unicode blocks always sized in multiples of 16, therefore the first hex digit in an unicode block will always end 0, and the last digit will always end F.
Unicode blocks are always contiguous and disjoint with each other.
In general, an unicode block should be united by a common purpose in some way.

###### plane table

0|Basic Multilingual Plane|contains the most common unicode characters, such as most writing systems & symbols
1|Supplementary Multilingual Plane|assortment of different characters and emoji
2|Supplementary Ideographic Plane|bunch of extra, mostly historical/variant CJK characters
3|Tertiary Ideographic Plane|bunch of extra, mostly historical/variant CJK characters
4-13|Currently unassigned
14|Supplementary Special-purpose plane
15-16|Private Use Area planes

All planes beside the basic multilingual plane are supplementary.
Unicode code points outside of the basic multilingual plane are sometimes called astral

##### multiple characters

A 'character' may consist of one or more (encoded) unicode code points.
Some characters can be created both by combining a character with a combining character/mark, or by using an one-codepoint precomposed version.
Combining characters/marks are unicode codepoints that modify other characters, instead of standing by themselves as characters.
Combining characters/marks come after the thing they are modifying.
You can attach many different combining characters to one character at the same time.
Precomposed characters are characters that look like the combination of a character and a diacritic but actually occupy only one codepoint.
é could be a character plus a combining character, or a precomposed character.
Two unicode characters are compatible if they share the same semantics in at least some situation.
U+FB00 (the typographic ligature "ﬀ") and U+0066 U+0066 (two Latin "f" letters) are two characters that are compatible.
Canonical equvalency is a subset of compatibility.
two unicode characters are canonically equivalent if they display the same and have the same meaning.
Two canonically equivalent characters should be treated in the same way by (pretty much) every program.
Unicode normalization takes two texts that are canonically equivalent or compatible and reduces them to the same sequence of codepoints.

##### directionality

In unicode, strongly typed characters have an associated direction (LTR or RTL)
In unicode, characters are strongly typed, or are neutral/weak.
The unicode-bidi algorithm produces directional runs of sequences of characters of contiguous characters with same directionality.
neutral characters become part of the same directional run between two strongly typed characters of the same direction.
In unicode, characters like punctuation, spaces and numbers are weak.
neutral characters between two strongly typed characters of opposite directions become part of the directional run become part of the run in the inline base direction.
<bdo> is for the cases in which you don't want the bidirectional algorithm to anything at all, e.g. if you want to show the order of characters in memory.
<bdi> is for wrapping text whose directionality you can't predict, but which you don't want to absorb neutral characters on other sides.
If one knows the directionality in advance, one doesn't need <bdi> to isolate an element from the bidi algorithm all, one can just add a span or whater with a dir attribute to force the directionality and isolate at the same time.

##### policy

Unicode follows a number of policies
Unicode encoding stability policy|Once a character is encoded, it will not be moved or removed

##### encodings

UTF|Unicode Translation Formats
There are three main unicode encodings: UTF-32, UTF-16 and UTF-8
UTF-32 encodes any codepoint as 4 bytes, and is thus very wasteful for something like latin text.
UTF-8 may take 1-4 bytes to encode a cahracter.

Today, most things default to UTF-8, however a few things such as JS and Java default to UTF-16.

###### UTF-16

UTF-16 consists of 16-bit code units.
An unicode code point encoded with UTF-16 may consist of one or two code units
UTF-16 requires one code unit(s) for things in the BMP, and two code unit(s) for anything else
if UTF-16 needs ⟮c1;two code units⟯, these ⟮c1;two code units⟯ are called ⟮c2;a surrogate pair⟯
In surrogate pairs (UTF-16) the code unit that should come ⟮c1;first⟯ is called the ⟮c2;high surrogate⟯, the code unit that should come ⟮c1;second⟯ is called the ⟮c2;low surrogate⟯
⟮c1;High-surrogate⟯ code units have a hex value ⟮c2;0xD800-0xDBFF⟯

###### UTF-8

UTF-8 guaranteees that there would never be 8 subsequent zeroes, as that could be interpreted as 0x00, which would end an null-terminated string (and thus could produce bugs or even allow injection attacks)
UTF-8 encodes the 128 ASCII characters the same way as ASCII, but with a leading zero (since 8 not 7 bit)
First UTF-8 byte starts|character contains n bytes
0|1
110|2
1110|3
11110|4
Any UTF-8 byte but the first starts 10
To encode a character in UTF-8, first we determine how many bit the character requires, then we set the appropriate first byte header, and then insert the binary code point starting from the less significant end, finally filling up empty spaces with 0s.
7>|1
8-11|2
12-16|3
17-21|4


###### Percent

(near) synonyms: ⟮c1;Percent encoding⟯, ⟮c2;URL/I encoding⟯

To percent-encode a character, use the characters UTF-8 representation, and then percent-encode each byte.
percent-encoded-byte ::= %<hex-digit><hex-digit>

Newline may refer to the newline character or any newline

even?|Is the thing even|Integer
next|get the next element|Integer, String
class|get the class this is an object of|any object
methods|get the methods the object has|any object

An aspect is a cross-cutting concern.
A cross-cutting concerns is a common feature that's typically scattered across methods, classes, object hierarchies, or even entire object models.
Examples for a cross-cutting concern might be logging.

Case-preservation is whether something ⟮c1;stores or disregards case information⟯
Case-sensitivity is whether something ⟮c1;differentiates based on case⟯

## more misc

A bricked device is one that no longer can function at all (has become as useful as a brick)
SKU|Stock Keeping Unit
An instance is something that has been created on some sort of model.

## placeholder images

Placeholder images using kittens|placekitten.com
Placeholder images using boring boxes|via.placeholder.com

via.placeholder.com/⟮c1;width⟯[⟮c2;x⟯⟮c3;height⟯]
placekitten.com/⟮c1;width⟯⟮c2;/⟯⟮c3;height⟯


