# across languages

bold (no importance impl)|\textbf{} (though there are others)|&lt;b>|**text** or __text__
italic (no importance impl)|\textit{}|&lt;i>|*text* or _text_
emphasize (generally via italics)|\emph{}|&lt;em>|N/A
strongly emphasize||<strong>|N/A
underline|\underline{}|&lt;u>|N/A
strikethrough foo (whithout special semantics)|different ones in packages|&lt;s>foo&lt;s>|~foo~ or ~~foo~~ (most md flavors)
hyperlink link with title title|\href{link}{title}|&lt;a href="link">title&lt;/a>|[title](link)
hyperlink link with title link|\url{}|&lt;a href="link">link&lt;/a>|[link](link)
block quotation of foo|quote, quotation, or verse environment|&lt;blockquote>&lt;/blockquote>|<code>>foo</code> or <code>> foo</code> (space after > is optional)
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
title of a cited work||<cite>
preformatted text that is to be presented exactly as written||<pre>

using \url{} or \href{} requires the package hyperref in Latex
package hyperref also does autolinking to things such as the TOC

strike is similar to <s>, but obsolete
<tt> used to indicate teletype text, but is now obsolete
<big> used to indicate big text, but is now obsolete; however <small> still works.
<center> used to indicate centered text but is now obsolete

most text markup languages (HTML, Latex, md) will ignore duplciate spaces.
most text markup languages (HTML, Latex, md) will transform newlines into a single space unless otherwise indicated.


i|italic|conventionally italic
em|italic|more important
b|bold|conventionally bold
strong|bold|super important
u|underline|has non-textual annotation of some kind
mark|yellow highlighter|highlighted ≈ area of interest
 

non-breaking space|\nonbreakspace or ~|&amp;nbsp;
ampersand||&amp;amp;
non-breaking hyphen|"~
soft hyphen|\- (only hyphtenates in indicated location) "- (allows hyphenation in other places in the word)|&amp;shy;
"=
if you want a word {{c3::with a hyphen}} to be {{c2::able to be split anywhere}} (using babel ngerman), use {{c1::"=}}

hyperref|create links automatically and \href, \url commands


nested blockquotes| <code>>></code> or <code>> > </code>(space after > to begin blockquotes is optional)

Pandoc md is a superset of most other markdown flavors
Pandoc md defaults to tilde-delimited code blocks.
In pandoc md, you can specify heading identifiers to contain things such as classes, ids, etc
pandoc-md-heading ::= #{#} <title> [\{{<class>|<id>|...}\}]

# SGML/XML/HTML

SGML stands for Standard Generalized Markup Language.
XML is a subset of SGML.
XML|Extensible Markup language
HTML was originally based on SGML, though the relationship has sometimes been fraught.
Since XML is a subset of SGML and HTML is based on it, HTML and XML share similarities in syntax.

SGML/XML/HTML <dfn>tags</dfn> are delimited by &lt;...&gt;
SGML/XML/HTML end tags additionally feature a / to look like &lt;.../&gt;
An SGML/XML/HTML <dfn>element</dfn> is everything from an elements start tag to an elments end tag.
An SGML/XML/HTML element has an <dfn>element name</dfn>.
An SGML/XML/HTML elements start and end tag feature its name: &lt;foo&gt; ... &lt;/foo&gt;.
SGML/XML/HTML elements are begun by a <dfn>start tag</dfn> and ended by an <dfn>end tag</dfn>, unless they are self-closing.
SGML/XML/HTML element consist of start tag, content, and end tag.
SGML/XML/HTML elements' <dfn>content</dfn> is either text or other elements ('child elements').
SGML/XML/HTML content goes between the start and the end tag.
<dfn>Empty elments</dfn> are created by (or a synonym to) self-closing tags.
Self-closing tags in SGML/XML/HTML only consist of a start tag.
Self-closing tags must end /&gt; in XML.
Self-closing tags may end /&gt; or merely &gt; in HTML.
Using a closing tag for self-closing tags is usually invalid.
Empty elements cannot have content, since there is nowhere to put it.
Some HTML elements that are not empty (not self-closing) nevertheless may omit their end tag, an end tag will instead be inserted automatically when necessary.

Whitespace within tags is usually ignored, as long as its not within a tag name or attribute
an HTML element name may only 

SGML/XML/HTML attributes are placed in the start tag.
SGML/XML/HTML attributes have the syntax key="value".
HTML attribute values may be unquoted if they do not feature whitespace and a few reserved characters.
HTML features boolean attributes: attributes which <em>may not</em> take a value, but whose presence or absence represnets true or false.
HTML also features enumerated attriubtes: attributes that take a fixed set of values.
Confusingly, some HTML attributes with boolean semantics are not boolean attributes, but instead enumerated attributes, mostly with the possible values "yes" and "no" or "true" and "false".

SGML/XML/HTML element names may be in any case.
in HTML, putting element names in all lower case is common.
XML element names may contain any unicode with the exception of some metacharacters.
HTML and SVG built-in element names only contain characters a-z.
HTML custom elements must start with a character a-z in lowercase, must contain at least a hyphen character, but otherwise may contain any unicode.

SGML/XML/HTML documents contain exactly one root element. All other elements are contained in the root element.
The SGML/XML/HTML root element has the same name as the relevant language (i.e. html for html, xml for xml, svg for svg)

The document prolog (if you use one) comes at the top of the document, before the root element. There are two parts (both optional): an XML declaration and a document type declaration.

## declaration

the {{c1::XML declaration}} {{c2::contains information about the coming xml document}}. 
the {{c19::XML declaration}}  is {{c3::optional}}, {{c3::but if it appears}}, it must appear in {{c4::the first line of the document}}. 
the {{c20::XML declaration}} takes {{c5::three}} parameters:
<div class="c1-5-scr c12-18-scr">
 <table>
  <tbody><tr>
    <td><code>{{c6::version}}</code></td>
    <td>{{c9::The XML version the document is using}}</td>
  </tr>
  <tr>
    <td><code>{{c7::encoding}}</code></td>
    <td>{{c10::The text encoding this is using, e.g. UTF-8 or Shift_JIS}}</td>
  </tr>
  <tr>
    <td><code>{{c8::standalone}}</code></td>
    <td>{{c11::Whether the document relies on an external source such as an external DTD}}</td>
  </tr>
  </tbody>
  </table>
</div>
<p class="c1-11-scr">Of these, <code>{{c12::version}}</code> is {{c13::mandatory}}. It's syntax is:</p>
<div class="c1-11-scr"><pre><code>{{c18::&lt;?xml}} {{c14::version=}}"1.0" {{c15::encoding=}}"UTF-8" {{c16::standalone=}}"no" {{c17::?&gt;}}
</code></pre></div>

## doctype

A document type declaration, or doctype, is an instruction that associates a particular XML or SGML document (for example, a webpage) with a document type definition (DTD).
A document type declaration must be the first thing in the page if HTML.
A document type declaration must be the first thing after the XML declaration if XML
The syntax of a doctype declaration is &lt;!DOCTYPE somestuff&gt;
In HTML 5, the doctype no longer actually references a DTD, but merely prevents the browser from switching into quirks mode.

## PI

PI|Processing instruction


## HTML

### General structure

An HTML document is started by the &lt;html&gt; tag and ended by the &lt;/html&gt; tag.
a &lt;html&gt; element consists of a &lt;head&gt; section and a &lt;body&gt;

### elements

#### <head>

The &lt;head&gt; in HTML contains metadata about the document.
it can contain:
the &lt;title&gt; element, which defines the documents title
the &lt;title&gt; element is mainly shown in the browsers tab name / title bar, as well as search engines.
the &lt;title&gt; element can only contain text, not tags.
the &lt;title&gt; element's content should change in response to major state changes.

the <base> element specifies the base URL for the document with its href attribute.
The <abse> element optionally accepts a target argument to choose the browsing context links open in by default.
The <basefont> element used to specify the default font (color, fontface etc.) but is now deprecated.

##### <meta>

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

#### various inline text

The abbr HTML element represents an acronym or abbreviation.
There used to be an <acronym> element which was obsoleted in favor of <abbr>
The thing an abbr element is short for may either be explained in the text or specified in a title attribute.
<dfn> represents defining instance of a term
The <p> element, the <dt>/<dd> pairing, or the <section> element which is the nearest ancestor of the <dfn> is considered to be the definition of the term.
If the <dfn> element has a title attribute, the value of the title attribute is considered to be the term being defined. The element must still have text within it, but that text may be an abbreviation (perhaps using <abbr>) or another form of the term.
If the <dfn> contains a single child element and does not have any text content of its own, and the child element is an <abbr> element with a title attribute itself, then the exact value of the <abbr> element's title is the term being defined.
Otherwise, the text content of the <dfn> element is the term being defined. 

#### Media

&lt;video&gt; and &lt;audio&gt; embed a video/audio media player.
Both HTMLVideoElement and HTMLAudioElement inherit from HTMLMediaElement.
The {{c1::HTMLMediaElement}} has a bunch of properties, amongs others

<table>
<tbody>
<tr>
<td>((c:2;::muted))</td>
<td>((c:7;::audio is muted/mute audio))</td>
<td>IDL & Content</td>
</tr>
<tr>
<td>((c:3;::paused))</td>
<td>((c:8;::is paused/pause))</td>
<td>IDL</td>
</tr>
<tr>
<td>((c:5;::loop))</td>
<td>((c:10;::will loop/loop))</td>
<td>IDL & Content</td>
</tr>
<tr>
<td>((c:5;::controls))</td>
<td>((c:10;::is showing controls/show controls))</td>
<td>IDL & Content</td>
</tr>
<tr>
<td>((c:5;::autoplay))</td>
<td>((c:10;::will autoplay/enable autoplay))</td>
<td>IDL & Content</td>
</tr>
<tr>
<td>((c:4;::ended))</td>
<td>((c:9;::Indicates whether it has finished playing))</td>
<td>IDL</td>
</tr>
<tr>
<td>((c:6;::playbackRate))</td>
<td>((c:11;::Represents the speed at which the thing is playing))</td>
<td>JS</td>
</tr>
</tbody>
</table>

You may define a single source for &lt;video&gt; or &lt;audio&gt; via a src element.
You may define multiple sources for &lt;video&gt; or &lt;audio&gt; via child &lt;source&gt; elements.
&lt;track&gt; defines text tracks for media elements (&lt;video&gt; and &lt;audio&gt;)

the poster attribute for video specifies a URL for an image to be shown while the video is downloading. 
If the poster attribute for <video> isn't specified, nothing is displayed until the first frame is available, then the first frame is shown as the poster frame.

##### track

track has a default attribute to indicate that this is a default track
track has a kind attribute to indicate its purpose
track kinds: captions, chapters, descriptions, metadata, subtitles

#### images

<img> is used for including images

The picture element contains 0 - ∞ source elements and one <img> element.
The <img> child of <picture> is there to act as a fallback and to give the picture its dimensions.

##### srcset 

srcset-values ::=  <srcset-specifier>{, <srcset-specifier>}
srcset-specifier ::= <url> <integer>w
sizes-values ::= <sizes-specifier>{, <sizes-specifier>}
sizes-specifier ::= <media-query> <resolution-length-percentage>

scrset specifies a list of sources and their actual sizes, while sizes declares a set of media condition and what width the image should be in that case (width as in resolution, not width of the  box). The browser then picks the closest one, but preferring ones that are too large than too small.
If no sizes is provided, the browser chooses one of scrset based on which is closest to the viewport width (essentially just assuming that the image wlll be 100 vw)

#### source

the type (a MIME type) of a &lt;source&gt; element is specified via the type attribute, or else the browser will check the MIME type in the HTTP header.
The lists of <source>s for <picture>, <video> and <audio> represents a priority hierarchy - the browser will take the first one that matches.
Conditions that <source>s may have are the type and media attributes
&lt;source&gt; elements for audio/video take their URL in a src attribute; &lt;source&gt; elements for picture take their URL in a srcset attribute

#### Headings

&lt;h1&gt; to &lt;h6&gt; define headings.
It is an antipattern to skip heading levels between &lt;h1&gt; and &lt;h6&gt;
There may only be one &lt;h1&gt; per page, which should describe the overall purpose of the page.
Skipping heading levels between &lt;h1&gt; and &lt;h6&gt; results in bad accessibility and SEO heading levels
Based on h1 to h6 (and nothing else, sadly), the browser generates a document outline 
There was a push to generate the document outline dynamically from nested semantic containers, but this was never implemented.

#### del and ins 

The &lt;del&gt; HTML element represents text that has been deleted from a document.
The &lt;ins&gt; HTML element represents text that has been added to the document.
The &lt;del&gt; and &lt;ins&gt; elements are often used for purposes such as tracking changes or source code diffs.

#### progress and meter

A progress bar shows the progress of a task via a bar that becomes fuller as the task nears completion.
In HTML, a progress bar can be indicated by &lt;progress&gt;
In HTML, meter generally displays as a bar of varying fullness.
In HTML, meter supposedly represents a scalar value within a known range.
In HTML, progress only accepts max and value as attributes, reflecting the semantics of the completion of a task.
The min and max attributes specify the minimum/maximum value and are allowed on certain types of <input>s as well as <meter> and max also on <progress>
The low, high and optimum attributes may only be specified on <meter>
In HTML both progress and meter support a fallback text value within their tags.

#### tables

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

#### canvas

The <canvas> element allows drawing graphics and animations via the canvas scripting API or the WebGL API
Sizing the canvas using CSS versus HTML

The displayed size of the canvas can be changed using CSS, but if you do this the image is scaled during rendering to fit the styled size, which can make the final graphics rendering end up being distorted.

It is better to specify your canvas dimensions by setting the width and height attributes directly on the <canvas> elements, either directly in the HTML or by using JavaScript.

#### map

<map> defines an image map, within which <area> defines clickable areas.
<map> takes a shape attribute with the possible values circle, poly, rect.
The shape of a map with a given shape attribute is specified by the coords attribute
You refer to a map via its name attribute included in an <img> usemap attribute prefixed by #

#### links

The content between the tags should be descriptive of what the link does.

The <link> HTML element specifies relationships between the current document and an external resource. This element is most commonly used to link to stylesheets, but is also used to establish site icons (both "favicon" style icons and icons for the home screen and apps on mobile devices) among other things.

The rel attribute defines the relationship between a linked resource and the current document. Valid on <link>, <a>, <area>, and <form>, the supported values depend on the element on which the attribute is found.

rel=opener/noopener create a top-level browsing context that is/is not a auxiliary browsing context if the hyperlink would create either of those, to begin with (i.e., has an appropriatetargetattribute value).
rel=nofollow indicates that the current document's original author or publisher does not endorse the referenced document.
rel=noreferrer: No HTTP Referer header will be included. Additionally, has the same effect as noopener.	 

##### <link>

rel="icon"|specifies an icon representing the current document
rel="stylesheet"|indicates a stylesheet for the document

If rel="icon", the sizes attribute of link specifies which sizes are applicable.
link-sizes-values ::= any|(<size-spec>{ <size-spec>})
size-spec ::= <width>(x|X)<height>

the type attribute of <link> specifies the mime type of the resource; however this is generally omitted except for rel="icon"

##### hyperlinks

The two elements that create hyperlinks are <area> and <a>.
use the attribute href for <area> and <a> to specify an URL of the links target.
The target attribute of <area>/<a> specifies in which browsing context to open the link.
_self|current browsing context
_blank|new window/tab
_parent|parent browsing context
_top|root node browsing context
for <form>, the target attribute represents where to display the response after submitting the form  

###### a

the download attribute of <a> Prompts the user to save the linked URL instead of navigating to it. 
the download attribute of <a> Can be used with or without a value.
the download attribute of <a> used without a value will prompt the browser to suggest a file type.
the download attribute of <a> used with a value will prompt the browser to save it with the specfied name as a prefilled suggestion.

#### forms


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

##### form itself

A <form> element represents a form.
the method attribute of form accepts post|get|dialog.
post/get|use the POST/GET methods
// for dialog see <dialog>
The action attribute for form specifies the URL to which the form should be submitted.
Forms may not be nested.

##### fieldset

A <fieldset> is an HTML element used to group multiple inputs (and their labels)
The first child of a fieldset may be a <legend> (this is the only place it may appear), which captions its parent fieldset

##### button

The <button> HTML element represents a clickable button
the type attribute for <button> represents the default functionality
submit|submit form data to server
reset|reset form data
button|no default behavior, must manually be implemented

##### textarea

textarea represents a multiline text input field
textarea is not an empty element, and in fact the content can be used to provide a default value.

##### label

A <label> provides a caption/label for a thing, most commonly an <input>
There are two ways of associating an <input> with a label, either nest the input within the label, or set the for attribute of the label to the id of the input.

##### input

specifying the value property of an input element in HTML sets its initial value.
As the state of <input>s changes, the value property in JS is updated.
The validation states of an input are contained in the ValidationState API and corresponding property./

###### types

type="color" for colors
type="hidden" does not show the control, but still submits the data.

####### radio & checkbox

A radio button is a graphical control element that allows the user to choose only one of a predefined set of mutually exclusive options. 
In HTML, a radio button is realized by <input type="radio">
In HTML, multiple radio buttons are linked by assigning them the same number.
radio and checkbox input accept the attribute checked to specfiy if they are checked


Bootstrap:

.form-check # set of radio buttons
.form-check-label   define a label for a checkbox/radio button
.form-check-input   define a checkbox/radio button

####### text

&lt;input type="text"&gt; is single-line only
There are a set of input types that act similarly text, but force a certain type of validation and change the soft keyboard/add input helpers, similar to inputmode:
time-related: date, datetime-local, month, time, week
number: number
other: email, password, tel, search, url
On any text-like input which is not time-related and not 'number' as well as on textarea, you may specify the minlength and maxlength attributes to contstrain the amount of UTF-16 code units.
On any non-time-related, non-number text-like input, you may specify the attribute pattern, providing a regex against which to match the input.
most text-only input fields may have the readonly attribute specfied, which shows the inital value but doesn't allow the user to modify it
the time-related and number text-like inputs plus range accept a step argument.

####### file

inputs of type file accept an attribute accept (lol) which takes a CSL of unique file type specifiers
an unique file type specfier is either a filename extension starting with a period, or a valid MIME type.
valid for the file input type only, the capture attribute defines which media—microphone, video, or camera—should be used to capture a new file for upload with file upload control in supporting scenarios.

####### image

Input type image supports the attributes <img> supports, in addition to the usual ones of input.
When clicked, input type="image" behaves like submit, but also sends the coordinates of the area being clicked.
The coordinates of an input type="image" will be submitted as <name>.x=<coord>&name.y=<coord>

####### submit

###### attributes

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

#### select, option

The <select> HTML element represents a control that provides a menu of options:
The <option> HTML element is used to define an item contained in a <select>, an <optgroup>, or a <datalist> element. 
The <optgroup> HTML element creates a grouping of options within a <select> element.
to set the default option, specify the selected attribute on the option.

#### output

The <output> HTML element is a container element into which a site or app can inject the results of a calculation or the outcome of a user action.
<output> are often used within forms, however tehy are not submitted with the form.

#### script

to include an external script, set the src attribute of the <script> element to its URL
the <noscript> tag is for displaying content if the browser does not support JS

#### Ruby 

ruby text/characters are small annotative glosses placed on the top or to the right of characters.
Ruby text/characters is called furigana in japanese.
In HTML, ruby text is delimited by the &lt;ruby&gt; tag
In HTML ruby annotation, the syntax is &lt;ruby&gt;lowertext&lt;rt&gt;uppertext&lt;/rt&gt;&lt;/ruby&gt;
In HTML, one may designate fallback delimiters for the upper text. 
Ruby fallback delimiters are enclosed in &lt;rp&gt; tags, and go before and after the &lt;rt&gt; delimited uppertext.

#### aside

An aside (there is no agreed-upon term, so I'm using the term that HTML uses) is a part of the main content thats only partially related to the main content, and often placed outside of the main flow. 
A pull quote is an aside that is a quote from the article.

#### figure

In general, figures are images/diagrams/similar with a caption.
In general, figures float (in the general sense).
In HTML, the <figure> element specifies its caption with <figcaption>

#### float

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

<br>---<br>
  §§ In contrast to ((c:10;::CSS)), in ((c:10;::Latex)) ((c:11;::floats)) merely ((c:12;::move vertically and not horizontally)). §<br>
§§ If possible, latex places ((c:13;::floats)) ((c:14;::close to where they appear in the source text)). §<br>
§§ ((c:15;::Floats)) are relevant for ((c:9;::things that cannot be broken over a page (images, tables))). §<br>
§§ To ((c:16;::uniquely identify)) ((c:17;::floats)) no ((c:18;::matter where they end up)), they are ((c:19;::numbered)) by latex. §<br>
§§ By default, ((c:20;::table)) and ((c:21;::figure)) are the two ((c:22;::environments)) that are ((c:23;::floats)). §<br>
§§ The ((c:24;::table environment)) is ((c:25;::functionally equivalent to)) the ((c:26;::figure environment)), but ((c:27;::has a separate index of numbering)). §<br>
===<br>

<br>---<br>
  §§ The ((c:28;::[option])) for ((c:29;::table, figure)) says ((c:30;::where roughly you would like the table/figure to float.)) §<br>
§§ ((c:31;::the option for controlling where a floating element)) goes consists of ((c:32;::a list)) of specifiers, which are ((c:33;::single chars)) ((c:34;::one after the other)) without ((c:35;::separators)), indicating ((c:36;::relative preference)) §<br>
===<br>

<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th></th>
    <th></th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:1;::h))</td> <td>((c:2;::place where it appeared in the source text as much asp possible))</td></tr>
<tr><td>((c:3;::H))</td> <td>((c:4;::force place where it appears (basically turn it into a nonfloat)))</td></tr>
<tr><td>((c:5;::p))</td> <td>((c:6;::special page for floats only))</td></tr>
<tr><td>((c:7;::t/b))</td> <td>((c:8;::place at top / bottom of page (respectively)))</td></tr>
  </tbody>
</table>

<br>---<br>
  §§ the ((c:37;::float)) package ((c:40;::improves)) ((c:38;::float handling)) and ((c:40;::defines)) ((c:39;::the float specifier H)) §<br>
===<br>

<br>---<br>
  §§ If you have ((c:41;::a table (tabular))) where you want to make sure it ((c:42;::flows well and does not cause awkward page breaks)), you should ((c:43;::float it (surround it in a table env) )), but if ((c:44;::you care exactly where it appears in relation to the source text)), you should ((c:43;::not float it (not surround it in a table env))) §<br>
===<br>

<br>---<br>
  §§ ((c:45;::\caption{foo))} is there to ((c:46;::add a caption foo)) to ((c:47;::floating environments)). §<br>
§§ ((c:48;::the optional argument [])) to ((c:49;::\caption)) takes ((c:50;::a short title)) for use ((c:51;::in the listoftables/figures)) §<br>
§§ to ((c:52;::\label)) a ((c:53;::table/figure)), the ((c:52;::\label)) must go ((c:54;::directly after \caption)) §<br>
===<br>

<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}{{c28::}}{{c29::}}{{c30::}}{{c31::}}{{c32::}}{{c33::}}{{c34::}}{{c35::}}{{c36::}}{{c37::}}{{c38::}}{{c39::}}{{c40::}}{{c41::}}{{c42::}}{{c43::}}{{c44::}}{{c45::}}{{c46::}}{{c47::}}{{c48::}}{{c49::}}{{c50::}}{{c51::}}{{c52::}}{{c53::}}{{c54::}}</span>

#### data

<data> represents things that have a machine-readable translation
<time> represents a time/date/duration.

#### Lists

In HTML and Latex, ordered and unordered lists are surrounded with something different, but use the same list items.
Latex uses the same list items for description lists also, while HTML uses different elements for those.
by default, latex only allows the nesting of lists to a depth of four

ordered list|enumerate environment|&lt;ol>
unordered list|itemize environment|&lt;ul>
description list|description environment|&lt;dl>
list item|\item|&lt;li>
Term in a description list with title foo and description/explanation bar|\iten[foo]bar|&lt;dt>foo&lt;/dt>&lt;dd>bar&lt;/dd>

<br>---<br>
  §§ In markdown ((c:1;::Lists items)) are each ((c:3;::started by)) ((c:2;::one or more symbols)), while lists themselves are delimited by nothing more than any block-level item.. §<br>
§§ ((c:4;::ordered list items)) are started by ((c:5;::&lt;n&gt;. (e.g. 1. or 7.))). §<br>
§§ it does not matter ((c:6;::with which digit you number list items with (e.g. even if you do <code>21. foo\n2. bar)</code>))&nbsp;they will ((c:7;::always start one and go from there (or whatever you then change it to via css))). §<br>
§§ ((c:8;::unordered list items)) are started by ((c:9;::-)), ((c:9;::*)) or ((c:9;::+)), which can be ((c:10;::mixed and matched)). §<br>
===<br>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}</span>

#### containers

div and span are 'pure' container without any semantics.
the difference between div and span is that div is by default block-level (display: block flow) and that span is by default inline (display: inline flow)

##### dialog

The dialog element rerpesents a dialog box container semantically.
The dialog element has a boolean attribute open representing whether the dialog should be shown or not.
<form> elements can close a dialog if they have the attribute method="dialog". When such a form is submitted, the dialog closes with its returnValue property set to the value of the button that was used to submit the form.

##### semantic containers

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

#### inline nonhtml

&lt;style> allows including CSS inline, by including it as content
&lt;script> allows including JS or other scripting languages inline, by including it as content

#### deprecated elements

<menu> was supposed to be a semantic alternative to <ul> for menus, but is now deprecated
<menuitem> was meant to be a child of <menu> if <menu> was a context menu, but is now deprecated.
<dir> was supposed to be a semantic alternative to <ul> for directories of files and folders, but is now deprecated.
<keygen> was an element to facilitate the generation of keys for data transfer, esp. with forms, but is now deprecated.
<font> was an element to style text, but is now deprecated.

### content categories

Most HTML elements are a member of one or more content categories — these categories group elements that share common characteristics. This is a loose grouping (it doesn't actually create a relationship among elements of these categories), but they help define and describe the categories' shared behavior and their associated rules.

Flow content
Flow content is a broad category that encompasses most elements that can go inside the &lt;body> element.

Heading content is a subset of flow content that includes h1-h6, and theoretically though not relevantly the never-implemented the-spec-is-lying-about-it hgroup
Sectoning content is a subset of flow content that was supposed to be relevant for the outline algorithm that was never implemented, and so is a somewhat-irrelevant category.

Phrasing content is a subset of flow content that defines the text and the markup it contains, and can be used everywhere flow content is expected. 

Content is palpable when it's neither empty or hidden; it is content that is rendered and is substantive. Elements whose model is flow content should have at least one node which is palpable.

#### embedded content

Embedded content is a subset of flow content that imports another resource or inserts content from another mark-up language or namespace into the document, and can be used everywhere flow content is expected.

embedded cotnetn cotnains the media elements video and audio, image-related elements img, picture, and svg, math, frames, canvas, object, embed plus the obsolete elements applet

<applet> was used to embed java applets, but is now obsolete.
The <object> HTML element represents an external resource, which can be treated as an image, a nested browsing context, or a resource to be handled by a plugin.
The <param> HTML element defines parameters for an <object> element.
The <embed> HTML element embeds external content at the specified point in the document. This content is provided by an external application or other source of interactive content such as a browser plug-in.

&lt;math> and &lt;svg> embed content in HTML from MathML and SVG respectively

### JS interface

any HTML element has a JS interface that is called HTMLSomeelementnameElement.

An IDL (Interface Description Language) is a generic language used to specified objects' interfaces apart from any specific programming language.

In HTML, most attributes have two faces: the content attribute and the IDL attribute.

The content attribute is the attribute as you set it from the content (the HTML code) and you can set it or get it via element.setAttribute() or element.getAttribute(). The content attribute is always a string even when the expected value should be of a different type.

the IDL attribute may be accessed from js like element.foo.

Any content attribute is also acessiable as an IDL attribute.

### Common attributes

the <code>datetime</code> attribute specifies the date and time associated with the element
<code>datetime</code> is an attribute taken by &lt;del&gt;, &lt;ins&gt;, and &lt;time&gt;

The <code>cite</code> attribute provides an URI that points to the source of a quote or change.
The <code>cite</code> attribute can be used on &lt;blockquote&gt;, &lt;q&gt;, &lt;ins&gt;, &lt;del&gt;

The HTML autocomplete attribute lets web developers specify what if any permission the user agent has to provide automated assistance in filling out form field values, as well as guidance to the browser as to the type of information expected in the field.
The autocomplete attribute can be used on inputs that take a text-like value, textarea elements, select elements and form elements.
The Boolean disabled attribute, when present, makes the element not mutable, focusable, or even submitted (if in a form).
The disabled attribute is supported by <button>, <command>, <fieldset>, <keygen>, <optgroup>, <option>, <select>, <textarea> and <input>.
The value attribute specifies the value of a thing.
If the value attribute of an element is pre-filled, it generally appears as a default.

content within <video>/<audio>/<canvas> is shown as a fallback for browsers that don't support the element.


#### Global attributes

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
&nbsp;{{c1::tabindex}}{{c2::=0}} indicates that {{c3::an element can be focused}} (e.g.&nbsp;{{c4::by the tab key}})
&nbsp;{{c1::tabindex}}{{c2::=-1}} indicates that {{c3::an element can <b>not&nbsp;</b>be focused}} (e.g. by {{c4::the tab key}})
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

##### text editing only

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

# environment ≈ Web APIs

## browsing contexts

A browsing context is the environment in which a browser displays a Document. 
A browsing context may be a tab or a window as well as a frame (iframe/frame)
A browsing context has a corresponding WindowProxy object.
A WindowProxy object acts as a interface for the Window object of a browsing contexts active Document.
A browsing context has an opener browsing context, which is null or a browsing context. It is initially null.
A browsing context has a disowned boolean. It is initially false.
A browsing context has an is closing boolean. It is initially false.

It is possible to create new browsing contexts that are related to a top-level browsing context without being nested through an element. Such browsing contexts are called auxiliary browsing contexts. Auxiliary browsing contexts are always top-level browsing contexts.

An auxiliary browsing context has an opener browsing context, which is the browsing context from which the auxiliary browsing context was created, and it has a furthest ancestor browsing context, which is the top-level browsing context of the opener browsing context when the auxiliary browsing context was created.
The opener attribute of Window returns the WindowProxy object of the opener broswing context, if extant/available.

## session history

Each browsing context has a session history.
A session history conttains the Document objects that the browsing context has presented, is presenting, or will present. 

## window

the Window object has a few properties representing certain UI elements (all bars), all represented by a BarProp object with the single attribute 'visible'
BarProps: locationbar, personalbar, menubar, crollbars, statusbar, toolbar

### intervals

{{c1::window}}.​setTimeout(function, delay, args);


## the DOM

DOM|Document Object Model
The DOM is a tree data structure that acts as an interface for a XML or HTML document.
DOM vertices are `Node`s.
`Node` implements the EventTarget interface, so all things inheriting from Node also do.

### Nodes

#### NodeLists

A NodeList is similar to an Array, but doesn't have all the methods.
A NodeList is a linear collection of nodes.
NodeList has a foreach method
NodeLists can be live or static.

#### types of

<table>
  <tbody>
    <tr>
      <th colspan="5"><span class="c9-cloze">Node</span></th>
    </tr>
    <tr>
      <td>others...</td>
      <td>
        <table>
          <tbody>
            <tr>
              <th colspan="3"><span class="c12-cloze">Element</span></th>
            </tr>
            <tr>
              <td>others...</td>
              <td><span class="c10-cloze c12-scr">HTMLElement</span></td>
              <td><span class="c11-cloze c12-scr">SVGElement</span></td>
            </tr>
          </tbody>
        </table>
      </td>
      <td>
        <table>
          <tbody>
            <tr>
              <th colspan="2"><span class="c8-cloze">Document</span></th>
            </tr>
            <tr>
              <td><span class="c6-cloze c8-scr">HTMLDocument</span></td>
              <td><span class="c7-cloze c8-scr">XMLDocument</span></td>
            </tr>
          </tbody>
        </table>
      </td>
      <td><table><tbody><tr><th><span class="c5-cloze">DocumentFragment</span></th></tr></tbody></table></td>
      <td>
        <table>
          <tbody><tr>
            <th colspan="3"><span class="c1-cloze">CharacterData</span></th>
          </tr>
          <tr>
            <td><span class="c2-cloze c1-scr">Text</span></td>
            <td><span class="c3-cloze c1-scr">Comment</span></td>
            <td><span class="c4-cloze c1-scr">ProcessingInstruction</span></td>
          </tr>
        </tbody></table>
      </td>
    </tr>
  </tbody>
</table>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}</span>

#### Elements

element.innerHTML|content between the tags
The Element.classList is a read-only property that returns a live DOMTokenList collection of the class attributes of the element

##### HTMLCanvasElement

The HTMLCanvasElement.toDataURL(type) method returns a data URI containing a representation of the image in the format specified by the MIME type in the type parameter.

### DOM traversal

document.querySelector(selector)|get first element that matches selector
document.querySelectorAll(selector)|get NodeList of elements that matches selector
qs and qsa can be called on document for a global search, or on an element for a search only on that elements children.
document.getElementById()


### other interfaces & classes

#### DOMTokenList

The DOMTokenList interface represents a set of space-separated tokens. 

## Web Storage API

getItem(name)
setItem(name,"")

## Web Speech API

Web Speech API: text to speech/speech to text

## web workers

# CSS

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

<img src="sm_tmpyk7c4jes.png">

style as a HTML attribute takes n declarations

## Selectors

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

### Selectors

#### Simple selectors



##### Basic types

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

##### Pseudo-classes

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

###### input pseudo-classes

a number of pseudo-classes have to do with input
:enabled/:disabled|HTML enabled attribute is specified, or specified on the parent fieldset (or not, for disabled)
:read-write/:read-only|element is not disabled and is not readonly, or has the contenteditable attribute set to true/element has none of these things
:in-range/:out-of-range|element is/is not within a specified range 
:required/:optional|elements with the "required" attribute specified/not specified
:valid/:invalid|element is valid/invalid according to properties specified in HTML
:checked|selects a toggled radio button or checkbox


###### Tree-structural pseudo-classes

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

###### link-related pseudo-classes

:any-link|All links: <a> and <area> elements
:link|Selects all unvisited links  
:visited|Selects all visited links  

###### user action pseudo-classes

user action pseudo-classes are pseudo-classes that allow you to react to user action

:active|Selects the active link (when you click it/hold down the mouseclick on it)  
:hover|Selects links on mouse over  
:focus|element has the focus (accepts keyboard or mouse events, or other forms of input).
The :focus-within CSS pseudo-class matches an element if the element or any of its descendants are focused. In other words, 
The :focus-visible pseudo-class applies while an element matches the :focus pseudo-class and the UA (User Agent) determines via heuristics that the focus should be made evident on the element.

##### Pseudo-elements

A pseudo-element indicates a part of a element which isn't a real element.
A pseudo-element is begun by two colons

::after, ::before
In CSS, ::before/::after creates a pseudo-element that is the first/last child of the selected element. 
content can only be usefully be used on ::after and ::before
content-values ::= normal|none|({<content-specifier>} / <alt-text>)
alt-text ::= <string>|<counter>
the content-specifier can be a bunch of different things

::placeholder|matches placeholder text
In HTML/CSS, <input> and <textarea> can have placeholder text in form of a placeholder attribute.
::selection|matches text currently selected/highlighted by the user via cursor/touch etc.
::selection only supports a subset of properties, mainly color, background-color and text-shadow.
::first-letter|matches the first letter of a block-level element
::first-line|matches the first line of a block-level element
::backdrop is the pseudo-element that is the size of the viewport and is rendered beneath {{c1::any element that is in fullscreen}}


#### Combinators


+
~
>


#### The Grouping selector

### value processing

Once a user agent has parsed a document and constructed a document tree, it must assign, to every element in the flat tree, and correspondingly to every box in the formatting structure, a value to every property that applies to the target media type.

The final value of a CSS property for a given element or box is the result of a multi-step calculation:

First, all the declared values applied to an element are collected, for each property on each element. There may be zero or many declared values applied to the element.
Each property declaration applied to an element contributes a declared value for that property associated with the element.
Cascading yields the cascaded value. There is at most one cascaded value per property per element.
Defaulting yields the specified value. Every element has exactly one specified value per property.
Resolving value dependencies yields the computed value. Every element has exactly one computed value per property.
Formatting the document yields the used value. An element only has a used value for a given property if that property applies to the element.
Finally, the used value is transformed to the actual value based on constraints of the display environment. As with the used value, there may or may not be an actual value for a given property on an element.

### Cascading

The cascade takes an unordered list of declared values for a given property on a given element, sorts them by their precedence as determined below, and outputs a single cascaded value.

The cascaded value is determined by their precedence, which is specified by the cascade sort order:
origin & importance > context > specificity > order of appearance in source document.

#### Cascade origin

The three possible cascade origins are user-agent, user, or author.
author stylesheet|applied by the website author
user stylesheet|applied by the user, e.g. via addons
user-agent stylesheet|applied by the user-agent = browser
In addition, there are two virtual cascade origins, transition declarations and animation declarations.
the weakest style in an element higher in the cascade origin hierarchy beats the strongest style in an element lower in the cascade origin hierarchy
normal declarations|author>user>user-agent
important declarations|user-agent>user>author

#### important

A declaration is important if it has a !important annotation as defined by [css-syntax-3], i.e. if the last two (non-whitespace, non-comment) tokens in its value are the delimiter token ! followed by the identifier token important. All other declarations are normal (non-important).
An important declaration takes precedence over a normal declaration.

Ergo, for cascade origin plus important there is the following hierarchy:

transition declarations > Important user agent declarations > Important user declarations > Important author declarations > Animation declarations > Normal author declarations > Normal user declarations > Normal user agent declarations

#### context

#### Specificity

Specificity is the means by which browsers decide which CSS property values within a single source type are the most relevant to an element, based on selectors.
Specificity is tiered, with lower tiers not being able to beat higher tiers.
Each specifier on a tier gains you one point on the specificity scale.

3rd lowest|id selectors
2nd lowest|class selectors|attribute selectors|pseudo-class selectors
lowest|element selectors|pseudo-element selectors
no effect on specificity|:not(), universal selector

## Declarations

### Properites and Values

#### inherited, initial, etc.

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

#### css variables

Declaration: --var-name: value;
Accessing: var(--var-name)

#### vendor prefixes

vendor prefixes have the syntax -<vendorname>-<propertyname>
webkit|any webkit-based (and thus also blink-based) browser besides edge
moz|firefox
o|pre-webkit opera
ms|IE and edge

vendor prefixes were designed to allow experimenting with experimental CSS features without having to worry about future changes to the standard creating breaking changes.
The problem with vendor prefixes is that in fact, vendor-prefixed properties just got used in productio as well.
As of ~2020, the trend is away from using vendor prefixes, and instead using user-controlled experimental flags.

#### Props

A shorthand property is a css property that allows setting multiple other properties at once.
shorthand properties in css try to not force a specific order, where semantically possible.
If a value is not set within a shorthand property, it is set to its initial value, overriding subvalues.
Using inherit as a value of many within a shorthand property is invalid.

##### Cursor

`cursor` sets how the cursor looks when mousing over (generally irrelevant for touchscreens).
`cursor` value syntax {<url> <x> <y>,} <keyword>
When specifying an url() for cursor, the x and y values specify the offset in px of the hotspot of the cursor
`cursor: none` hides the cursor.
`cursor: default` shows the platform-default cursor.
Other <keyword>s for `cursor` (non-exhaustive, as there are ~40) are wait, crosshair, not-allowed, zoom, copy, grab.

##### Caret

The caret-color CSS property sets the color of the insertion caret, the visible marker where the next character typed will be inserted. 

##### scroll-snap

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

##### word-break, overflow-wrap

##### width, height

width and height each have corresponding min- and max- properties
power of width and height properties: min- > max- > ø
width and height and corresponding min/max values take the following values: <lpminmaxauto>|fit-content(<length-percentage>)

What width and height size depends on the box-sizing property
content-box|width and height size content-box
border-box|width and height size border-box

##### flexbox, grid and columns

Flex or grid containers are declared by setting display to flex/inline-flex or grid/inline-grid.
A grid (as a layout, not just in CSS) is made up of horizontal and vertical (and sometimes angular) <dfn>grid lines</dfn> that intersect to define n <dfn>grid cells</dfn> 
In a grid layout, multiple adjacent cells (in CSS, forming a rectangle) are called a grid area.
In a grid layout, the area between two adjacent grid lines is called a grid track.

The order CSS property sets the order to lay out an item in a flex or grid container. Items in a container are sorted by ascending order value and then by their source code order.

###### box alignment properties

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

###### flexbox axes

For flexbox, if flex-direction is row or row-reverse, the main axis corresponds to the inline base direction, and the cross axis corresponds to to the block flow direction.
For flexbox, if flex-direction is column or column-reverse, the main axis corresponds to the block flow direction, and the cross axis corresponds to to the inline base direction.

###### gaps

the gap, row-gap and column-gap specifiy gutters between items in a flex/multi-column/grid container.
gap is a shorthand for row-gap and column-gap, if only one value is specified, it sets them to the same value.
the three gap properties take a <length-percentage>
For multi-column containers, row-gap currently does nothing.
for flex containers, column-gap specifies minimum spacing between flex items, and row-gap specifies minimum spacing between flex lines if flex-direction is row or row-reverse, otherwise what column-gap and row-gap do is reversed.
For the gap, row-gap and column-gap there exist the now archaic grid-* aliases.

###### grid

Fundamentally, the grid consists of two tasks: defining a grid & its sizes, and placing items within that grid.

####### defining and sizing a grid

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

####### placing items

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

###### flex

flex-flow is a shorthand for flex-direction and flex-wrap
flex-wrap may take the values nowrap, wrap, wrap-reverse.
flex-direction may take the values row, row-reverse, column, column-reverse

flex is a shorthand of flex-grow flex-shrink flex-basis (in that order)
flex-grow and flex-shrink specify a factor, which specifies how fast that element should grow/shrink relative to other flex elements.
flex-basis specifies the initial size of a flex item along its main axis.

By default flex items don't shrink below their minimum content size. To change this, set the item's min-width or min-height.

###### columns

The column-fill CSS property controls how an element's contents are balanced when broken into column fragmentainers (= column boxes)
auto|fill column boxes sequentially in the inline base direction, until the column box is full
balance|fill column boxes so that they have roughly the same height.

columns is a shorthand for column-count and column-width.
column-span: all transforms an element into a spanning element.
A spanning element spans all columns.

column-span specifies a maximum amount of columns
column-width specifies a minimum width of columns

##### Pointer-events

pointer-events: {{c1::none}} makes a thing completely ininteractable with a mouse.

##### Text

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


###### font

font-family sets the font family = typeface of the text.
font-family takes a font stack.
A font stack comma-separated list of font family names or generic family names, which repesents a priority of which ones to use.
generic family names are names like serif, sans-serif, monospace, cursive...
generic family names are guaranteed to resolve to an existing font family, and thus a font stack should generallly end in one.
It is good pracktice to quote font family names that contain whitespace, digits or punctuation characters.

The font shorthand allows setting properties starting with font-, as well as line-height.1

font-variant is a shorthand property for a few low-level font features, which all start with font-variant-
font-variant-caps: small-caps/petite-caps forces small caps/petite caps for non-capital letters, font-variant-caps: all-small-caps/all-petite-caps forces small caps for any letters, capital or not.

It may seem that certain html form elements can't have their font styled {{c1::because by default, these elements don't inherit font properties}}

##### Scrolling

overscrolling is what happens when you scroll further on something than that thing allows.
on mobile browsers and some desktop browsers, there is a form of overscrolling where the site will rubberband
when you overscroll a container, and this then starts scrolling the next-higher container, this is known as scroll chaining.
overscroll-behavior is actually a shorthand for overscroll-behavior-x and overscroll-behavior-y
overscroll-behavior: none prevents all overscrolling.
overscroll-behavior: contain will prevent scroll chaining only

##### Background

The background: property is a shorthand for {{c1::background-clip}}, {{c2::background-color}}, {{c3::background-image}}, {{c4::background-origin}}, {{c5::background-position}}, {{c6::background-repeat}}, {{c7::background-size}} and {{c8::background-attachment}}
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

##### edges

Things in css that take the edge shorhand and also have four individual properties to set them: border (border, border-color, border-width, border-style), margin, padding, scroll-padding, scroll-margin
Shorthand for edges in CSS use a consistent syntax:

1 value|specifies all sides|<img src="sm_1_border.png">
2 values|1st specifies top/bottom, 2nd specifies left/right|<img src="sm_2_border.png">
3 values|1st specfies top, 2nd specfies left/right, 3rd specifies|<img src="sm_3_border.png">
4 values|1,2,3,4 top right bottom left (TRBL)|<img src="sm_4_border.png">

Normally, instead of using the shorthand, you can also set the properties individually by using -top(-), -left(-), -bottom(-), -right(-) properties.

typically, any edge width is specified as a <length-percentage>
<length-percentage-edges> ::= <length-percentage> [<length-percentage>] [<length-percentage>] [<length-percentage>]

###### css box model

<div class="onion-box">
  <span>((c:1;s:all;::Margin-box))</span>
  <div class="onion-box">
    <span>((c:2;s:all;::Border-box))</span>
    <div class="onion-box">
      <span>((c:3;s:all;::Padding-box))</span>
      <div class="onion-box">
        <span>((c:4;s:all;::Content-box))<br><br></span>
      </div>
    </div>
  </div>
</div>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}</span>
margin: auto can be used to center a thing horizontally, but not vertically

###### Border & outline

border can also be seen as a shorthand for border-top, border-right...
border-width, border-style, border-color are all shorthand for edges, and can be set via the 4 properties individually.
Notably, outline is similar to border in that it is composed of -width, -style, -color, but that in contrast to border, neither it itself nor its three subproperties are shorthands for the sides, nor are there individual properties for the sides - you either set the outline on all sides, or none at all.
Outlines can be moved away from its box via outline-offset: <length>

##### lines

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

##### Corners

1 value|specifies all corners|<img src="sm_1_corner.png">
2 values|1st specifies topleft and bottomright, 2nd specifies topright and bottomleft|<img src="sm_2_corner.png">
3 values|1st specfies topleft, 2nd specfies topright and bottomleft, 3rd bottomright|<img src="sm_3_corner.png">
4 values|1,2,3,4 topleft topright bottomright bottomleft|<img src="sm_4_corner.png">

Normally, instead of using the shorthand, you can also set the properties individually by using -top-left(-), -top-right(-), -bottom-right(-), -bottom-left(-) properties.

things that take corners may also take two sets of corners specifiers, separated by a slash.
If a thing takes two sets of corner specifiers, the first apply in x direction and the second in y direction.

Data types that specify corners are <border-radius>
border-radius: <border-radius>

##### Custom Counting

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

<pre><code>ol {
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
}</code></pre>

<pre><code><ol>
  <li>item</li>          <!-- 1     -->
  <li>item               <!-- 2     -->
    <ol>
      <li>item</li>      <!-- 2.1   -->
      <li>item</li>      <!-- 2.2   -->
      <li>item           <!-- 2.3   -->
        <ol>
          <li>item</li>  <!-- 2.3.1 -->
          <li>item</li>  <!-- 2.3.2 -->
        </ol>
        <ol>
          <li>item</li>  <!-- 2.3.1 -->
          <li>item</li>  <!-- 2.3.2 -->
          <li>item</li>  <!-- 2.3.3 -->
        </ol>
      </li>
      <li>item</li>      <!-- 2.4   -->
    </ol>
  </li>
  <li>item</li>          <!-- 3     -->
  <li>item</li>          <!-- 4     -->
</ol>
<ol>
  <li>item</li>          <!-- 1     -->
  <li>item</li>          <!-- 2     -->
</ol></code></pre>

##### animations & transitions

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

###### timimg functions

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

####### cubic-bezier

Bezier curvers are frequently used for curves in computer graphics
A bezier curve is constructed from two or more points.
linear|2
quadratic|3
cubic|4
To construct a bezier function, one connect the points until one has only a curve between two points left.
To construct a linear bezier function, connect P0 and P1. You're done (it's a straight line).
To construct a quadratic bezier function, connect P0P1 and P1P2. Now, let a point travel on P0P1 and P1P2 from 0 to 1. connect P<sub>P0P1</sub> and P<sub>P1P2</sub> with a further line. Let a point travel on P<sub>P0P1</sub>P<sub>P1P2</sub> from 0 to 1. This point describes the quadratic bezier curve.
To construct a cubic bezier function, connect P0P1, P1P2, P2P3. Now, let a point travel on P0P1, P1P2 and P2P3 from 0 to 1. connect P<sub>P0P1</sub> and P<sub>P1P2</sub> as well as P<sub>P1P2</sub> and P<sub>P2P3</sub> with a further line. Let a point travel on P<sub>P0P1</sub>P<sub>P1P2</sub> and on P<sub>P1P2</sub>P<sub>P2P3</sub> from 0 to 1. Connect P<sub>P<sub>P0P1</sub>P<sub>P1P2</sub></sub> and P<sub>P<sub>P1P2</sub>P<sub>P2P3</sub></sub> with a further line. Let a point travel on P<sub>P<sub>P0P1</sub>P<sub>P1P2</sub></sub> P<sub>P<sub>P1P2</sub>P<sub>P2P3</sub></sub>, this point describes the cubic bezier curve.

<img src="sm_cubBezstep3-1.png"><img src="sm__cat_acad_inf_code_css_bez60pc.png"><img src="sm__cat_acad_inf_code_css_bez80pc.png">

The CSS cubic-beziers map the dependent variable (y) to change in property, and the independent variable (x) to change in time.
For CSS, the x values of cubic-bezier must be between 0 and 1 (representing time), the y values are not limited in such a way
For the CSS cubic beziers only two points matter, the other two are fixed at (0|0) and (1|1)
For cubic-bezier(), the four parameters represent x1, y1; x2, y2

linear|<img src="sm_Screenshot%202020-06-02%20at%2001.59.05.png">
ease-in-out|<img src="sm_Screenshot%202020-06-02%20at%2002.03.45.png">
ease-in|<img src="sm_Screenshot%202020-06-02%20at%2002.02.33.png">
ease|<img src="sm_Screenshot%202020-06-02%20at%2002.02.03.png">
ease-out|<img src="sm_Screenshot%202020-06-02%20at%2002.03.02.png">

##### tables

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

##### misc

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
{{c4::Background-blend-mode}} regulates blending between ({{c3::a}}) {{c1::background-image}}({{c3::s}}) as well as the {{c2::background-color}}.
{{c2::mix-blend-mode}} regulates blending between {{c1::the}} {{c1::element's}} {{c3::content}}, {{c1::the}} {{c1::element's}} {{c4::parents content}}, and {{c1::the}} {{c1::element's}} {{c5::background}}.
css <blend-modes> are the usual blend modes

#### Values

##### Functions

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

##### variables

custom properties are properties that start with -- and save their value, which then can be referred to with the var() function.
custom properties have a scope of the variable they are declared on and all children, since they particpate in the cascade.
The var() css function can be used instead of any part of a value of another property, and may even contain commas.
var ::= var\(<custom-property-name>, <fallback-value>\)

##### offsets

generally from the top left corner
for <offset>, the first value is x and the second is y
while offset is not a official datatype, I will define it as offset ::= <length> <length>

###### position

<position> can take two kinds of values: keywords and values.
Keywords for <position> are center, top, right, bottom and left.
A value for <postion> can be a <percentage> or <length>.
For <position>, specifying one value positions it exactly at that keyword (if keyword), or at value on the x axis and the y defaults to 50%.
For <position>, specifying two values means that the first will apply to x positioning, and the second will apply to y positioning, unless it is two keywords.
For <position>, a keyword followed by a value specifies the offset from the keyword.
For <position>, if specifying two keywords or two keywords with values each, the order doesn't matter.
The value described by <position> need not be inside the elements box.

<img src="sm_position_value.png">

##### <image>

The <image> CSS data type represents a two-dimensional image.
While there are many kinds of things in the spec that an <image> could be, currently it can only be an <url> or a <gradient>

###### <gradient>

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

##### <size>

size ::= (<length-percentage>[ <length-percentage>])|size-keyword
size-keyword ::= closest-side|closest-corner|farthest-side|farthest-corner
closest-side	The gradient's ending shape meets the side of the box closest to its center (for circles) or meets both the vertical and horizontal sides closest to the center (for ellipses).
closest-corner	The gradient's ending shape is sized so that it exactly meets the closest corner of the box from its center.
farthest-side	Similar to closest-side, except the ending shape is sized to meet the side of the box farthest from its center (or vertical and horizontal sides).
farthest-corner	The default value, the gradient's ending shape is sized so that it exactly meets the farthest corner of the box from its center.

For <size>, specifying two <length-percentages> applies them to horizontal/vertical direction respectively. specifying only one makes it applly two both horizontal and vertical directions. Places that expect a <size> for a circle may only recieve one <legnth-percentages>

##### <basic-shape>

basic-shape ::= <inset>|<circle>|<ellipse>|<polygon>|<path>
inset ::= inset\{<length-percentage-edges>[ round <border-radius>]\}
circle ::= circle\(<size>[at <position>]\)
ellipse ::= ellipse\(<size> [at <position>\)

##### color

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

##### simple types

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

##### length

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
<code>rem</code>|font-size of the root element
<code>ex</code>|the height of a lowercase x of the current font (rarely used)
<code>em</code>|the font-size of the element
<code>ch</code>|width of the "0" (zero)

viewport-relative-length-units
<code>vw</code>|1% of the width of the viewport*
<code>vmin</code>|1% of viewport's* smaller dimension
<code>vmax</code>|1% of viewport's* larger dimension
<code>vh</code>|1% of the height of the viewport*

absolute units in CSS may or may not refer to their real-world equivalent.
On print media and similar situations, css absolute units refer to their real-world equivalent.
For low dpi devices, absolute units are instead defined in reference to the reference pixel: 1 in = 96 px, thus `1in` may not correspond to 1 RL inch. 
For high dpi devices, px are instead defined in reference to real-world units, so that 1 in is one 1 RL in, and 1px is 1/96in, no matter how many screen pixels that would actually correspond to on the device.
absolute-length-unit ::= <metric-length-unit>|<imperial-length-unit>|px
metric-length-unit ::= cm|mm|Q
imperial-length-unit ::= in|pc|pt

##### filters

backdrop-filter applies a filter to the area behind an element.
for backdrop-filter to apply, the element or its background must be at least partially transparent.
backdrop-filter and filter take a <filter-function-list>
filter-function-list ::= <filter-function>|<svg-filter>{ <filter-function>|<url>} # the URL is for a svg filter
a <filter-function> is a <function> that applies a filter (i.e. changes the appearance of an image)
filter-functions: 
blur(): takes a blur-radius
brightness(): <number-or-percentage-to-infinity>
contrast(): <number-or-percentage-to-infinity>
drop-shadow(): arguments are <code>offset-x offset-y [blur-radius] [color]</code>
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

##### shadows

The box-shadow property creates a rectangular shadow behind an element's entire box, while the drop-shadow() filter function creates a shadow that conforms to the shape (alpha channel) of the image itself.

the first two <lengths> of text-shadow, box-shadow and drop-shadow() take a <offset> (two <length>s), the third <length> specifies the blur-radius
for box-shadow, the fourth <length> specifies the spread-radius, for text-shadow and drop-shadow(), there is no way to specify a spread radius.
for text-shadow, box-shadow and drop-shadow(), the non-length value specifies the color.
box-shadow additionally may take the keyword inset, which specifies that the shadow should render inside the box instead of outside it.

text-shadow and box-shadow also accept a CSL of shadow specifiers for specifying multiple shadows.

## at-rules

### nested at-rules

#### @font-face

@font-face defines a font face for use within the document.
@font-face takes at least a font-family: foo, which is the name we will use to refer to it, and a src, which provides the file for the font itself.
@font-faces src syntax: (<font-face-name>|<url> [format(<string>)]) {<url> [format(<string>)]}
font-face-name: local(<string>) # where the string is the name of a locally-installed font.
calls to local() for @font-faces src should go first since if it finds the font locally, it does not have to load it fron the URL.
for @font-faces src, the first call to local() or url() that is usable will be used.
For the @font-face src call, the format() function takes a string specifying the format of the font, where the font will only be loaded if the browser supports that format.
for @font-face, since you're specifying fonts and not font-families, for different font-weights and font-styles, you must specify multiple @font-face declarations, and within those, specify which font-weight or font-style this is specifying. Only fonts actually used will be loaded. This does not apply to variable fonts.

unicode-range: some-range will only load the font if the document uses the font for at least one character within the range

#### @keyframes

Keyframes at-rule syntax: @keyframes <keyframes-name> \{ <keyframe-block-list> \}
<keyframes-name> ::= <custom-ident>|<string>
<keyframe-block-list> ::= {<keyframe-block>}
<keyframe-block> ::= <keyframe-selector-list><declaration-block>
<keyframes-selector-list>  ::= <keyframe-selector>{,<keyframe-selector>}
<keyframe-selector> ::= from|to|<percentage>

from is an alias of 0% and to is an alias of 100%
Properties that aren't specified in every keyframe are interpolated if possible — properties that can't be interpolated are dropped from the animation.

if you mark something with !important in a keyframe,&nbsp;{{c1::That value will be ignored}} (since !important can't be used in keyframes)
if you don't provide a from/0% andor a to/100% it will {{c1::Animate to/from the elements existing styles}}
If you specify multiple @keyframes with the same name, {{c1::The last one encountered will be used}}

#### @page

@page syntax: @page <page-selector-list>\{<page-body>\}
page-selector-list ::= <page-pseudo-class>{, <page-pseudo-class>} #maybe it's not a comma? I couldn't find any documentation this
page-pseudo-class ::= :first|:blank|:left|:right
page-body :: <page-declaration>;|<margin-at-rule>
currently supported properties for the page declaration are margins, orphans, widows and break
margin-at-rule = @<margin-at-rule-name><declaration-block>
<img src="page_margin_at_rules.png">

#### @counter-style

@counter-style produces values of type <@counter-style>
@namespace is an at-rule that defines XML namespaces to be used in a CSS style sheet.

### non-nested at-rules

@charset "<charset>"; declares the charset, though this is often unnecessary if UTF-8 is desired, as the browser will assume UTF-8 if no charset decaration is present.
@charset must be the first statement in the document if present.

## elements

### replaced elements

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

#### images

image-rendering controls how an image upscales. 
image-rendering: pixelated - image will seem to be composed of large pixels
image-rendering: crisp-edges - preserve edges
image-rendering: auto - browser-defined algorithm

## flow

CSS takes as its input a tree of elements and text nodes, most commonly a pared-down DOM.
CSS converts the DOM to a flattened element tree, which is the same but has shadow trees merged back in.
CSS takes the flattened element tree and converts it to an intermediary structure, the box tree.
To create the box tree, CSS first gets the computed value for each CSS property for each element. Then CSS generates zero or more boxes for each element as specified by that elements display property.
Typically, CSS generates one box per element, the principal box.
Typically, CSS generates one text run per contiguous sequence of simbling text nodes.
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

### display

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
<img src="sm_inline_margins.png">
Since inline-level elements don't have block flow direction margins, they can't suffer from margine collapsing.
inline-level elements and text nodes are handled via an inline formatting context using line boxes.
Whenever the browser encounters inline elements wiwthin a block container, it creates a new root inline box which establishes an inline formatting context.
CSS fragments inline-level elements into a stack of fragmentainers called line boxes, which are inserted into the root inline box.
the browser will fill a line box in the inline base direction with inline-level elements or text until it is full.
Once a line box is full, the browser will create a second line box, etc.
A line box is as tall as its tallest content.
If the browser encounters a block-level element while creating line boxes, it stops the line box, closes the root inline box and thus the inline formatting context, puts the block-level element on a line of itself, and then creates a new root inline box with new line boxes etc. if there's more inline-level elements/text to be handled.
line-height sets the minimum height of a line box.
line-height may be specified as a <length-percentage> or as a <number>, which is a multiple of the current font-size
If we set the line height of multiple things in the same line box to different values, they may overflow into each others boxes.
<img src="sm_line_height_overflow.png">
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

#### display-internal

behave as ...|<display-internal> value
tbody|table-row-group
thead|table-header-group
tfoot|table-footer-group
tr|table-row
td|table-cell
colgroup|table-column-group
col|table-column
caption|table-caption

### fragmented flow

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

#### Orphans and Widows

orphans and widows are two twin properties in CSS that apply only to pages or columns.
Both orphans and widows take an <integer>
orphans says how many lines of a block container must appear at the bottom of a page/column if it is broken over two pages/columns
widows says how many lines of a block container must appear at the top of a page/column if it is broken over two pages/columns

#### Break

The break-before/break-after/break-inside properties apply to pages and collumns.
The break-before/after/inside says how to break before/after/within a block-level element
break-before/after/inside take a keyword called avoid which prevents breaking within (if possible).
The avoid keyword for break-* is available as avoid-page and avoid-column to only apply to these, repsectively.
break-before/after but not inside  take a keyword called page or column which forces breaking before/after/within the respective thing (if possible).
break-before/after but not inside take the keywords left/right to force breaking before/after if the thing is a page that is a left/right page
break-before/after/inside default to auto, which means a break is allowed but not mandatory.
A break created by break-before and break-after is called a forced break.

## meida queries

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

### media types

Media types

all|all devices
print|inteded for printing
screen|intended for screens
speech|intended for speech synthesizers/screen readers

Media types are specified as boolean attributes, i.e. the presence of the keyword is enough

### media features

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

### logical ops

The logical operators that are valid within media queries are and and not (which work as expected), and the comma, which acts as an or, but cannot be nested (i.e. can only combine media queries at the top level). 
as of Level 3 media queries (changes in level 4 media queries), the not keyword can't be used to negate an individual media feature expression, only an entire media query.
feature queries supports similar logical operators to media queries, but instead of the comma, it has a normal or operator, and not can also invert parts of feature queries.
The operator only is mainly useful for preventing browsers from matching if part of the media query applies, and there is another part that they don't understand (e.g. older browsers) and thus ignore.

### atrules

An @media at-rule is a conditional which takes a media query and executes the CSS contained within if the media query is true.
Multiple @media at-rules may apply at the same time
Syntax @media &lt;media-query&gt; &lt;block&gt;

@media screen and (min-width: 900px) {
  article {
    padding: 1rem 3rem;
  }
}

A @supports at-rule is a conditional which takes a feature query

### in HTML

The media HTML attribute may be applied to <link>, <source>, or <style>.
The media HTML attribute indicates when to load the specific resource.

### in JS

window.matchMedia() takes a media query and returns a MediaQueryList object, whose matches property indicates exactly that.
To react to changes in media features/types, you can register the change event on the MediaQueryList boject.

## misc

In typography, a column is one or more vertical blocks of content positioned on a page, separated by gutters.
Gutters are whitespace between two rows or columns.
To clamp a value is to specify an upper and a lower bound, and keep the number within those values.

### Accessibility

Accessibility improvements often do not merely benefit the disabled, but also non-human users (e.g. web crawlers and thus SEO), users with different input methods (such as the keyboard)

#### WAI & WCAG basics

{{c1::the Web Accessibility Initiative (WAI)}} is the W3C initiative supporting accessibility.
the WCAG (Web Content Accessibility Guidelines) are guidelines for web accessibility published by the WAI.
The WCAG consists of principles, guidelines, successs criteria, and techniques.
WCAG principles are the general ideas underlying web accessibility: percievable, operable, undertandable, robust.
Each WCAG principle is broken up into one or more guidlines.
Each WCAG guideline has one or more successs criteria, which are characterized by being testable.
For each guideline and success criterion the WCAG also includes a wide variety of techinques for (better) achieving these.
WCAG techniques may either be <dfn>sufficient</dfn>, i.e. enough to meet a success criterion, or be <dfn>advisory</dfn>, which is going beyond the success criterion to better address the guideline behind it. Additionally, WCAG techniques may document common failures.
The WCAG defines three levels of conformance, A, AA, And AAA, for each success criterion.
In some countries websites, especially those of public sector bodies must conform with certain WCAG levels.
§§ the WAI published the WCAG ((c:5;::2.1)) version in ((c:6;::2018)), and is expected to publish WCAG ((c:5;::2.2)) in ((c:6;::2021)) §<br>
§§ According to the WCAG ((c:7;::level AA)), color should have a ((c:8;::contrast ratio)) of at least ((c:9;::3:1)) for ((c:10;::large)) and ((c:9;::4.5:1)) for ((c:10;::normal)) text §<br>
§§ According to the WCAG ((c:11;::level AAA)), color should have a ((c:12;::contrast ratio)) of at least ((c:13;::4.5:1)) for ((c:14;::large)) and ((c:13;::7:1)) for ((c:14;::normal)) text §<br>
===<br>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}</span>

#### WCAG success critera

##### Non-text content

the alt text should be blank if the image is merely presentational, don't just not specifiy it, or screen readers might e.g. read out the url

#### WCAG techniques

##### Semantic HTML

Semantic HTML is HTML where the tags contain semantic information about the content
Semantic HTML includes elements like &lt;article&gt;, &lt;nav&gt;, &lt;summary&gt;, contrasting with elements like &lt;div&gt;, &lt;span&gt;


##### aria

ARIA  Accessible Rich Internet Applications
ARIA is mainly realized in HTML attributes.
ARIA attributes change the accessibility tree, but nothing else.
There are three types of attributes that {{c4::ARIA}} has: {{c1::Roles}}, {{c2::States}} and {{c3::Properties}}
ARIA {{c1::states}} define some property {{c2::that can change}}
ARIA {{c1::roles}} define a {{c2::type of component}}, e.g. {{c3::toolbar, banner}}
ARIA {{c1::properties}} define some property {{c2::that is expected to stay the same}}



### system UI themes

the {{c1::System UI Theme Specification}} is a {{c2::reasonably widely}} adopted spec for {{c3::a style object}} that stores things for {{c4::design systems}}, especially {{c5::scales}}
at the heart of the {{c1::System UI Theme Specification}} are {{c2::scales}} - 
scales are {{c3::arrays}} or {{c3::objects}} of {{c4::predefined sets of values}}, for things such as {{c5::font sizes}}, {{c5::colors}}, etc.
According to the {{c1::System UI Theme Specification}}, the {{c4::CSS properties}} that accept {{c2::only a small, finite number}} of valid CSS values {{c3::should not be included as a scale object}}.
According to the {{c1::System UI Theme Specification}}, a {{c2::key}} defining a {{c2::scale}} should be called the {{c3::same thing as the css property}}, except {{c4::plural}} (except for the weirdly-named <code>{{c4::space}}</code>) and {{c5::camelCase}}, unless there are {{c6::multiple css properties it might be used for}}
<pre><code>// example fontSizes scale as an array
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
}</code></pre>
<table>
  <thead>
    <tr>
      <th>scales</th>
      <th>CSS Properties</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>space</code></td>
      <td>
        <code>margin</code>, <code>margin-top</code>, <code>margin-right</code>,
        <code>margin-bottom</code>, <code>margin-left</code>,
        <code>padding</code>, <code>padding-top</code>,
        <code>padding-right</code>, <code>padding-bottom</code>,
        <code>padding-left</code>, <code>grid-gap</code>,
        <code>grid-column-gap</code>, <code>grid-row-gap</code>
      </td>
    </tr>
    <tr>
      <td><code>fontSizes</code></td>
      <td><code>font-size</code></td>
    </tr>
    <tr>
      <td><code>colors</code></td>
      <td>
        <code>color</code>, <code>background-color</code>,
        <code>border-color</code>
      </td>
    </tr>
    <tr>
      <td><code>fonts</code></td>
      <td><code>font-family</code></td>
    </tr>
    <tr>
      <td><code>fontWeights</code></td>
      <td><code>font-weight</code></td>
    </tr>
    <tr>
      <td><code>lineHeights</code></td>
      <td><code>line-height</code></td>
    </tr>
    <tr>
      <td><code>letterSpacings</code></td>
      <td><code>letter-spacing</code></td>
    </tr>
    <tr>
      <td><code>sizes</code></td>
      <td>
        <code>width</code>, <code>height</code>, <code>min-width</code>,
        <code>max-width</code>, <code>min-height</code>, <code>max-height</code>
      </td>
    </tr>
    <tr>
      <td><code>borders</code></td>
      <td>
        <code>border</code>, <code>border-top</code>, <code>border-right</code>,
        <code>border-bottom</code>, <code>border-left</code>
      </td>
    </tr>
    <tr>
      <td><code>borderWidths</code></td>
      <td><code>border-width</code></td>
    </tr>
    <tr>
      <td><code>borderStyles</code></td>
      <td><code>border-style</code></td>
    </tr>
    <tr>
      <td><code>radii</code></td>
      <td><code>border-radius</code></td>
    </tr>
    <tr>
      <td><code>shadows</code></td>
      <td><code>box-shadow</code>, <code>text-shadow</code></td>
    </tr>
    <tr>
      <td><code>zIndices</code></td>
      <td><code>z-index</code></td>
    </tr>
    <tr>
      <td><code>transitions</code></td>
      <td><code>transition</code></td>
    </tr>
  </tbody>
</table>

### CSS processing

a CSS preprocessor is a transpiler from a language that is not css (though typically a superset) to css.
{{c3::Sass}} is a {{c4::CSS preprocessor}} that works with the two syntaxes {{c1::Sass (the syntax)}} and {{c2::SCSS}}
Sass syntax that is indented rather than curly-braced   Sass
Sass syntax that is a CSS superset   SCSS (Sassy CSS)
PostCSS is a CSS processor (CSS -> CSS), that does nothing by default, but can be hooked into by JS plugins.
Autoprefixer is a tool to add vendor prefixes to CSS properties automatically, implemented as a PostCSS plugin.

### CSS naming schemes

# not css

A {{c1::FOUC (Flash of unstyled content)}} is when a {{c3::page (or some content)}} is briefly&nbsp; visible with {{c2::no styling/browser default styling}}

## blending

Blend modes (or mixing modes[1]) in digital image editing and computer graphics are used to determine how two layers are blended with each other. 
Blend modes typically use values from 0 to 1 for the channels for the math.
When describing blend modes, t denotes the top layer and b the bottom layer
In general, when channel is specified, assume it is done to each channel.
normal|use alpha compositing
multiply|channel_t * channel_b|result will be darker (since two numbers less than 1 multiplied will always be smaller)
screen|1 - (1 - channel_t) (1 - channel_b)|result will be always be lighter

## placeholder images

Placeholder images using kittens   placekitten.com
Placeholder images using boring boxes   via.placeholder.com

via.placeholder.com/{{c1::width}}[{{c2::x}}{{c3::height}}]
placekitten.com/{{c1::width}}{{c2::/}}{{c3::height}}

# web frameworks

## react

# other stuff

ISO dates
The chrominum javascript engine is v8, d8 is the developer shell for v8
A bricked device is one that no longer can function at all (has become as useful as a brick)
SKU|Stock Keeping Unit
An instance is something that has been created on some sort of model.

# data

open data is data available to everyone freely.
linked data is data that is interlinked usefully.

## data models

A data model is a model that provides structure to data, and to their properties, how they relate amongst each other, and how they relate to RL.

In computing, a database is an organized collection of data stored and accessed electronically. 
A DBMS (database management system) is the software used to manage a database.

A (data)(base) query language is a language used to query data in databases/information systems.

Structured data is a data model used for describing web pages.
Structured data is used by search engines to provide more rich results.
Shema.org is a set of schemas for structured data.

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

<br>---<br>
  §§ ((c:5;::A table)) (e.g. in ((c:5;::database or spreadsheet)) contexts) is ((c:6;::a collection/sequence/whatever of)) ((c:7;::records)). §<br>
§§ ((c:8;::A record)) is ((c:9;::a collection/sequence/whatever of)) ((c:10;::fields)), which ((c:10;::each contain an item of data)). §<br>
§§ A ((c:11;::record)) is ((c:12;::more or less kinda)) synonymous to ((c:13;::row)). §<br>
§§ ((c:14;::Field)) is ((c:15;::sometimes used)) as a synonym for ((c:16;::column)), though following ((c:17;::the above differentiation)), this is of course ((c:17;::incorrect)). §<br>
§§ ((c:18;::csv)) and ((c:19;::tsv)) both store ((c:20;::tables/tabular data)). §<br>
§§ ((c:21;::csv/tsv)) separate ((c:22;::records)) via ((c:23;::newlines (generally CRLF))) §<br>
§§ The ((c:24;::first line)) of ((c:25;::csv/tsv)) may be ((c:26;::a header)). §<br>
§§ ((c:27;::the csv/tsv header)) should have ((c:28;::as many fields)) ((c:29;::as the other records in the documents)). §<br>
===<br>

<table>
  <thead>
    <tr><th>name</th>
    <th>separates fields how</th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:1;::csv))</td> <td>((c:2;::with commas)), sometimes also ((c:30;::arbitrary different characters))</td></tr>
<tr><td>((c:3;::tsv))</td> <td>((c:4;::with tags))</td></tr>
  </tbody>
</table>
<br>---<br>
  §§ Neither ((c:30;::csv)) nor ((c:30;::tsv)) are ((c:31;::fully standardized)), or rather ((c:32;::the specs aren't always followed)). §<br>
§§ In ((c:33;::csv/tsv)), ((c:34;::wrapping a field in double quotes)) commonly allows ((c:35;::the field separator to be included in the field)). §<br>
§§ If in csv/tsv ((c:36;::a field is wrapped in double quotes to allow the field separator to be included in the fields)), ((c:37;::double qoutes)) are then excaped by ((c:38;::double double quotes)). §<br>
§§ ((c:39;::Trailing newlines)) at the ((c:40;::end of documents)) are ((c:41;::optional)) for ((c:42;::csv/tsv)), ((c:43;::field separators)) at ((c:44;::the end of the line)) will ((c:45;::create empty fields)). §<br>
===<br>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}{{c28::}}{{c29::}}{{c30::}}{{c31::}}{{c32::}}{{c33::}}{{c34::}}{{c35::}}{{c36::}}{{c37::}}{{c38::}}{{c39::}}{{c40::}}{{c41::}}{{c42::}}{{c43::}}{{c44::}}{{c45::}}</span>

### graph data models

A graph data model is one that organizes entities and their relationships as a graph.
A graph database is a database that uses a graph data model.

A ontology languages is a language that describes an ontology. 

The semantic web is sometimes known as web 3.0
The goal of the samntic web is to make internet data machine readable
A semantic query is a data query on the semantic web.
the social graph is a graph that represents social relationship between entities.
the open graph allows web pages to become objects in a social graph

#### RDF

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

##### sparql

SPARQL = SPARQL Protocol and RDF Query Language
SPARQL is proounced sparkle
SPARQL is an RDF query language

##### JSON-LD

JSON-LD is an implementation of RDF
JSON-LD is included via a script tag 
Of the structured data formats, google prefers JSON-LD.

#### Other implementations of structured data

RDFa Lite is a minimal subset of RDFa that can be directly included in HTML.
Microdata is a format to include metadata, including but not limited to RDF data, directly included in HTML.

#### OWL

OWL short for web ontology langauge
OWL, RDFS and SHACL are ontology languages for RDF

#### applications

FOAF = friend of a friend
FOAF is an ontology for people, their properties and their relations using RDF/OWL 

##### open graph

The Open Graph protocol enables any web page to become a rich object in a social graph.
open graph is based on RDFa.
Open graph metadata is specified within meta tags.
There are four required properties for open graph, which are og:image, og:title, og:type and og:url.
The property of the open graph metadata is specified within the property property, and the value of the open graph metadata is specified within the content property.

# Modelling

UML  Unified Modeling Language
UML is a general modelling language most commonly used in the field of software engineering.

## class

An UML class diagram generally consists of three parts, a class name on top, member variables in the middle, and member methods at the bottom.
<img src="sm_220px-BankAccount1.svg.jpg">

## sequence

((h:all;::<img src="sm_paste-d8abaabcb6ec43ff8294b3567cb96b4fe4aa48f2.jpg">))

A sequencie diagram is an UML diagram showing object interactions as time flows.
In a sequene diagram, the lifelines go from the objects downwards.
In a sequence diagram, a thicker bar on the lifeline means the object is active.
In a sequence diagram, messages between objects are indicated by horizontal lines between the lifelines.
In a sequence diagram, the further down a message, the later it comes
non-filled arrowheads   Async messages
filled arrowheads   synchronous messages
request messages   solid line arrows
Answer messages   dashed arrows


## object

<img src="sm_paste-7a55c6f447e4be8da11b84f2d660fe36fa529dc8.jpg">
Objects in UML object diagrams at least contain a top field with the object name, the class name or both, often they also contain a field below that for instance varaibles




# HCI

HCI = Human Computer 
The set of ways a human can interact with a computer   Interaction styles
WYSIWYG   What you see is what you get

## IO

Input devices are devices that move/transform data from  {{c1::the world ≈ the user to the computer}}
Output devices are devices that move/transform data from {{c1::the computer to the world ≈ the user}}
The most important input devices are probably mouse and keyboard, less common ones are gamepads, motion tracking devices, microphones, cameras, etc.
Examples of output devices are screens, speakers, etc.
A pointing device is an input device that allows a user to input spatial information.
Examples of pointing devices are mice, trackpads, trackballs, pointing sticks aka trackpoints.
Pointing devices are governed by fitts law
Fitts law says that the time required to rapidly move move to a target area, e.g. by a pointing device, is a function of the ratio between the distance to the target and teh widht of the target.

### text input

#### autocomplete

<br>---<br>
  §§ <dfn>((c:1;::Autocomplete/word completion))</dfn> is a feature where ((c:2;::an application predicts the rest of something the user is typing)).  §<br> 
  §§ <dfn>((c:3;::Autocomplete/word completion))</dfn> on ((c:4;::smartphone keyboards)) is called <dfn>((c:5;::predictive text))</dfn>, ((s:gb;::this used to refer to ((c:6;::the prediction of typing on numeric keypads (e.g. T9))))) §<br>
  §§ <dfn>((c:7;::Autocomplete/word completion))</dfn> ((c:8;::in a command-line interface)) is called <dfn>((c:9;::command-line))</dfn> or <dfn>((c:9;::tab)) ((c:9;::completion))</dfn>, ((s:gb;::which generally uses ((c:10;::the tab key (whence the name))).)) §<br>
  §§ <dfn>((c:11;::Autocomplete/word completion))</dfn> in ((c:12;::code editors)) is also known as <dfn>((c:13;::code completion))</dfn>. Examples include ((s:gb;::((c:14;::VS &amp; VS Code))'s ((c:15;::IntelliSense)), and ((c:16;::AI (modfied GPT-3)))-powered ((c:17;::GitHub Copilot)).)) §<br>
===<br>

## shells

A shell is a wrapper around the OS that humans or similar interact with.
Types of shells: graphical, command-based
Shell is often but kinda incorrectly used as a synonym to command-based shell

### GUI

WIMP = Windows, icons, menus, pointer

#### elements

##### breadcrumbs

<img src="sm_2021-06-26--14-46-16-screenshot.png">
A breadcrumb trail is a series of separated breadcrumbs, each representing a distict navigational item organized into a logical sequence.
A breadcrumb trail most commonly represents a hierarchical structure.
Each breadcrumb is usually a minimal element containing text only.
In bootstrap, breadcrumbs are created by .breadcrumb > .breadcrumb-item*n

##### disclosure widgets

A disclosure widget has a collapsed state where it only shows a heading, and an expanded state which shows the heading and more content contained within.
With a disclosure widget, the content contained within is shown if the heading is interacted with.
With a disclosure widget, the heading often indicates that it can be expanded/shrunken either via ▼/▲ or via +/-
In html, a disclosure widget is defined via a details element.
In html, the header of a disclosure widget is defined by a summary element.
An accordion is a set of multiple disclosure widgets.
Most commonly, disclosure widgets start out in their collapsed state by default.
In html, you can force a disclosure widget to start in its open state by specifying the boolean attribute open.
<img src="disc.png"><img src="kfw-disclosure.jpg">((h:2;::<img src="sm_FAQ-Content-Style-Accordion.gif">))

##### status bar

<div class="flex-container">((h:all;::<img src="sb-paint.png">))((h:all;::<img src="460px-Emacs_statusline.png">))((h:all;::<img src="Gedit_3.11.92.png">))((h:all;::<img src="StatusBar_Light.png">))((h:all;::<img src="lGPcKx09nzIAFtAjFbQ_6FoXc3hnT7y0oMOGVNI8tbFWziGJQdUAgar1TBMmIGP_2Sj0gvLJonpoydv5UyTrOl_WJnrDz45RPMkSM7s=w1064-v0.png">))</div>
<br>---<br>
  §§ On ((c:1;::desktop)), a ((c:2;::status bar)) is a ((c:3;::horizontal)) ((c:4;::bar)) generally at ((c:5;::the bottom of a window)). §<br>
  §§ A ((c:15;::status bar)) on desktop displays ((c:6;::various kinds of information)), often used when ((c:7;::editing documents ((n)vi(m), vscode, various office programs, etc.))). §<br>
  §§ On ((c:8;::mobile)), a ((c:9;::status bar)) is a ((c:10;::horizontal)) ((c:11;::bar)) at ((c:12;::the top of the screeen)). §<br>
  §§ A ((c:16;::status bar)) on mobile contains ((c:13;::notification)) and ((c:13;::system)) ((c:13;::icons)) ((h:gb;::(such as ((c:14;::power, networks, time))))) §<br>
===<br>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}</span>>

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
Virtual memory & addresses are used by the OS for primary memory, but also may be used in other circumstances.
Nearly all current implementations of virtual memory for primary memory divide virtual memory into pages.
Pages of virtual memory typically have a fixed size or a few preditermined fixed lenths.
For primary memory, virtual addresses are mapped to physical addresses in the page table.
The MMU (Memory management unit) is a hardware device typically used to handle the page table/mapping of log to phys addr.
Each process has its own section in virtual memory.
Virtual memory will appear to an application using it to be continuous, though the physical memory it occupies may be discontinous.
Today, modern OSs only expose virtual memory to user-level programs.
Virtual memory benefits security, as it means programs can't access each other's memory.

#### memory management

swap/page storage are virtual memory that is secondary memory used as an extension of primary memory
swap/page storage may be a file(s) or a partition(s).
managing virtual memory pages within primary memory|paging
moving virtual memory from secondary to primary memory or v.v. (using pages)|swapping or paging
moving virtual memory from secondary to primary memory or v.v. (without using pages)|swapping
primary -> secondary memory|paged/swapped out
secondary -> primary memory|paged/swapped in



### relation to CPU

The difference between primary and secondary memory is that the CPU can address primary memory directly.

#### primary memory/storage

The terms primary storage/memory, internal storage/memory, and main storage/memory are often used interchangeably.
As I will use the term, primary memory consists of CPU Registers and Cache as well as main memory.
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
registers > cpu cache > main memory > secondary memory

#### secondary memory

secondary meory is generally non-volatile memory

##### drives

HDD  Hard disk drive
SSD  Solid state drive/device/disk

###### HDD

HDDs store bits of data data via magnetic north/south.
Physically, a HDD stores the data on rotating platters.
A HDD usually includes a few platters.
HDDs are thick even though individual platters are thin because HDDs generally contain multiple platters.
HDD platters are discs usually made up of a aluminum/glass plate coated with a magnetic coating.
in a HDD, the head performs read-writing.
in a HDD, the head is mere nanometers from the platter.
((h:1;::<img src="sm_250px-Samsung_Harddrive_headcrash_DSCN0124b.jpg">))
A head crash is the head of a HDD making contact with its rotating platter, slashing the surface and causing disk damage/failure.
Head crashes generally happen due to falling/jolts or due to dust sticking to the head.
a HDD is made up of clusters which are made up of sectors.
A sector used to be 512 byte large normally; today, that is usually 4096 Bytes (4KiB)
<img src="sm_hdd_w_labels.svg">
<img src="sm_1280px-Seagate_ST33232A_hard_disk_head_and_platters_detail.jpg"><img src="sm_220px-Laptop-hard-drive-exposed.jpg">
as of 2020, HDDs usually spin at 5400 or 7200 RPM.
as of 2020, HDDs are typically a few TB in size.

###### SSD

A flash memory device typically consists of multiple flash chips and a controller.
a flash chip is made up of blocks which are made up of pages
To write new data on a flash memory device, first you need to erase the old data.
Flash memory can either be NAND or NOR based.
NAND flash can typically erase only whole blocks, but write pages too
After a certain number of write cycles, flash memory begins to decay.
Flash memory is typically faster than magnetic memory.
SSDs are a type of flash memory device.

<div class="onion-box"><span>((c:;::SSD chip))</span><div class="onion-box"><span>((c:;::block))</span><div class="onion-box"><span>((c:;::page))</span></div><div class="onion-box"><span>((c:;::page))</span></div><div class="onion-box"><span>((c:;::page))</span></div><div class="onion-box"><span>((c:;::...))</span></div></div><div class="onion-box"><span>((c:;::block))</span></div><div class="onion-box"><span>((c:;::...))</span></div></div>

## secondary memory organization

### partitons

A secondary memory device is divided into n partitions.
How partitions are layed out on a secondary memory device is described by the partition table.
in the past, the MBR would have also included a partition table.
the MBR partition table was limited to 64 byte, which allowed for up to four partitions.
Today, partition tables are generally GPT, since MBR was limited to addressing 2 TiB drives.
GPT  GUID Partition Table
GUID in GUID Partition Table  globally unique identifier

### file system

The file system is the method/system/whatever that controls/specifies how {{c1::data is organized within a partition}}
A flat file system is a file system with no {{c1::subdirectories}}
Most *nix file systems are case-sensitive, but the apple ones (AFS/HFS+) are not; furthermore, windows is not case-sensitive.
Even non-case-sensitive file systems are almost always case-preserving.

### directory structure

{{c1::the directory structure}} is the way data is organized in a file system using directories.
In *nix-likes, the root directory is the directory all other directories descend from.
In *nix-likes, the root directory is `/`
In windowslikes, each partition is its own root directory, with a drive letter assigned.
Windows drive letters have the syntax <letter>:
An absolute path begins at the root directory.
A relative path begins at the current working directory.

#### home dir

Generally one home directory per user.
On *nix, the home directory of a user generally contains all the stuff pertaining ot a user.
FHS: Home directories live in /home/
$XDG_CONFIG_HOME/autostart contains .desktop files to run on system start
$XDG_DATA_HOME/fonts contains fonts for a specific user

#### XDG Base Directory Specification

XDG Base DIrectory Specification is the spec governing the organization of files in your home directory   

XDG Base Dir Var|default|global equivalent
$XDG_DATA_HOME|$HOME/.local/share|/usr(local/)share
|$HOME/.local|/usr/local
|$HOME/.local/lib|/usr/local/lib
|$HOME/.local/bin|/usr/local/bin
$XDG_CONFIG_HOME|$HOME/.config|/etc
$XDG_CACHE_HOME|$HOME/.cache|/var/cache

#### FHS

FHS  Filesystem Hierarchy Standard
FHS (Filesystem Hierarchy Standard) is the Linux spec for {{c1::directory structure}}
source code should be in src for reference only

##### /sys

/sys provides a window to the kernel

##### /proc

/proc contains information for each process and a lot of runtime system info.

##### /var

/var/mail/   MBOXes for each user
/var/spool/   data awaiting processing

##### /opt

/opt   software packages (complete and kind of foreign)

##### /usr

Data within /usr should be usable on any FHS-compliant host, ergo data specific to host or time should not go in /usr.
Data within /usr should be read-only

##### bins

whatever/bin is generally for executables
Originally and still in some unixes, /bin would have contained system-essential binaries, while /usr/bin and /usr/local/bin would have contained non-system essential bins (and analogously for lib)
today, /bin often just is a symlink to /usr/bin (and analogously for lib)
whatever/lib generally conains libraries for whatever/bin
/sbin is for binaries needing superuser priviledges/for system administration

##### /tmp

/tmp is for temporary files.
/tmp is sometimes emptied on process exit or on boot.

##### /etc

/etc contains confi files for all the programs that run on your Linux/Unix system
/etc/hosts
/etc/motd|contains the message of the day
/etc/machine-info contains machine metadata such as type of computer, deployment, location and pretty-printed hostname
/etc/hostname contains the usesrs static hostname.
hostnamectl administers the stuff in /etc/hostname and /etc/machine-info, i.e. all the hostnames and the machine metadata.
hostname - show or set the system's host name

##### /dev

/dev contains device files.
It makes sense to treat devices as just another file, as the operations they support (reading, writing or both) are the same as a file.
device files are files that are interfaces to device drivers (or more rarely other things).

##### not real devices

/dev/random and /dev/urandom are CSPRNGs of nix* systems
the difference between /dev/random and /dev/urandom is that the former blocks to wait for more entropy if necessary, the latter does not.
the man suggests one use /dev/random for long-lived GPG/SSL/SSH keys, and /dev/urandom for anything else.
/dev/full is  always full
/dev/zero returns as many 0x00 as you like.
anything written to /dev/null discards the data, whence its nicknames bit-bucket/black hole

##### block device files

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

##### character device files

/dev/stdin and /dev/stdout are symlinks to /dev/fd/0 and /dev/fd/1

#### Mac

((h:all;::<img src="sm_Screenshot%202020-07-09%20at%2014.36.21.jpg">))((c:2;::macOs))'s ((c:1;::/private)) folder contains ((c:3;::a few directories that would have been found in / on FHS-compliant devices)), namely ((s:1-3;::((c:4;::etc)), ((c:5;::tmp)), and ((c:6;::var))))
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}</span>

## files

binary files are often contrasted with plaintext files

### principle types

folder (windows) = directory (*nix)

### binary

Binary files without a specification/documentation/parser are basically meaningless/unreadable.
What the binary files contents mean is defined by the file format.
Binary files are generally smaller and quicker to process than plaintext files

#### bitmaps

In the technical definition, a bitmap maps some domain to some bits.
In the technical definition, a pixmap is a bitmap mapping a pixel to a set of bits.
While in the technical definition, a pixmap is a hyponym of bitmap, they also may be treated synonymously, or sometimes a bitmap is seen as a hyponym of pixmap where one uses one bit per pixel.
The common file format for a pixmap image is BMP.
Pixmap images are very large, since they don't have any compression.

#### multimedia

(multi)media files are almost always binary files

##### images

### plaintext

Markup files are subset of plaintext files.
Markup files are written in markup languages.
markup languages consist of normal text and specific markup, which are intermingled.

#### toml xdg systemd

INI files inspired XDG desktop files.
XDG desktop files inspired systemd unit files.
TOML was inspired by INI, XDG and systemd unit files.
TOML|Tom's obvious, minimal language

#### m3u

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

#### ICAL/VCARD

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

In vCard, properties are direct children of the {{c1::the vCard object}}
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

#### dictionary-based

##### YAML

YAML|YAML Ain't Markup Language

##### JSON

JSON|JavaScript Object Notation
JSON is a plaintext file format.
JSON has the same syntax as JS object literals, with a few exceptions.
In JSON but not JS object literals, keys must be quoted.
In JSON but not JS object literals, functions are forbidden.
In JSON, the top-level item can either be an object or an array.

##### Schema

JSON schemas are schemas for JSON, YAML, usually written in JSON, though they can be written in different things.
top-level keys
title|title for the schema
description|description for the schema
$schema|URL of the version of JSON Schema this document adheres to 
$id|base url for the document, similar to <base> in HTML

##### jq yq

jq|process JSON
yq|process YAML & convert to/from JSON
yq -y/-Y roundtrip back to YAML
<code>yq {{c1::&lt;command&gt;}} {{c2::&lt;flags&gt;}} {{{c3::&lt;file&gt;}}}</code>
<code>yq {{c2::-t/--to-type}} {{c1::yaml}}/{{c1::json}}/...</code> {{c3::outputs the file as the specified file format}}


##### tex

<br>---<br>
  §§ ((c:3;::Tex)) consists of ((c:1;::tex-core)) and ((c:2;::plain-tex)) §<br>
§§ ((c:4;::plain-tex)) is ((c:5;::the set of macros that the tex typsetting program uses)); ((c:6;::tex-core)) is ((c:7;::the typesetting program (that transforms it into output))) §<br>
§§ ((c:8;::Tex)) and thus ((c:8;::latex)) is meant for ((c:9;::typesetting)) §<br>
§§ ((c:13;::TeX)) and thus ((c:13;::LaTeX)) mainly work via ((c:14;::macros)) §<br>
§§ ((c:15;::Mathjax)) renders ((c:16;::a subset of latex)) ((c:17;::in browsers (using js))) §<br>
§§ ((c:18;::current)) latex version: ((c:19;::Latex 2e)) §<br>
§§ ((c:20;::next)) latex version: ((c:21;::Latex 3)) §<br>
§§ <q>latex</q> is properly capitalized ((c:22;::LaTeX)) §<br>
§§ <q>tex</q> is properly capitalized ((c:23;::TeX)) §<br>
§§ the x in ((c:24;::tex and latex)) is pronounced as ((c:25;::a voiceless velar fricative (e.g. loch, bach))) §<br>
===<br>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}</span>

§§ ((c:10;::latex)) is ((c:11;::a set of tex macros)) that is supposed to be ((c:12;::more semantic)). §<br>
texinfo is a set of macros for tex for generating hypertextual documentation

info|read texinfo files

#### subtitles

WebVTT|Web Video Text Tracks Formats
  §§ ((c:33;::WebVTT)) and ((c:33;::.srt)) are file formats for ((c:34;::subtitles)). §<br>
§§ ((c:35;::WebVTT)) is ((c:36;::based on)) and ((c:36;::similar to)) ((c:37;::.srt)) §<br>
§§ ((c:38;::.srt)) is ((c:39;::more common)) than ((c:38;::WebVTT)), but ((c:38;::WebVTT)) is ((c:40;::more new/featurefu))l. §<br>
§§ ((c:41;::Youtube)) amongst others does not support ((c:42;::srt or WebVTT tag formatting)), and ((c:43;::pretty much nothing)) supports ((c:44;::most of WebVTT's most advanced features)). §<br>
§§ ((c:45;::WebVTT and .srt)) mark up their payload with ((c:46;::HTML/XML-style tags)). §<br>
§§ Things in ((c:47;::WebVTT/.srt)) are ((c:48;::generally separated)) by ((c:49;::a blank line (i.e. two newlines))) §<br>
===<br>

<br>---<br>
  §§ WebVTT delimits ((c:51;::major sections)) with ((c:50;::allcaps words)): §<br>
  <table>
  <thead>
    <tr><th>section name</th>
    <th>section semantics/function</th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
<tr><td>((c:1;::WEBVTT))</td> <td>((c:2;s:32;::Begin WebVTT document)) ((h:2;::(may be followed by ((c:32;::text header on the same line)))))</td></tr>
<tr><td>((c:3;::STYLE))</td> <td>((c:4;::inline styling section))</td></tr>
<tr><td>((c:5;::NOTE))</td> <td>((c:6;::comment))</td></tr>
  </tbody>
</table>
===<br>


<br>---<br>
  §§ A ((c:52;::cue)) is ((c:53;::the main unit of information)) in ((c:54;::WebVTT/.srt.)) §<br>
§§ ((c:55;::A cue)) ((c:56;::starts (.srt)/may start (WebVTT))) with ((c:57;::a header line)). §<br>
§§ ((c:58;::The header line that starts a cue)) must be ((c:59;::a running number indicator)) in ((c:60;::.srt)), this is ((c:61;::optional)) in ((c:60;::WebVTT)) §<br>
§§ ((c:62;::The line after the header line if it exists or the first line of a WebVTT/.srt)) ((c:63;::cue)) contains ((c:64;::the time to show the text)), consisting of ((c:65;::two timestamps (RFC 3339 (hh):mm:ss.ttt))) ((c:66;::separated by <code> -&gt; </code> (notice the spaces).))((c:67;::&nbsp;Every line of a cue after the line specifying the time)) specifies ((c:68;::text to be shown.)) Together, these are known as ((c:69;::the payload)). §<br>
§§ Every line of a cue may optionally be ((c:70;::started by <code>- </code>)), this will ((c:71;::not be displayed)) §<br>
===<br>


<table>
  <thead>
    <tr><th colspan="2">WebVTT-specific properties</th></tr>
    <tr><th>CSS property syntax</th>
    <th>CSS function</th></tr>
  </thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
<tr><td>((c:7;::vertical:rl/lr make captions go from top to bottom and either right -&gt; left or left -&gt; right (changes the direction of other settings by 90 deg)))</td></tr>
<tr><td>((c:8;::line:0-100%))</td> <td>((c:9;::display the cue at % offset from the top (or left/right if vertical is specified) (i.e., along the y axis if no <code>vertical</code>)))</td></tr>
<tr><td>((c:10;::position:0-100%))</td> <td>((c:11;::display the cue at % offset from the left (or top/bottom if vertical is specified) (i.e., along the x axis if no <code>vertical</code>)))</td></tr>
<tr><td>((c:12;::size:0-100%))</td> <td>((c:13;::set the width of the cue to %))</td></tr>
<tr><td>((c:14;::&lt;c.foo&gt;content&lt;/c&gt;))</td> <td>((c:15;::specify a class foo to target))</td></tr>
<tr><td>((c:16;::&lt;ruby&gt;...))</td> <td>((c:17;::add furigana etc.))</td></tr>
<tr><td>((c:18;::&lt;v foo&gt;))</td> <td>((c:19;::indicate that foo is speaking))</td></tr>
<tr><td>((c:20;::align:start/end...))</td> <td>((c:21;::align the captions along the x-axis (if not <code>vertical</code>), i.e. the same axis as the position property))</td></tr>
<tr><td>((c:22;::&lt;font color="...))</td> <td>((c:23;::Set the text to a certain color))</td></tr>
<tr><td>((c:24;::&lt;b&gt;, &lt;i&gt;, &lt;u&gt;))</td> <td>((c:25;::make the text bold, italic or underlined))</td></tr>
  </tbody>
</table>
<table>
  <thead>
    <tr><th colspan="2">WebVTT-specific selectors</th></tr>
    <tr><th>CSS Selector</th>
    <th>Selects</th></tr>
  </thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
<tr><td>((c:26;::::cue(.foo)))</td> <td>((c:27;::Target a cue with class foo (&lt;c.foo&gt;)))</td></tr>
<tr><td>((c:28;::::cue))</td> <td>((c:29;::Target any WebVTT cue (shown subtitle)))</td></tr>
<tr><td>((c:30;::::cue(b)))</td> <td>((c:31;::Target a &lt;b&gt; tag within WebVTT))</td></tr>
  </tbody>
</table>
<br>---<br>
  §§ If you ((c:72;::specify timestamp text (WebVTT only))), then ((c:73;::any text before a timestamp text whose time you are at or after)) is ((c:74;::previous text)), ((c:75;::the text from the current to the next timestamp tag)) is ((c:76;::active text)) and ((c:77;::text after the next timestamp tag)) is ((c:78;::future text)). §<br>
§§ If we specify ((c:79;::&lt;track kind="chapters"&gt;)), cues ((c:80;::may not overlap time-wise)), and payloads ((c:81;::may not contain tags)) §<br>
===<br>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}{{c28::}}{{c29::}}{{c30::}}{{c31::}}{{c32::}}{{c33::}}{{c34::}}{{c35::}}{{c36::}}{{c37::}}{{c38::}}{{c39::}}{{c40::}}{{c41::}}{{c42::}}{{c43::}}{{c44::}}{{c45::}}{{c46::}}{{c47::}}{{c48::}}{{c49::}}{{c50::}}{{c51::}}{{c52::}}{{c53::}}{{c54::}}{{c55::}}{{c56::}}{{c57::}}{{c58::}}{{c59::}}{{c60::}}{{c61::}}{{c62::}}{{c63::}}{{c64::}}{{c65::}}{{c66::}}{{c67::}}{{c68::}}{{c69::}}{{c70::}}{{c71::}}{{c72::}}{{c73::}}{{c74::}}{{c75::}}{{c76::}}{{c77::}}{{c78::}}{{c79::}}{{c80::}}{{c81::}}</span>

### complex

epub is a format for ebooks that is in essence just a zip wrapper + scaffolding around web technologies such as HTML, CSS, JS, SVG, etc.

#### container

A container format is a file format that contains different parts.
The component parts of a container format may be called chunks, segments, streams, or something else.
In general, the component parts of a container format have some kind of header aand a body.
IFF is a chunk-based file format.
IFF chunks begin with a type ID, followed with a specifier of the length of the chunk.
RIFF and AIFF are file formats based on IFF, but TIFF (surprisingly) isn't 

### cross-cutting

#### email

Fundamentallly, all emails in an email account (generally associated with a single email address, but not necessarily) are stored in an an (email) mailbox
Message/mail delivery agents are programs that deliver emails to a mailbox.

##### mbox & imf

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

##### maildir

The maildir format is a format to store mailboxes and mail directories.
The maildir format has three subdirectories (at least) for any directory.
The three mandatory directories for any subdirectory in maildir are cur, new, and tmp.
Using maildir, an arriving message will be sorted into tmp until it is processed completely, then it is inserted into new.
Using maildir, once a mail in new has been read, it si sorted into cur.

## VCS

VCS|Version Control System

# hardware/low-level

## hardware only

### circuits

A logic circuit consists of interconnected logic gates.
A combinatorial logic circuit is one whose output only depends on its input.
A sequential logic circut is one whose output depends on its input, and the previous state.

### processors

#### architecture

The harvard architecture separates instructions and data (= does not store them in the same way/treat them differently)
Modern CPUs are claimed to be stored-program computers, but since they separate data and instructions to a certain extent, they may be considered modified Harvard architecture to a certain extent.

In the VNA, the CPU, memory and IO are connected to/via the bus.
<img src="sm_tmp_xpihn7q.png">

#### CPU

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

#### CU

CU  Control Unit

#### machine code & instruction set

Assembly language is syntactic sugar for machine code.
Machine code consists of machine language instructions.
Machine code and thus machine language instructions are what run directly on the CPU, at least in the classical model.
In fact, by now, there is often a layer below machine code known as microcode.
opcode is short for operation code
Within a machine language, an instruction is defined by an opcode.
Within a machine language, an instruction consists of the opcode it is defined by, plus zero or more operands.
An instruction set architecture defines the instruction set plus a bunch of other CPU features (such as registers, addressing, I/O) (however, the two terms are often also used interchangably)
The instruction set is the set of operations a processor supports, which bit sequences represent which  machine language instructions, and how the arguments are organized.
Depending on the instruction set, machine langauge instructions may all be the same length or not.
In a general sense, a word is the fundamental unit used by a processor of a given ISA ≈ how many bits a PU may address at once.
The length of a word is the word size.
In general, most registers are word-sized, as are memory cells.
The largest possible memory address is also word-sized (since otherwise, how would you address them) .
what is 32 bit in a 32-bit processor and 64 bit in a 64-bit processor is the size of memory addresses and thus the {{c1::the word size}}

A Load-store architecture is a type of instruction set architecture which only has instructions that either do ALU operation {{c1::access (load/store) memory}}, never at the same time.
For a load-store architecture, all things being operated on must be in registers.

##### Instruction-level parallelism

Instruction-level parallelism is the parallel execution of instructions of a single thread (thus it is different from concurrency).
In general, the goal of instruction-level parallelism is to keep all of the CPU busy
fors of instruction-level parallelism include Instruction pipelining, Out-of-order execution + register renaming, speculative execution + branch prediction.
Instruction pipelining attempts to keep every part of the processor busy with some instruction by dividing incoming instructions into a series of sequential steps (the eponymous "pipeline") performed by different processor units with different parts of instructions processed in parallel.
Out-of-order execution executes instructions as resources are available, rather than the order in the program, if this is possible.
register renaming is a technique that abstracts logical registers from physical registers.
Register renaming allows us to eliminate false data dependencies coming from write after read dependencies, enabling more out-of-order execution.
If compilers did not reuse registers, register renaming would not be necessary, however this is often difficult in practice.
speculative execution is executing instructions before we know if they will be needed
speculative execution is worthwhile if the cost of waiting until we know if the instructions will be needed to be executed is higher than the cost of speculatively executing.
speculative execution is most commonly referred to in the case of instuction pipelining, but may also be performed in many higher-level tasks.
speculative execution (in CPUs) is most often performed in the case of control flow, where branch prediction is often used to try and guess which branch is most likely.


##### Hazards

In CPUs, a hazard is when the next instruction cannot execute in the following cycle, or doing so would lead to an error.
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
Most RISC ISAs are also load-store ISAs.
CPI = clocks/cycles per instruction
In general, a RISC ISA has 1 CPI, with fixed-length instructions.

#### cache

CPU caches are used to speed up memory access, which is especially important since CPU memory is orders of magnitude slower than processing speed.
The cache levels that are common as of 2021 are L1, L2 and L3 cache, with L4 cache slowly becoming more common.
L1 cache is the fastest cache level, and it goes downwards from there
Multi-level caches are caches that are composed of different cache levels.
The organization of multi-level caches into faster/slower cache levels is known as the cache hierarchy.
processor finds memory location in cache   cache hit
processor does not find memory location in cache   cache miss
When a cache miss occurs, the processor generally needs to wait while the data is being fetched
the {{c1::Cache replacement policy}} is the policy that decides what to 'evict' on having to add something new to the cache on a cache miss

#### clocking

A clock signal {{c1::coordinates/synchronizes the circuits}} the circuits of the thing it's governing.
A clock signal is usually a square wave with a high and low state.
In relation to the clock signal's square wave the circuits activate on {{c1::on one (or both) of the (vertical-ish) edges}}, depending on the implementation
{{c1::A synchronous circuit}} is a circuit where the changes are synchronized by a clock signal.
DDR  Double data rate
{{c1::DDR (double data rate)}} is the technology that activates the circuit. both on the rising and the falling edge of the clock signal

### chipset

<img src="sm_chipset.svg">

### assembler

Why don't we just write programs in machine code/assembler?  extremely mühselig and error-prone
Today, assembler/machine code is almost always generated by compilers/interpreters/etc.

## layering on hardware 

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

# crypt

{{c1::a cipher}} is an algorithm for performing encryption/decryption
Ciphertext is the text that is the result of {{c1::using a cipher}}
A substitution cipher is a cipher where an unit of plaintext is replaced by an unit of cipher text
The caesar cipher is a kind of substitution cipher where the replacement is done by rotating the entire alphabet by some number.
A brute-force attack is an attack of something such as a password {{c1::By trying until successful}}

## random numbers

C(S)PRNG  Cryptographically (secure) pseudorandom number generator
PRNG  pseudorandom number generator
RNG  random number generator

# *nix

## POSIX

The Portable Operating System Interface (POSIX) is a family of standards specified by the IEEE Computer Society for maintaining compatibility between operating systems.
POSIX specifies both kernel- and user-level APIs as well as various shells and utilities.

## GNU/Linux

GNU is the set of free software that accompanies the linux kernel in GNU/Linux.
GNU = GNU's not unix
The GPL was originally created for GNU
(GNU) GPL = GNU General Public License
Linux technically refers to the Linux kernel.
GNU software set + Linux kernel = GNU/Linux
Often, Linux alone is used (technically incorrectly) to refer to GNU/LInyx

### linux

#### distros

A Linux distribution is GNU/Linux plus a set of other stuff, which depends on the flavor.

#### input

On Linux, input devices are often handled on linux by the library libinput, which is also the name of the command used to interface with it. 
libinput is native in wayland, but optional in X, which can also manage input devices directly, whose implementation you can interface with via xinput.

#### X

#### systemd

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

##### units

systemd deals with system units.
A systemd unit represents any kind of system resource.
systemd units contain dependencies to tell us what we need to load first.
Systemd units end .unittype.
Systemd units are stored in unit files.

.timer   timed functionality similar to cron
.target   a state to be reached
.socket   sockets
.service   Managing some kind of service
.mount   predefined mount points
.automount   .mounts that will be automatically managed
.path   notifying when a path becomes available

When a .path units path becomes available, {{c1::an associated .service}} is started.
When a .socket unit has some activity, an associated service is started.
When a .timer units time state is reached, an associated unit is started.

###### targets

reboot.target   The target for rebooting
poweroff.target   The target for turning off the computer
multi-user.target   multiuser (but no GUI)
graphical.target   multiuser <b>with GUI</b>
default.target   what the machine should try and aim for when booting (another target generally)

###### CLI

The main command to administer systemd is systemctl
starting/stopping an unit for systemd does that {{c1::right now}} but temporarily
enabling/disabling an unit for systemd does that {{c1::next reboot/session (by default)}} but permanently.
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


## files

linux: "Everything is a file"
Plan 9: "Really everything is a file"

### 7 types of files

In unix, there are 7 types of files.
Types of files in linux: {{c7::Regular file}} {{c6::Directory}} {{c5::Symlink}} {{c4::FIFO/named pipe}} {{c3::Socket}} {{c2::Device file (block)}} {{c1::Device file (character)}}

#### named pipe

named pipe = FIFO
mkfifo creates a new named pipe
named pipes are deleted via rm

#### links

ln creates hardlinks by default, and symlinks with -/--symbolic.
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

#### directories

dentry = directroy entry.
in the ext filesystem, a directory file is made up of a list of directory entries.
In the ext filesystem, a directory entry contains the inode number, file name and file name length.
Within the ext filesystem, the first entry in any directory file is the . entry.
Within the ext filesystem, the second entry in any directory file is the .. entry.
.|current directory
..|parent directory
If there is an inode not referenced by any directory entry, it will be placed in lost+found.

#### device files

two of the seven types of files are device files.
Block device files grant random access.
Character device files grant sequential access.

### permissions

The user-and-group model means that for each file every user on the system falls into one of three categories: the owner of the file, someone in the file’s group and everyone else
The three permissions that unix tracks are {{c1::read}}, {{c2::write}},, and {{c3::execute}}
<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th></th>
    <th></th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:1;::x))</td> <td>((c:2;::execute))</td></tr>
<tr><td>((c:3;::w))</td> <td>((c:4;::write))</td></tr>
<tr><td>((c:5;::r))</td> <td>((c:6;::read))</td></tr>
  </tbody>
</table>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}</span>

### misc

When config files are split up into multiple files, .d directory names are often used.
.d directory names are often used to give them a different names from normal files doing something  similar.
dotfiles are files starting with a dot.
Dotfiles are generally hidden by default.
Dotfiles are often used for config or metadata.

## command-line 

### meta

most configurable commands are done so by a config file, either at ~/.commandname or XDG_CONFIG_HOME/commandname if following the XDG base directory specification, some also read from a global config file generally in /etc

#### common syntax considerations

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
-a|show dotfiles
-E|use ERE instead of BRE (Only where applicable, obv)

Options ≈ switches ≈ flags are indicated by hyphen(s) followed by characters
By convention, an option started by a single hyphen is one character long.
By convention, an option started by two hyphens is multiple characters long.
Generally, multiple single character flags can be joined into one: -h -a = -ha
In general, mac only features short flags, while linux also has long ones (this presumably has a deeper reason that I currently don't know)
In general commands that do something from a source to a target (e.g. cp, mv) have the default syntax SOURCE TARGET
{{c1::}}
-- normally ends the list of flag arguments and allows you to pass plain arguments

Well-behaved shell programs take input from stdin (if there is data to operate on) and output to stdout (act as filters).

#### man

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

### full-on programs

#### subscriptions

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

#### mail

mail or the older mailx are *nix builtins to manage mail.

#### termdown

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

### fs

#### navigation

##### information

pwd|print path of current directory
ls|list file in directory
tree|print a directory tree
tree -L <n>|go to depth n

-s|display files and directories with their sizes
-S|sorting by size in output
-F|list all files and directoreis annotated with /*@

something/|directory
something@|symlink
something*|executable

###### find

find|find files

###### grep

grep is a tool that takes a regex, applies it to a set of files, and prints the lines that match.
There are tons of grep variants:
agrep|grep with fuzzy matches

There are also many alternative variants of grep using more modern regexes, and also significantly faster:
speed: rg > ag > ack

greps exit status if it finds a match is 0, if it does not find a match, it is 1.
grep -c count the produced lines.

##### file info

stat|info about file
od|output files in octal, but also in other repreesentations
od -x|hex dump
cat|output a file
wc|count words, characters and lines

wc output ordering
{{c1::lines}} {{c2::words}} {{c3::characters}}

##### traversal

cd|move to specified directory

cd without an argument moves back to your home directory
cd - moves back to previous directory (not parent directory)

#### changing files

mv will silently overwrite if moving to something that already exists.
dd   copying (similar to cat/cp) with some low-level options
shred overwrites a file multiple times so it is difficult to recover, however this interacts badly with SSDs
touch|create emtpy file
mkdir|create empty directory

#### managing fs

<code>mount</code>|mounting a device
<code>umount</code>|unmount something

### text

#### editors

a stream editor is a filter used to do text transformations
The most common stream editor is sed。
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

For sed, specifying a regex within an addr selects lines that match the regex
For sed, using the \<char> syntax as a regex starting delimiter must then continue using <char> as a delimiter, allowing one not to have to escape \

original line editor for linux: ed

nano|basic cmd-line text editor

#### basic filters

lolcat   make output rainbowy
cowsay   make an ascii cow say the specific thing
sort|sort file line by line
-n sort by order of magnitude
uniq|remove adjacent (!) matching lines
cut|extract specific sections of each line based on delimiters
-f <list>|only extract fields <list>
-d <char>|treat <char> as delimiter

The commands head and tail print the first/last few lines of a file.
The amount of lines printed by head/tail defaults to 10

#### generation


### media

#### generation

Default mac japanese voice is  Kyoko

#### processing

pdftk and qpdf are the most common CLI tools for pdf transformation

##### ffmpeg

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

#### display 

lynx|text-based browser
ffmpeg media player   <code>ffplay</code>
feh|terminal-launched image viewer
imgat|in-terminal image viewer


mpv|terminal based video player

mpv plays files, urls, and playlists.

Play a playlist<filename>   --playlist=&lt;filename&gt;
don't open a new video window<filename></filename>   --no-video

##### mpd mpc

mpd is short for Music Player Daemon.
mpd acts as a server, which you can start via the <code>mpd</code> command (either directly or via a service)
As a proper server, mpd occupies a port on the host.
You can interface with the mpd server with a number of clients, e.g. mpc

mpc -p port or --port=port|connect to mpd at the specified port
<code>mpc queue(d)</code>|<b>show</b> next song
<code>mpc current</code>|show currently playing songm<br><div class="sub">
<code>mpc update</code>|update collectiion by scanning for changed files
<code>mpc stats</code>|display mpd playing info such as total play time up until now, etc.
<code>mpc rescan</code>|rescan whole music directory
<code>mpc lsplaylists</code>|list all current playlists
<code>mpc ls</code>|list the contents of the music directory
<code>mpc load &lt;name&gt;</code>|load a certain playlist
<code>mpc clear</code>|clear queue
<code>mpc shuffle</code>|reshuffle the playlist
<code>mpc single</code>|toggle single mode (will stop playing after one song, or repeat one song if repeat is toggled)
<code>mpc repeat</code>|toggle repeat
<code>mpc random</code>|toggle random playback (that is, pick songs from the queue at random)
<code>mpc prev</code>|go to previous song
<code>mpc playlist</code>|show the current playlist
<code>mpc pause</code>|pause
<code>mpc next</code>|go to next song
<code>mpc toggle</code>|play if paused, pause if playing</div>

### online data fetching

<code>urban</code>|Terminal urban dictionary browser
<code>trans</code>|Use google translate to translate text
<code>deepl</code>|Use deepl to translate text

lang-specifier (trans, deepl) ::= [<lang>]:<lang>{+<lang>} # leave out first arg for detection


### sysadmin

uptime -  Print the current time, the length of time the system has been up, the number of users on the
       system, and the average number of jobs in the run queue over the last 1, 5 and 15 minutes. 

#### arch

arch with no args prints the current system architecture
the arch command can be made to run programs on other architectures via arguments.

#### hardware info

lspci   list pci devices
lshw   list hardware config
lsblk   list block devices
lsusb   list USB devices

#### GUI

##### X

wmctrl   Manage an X window manager

#### state change

<code>shutdown</code>|shutting your system down
reboot|restart your computer

caffeinate creates assertions to alter system sleep behavior. 
If no assertion flags are specified, caffeinate creates an assertion to prevent idle sleep.  
If a utility is specified with -u, the caffeinate assertions will persist for the duration of the utility's execution. 
if no utility is specified with -u, caffeinate creates the assertions directly, and those assertions will persist until caffeinate exits, or until the timeout specfied w/ -t.

### leaving the shell

termux-open-url   open an url in its default application (termux)

### misc

<code>redshift</code>|make screen red/yellowish (linux)

set color temperature    <code>-O temp </code>
reset color temp   <code>-P</code>

<code>nightlight</code>|make screen red/yellowish (mac)

<code>nightlight status</code>|show <code>nightlight</code> status   
<code>nightlight on</code>|enable <code>nightlight</code>   
<code>nightlight schedule</code>|manage <code>nightlight</code> schedule   
<code>nightlight temp</code>|show current <code>nightlight</code> color temperature (with arg: set it)

CLI tool for managing displays|<code>display_manager.py</code>
<code>display_manager.py res</code>|manage resolutions (display_manager.py)
<code>display_manager.py res width height</code>|Set the resolution to width * height (display_manager.py)

date is a tool for showing, formatting or changing date and time
If run without arguments, date gets the current date and time.

<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th>option</th>
    <th>does</th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:1;::-u / --utc / --universal))</td> <td>((c:2;::use UTC))</td></tr>
<tr><td>((c:3;::-d date / --date=date))</td> <td>((c:4;::calculate the date for the specific date))</td></tr>
<tr><td>((c:5;::-I/--iso-8601))</td> <td>((c:6;::output the date as ISO 8601))</td></tr>
  </tbody>
</table>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}</span>

Sleep is a command that waits for the specified time.
sleep-command ::= sleep{ <number><suffix>}
suffix ::= s|m|h|d
for sleep, multiple number-suffix specifier waits for their sum

recode - converts files between character sets
insect - shell scientific calculator

unoconv is a CLI util to convert files using libreoffice in the background.

tee redirects a stream to stdout and to all listed files

## processes

On unix systems, a process is an (instance of a) program that is {{c1::running}}
On unix, a process is the instance that has its own heap.
On unix, every process has a parent.
PPID|Parent Process ID

### process management

ps|list of processes
pstree|processes as a tree
kill kills a process, given its PID
killall kills a n processes, given a string that their name contains

### file descriptors

A file descriptor is a positive integer that uniquely identifies a file (or file-like) things.
Each process has its own file descriptors.
The file descriptiors of a single process are stored in their own file descriptor table.
The kernel maps the file descriptors the file descriptor table of a single process to the file table.
The file table is a system-wide table of all open files.
The file table contains reference to the relevant inodes.
Each process has three file descriptors allocated automatically, namely for the standard streams.
stdin   0
stdout   1
stderr   2

### daemons

A daemon is a process running in the background, not under the direct control of a user.
In *nix, a daemon is generally a process which is a child of the init process.
A daemon is usually created either by a process forking a child process and then immediately exiting, thus causing init to adopt the child process, or by the init process directly launching the daemon. 
The names of daemons generally end with d.

### terminal system

#### fg bg

<pre><code>^Z</code></pre> (as keyboard input)   Stop (not kill) the current program
the bg command takes a suspended command (e.g. one that was Ctrl-Z ed) and resumes its execution in the <b>background</b>
fg  resume stopped task in foreground
bg  resume stopped task in background
{{c1::&amp;}} at the {{c2::end of an command}} {{c3::puts it in the backround}} (but it {{c3::still continues running}})
jobs|show processes running in the background

#### terminal

A physical terminal is connected via cables to an UART driver.
drivers for screen, keyboard etc. are connected to a terminal emulator (not a window).
The UART driver or terminal emulator are connected to the line discipline.
The line discipline may be disabled, in which case the characters are sent directly to the process, the so called cooked/canonical mode.
the line discipline is connected to the tty driver.
The tty driver is passive, while it has fields and methods, they need to be called from outside, e.g. via signals.

To the terminal, the shell is just one more process running within it.

Each physical terminal would have been its own separate thing, and so each terminal emulator is also its completely separate thing.
terminal emulators are represented by /dev/tty<n> files
terminal emulators are the things that are most often called ttys.
Terminal emulators may also be called virtual terminals/consoles, mainly in contrast to physical terminals.
virtual terminal = virtual console.
vt/vc is short for virtual terminal/console.
proper terminal emulators don't run within a GUI, but take over the whole screen (are the shell themselves, don't run within a shell)
/dev/tty<n> files are provided by the kernel.
/dev/tty0 represents the current controlling tty.
When in a GUI, /dev/tty0 may be the terminal emulator the window server is running in.
On linux, pressing ctrl + alt + f<number> switches to tty<number>
Linux typically starts with 6 virtual consoles, and then one additional one (tty7) to run the window manager in.
A terminal window is one level of emulation deeper than a terminal emulator, since it lives in a GUI which in linux at least itself lives within a terminal emulator.

In the past, many hardware/physical terminals might have been connected to one computer.
In the past, the system console would have been its own hardware/physical terminal connected directly to the computer.
Today, the system console is merely the device file /dev/console.

##### signals

signals allow the kernel to communicate asynchronously with a process.
In the context of terminals, signals may be sent by/via TTY driver or some other part of the terminal subsystem.

##### terminal window

A terminal emulated within a GUI is known as a terminal window
Alternative terminal window (mac)|iTerm2

##### shell commands for terminal management

There are a number of shell commands that nevertheless still are concerned with terminals, and not with shells
fgconsole   get the number of the current tty
fgconsole --next-avaliable   get next unallocated vt
deallocvt   remove unused virtual terminals
chvt N   change to ttyN

#### shell

the shell is typically the foreground process, buty may be the background process e.g. if we're using a TUI 
The shell is a special kind of program.
The shell is the interpreter that executes the commands.


clear|clears the terminal window

##### shell history

history|list of past commands
<pre><code>!index</code></pre>   Repeat the past command with index index
indexes for ! for repeating start at 1 for the first command and go from there



##### The directory stack

in nix, there is a stack of directories called the directory stack.
in nix, you can push/pop from the directory stack with the commands pushd/popd.
pushd not only pushes the specified directory to the stack, but also cds there.
The dirs command shows the contents of the directory stack.
dirs, pushd and popd all take a positional argument +/-<n>, which do something with the nth directory counting from zero and from the start/end respecitvely
dirs +/-<n>|display the nth directory counting from the start/end
pushd +/-<n>|bring the nth directory counting from the start/end to the top of the stack by rotating the stack
popd +/-<n>|remove the nth directory counting from the start/end from the directory stack (without cding)

##### Prepopulated shell variables

PWD|current directory
OLDPWD|directory before last pwd
DIRSTACK|everything on the directory stack
PAGER|set the pager
HOME|user home directory

EDITOR and VISUAL are shell environement variables {{c1::setting the default editors}}
PATH is for where to find executables.
PATH contains, well, paths, separated by colons.
For anything in PATH we can execute it by just using its name, to execute anything else we would have to use its path.


##### Pattern matching

*|any string
?|any single character

##### Shell lifecycle

0. The shell may get its input from a file, a string, or the terminal.
1. the shell tokenizes the input
2. the shell parses the input into commands
3. The shell performs expansions
4. the shell performs redirections
5. the commands are executed
6. the shell waits for the commands to complete and collects its exit status

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
Bash's two operators for specifying defaults within parameter expasion are :-, :+ and :=.
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
To implement process substitution, bash creates a pipe with two file descriptors.
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
To see what a command will actually get from a file name expansion, you can prefix it with <code>echo</code>

wildcard|matches
*|matches 0-n arbitrary characters, excluding directory separators
**|0 - infinity characters, including directory separators
?|matches 1 arbitrary character
@(foo|bar|baz)|one of the options foo, bar, baz
?(foo|bar|baz)|zero or one of the options foo, bar, baz
+(foo|bar|baz)|one <b>or more</b> of the options foo, bar, baz
!(foo|bar|baz)|none of the options foo, bar, baz
*(foo|bar|baz)|zero or more of the options foo, bar, baz
[^&lt;characters&gt;]   one character that is none of &lt;characters&gt;
[!&lt;characters&gt;]   one character that is none of &lt;characters&gt;
[aml]   one of the characters a, m, l
[a-m]   one character in range of characters a-m

####### Quote removal

After the preceding expansions, all unquoted occurrences of the characters ‘\’, ‘'’, and ‘"’ that did not result from one of the above expansions are removed. 

####### Redirection

Before a command is executed, its input and output may be redirected using a special notation interpreted by the shell. 

redirecting input [<n>]<[&]<word>
redirecting output [<n>]>[\||>][&]<word>

1> may be abbreviated > 
0< may be abbreviated <

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

###### declaration commands

declaration commands = {alias, declare, typeset, export, readonly, local}

### process relationships

A session is a collection of process groups.

## users and groups

GID|group id
UID|user id
groups/users on nix are uniquely identified by their user or group ID.

### commands

whoami|show current username
login|login as user
logout|logout of shell

### superuser

superuser = root = admin(istrator)
OS-independently, the superuser/root/administrator is a user with large to unlimited power over the system.
In unix, the superuser is the user with the UID 0.
In unix, the three groups that hasve superuser/sudo-related priviledges are wheel, sudo and admin.
sudo allows executing a single command with superuser priviledges.
To use sudo you need to enter your own password, to use su you need the password of the relevant user, in this case the superuser password.
Who can use sudo is managed in /etc/sudoers


## projects

freedesktop.org was formerly called X Desktop Group (XDG)
freedesktop.org governs projects such as the X Window System, wayland or systemd



# communication

## concepts

### serial and parallel

Serial communication sends its bits one after another over the channel.
Parallel communication sends multiple bits simultaneously over multiple subchannels.
One would expect parallel communication to be faster than serial communication, with the factor equivalent to the amount of channels/wires/whatever, however serial communication can often be clocked far higher to make up for it.
Serial communication is often far easier/simpler to implement and thus less error-prone, cheaper and thinner/lighter than parallel communication.

### allow & deny

an allowlist implies forbidding everything by default
an allowlist enumerates a set of things that may pass
a denylist implies allowing everything by default
an denylist enumerates a set of things that may not pass
allowlists were/are known as whitelists
denylists were/are known as blacklists

### topologies

A tree network may consist of star networks connected {{c1::via a bus network}}, or may be a tree just as a network.
In a bus, everyone attached recieves the transmission.
In a bus, only one entity can send at a time
A daisy chain is a topology where devices are linked in a line or ring.

### master/slave

master/slave is (problematically) a protocol where one thingy controls or serves as an exampleto a bunch of other thingys


## hardware / low-level

### concepts

Crosstalk is a signal transmitted on one circuit or channel causing an undesired effect {{c1:: on another circuit or channel}}
A telegraph is a system for communicating at a distiance via coded signals

### media

semaphore is telegraphy via visual signalling.

### protocols & connectors

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

#### DP

Mini and nonmini {{c4::DisplayPort}} is mainly for {{c1::video / audio}}, but can also carry {{c2::USB}} and {{c3::other data (e.g. thunderbolt)}}

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

<table class="yesno"><tbody><tr>
  <th>Standard
  </th>
  <th>USB 1.0
  </th>
  <th>USB 1.1
  </th>
  <th>USB 2.0
  </th>
  <th>USB 2.0 Revised
  </th>
  <th>USB 3.0
  </th>
  <th>USB 3.1
  </th>
  <th>USB 3.2
  </th>
  <th>USB4
  </th></tr>
  <tr>
  <th>Maximum transfer rate
  </th>
  <td colspan="2">12 Mbps
  </td>
  <td colspan="2">480 Mbps
  </td>
  <td>5 Gbps
  </td>
  <td>10 Gbps
  </td>
  <td>20 Gbps
  </td>
  <td>40 Gbps
  </td></tr>
  <tr>
  <th>Type A
  </th>
  <td colspan="4"><img src="https://upload.wikimedia.org/wikipedia/commons/7/7e/USB_Type-A_receptacle.svg" width="75" height="50">
  </td>
  <td colspan="2"><img src="https://upload.wikimedia.org/wikipedia/commons/f/f4/USB_3.0_Type-A_receptacle_blue.svg" width="75" height="67">
  </td>
  <td colspan="2" class="no">Deprecated
  </td></tr>
  <tr>
  <th>Type B
  </th>
  <td colspan="4"><img src="https://upload.wikimedia.org/wikipedia/commons/2/28/USB_Type-B_receptacle.svg" width="50" height="60">
  </td>
  <td colspan="2"><img src="https://upload.wikimedia.org/wikipedia/commons/8/8c/USB_3.0_Type-B_receptacle_blue.svg" width="59" height="75">
  </td>
  <td colspan="2" class="no">Deprecated
  </td></tr>
  <tr>
  <th>USB-C
  </th>
  <td colspan="3" class="no">N/A
  </td>
  <td colspan="5"><img src="https://upload.wikimedia.org/wikipedia/commons/0/07/USB_Type-C_Receptacle_Pinout.svg" height="80">
  </td></tr>
  <tr>
  <th>Mini-A
  </th>
  <td class="no">N/A
  </td>
  <td colspan="3"><img src="https://upload.wikimedia.org/wikipedia/commons/e/eb/USB_Mini-A_receptacle.svg" width="75" height="50">
  </td>
  <td colspan="5" class="no">Deprecated
  </td></tr>
  <tr>
  <th>Mini-B
  </th>
  <td class="no">N/A
  </td>
  <td colspan="3"><img src="https://upload.wikimedia.org/wikipedia/commons/e/ec/USB_Mini-B_receptacle.svg" width="67" height="50">
  </td>
  <td colspan="5" class="no">Deprecated
  </td></tr>
  <tr>
  <th>Mini-AB
  </th>
  <td colspan="3" class="no">N/A
  </td>
  <td><img src="https://upload.wikimedia.org/wikipedia/commons/f/f3/USB_Mini-AB_receptacle.svg" width="60" height="40">
  </td>
  <td colspan="5" class="no">Deprecated
  </td></tr>
  <tr>
  <th>Micro-A
  </th>
  <td colspan="3" class="no">N/A
  </td>
  <td><img src="https://upload.wikimedia.org/wikipedia/commons/8/86/USB_Micro-A.svg" width="75" height="50">
  </td>
  <td colspan="2"><img src="https://upload.wikimedia.org/wikipedia/commons/4/42/USB_3.0_Micro-A.svg" width="117" height="50">
  </td>
  <td colspan="2" class="no">Deprecated
  </td></tr>
  <tr>
  <th>Micro-B
  </th>
  <td colspan="3" class="no">N/A
  </td>
  <td><img src="https://upload.wikimedia.org/wikipedia/commons/1/1b/USB_Micro-B_receptacle.svg" width="75" height="42">
  </td>
  <td colspan="2"><img src="https://upload.wikimedia.org/wikipedia/commons/a/a8/USB_3.0_Micro-B_receptacle.svg" width="117" height="50">
  </td>
  <td colspan="2" class="no">Deprecated
  </td></tr>
  <tr>
  <th>Micro-AB
  </th>
  <td colspan="3" class="no">N/A
  </td>
  <td><img src="https://upload.wikimedia.org/wikipedia/commons/6/6c/USB_Micro-AB_receptacle.svg" width="75" height="50">
  </td>
  <td colspan="2"><img src="https://upload.wikimedia.org/wikipedia/commons/7/7a/USB_micro_AB_SuperSpeed.png/117px-USB_micro_AB_SuperSpeed.png" width="117" height="69">
  </td>
  <td colspan="2" class="no">Deprecated
  </td></tr></tbody></table>

USB has a tree (bus + star) topology 


##### usb 4

USB 4 was released in 2019.
As of USB 4, the only connector type is USB C.

## protocols

Protocols are often {{c1::layered}} to produce a {{c2::protocol stack}}

### pushpullpoll

pulling is where the request initiates from the client, and is responded to by the server
pushing is where a request is initiated by a server.
polling is frequently checking whether a thing is in a certain state
polling may be used to simulate push protocols.

### OAuth

OAuth 2.0 (grant type: Authorization code)
<img src="tmp7t5et6aw.png" />

## APIs

the point where one interfaces with an API is an endpoint
For HTTP APIs, the endpoint is most commonly an URL + request verb.

### REST

#### HATEOAS

in a RESTful API following HATEOAS, the API may change its URLs without creating incompatibilites
in a RESTful API following HATEOAS, one hits an initial API URL and navigates via hyperlinks from there.

## networks

### telegraphs

The first type of telegraph was the optical telegraph.
The electrical telegraph began to overtake optical telegraphs middle of the 19th century.
electrical telegraph is often just shortened to telegraph.
The electrical telegraph uses electrical pulses as a medium.
Telegraph stations were connected by wires.
The first telegraph was the needle telegraph, later replaced by the telegraph with key and sounder.
((h:all;::<img src="morse-vail-telegraph-key-1844-science-source.jpg">))A {{c1::telegraph key}} was/is a electrical switch where {{c2::pressing it}} would {{c3::produce a signal}} (and {{c4::holding it}} would {{c5::produce a longer one}}).
The telegraph sounder would have produced clicks from the electrical impulses.
Telegraphs were operated by telegraph operators until the advent of teh writing  pelegraphs.

### telex

Telex was the network of teleprinters common in a large part of the 20th century.
Rough synonyms: {{c1::Teletype}}, {{c2::Teleprinter}}, {{c3::Telex <sub>theoretically the network standard, but in practice used mostly for the machine</sub>}}, {{c4::TTY}} (abk.), teletype(writer)
Teletypewriters/teleprinters/telex/ttys have keyboard for input and a printer for output.
Video terminals then came to replace teletypewriters especially for computer IO
Teletypewriters + video terminals = physical/hardware terminals.

### the internet

On a basic level, the internet is a system of globally interconnected {{c1::computer}} {{c1::networks}}.
The internet runs on the internet protocol suite.

#### standards

IANA  Internet Assigned Numbers Authority
IETF  Internet Engineering Task Force
BCP   Best current practice
RFC   Request For Comment

RFCs are generally published by the IETFs.
RFCs may document internet standards, but RFCs may also be informational or experimental and non-normative. 
BCPs are a subset of RFCs.

## models

The OSI model remains useful, but unimplemented.
In both the OSI and the TCP/IP Model of how computers communicate, the application layer is the {{c1::top}} layer.
Internet protocol suite = TCP/IP
The internet protocol suite is a protocol stack
Instead of the OSI model, the TCP/IP model is used to model the communication on the internet today.
One of the first networks to implement the {{c1::TCP/IP protocol suite}} and one of the precursors to {{c2::the internet}} was {{c3::ARPANET}}

<table>
<thead>
<tr>
<th>OSI Model</th>
<th>TCP/IP Model</th>
</tr>
</thead>
<tbody>
<tr>
<td>((c:1;::Application))</td>
<td rowspan="3">((c:10;::Application))</td>
</tr>
<tr>
<td>((c:2;::Presentation))</td>
</tr>
<tr>
<td>((c:3;::Session))</td>
</tr>
<tr>
<td>((c:4;::Transport))</td>
<td>((c:5;::Transport))</td>
</tr>
<tr>
<td>((c:6;::Network))</td>
<td>((c:7;::Network/Internet))</td>
</tr>
<tr>
<td>((c:8;::Data Link))</td>
<td rowspan="2">((c:11;::Link))</td>
</tr>
<tr>
<td>((c:9;::Physical))</td>
</tr>
</tbody>
</table>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}</span>

### layer 7

HTTP, SMTP, POP, SSH, telnet...

#### common concepts

##### URLS & Hyperlinks

###### URI

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
URI unreserved characters: {{c5::alphanumerical}}, {{c4::-}}, {{c3::_}}, {{c1::.}}, {{c2::~}} (the rest are reserved)
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

###### URN 

the path of URN URIs can theoretically be anything, however it typically has the following syntax
urn-path ::= <urn-namespace>:{<urn-subnamespace>:}<unique-id> 
urn-namespace ::= ISBN|ISSN|UUID|...
e.g. urn:oasis:names:specification:docbook:dtd:xml:4.1.2

###### origins

Two or more URLs that share a common origin (s/h/p tuple) are same-origin, all others are cross-origin

###### domains

top-level domain   TLD

TLD
foo.bar.net  .net

Linux has three hostnames, static, transient, and pretty.
The pretty hostname can be pretty much anything
The static hostname is used for programmatic purposes, the transient hostname is used as a fallback.
While the pretty hostname can be pretty much anything, static and transient hostname are limited to 64 characters.

###### hotlinks, deeplinks

hotlinking = inline linking
Hotlinking is embedding a resource from {{c1::another fqdn}}
A deep link may be a link that links to any other page than the site's home page, a link that links to content within an installed app instead of a webpage (polysemy).
A link to the homepage of a page is called a surface link

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

#### protocols

##### WHOIS

whois is the command to query WHOIS.

##### HTTP

HTTP|HyperText Transfer Protocol

##### telnet/ssh

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

SSH allows using a short user@hostname form.
scp is cp (same syntax etc.) but remotely using SSH.
For scp, when using user@hostname, add the file with :filename to the end\

ssh-keygen manages keys for SSH.

##### NIS/YP

YP = Yellow Pages
NIS = Network Information Service
NIS and YP are the same thing, just that YP was trademarked in GB and hence NIS.
NIS/YP is a protocol for sharing configuration files between computers.
domainname shows or sets the NIS/YP (!) domain nime
aliases for domainname: nisdomainname, ypdomainname
dnsdomainname shows the systems DNS domain name (the part of the FQDN)

##### DNS

DNS|Domain Name System
DNS superceded the hosts file for the most part.
Today, the hosts file is used in some network bootstrapping, but mainly as a resource for internet resource blocking/redirection
To use the hosts file to block something, set its IP address to 0.0.0.0
hosts-file ::= {<hosts-line><linebreak>}
hosts-line ::= <ip-address> <hostname>{ <hostname>}

###### dig

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

##### WebSocket

WebSocket is an application-layer communications protocol with client and server APIs.
WebSocket, being an application-layer protocol, is distinct from HTTP, but uses the same TCP ports, mainly for firewall-related reasons
WebSocket, in contrast to HTTP allows full-duplex communication and streams of data
WebSocket use the scheme <code>ws:</code> (if unencrypted) or <code>wss:</code> (if encrypted)
To change from HTTP to WebSocket, the WebSocket handshake uses the HTTP Upgrade header

###### client

on the client side, sockets are created via the <code>WebSocket</code> constructor
the <code>WebSocket</code> constructor recieves the necessary argument of the url, and an optional argument of which sub-protocols to use
to send data on a <code>WebSocket</code>, use the method <code>send()</code>
To {{c3::react to incoming data}} {{c2::event handlers are registered}} on the WebSocket object
the four common events a <code>WebSocket</code> might recieve client-side are open, message, close, error

###### server 

the most common node web sockets library is <code>ws</code>

### layer 4

The ping utility uses the ICMP protocol's mandatory ECHO_REQUEST datagram to elicit an ICMP ECHO_RESPONSE from an IP.

#### IP

the {{c1::host URL element}} for the {{c2::loopback address}} is usually {{c3::localhost}}

# webadmin

Images used {{c3::on the web}} are typically {{c2::specifically compressed}} beforehand, e.g. {{c1::by using programs such as imageoptim}}

# applications

{{c1::Photoscape X}} is notable for being a {{c2::GUI}} program that has {{c3::batch editing of photos}}

## media viewers

### video 

Common shortcuts

<table>
  <thead>
    <tr>
      <th>Shortcut</th>
      <th>Action</th>
    </tr>
  </thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:1;::,))</td><td>((c:2;::one frame back))</td></tr>
    <tr><td>((c:3;::.))</td><td>((c:4;::one frame forwards))</td></tr>
    <tr><td>((c:5;:: <kbd>f</kbd> ))</td><td>((c:6;::go fullscreen))</td></tr>
    <tr><td>((c:7;::esc))</td><td>((c:8;::Exit fullscreen))</td></tr>
    <tr><td>((c:9;::space))</td><td>((c:10;::pause))</td></tr>
  </tbody>
</table>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}</span>

# principles

GIGO   Garbage In, Garbage Out
Garbage in, garbage out claims that if the input data is somehow bad {{c1::the output data will be too}}
Syntactic sugar is syntax that makes a programming language easier to use, but {{c1::doesn't expand it's functionality}}
"Anything that can go wrong will go wrong"   Murphy's law
{{c1::an anti-pattern}} is a pattern (intentional or not) that is ineffective/counter-productive 
YAGNI  You/ya ain't gonna need it
In computer programming, {{c1::code smell}} is a characteristic in code that indicates a deeper problem.
While code smell is often defined to mean :an indication of a problem, it often just means an actual anti-pattern/problem
DRY   Don't repeat yourself
KISS   Keep it simple stupid

## mech pol

the mechanism   what can be done
the policy   what should be done
separation of mechanism and policy.

# identifiers

## language

The locale of a user is a set of values for a set of parameters related to language and region.
The locale is generally specified as an identifier.
On POSIX platforms, locales are specified as environment variables with a certain syntax.
posix-locale-identifier ::= language[_location][.charset][@modifier]
the environment variables for locales are LANG as well as various LC_*.
All LC_* locale variables are overwritten with LC_ALL.

the locale command shows the currently specfied locales.
/etc/locale.gen and the command locale-gen associated with it is used for generating locales

### BCP47

<br>---<br>
  §§ A ((c:17;::IETF language tag)) indicates exactly ((c:18;::in which language a thing is)). §<br>
§§ Currently, the standard for ((c:19;::IETF language tags)) on the internet is ((c:20;::BCP47)). §<br>
§§ BCP 47: ((c:21;::&lt;primary-language&gt;))((c:22;::[-&lt;extended-language&gt;]))((c:23;::[-&lt;script&gt;]))((c:24;::[-&lt;region&gt;]))((c:25;::[-&lt;variant&gt;]))((c:26;::[-&lt;extension&gt;]))((c:27;::[-&lt;privateuse&gt;])) §<br>
§§ BCP 47 language tags should be kept ((c:28;::as short as possible)). §<br>
===<br>

<br>---<br>
  §§ The ((c:29;::primary language)) subtag of ((c:30;::BCP 47)) is specified as ((c:31;::a language code)). §<br>
§§ A ((c:32;::language code)) consists of ((c:33;::2 or 3 letters)). §<br>
§§ ((c:34;::Language codes)) are standartized in ((c:35;::ISO 639.)) §<br>
§§ ((c:36;::3-letter language codes)) are standartized ((c:37;::in ISO 639-2 and -3)). §<br>
§§ ((c:38;::2-letter language codes)) are standartized ((c:39;::in ISO 639-1)). §<br>
§§ ((c:41;::extlang (extended language))) subtags are for ((c:42;::sublanguages of a given language (e.g. hakka chinese, the variants of arabic))) §<br>
§§ ((c:43;::script)) subtags&nbsp;are for ((c:40;::writing systems)), and always ((c:44;::4 characters long)) §<br>
§§ ((c:45;::region)) subtags are for ((c:46;::locations (countries, other geo regions))) §<br>
§§ ((c:47;::variant)) subtags&nbsp;are for ((c:48;::dialects or other variations (however, use other tags if possible))) §<br>
===<br>

<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th>BCP 47 language tag</th>
    <th>meaning</th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:1;::en))</td> <td>((c:2;::english (no further info)))</td></tr>
<tr><td>((c:3;::zh-hak))</td> <td>((c:4;::hakka chinese))</td></tr>
<tr><td>((c:5;::zh-Hans))</td> <td>((c:6;::Chinese written in hanzi (simplified)))</td></tr>
<tr><td>((c:7;::en-GB))</td> <td>((c:8;::english as spoken in great britain))</td></tr>
<tr><td>((c:9;::az-Latn))</td> <td>((c:10;::azerbaijani, written in latin script))</td></tr>
<tr><td>((c:11;::ast))</td> <td>((c:12;::asturian (no further info)))</td></tr>
  </tbody>
</table>

<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th>tag</th>
    <th>problem</th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:15;::it-IT))</td> <td>((c:16;::unneccesary specification of IT (italian as spoken where else?)))</td></tr>
<tr><td>((c:13;::es-Latn))</td> <td>((c:14;::Unneccesary Latn (As opposed to spanish written in kanji? :P)))</td></tr>
  </tbody>
</table>


<br>---<br>
  §§ In HTML, the ((c:50;::language of the document)) should be indicated with ((c:51;::a lang attribute)) ((c:52;::on &lt;html&gt;))o §<br>
§§ In HTML, ((c:49;::anything that is not in the language indicated on &lt;html&gt;)) should be ((c:53;::indicated by an element with a lang attribute.)) §<br>
§§ In HTML, the ((c:54;::lang attribute)) takes ((c:55;::BCP 47 language tags)). §<br>
===<br>

<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}{{c28::}}{{c29::}}{{c30::}}{{c31::}}{{c32::}}{{c33::}}{{c34::}}{{c35::}}{{c36::}}{{c37::}}{{c38::}}{{c39::}}{{c40::}}{{c41::}}{{c42::}}{{c43::}}{{c44::}}{{c45::}}{{c46::}}{{c47::}}{{c48::}}{{c49::}}{{c50::}}{{c51::}}{{c52::}}{{c53::}}{{c54::}}{{c55::}}</span>



## licenses

Copyleft is type of restriction that does not allow creators of thing B including thing A to restrict the access to thing B more than thing A.
GPL is a type of copyleft license.
Share-alike is a type of copyleft license.

# automation

The Amazon Mechanical Turk is a service that allows crowdsourcing menial tasks.
The Amazon Mechanical Turk pays way below the minimum wage.
The Amazon Mechanical Turk is sometimes used for study subjects.

# todo

add quick note about Web Audio APi

# culture

## forum

OP|Original Poster