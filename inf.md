# SGML/XML/HTML

## SGML/XML/HTML itself

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

### declaration

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

### doctype

A document type declaration, or doctype, is an instruction that associates a particular XML or SGML document (for example, a webpage) with a document type definition (DTD).
A document type declaration must be the first thing in the page if HTML.
A document type declaration must be the first thing after the XML declaration if XML
The syntax of a doctype declaration is &lt;!DOCTYPE somestuff&gt;
In HTML 5, the doctype no longer actually references a DTD, but merely prevents the browser from switching into quirks mode.

### PI

PI|Processing instruction


### HTML

#### General structure

An HTML document is started by the &lt;html&gt; tag and ended by the &lt;/html&gt; tag.
a &lt;html&gt; element consists of a &lt;head&gt; section and a &lt;body&gt;

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
<td>IDL</td>
</tr>
</tbody>
</table>

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
rel=nofollow indicates that the current document's original author or publisher does not endorse the referenced document.
rel=noreferrer: No HTTP Referer header will be included. Additionally, has the same effect as noopener.	 

###### <link>

rel="icon"|specifies an icon representing the current document
rel="stylesheet"|indicates a stylesheet for the document

If rel="icon", the sizes attribute of link specifies which sizes are applicable.
link-sizes-values ::= any|(<size-spec>{ <size-spec>})
size-spec ::= <width>(x|X)<height>

the type attribute of <link> specifies the mime type of the resource; however this is generally omitted except for rel="icon"

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

###### textarea

textarea represents a multiline text input field
textarea is not an empty element, and in fact the content can be used to provide a default value.

###### label

A <label> provides a caption/label for a thing, most commonly an <input>
There are two ways of associating an <input> with a label, either nest the input within the label, or set the for attribute of the label to the id of the input.

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

.form-check ## set of radio buttons
.form-check-label   define a label for a checkbox/radio button
.form-check-input   define a checkbox/radio button

######## text

&lt;input type="text"&gt; is single-line only
There are a set of input types that act similarly text, but force a certain type of validation and change the soft keyboard/add input helpers, similar to inputmode:
time-related: date, datetime-local, month, time, week
number: number
other: email, password, tel, search, url
On any text-like input which is not time-related and not 'number' as well as on textarea, you may specify the minlength and maxlength attributes to contstrain the amount of UTF-16 code units.
On any non-time-related, non-number text-like input, you may specify the attribute pattern, providing a regex against which to match the input.
most text-only input fields may have the readonly attribute specfied, which shows the inital value but doesn't allow the user to modify it
the time-related and number text-like inputs plus range accept a step argument.

######## file

inputs of type file accept an attribute accept (lol) which takes a CSL of unique file type specifiers
an unique file type specfier is either a filename extension starting with a period, or a valid MIME type.
valid for the file input type only, the capture attribute defines which media—microphone, video, or camera—should be used to capture a new file for upload with file upload control in supporting scenarios.

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

<br>---<br>
  §§ In markdown ((c:1;::Lists items)) are each ((c:3;::started by)) ((c:2;::one or more symbols)), while lists themselves are delimited by nothing more than any block-level item.. §<br>
§§ ((c:4;::ordered list items)) are started by ((c:5;::&lt;n&gt;. (e.g. 1. or 7.))). §<br>
§§ it does not matter ((c:6;::with which digit you number list items with (e.g. even if you do <code>21. foo\n2. bar)</code>))&nbsp;they will ((c:7;::always start one and go from there (or whatever you then change it to via css))). §<br>
§§ ((c:8;::unordered list items)) are started by ((c:9;::-)), ((c:9;::*)) or ((c:9;::+)), which can be ((c:10;::mixed and matched)). §<br>
===<br>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}</span>

##### containers

div and span are 'pure' container without any semantics.
the difference between div and span is that div is by default block-level (display: block flow) and that span is by default inline (display: inline flow)

###### dialog

The dialog element rerpesents a dialog box container semantically.
The dialog element has a boolean attribute open representing whether the dialog should be shown or not.
<form> elements can close a dialog if they have the attribute method="dialog". When such a form is submitted, the dialog closes with its returnValue property set to the value of the button that was used to submit the form.

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

#### JS interface

any HTML element has a JS interface that is called HTMLSomeelementnameElement.

An IDL (Interface Description Language) is a generic language used to specified objects' interfaces apart from any specific programming language.

In HTML, most attributes have two faces: the content attribute and the IDL attribute.

The content attribute is the attribute as you set it from the content (the HTML code) and you can set it or get it via element.setAttribute() or element.getAttribute(). The content attribute is always a string even when the expected value should be of a different type.

the IDL attribute may be accessed from js like element.foo.

Any content attribute is also acessiable as an IDL attribute.

#### Common attributes

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

### JSX

{{c3::JSX}} is either said to be short for {{c2::JavaScript Syntax Extension}} or {{c1::JavaScript XML}}

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

DOM|Document Object Model
The DOM is a tree data structure that acts as an interface for a XML (or XML-derived) or HTML document.
DOM vertices are `Node`s (often subclasses of `Node`).
`Node` implements the EventTarget interface, so all things inheriting from Node also do.

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

##### NodeLists

A NodeList is similar to an Array, but doesn't have all the methods.
A NodeList is a linear collection of nodes.
NodeList has a foreach method.
NodeLists can be live or static.
A live NodeList (or similar) reflects changes in the DOM
A static NodeList (or similar) does not reflect changes in the DOM
`HTMLCollection`s are an interface similar to NodeLists, but may only contain elements, is live, and has a far less rich interface.

##### types of

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

##### Elements

element.innerHTML|content between the tags
The Element.classList is a read-only property that returns a live DOMTokenList collection of the class attributes of the element

###### HTMLCanvasElement

The HTMLCanvasElement.toDataURL(type) method returns a data URI containing a representation of the image in the format specified by the MIME type in the type parameter.

#### DOM traversal

document.querySelector(selector)|get first element that matches selector
document.querySelectorAll(selector)|get NodeList of elements that matches selector
qs and qsa can be called on document for a global search, or on an element for a search only on that elements children.
qsa returns a static NodeList
document.getElementBy<whatever>() returns HTMLCollections.
document.getElementBy<whatever> has four variants ById, ByClassName, ByTagName

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

#### notifications

Notification.requestPermission() is a promise, which if fulfilled means we have recieved permission to send notifications.
Browsers increasingly don't even allow us to ask for notification permissione exept in response to user action.
After gaining permission, we can create notifications with the Notification() constructor.
the {{c3::Notification() constructor}} takes two arguments, the {{c1::title of the notification}} and an {{c2::object of options}}
the options object for the notification constructor as a bunch of properties that precisely configure the notification.
.close()|closes the notification manually
Notification objects can have the events click, close, error and show (when the notification is shown) triggered on them.

#### intervals

{{c1::window}}.​setTimeout(function, delay, args);

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



### Web Speech API

Web Speech API: text to speech/speech to text

### Web Audio API

### web workers

### data fetching after the site has loaded

#### XHR

XHR|XMLHttpRequest
Ajax|Asynchronous JavaScript And XML

#### fetch

fetch is the new, modern method to fetch data via the interfet after a site has loaded.
fetch(<resource-to-get>, [<options-object>])
fetch() returns a Promise which itself resoves to a `Response`
Response
.json()|return promise with contents of response as parsed json

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

<img src="sm_tmpyk7c4jes.png">

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
::backdrop is the pseudo-element that is the size of the viewport and is rendered beneath {{c1::any element that is in fullscreen}}


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

pointer-events: {{c1::none}} makes a thing completely ininteractable with a mouse.

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

It may seem that certain html form elements can't have their font styled {{c1::because by default, these elements don't inherit font properties}}

###### Scrolling

overscrolling is what happens when you scroll further on something than that thing allows.
on mobile browsers and some desktop browsers, there is a form of overscrolling where the site will rubberband
when you overscroll a container, and this then starts scrolling the next-higher container, this is known as scroll chaining.
overscroll-behavior is actually a shorthand for overscroll-behavior-x and overscroll-behavior-y
overscroll-behavior: none prevents all overscrolling.
overscroll-behavior: contain will prevent scroll chaining only

###### Background

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
{{c4::Background-blend-mode}} regulates blending between ({{c3::a}}) {{c1::background-image}}({{c3::s}}) as well as the {{c2::background-color}}.
{{c2::mix-blend-mode}} regulates blending between {{c1::the}} {{c1::element's}} {{c3::content}}, {{c1::the}} {{c1::element's}} {{c4::parents content}}, and {{c1::the}} {{c1::element's}} {{c5::background}}.
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

generally from the top left corner
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

<img src="sm_position_value.png">

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

if you mark something with !important in a keyframe,&nbsp;{{c1::That value will be ignored}} (since !important can't be used in keyframes)
if you don't provide a from/0% andor a to/100% it will {{c1::Animate to/from the elements existing styles}}
If you specify multiple @keyframes with the same name, {{c1::The last one encountered will be used}}

##### @page

@page syntax: @page <page-selector-list>\{<page-body>\}
page-selector-list ::= <page-pseudo-class>{, <page-pseudo-class>} #maybe it's not a comma? I couldn't find any documentation this
page-pseudo-class ::= :first|:blank|:left|:right
page-body :: <page-declaration>;|<margin-at-rule>
currently supported properties for the page declaration are margins, orphans, widows and break
margin-at-rule = @<margin-at-rule-name><declaration-block>
<img src="page_margin_at_rules.png">

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

### flow

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

### meida queries

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

window.matchMedia() takes a media query and returns a MediaQueryList object, whose matches property indicates exactly that.
To react to changes in media features/types, you can register the change event on the MediaQueryList boject.

### related technologies

#### system UI themes

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

#### CSS processing

a CSS preprocessor is a transpiler from a language that is not css (though typically a superset) to css.
{{c3::Sass}} is a {{c4::CSS preprocessor}} that works with the two syntaxes {{c1::Sass (the syntax)}} and {{c2::SCSS}}
Sass syntax that is indented rather than curly-braced   Sass
Sass syntax that is a CSS superset   SCSS (Sassy CSS)
PostCSS is a CSS processor (CSS -> CSS), that does nothing by default, but can be hooked into by JS plugins.
Autoprefixer is a tool to add vendor prefixes to CSS properties automatically, implemented as a PostCSS plugin.

#### CSS naming schemes

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

## semantics

### semantic web

The semantic web is sometimes known as web 3.0
The goal of the samntic web is to make internet data machine readable
A semantic query is a data query on the semantic web.
the social graph is a graph that represents social relationship between entities.
the open graph allows web pages to become objects in a social graph

A ontology languages is a language that describes an ontology. 

### folksonomy

booru: image site with foksonomical tags
boorus: generally look similar to Danbooru, the original
sexual content: rating:s(afe), rating:q(uestionable), rating:e(xplicit)
Other boorus for anime pictures: danbooru(.donmai.us), zerochan, gelbooru, anime-pictures, safebooru (either safebooru.org or safebooru.donmai.us), rule34.paheal.net
<img class="c2-f c1-b" src="sm_2021-10-19--03-12-32-screenshot.jpg"><img class="c2-f c1-b" src="sm_2021-10-19--03-11-46-screenshot.jpg"><img class="c2-f c1-b" src="sm_2021-10-19--03-10-58-screenshot.jpg">

# HCI

HCI = Human Computer Interaction/Interfaces
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

### input

#### modes

A mode is a state which is explictly entered and exited where the same input will produce different results than if it wasn't in that state.
A quasimode is like a mode, but the state is only maintained as long as an action is performed.
Keyboard keys that maintain a quasimode are shift, alt, control, option....

#### text

##### keyboards

###### local variants

Keyboards are often identified based on {{c1::their first few keys on the top letter row}}
QUERTY|en
QWERTZ|de
AZERTY|fr

Between english and german keyboards, the only difference in actual letters in that z and y are flipped.

###### types of keys

####### modifier keys

modifier keys are keys that maintain a quasimode.
modifier keys that are found on any hardware keyboard as of 2020 are shift, ctrl, alt/option/altgr, win/cmd/linux equivalent.
On small layout keyboards, the additional modifier key function is often present.
Windows and linux treat ctrl as their primary modifier key, while mac treats cmd as the primary modifier keys.
Originally, super, meta and hyper keys were all dedicated modifier keys present on some keyboards.
today, different linux distros treat meta or super as their equivalent to cmd/windows.
today, since hyper keys are not really present anywhere, hyper key refers to a fictional modifier key created by simulating an insane number of modifier keys at the same time by pressing a different non-modifier key (often e.g. capslock)f

######## alt/option

alt gr = alt graph
alt gr was originally for producing box drawing characters.
Despite having similar names, alt and alt gr generally share no functionality.
alt gr produces a quasimode for alternative characters similar to shift. 
US keyboards typically have two normal alt keys.
European/international keyboards typcially have one alt and one alt gr key.
The mac option key has functionality of both the alt and alt gr keys: it can be used as a key in key command like alt, but can also produce additional characters like alt gr.
Due to historical reasons, emacs used to use the meta key as a modifier, but later switched to alt. However, it kept the label 'M' for this modifier key.

####### lock keys

Lock keys are keys that enter/exit a mode.

####### delete/backspace

Delete key|Delete characters forwards (to the right)
Backspace key|Delete characters backwards (to the left)

###### key combinations & actions

A keyboard shortcut some key input that performs an action different from its literal value.
A key combination is the pressing of a key and one or more modifier keys to perform an action
A key chord are two or more key combinations or key presses sequentially to perform an action.
e.g. cmd k then m to select the document language in VSCode

####### keyboard shortcuts

######## search 

<br/><table>
  <thead>
    <tr>
      <th>Action</th>
      <th>Shortcut</th>
    </tr>
  </thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:1;::Find in project/ other larger scope))</td><td>((c:2;::<kbd class="modifier cmd"></kbd> <kbd class="modifier shift"></kbd> <kbd>F</kbd> ))</td></tr>
<tr><td>((c:3;::Find next))</td><td>((c:4;::<kbd class="modifier cmd"></kbd> <kbd>g</kbd> ))</td></tr>
<tr><td>((c:5;::Find previous))</td><td>((c:6;::<kbd class="modifier cmd"></kbd> <kbd class="modifier shift"></kbd> <kbd>g</kbd> ))</td></tr>
<tr><td>((c:7;::Open search in window/smaller scope))</td><td>((c:8;::<kbd class="modifier cmd"></kbd> <kbd>F</kbd> ))</td></tr>
<tr><td>((c:9;::Open search in project/other large scope/advanced search))</td><td>((c:10;::<kbd class="modifier cmd"></kbd> <kbd class="modifier shift"></kbd> <kbd>F</kbd> ))</td></tr>
    </tbody>
</table>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}</span>

######## text editing 

<table>
  <thead>
    <tr>
      <th>Shortcut</th>
      <th>Action</th>
    </tr>
  </thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:1;::Paste as plain text))</td><td>((c:2;::<kbd class="modifier cmd"></kbd> <kbd class="modifier shift"></kbd> <kbd>v</kbd>))</td></tr>
<tr><td>((c:3;::Select all))</td><td>((c:4;::<kbd class="modifier cmd"></kbd> <kbd>a</kbd> ))</td></tr>
<tr><td>((c:5;::copy))</td><td>((c:6;::<kbd class="modifier cmd"></kbd> <kbd>c</kbd> ))</td></tr>
<tr><td>((c:7;::cut))</td><td>((c:8;::<kbd class="modifier cmd"></kbd> <kbd>x</kbd> ))</td></tr>
<tr><td>((c:9;::paste))</td><td>((c:10;::<kbd class="modifier cmd"></kbd> <kbd>v</kbd> ))</td></tr>
  </tbody>
</table>

######## code editing

######### vscode

rename a symbol|<kbd>f2</kbd>
see code actions (available refactorings and quick fixes)|<kbd class='modifier cmd'></kbd><kbd>.</kbd>
change (programming) language of current document|<kbd class='modifier cmd'></kbd><kbd>k</kbd>&nbsp;&nbsp;<kbd>m</kbd>
show integrated terminal|<kbd class='modifier ctrl'></kbd> (even on mac) <kbd>`</kbd>
fast scrolling|<kbd class='modifier alt'></kbd> <kbd>scroll</kbd>
copy line up/down|<kbd class='modifier shift'></kbd> <kbd class='modifier alt'></kbd> <kbd>up/down</kbd>
move line up/down|<kbd class='modifier alt'></kbd> <kbd>up/down</kbd>

##### autocomplete

<br>---<br>
  §§ <dfn>((c:1;::Autocomplete/word completion))</dfn> is a feature where ((c:2;::an application predicts the rest of something the user is typing)).  §<br> 
  §§ <dfn>((c:3;::Autocomplete/word completion))</dfn> on ((c:4;::smartphone keyboards)) is called <dfn>((c:5;::predictive text))</dfn>, ((s:gb;::this used to refer to ((c:6;::the prediction of typing on numeric keypads (e.g. T9))))) §<br>
  §§ <dfn>((c:7;::Autocomplete/word completion))</dfn> ((c:8;::in a command-line interface)) is called <dfn>((c:9;::command-line))</dfn> or <dfn>((c:9;::tab)) ((c:9;::completion))</dfn>, ((s:gb;::which generally uses ((c:10;::the tab key (whence the name))).)) §<br>
  §§ <dfn>((c:11;::Autocomplete/word completion))</dfn> in ((c:12;::code editors)) is also known as <dfn>((c:13;::code completion))</dfn>. Examples include ((s:gb;::((c:14;::VS &amp; VS Code))'s ((c:15;::IntelliSense)), and ((c:16;::AI (modfied GPT-3)))-powered ((c:17;::GitHub Copilot)).)) §<br>
===<br>

### Natural Language Processing

NLP = Natural Language Processing
Text to speech AKA Speech synthesis
Speech to text AKA Speech recognition

## shells

A shell is a wrapper around the OS that acts as an interface between it and humans.
Types of shells: graphical, command-based
Shell is often but kinda incorrectly used as a synonym to command-based shell
A TUI is a user interface that uses Text to render, but accept input like GUIs, and like GUIs they consume a fixed part of the screen.
<img src="sm_Midnight_Commander_(2005)_en.png"><img rc="sm_1024px-Vim-(logiciel)-console.jpg">
NUIs are (mostly theoretical/hypothesized) intefaces that are claimed to be natural to use in some way.

UI|User interface
NUI|natural user inteface
GUI|graphical user interface
TUI|Text-based user interface
CLI|Command-line interface

### CLI

A command-line shell/interface is a type of shell (in the wide sense, it is decidedly not a type of shell in the sense of the interpreter such as bash, csh) where actions are accomplished by entering commands.
The shell living within the terminal is interacted with via a CLI, but so does e.g. vim, or various cheat consoles in games.

### GUI

A graphical shell/grapical user interface is a type of shell (in the wide sense) that allows accomplishing commands via interaction through visual elements.

WIMP = Windows, icons, menus, pointer

#### theming

lxappearace is a gtk theme switcher

#### widgeting toolkits

#### elements

##### menu

A menu contains a lists of options or commands, one or more of which can be chosen or executed.

###### text-based 

A text-based menu is a type of menu that contains only text entries, most commonly as a list of one or more collumns.

####### searchable 

Many text-based menus are searchable by a type of fuzzy search.
dmenu and its successor rofi are shell filters that act as a text-based fuzzily searchable menu.
rofi can similate dmenu with the -dmenu argument
dmenu/rofi create a menu entry for each item in stdin, where newline is treated as the delimiter by default
dmenu/rofi output the selected item to stdout

######## command palette / quick open menu

((h:all;::<img src="Screenshot%202021-12-09%20at%2003.12.09.png">))
<br>---<br>
A command palette is a text-based fuzzily searchable menu containing most things one can do in a program.
A quick open menu is a text-based fuzzily searchable menu containing navigation items.
Often (VSCode, Devltools) a command palette is merely a mode of a quick open menu, enterable or exitable by adding/removing >
§§ A ((c:19;::Command Palette)) often also shows ((c:20;::the direct keyboard shortcuts)). §<br>
§§ A ((c:21;::Command Palette)) generally appears as ((c:22;::a modal)) floating in ((c:23;::the upper center)) of the window. §<br>
§§ Following ((c:24;::Sublime text and VSCode)), ((c:25;::many applications have adapted)) ((c:26;::the Command Palette)). §<br>
===<br>

<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th>Shortcut to open command palette</th>
    <th>Platform</th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:11;::<kbd class="modifier cmd"></kbd> <kbd class="modifier shift"></kbd> P))</td> <td>((c:12;::VSCode, Chrome Devtools))</td></tr>
<tr><td>((c:13;::<kbd class="modifier cmd"></kbd> (<kbd class="modifier alt"></kbd>) K))</td> <td>((c:14;::GitHub))</td></tr>
  </tbody>
</table>

<br>---<br>
§§ ((c:35;::Quick open menus)) are often entered via ((c:36;::<kbd class="key modifier cmd"></kbd> <kbd>P</kbd>.)) §<br>
===<br>

<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th colspan="2">Possible prefixes in Quick Open menus</th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:1;::@somestring))</td> <td>((c:2;::go to symbol somestring))</td></tr>
<tr><td>((c:3;:::somenumber))</td> <td>((c:4;::go to line somenumber))</td></tr>
<tr><td>((c:5;::?))</td> <td>((c:6;::show suggestions what you can do with quick open))</td></tr>
<tr><td>((c:7;::&gt;))</td> <td>((c:8;::enter command palette mode))</td></tr>
  </tbody>
</table>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}{{c28::}}{{c29::}}{{c30::}}{{c31::}}{{c32::}}{{c33::}}{{c34::}}{{c35::}}{{c36::}}</span>

####### context menu

((h:all;::<img src="Menu_key_screen.jpg">))((h:all;::<img src="Context_menu_windows.png">))((h:all;::<img src="Context_Menu_on_OS_X_10.9.png">))
A context menu is a menu of actions for wherever the focus is, most commonly summoned by right-clicking.

###### ambiguous

####### task switcher

A task/app(lication) switcher is a menu that allos switching between open programs or windows.
A task switcher that allows switching between windows is more properly a window switcher.
windows|alt+tab|windows
mac|cmd+tab|applications

####### hamburger 

<img src="hamburger-menu-definition.png">
A hamburger menu is a menu triggered by a hamburger button.
A hamburger menu generally comes out from the side, contains a a list of navigation options, and covers between 70% - 100% of the screen
A hamburger button is a three-line icon that contains 
A hamburger menu most often refers to the menu you get when you click a hamburger button but also may refer to the button itself, or the whole package

##### bar

A bar is a long-ish rectangle found at the edge of an UI element.

###### title bar

A title bar is a bar that is typically located at the top of a window and contains the name of the application andor document/window, as well as the title bar buttons.
the title bar buttons are most typically minimize, maximise and close.
In most GUIs, you can move the window by grabbing the title bar and dragging.
In most GUIs, you can expand the window to fill the screen by double-clicking the title bar.

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

#### actions

##### window snapping

Window snapping is making windows take up an exact area of the screen (most commonly halves, thirds, corners)
Window snapping is most commonly performed by dragging them to edges/corners, via keyboard shortcuts or other buttons/automatic dialogs.
Windows has had window snapping as of windows 7.
Mac requires custom programs sto achieve window snapping, e.g. Spectacle (now deprecated) or Rectangle

## user experience

### waiting

Waiting is less frustrating when there is an indication of progress and transparancy of how the progress relates to the whole (e.g. Kayak.com showing cheaper prices trundling in).
Jason Farman (Delayed Response) argues that what really matters about if we leave a waiting situation satisified is if we waited less than we expected, rather than the whole wait time.
The fact that our expectations are the thing that determines our assesment of waiting and progress bars has given rise to the progress bar that starts out slow and then speeds up towards the end (no matter if this is a correct interpretation)

## text markup across languages

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


## computer graphcis

A {{c1::FOUC (Flash of unstyled content)}} is when a {{c3::page (or some content)}} is briefly visible with {{c2::no styling/browser default styling}}

### color

<br>---<br>
  §§ A ((c:17;::color model)) is a model of how ((c:18;::a set of channels)) ((c:19;::make up a color)). §<br>
§§ A ((c:20;::color space)) is a ((c:21;::color model)) ((c:22;::associated with)) ((c:23;::how the results are to be interpreted (viewing conditions etc.))) §<br>
§§ A ((c:24;::gamut)) is ((c:25;::a complete/'adjacent')) ((c:26;::subset of a colors)). §<br>
§§ Often a ((c:27;::gamut)) refers specifically to ((c:28;::the subsset of colors)) that ((c:29;::can be displayed or represented by something)). §<br>
===<br>

<br>---<br>
  §§ ((c:30;::Each pixel)) in a ((c:31;::color image)) is made up of ((c:32;::two or more channels)). §<br>
§§ ((c:33;::Each channel)) in an image/pixel is ((c:34;::associated with a color)). §<br>
§§ ((c:35;::channels)) of color may also be called ((c:36;::components)). §<br>
§§ ((c:37;::A channel)) is ((c:38;::the value of a color)) for ((c:39;::a specific pixel, and thus the whole image)). §<br>
§§ ((c:41;::Combining)) ((c:40;::the color channels)) of a pixel (and thus the image) ends you up with ((c:42;::the color of the pixel/image)). §<br>
===<br>

<br>---<br>
  §§ In the ((c:43;::RGB)) ((c:44;::color model)) a thingy has the ((c:45;::three)) ((c:46;::channels)) ((c:47;::red, green and blue)). §<br>
§§ In the ((c:48;::CMY)) ((c:49;::color model)) a thingy has the ((c:50;::three)) ((c:51;::channels)) ((c:52;::cyan, magenta and yellow)). §<br>
§§ The ((c:53;::CMYK)) ((c:54;::color model)) ((c:56;::adds a channe))l of ((c:55;::key)) (= ((c:55;::black))). §<br>
§§ The ((c:57;::key channel)) is ((c:58;::generally added to CMYK)) because ((c:59;::black ink is cheaper,)) and ((c:60;::producing black by mixing cyan, magenta and yellow is in practice quite hard)). §<br>
§§ The ((c:61;::CMY)) and ((c:62;::RGB)) ((c:63;::color models)) are ((c:64;::the most common color models in use today)), in part because ((c:65;::they correspond roughly to human tricromatic color vision)). §<br>
§§ An ((c:66;::additive color model)) is one where ((c:67;::colors)) ((c:68;::added together)) produce ((c:69;::progressively lighter colors)). §<br>
§§ ((c:70;::Light emission)) follows ((c:71;::an addtive)) color model. §<br>
§§ A ((c:72;::subtractive color model)) is one where ((c:73;::colors)) ((c:74;::added together)) produce ((c:75;::progressively darker colors)). §<br>
§§ ((c:76;::Light absorption)) follows ((c:77;::a subtractive)) color model. §<br>
§§ ((c:78;::RGB)), being ((c:79;::an additive color model)), is mainly used for ((c:80;::displays and other places where light is emitted)). §<br>
§§ ((c:81;::CMYK)) being ((c:82;::a subtractive color model)) is mainly used for ((c:83;::printing and other places where light is absorbed.)) §<br>
§§ ((c:84;::RYB)) is an alternative ((c:85;::subtractive)) ((c:86;::color model)) still used in the arts. It can however not ((c:87;::create black)). §<br>
===<br>

<br>---<br>
  §§ ((c:88;::Color depth)) indicates ((c:89;::the amount of bits used)) for ((c:90;::color)) ((c:91;::per pixel)) or ((c:92;::per channel)) (since ((c:93;::these rarely overlap)), there is no ((c:93;::confusion)).) §<br>
§§ ((c:94;::Color depth)) is more rarely also called ((c:95;::bit depth)). §<br>
§§ Today, the ((c:96;::most common)) ((c:97;::color depth)) is ((c:98;::8 bit per channel)). §<br>
===<br>

<br>---<br>
  §§ the ((c:99;::common color depth of 8 bit per channe))l means values from ((c:100;::0 - 255)) / ((c:101;::00 to ff)). §<br>
§§ Most colors are specified by ((c:102;::specifying the color model)) and then ((c:103;::the components)) (e.g. ((c:104;::RGB 0, 120, 58))). §<br>
§§ ((c:105;::RGB colors)) are also often displayed as ((c:106;::a hex triplet,)) which is generally ((c:107;::prefixed by a # character)). §<br>
§§ In certain places, e.g. HTML/CSS, hex colors ((c:226;::with reduplicated digits only (e.g. 663399))) can ((c:227;::be shortened to three-digit variants (e.g. 639))) §<br>
===<br>

<br>---<br> 
  §§ ((c:108;::A primary color)) is ((c:109;::a member of)) a ((c:110;::set of colors)) (all ((c:111;::defined to be primary))) that ((c:112;::can be combined in varying amounts)) to ((c:113;::create a gamut of colors)). §<br>
===<br>

<br>---<br>
  §§ ((c:114;::CMY)) and ((c:114;::RGB)) are ((c:115;::complementary)) in such a way that ((c:116;::C+R)), ((c:116;::M+G)), and ((c:116;::Y+B)) are ((c:117;::all 100% (255 with an 8 bit color depth))). To ((c:118;::get one channel)), ((c:119;::the other is subtracted from 100%)). §<br>
§§ To get ((c:120;::the K channel)) from ((c:120;::CMY)): K = ((c:121;::min(C, M, Y))) §<br>
§§ After ((c:122;::getting the K channel)), to ((c:123;::convert CMY to CMYK)): ((c:125;::Channel_new)) =&nbsp;&nbsp;<div style="width:fit-content; display:inline-block; text-align: center"><div style="border-bottom: 0.1em solid currentcolor">((c:124;::Channel - K))</div><div>((c:125;::1 - K))</div></div> §<br>
===<br>

<br>---<br>
§§ ((c:129;::Hue)) is what we might call ((c:130;::<i>color</i>))&nbsp;color. §<br>
§§ ((c:131;::Hue)) is what ((c:132;::most languages)) ((c:133;::consider primary)) about ((c:134;::color)), with ((c:135;::other attributes such as light/dark/muddy/vivid/pastel)) ((c:136;::attached later)). §<br>
§§ ((c:137;::Hue)) is often ((c:138;::generated from)) ((c:139;::RGB)), e.g. for ((c:140;::use in HSL &amp; HSV/HSB)). §<br>
§§ If ((c:141;::Hue)) is ((c:142;::generated)) from ((c:142;::RGB)) for ((c:142;::HSL/HSV)), it is specified in ((c:143;::a degree from 0 to 360 deg)) §<br>
===<br>

<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th colspan="2">If Hue is specified in a degree measurement</th></tr>
    <tr><th>degree</th>
    <th>color</th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:144;::0deg/360deg))</td> <td>((c:145;::red))</td></tr>
<tr><td>((c:146;::120deg))</td> <td>((c:147;::green))</td></tr>
<tr><td>((c:148;::240deg))</td> <td>((c:149;::blue))</td></tr>
  </tbody>
</table>

<br>---<br>
§§ Commonly, ((c:156;::saturation)) ≈ ((c:157;::chroma)) refers to ((c:158;::the distance)) of ((c:159;::a color)) ((c:158;::from)) t((c:160;::he white-gray-black spectrum)). §<br>
===<br>

<br>---<br>
§§ ((c:161;::Lighntess)) attempts to model ((c:162;::adding white/black paint)) to ((c:163;::make the color white/black)). §<br>
§§ ((c:164;::100%)) ((c:166;::lightness)) is ((c:165;::white)) for ((c:165;::any saturation/hue)). §<br>
§§ ((c:167;::50%)) ((c:171;::lightness)) ((c:168;::allows for fully saturated colors)). §<br>
§§ ((c:169;::0%)) ((c:172;::lightness)) is ((c:170;::black)) for ((c:170;::any saturation/hue)) §<br>
§§ ((c:173;::Value/brightness)) attempts to model ((c:174;::how shining more/less light on a thing)) will ((c:175;::change the color)). §<br>
§§ ((c:176;::100%)) ((c:181;::value/brightness)) ((c:177;::allows for fully saturated colors.)) §<br>
§§ ((c:178;::0%)) ((c:179;::lightness)) is ((c:180;::black)) for ((c:180;::any saturation/hue)). §<br>
===<br>

<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th></th>
    <th></th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:151;::tint))</td> <td>((c:152;::mixture of a color with white))</td></tr>
<tr><td>((c:153;::tone))</td> <td>((c:154;::mixture of a color with gray))</td></tr>
<tr><td>((c:155;::shade))</td> <td>((c:150;::mixture of a color with black))</td></tr>
  </tbody>
</table>

<br>---<br>
§§ ((c:182;::HSL)) = ((c:186;::hue, saturation, lightness)). §<br>
§§ ((c:183;::HSV)) = ((c:187;::hue, saturation, value)) ((c:190;::is the same as)) ((c:188;::HSB)) = ((c:189;::hue, saturation, brightness.)) §<br>
§§ ((c:184;::HSL)) and ((c:184;::HSV/HSB)) are alternate ((c:191;::color models)), which are both ((c:192;::variants of/generated from)) ((c:193;::the RGB color model)). §<br>
§§ ((c:185;::HSL)) and ((c:185;::HSV)) were created because ((c:194;::they are more natural to how we as humans understand color.)) §<br>
§§ ((s:ga;::While ((c:195;::RGB)) and ((c:195;::CMY)) are most naturally represented as ((c:196;::cubes)))), ((s:gb;::((c:197;::HSL)) and ((c:197;::HSV/HSB)) are commonly represented as ((c:198;::cylinders)))). §<br>
§§ Since ((c:199;::the top and bottom)) of ((c:200;::a ((s:202;::HSL)) cylinder)) ((c:201;::all approach the same color (white and black respectively))), ((s:gb;::((c:202;::HSL)) may also ((c:203;::be represented as a bicone)))). §<br>
§§ Since the ((c:204;::bottom)) of ((c:205;::a HSV/HSB cylinder)) ((c:206;::approaches the same color (black))), ((s:gb;::HSV/HSB may more naturally be represented as a cone.)) §<br>
§§ ((c:207;::HSL)) and ((c:208;::HSV/HSB)) both have ((s:211-212;::((c:209;::hue)) as ((c:210;::the degree)))), and ((s:209-210;::((c:211;::saturation)) as ((c:212;::the radius)).)) §<br>
§§ ((c:213;::HSL)) has ((c:214;::lightness)) as ((c:215;::the height.)) §<br>
§§ ((c:216;::HSV/HSB)) has v((c:217;::alue/brightness)) as ((c:218;::the height)).  §<br>
§§ both ((c:219;::HSL)) and ((c:219;::HSV/B)) have the problem that ((c:220;::changing)) the ((c:221;::saturation)) and ((c:223;::to a certain extent)) ((c:222;::the hue)) ((c:220;::will change)) ((c:224;::the percieved lightness/brightness)), even when ((c:225;::they are supposed to be independent)). §<br>
===<br>

<div class="flex-container">((h:all;::<img src="sm_hsl_cylinder.png">))((h:all;::<img src="sm_hsv_cylinder.png">))</div>
<div class="flex-container">((h:all;::<img src="sm_hsl_cone.png">))((h:all;::<img src="sm_hsv_cone.png">))
</div>
<br>---<br>
For any given color model, to ((c:228;::specify transparency)), you ((c:229;::add another channel)), which is called the ((c:230;::alpha)) channel.
For a color hex, you ((c:231;::specify the alpha channel)) by ((c:232;::adding another two-digit hex to the end)).
  §§ ((c:126;::&lt;color-model&gt;-D)) is ((c:127;::just that color model)) with ((c:128;::an additional depth channel.)) §<br>
===<br>

<table>
  <thead>
    <tr><th>RGB 3-tuple notation</th>
    <th></th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:1;::Rgb(0, 0, 0)))</td> <td>((c:2;::<img src="sm_Screenshot%202020-02-25%20at%2017.42.47.png">))</td></tr>
    <tr><td>((c:3;::Rgb(0, 0, 255)))</td> <td>((c:4;::<img src="sm_Screenshot%202020-02-25%20at%2017.43.44.png">))</td></tr>
    <tr><td>((c:5;::Rgb(0, 255, 0)))</td> <td>((c:6;::<img src="sm_Screenshot%202020-02-25%20at%2017.43.16.png">))</td></tr>
    <tr><td>((c:7;::Rgb(0, 255, 255)))</td> <td>((c:8;::<img src="sm_Screenshot%202020-02-25%20at%2017.44.39.png">))</td></tr>
    <tr><td>((c:9;::Rgb(255, 0, 0)))</td> <td>((c:10;::<img src="sm_Screenshot%202020-02-25%20at%2017.42.26.png">))</td></tr>
    <tr><td>((c:11;::Rgb(255, 0, 255)?))</td> <td>((c:12;::<img src="sm_Screenshot%202020-02-25%20at%2017.41.37.png">))</td></tr>
    <tr><td>((c:13;::Rgb(255, 255, 0)))</td> <td>((c:14;::<img src="sm_Screenshot%202020-02-25%20at%2017.45.11.png">))</td></tr>
    <tr><td>((c:15;::Rgb(255, 255, 255)?))</td> <td>((c:16;::<img src="sm_Screenshot%202020-02-25%20at%2017.41.09.png">))</td></tr>
<tr><td>((c:233;::#f2f12f))</td> <td>((c:234;::<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #f2f12f 0%, #f2f12f 100%);">))</td></tr>
<tr><td>((c:235;::#e6281f))</td> <td>((c:236;::<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #e6281f 0%, #e6281f 100%);">))</td></tr>
<tr><td>((c:237;::#e2e))</td> <td>((c:238;::<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #e2e 0%, #e2e 100%);">))</td></tr>
<tr><td>((c:239;::#daefe4))</td> <td>((c:240;::<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #daefe4 0%, #daefe4 100%);">))</td></tr>
<tr><td>((c:241;::#867d7e))</td> <td>((c:242;::<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #867d7e 0%, #867d7e 100%);">))</td></tr>
<tr><td>((c:243;::#17F099))</td> <td>((c:244;::<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #17F099 0%, #17F099 100%);">))</td></tr>
<tr><td>((c:245;::#132133))</td> <td>((c:246;::<img style="width: 5ch; min-height: 1em; background-image: linear-gradient(to right, #132133 0%, #132133 100%);">))</td></tr>
  </tbody>
</table>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}{{c28::}}{{c29::}}{{c30::}}{{c31::}}{{c32::}}{{c33::}}{{c34::}}{{c35::}}{{c36::}}{{c37::}}{{c38::}}{{c39::}}{{c40::}}{{c41::}}{{c42::}}{{c43::}}{{c44::}}{{c45::}}{{c46::}}{{c47::}}{{c48::}}{{c49::}}{{c50::}}{{c51::}}{{c52::}}{{c53::}}{{c54::}}{{c55::}}{{c56::}}{{c57::}}{{c58::}}{{c59::}}{{c60::}}{{c61::}}{{c62::}}{{c63::}}{{c64::}}{{c65::}}{{c66::}}{{c67::}}{{c68::}}{{c69::}}{{c70::}}{{c71::}}{{c72::}}{{c73::}}{{c74::}}{{c75::}}{{c76::}}{{c77::}}{{c78::}}{{c79::}}{{c80::}}{{c81::}}{{c82::}}{{c83::}}{{c84::}}{{c85::}}{{c86::}}{{c87::}}{{c88::}}{{c89::}}{{c90::}}{{c91::}}{{c92::}}{{c93::}}{{c94::}}{{c95::}}{{c96::}}{{c97::}}{{c98::}}{{c99::}}{{c100::}}{{c101::}}{{c102::}}{{c103::}}{{c104::}}{{c105::}}{{c106::}}{{c107::}}{{c108::}}{{c109::}}{{c110::}}{{c111::}}{{c112::}}{{c113::}}{{c114::}}{{c115::}}{{c116::}}{{c117::}}{{c118::}}{{c119::}}{{c120::}}{{c121::}}{{c122::}}{{c123::}}{{c124::}}{{c125::}}{{c126::}}{{c127::}}{{c128::}}{{c129::}}{{c130::}}{{c131::}}{{c132::}}{{c133::}}{{c134::}}{{c135::}}{{c136::}}{{c137::}}{{c138::}}{{c139::}}{{c140::}}{{c141::}}{{c142::}}{{c143::}}{{c144::}}{{c145::}}{{c146::}}{{c147::}}{{c148::}}{{c149::}}{{c150::}}{{c151::}}{{c152::}}{{c153::}}{{c154::}}{{c155::}}{{c156::}}{{c157::}}{{c158::}}{{c159::}}{{c160::}}{{c161::}}{{c162::}}{{c163::}}{{c164::}}{{c165::}}{{c166::}}{{c167::}}{{c168::}}{{c169::}}{{c170::}}{{c171::}}{{c172::}}{{c173::}}{{c174::}}{{c175::}}{{c176::}}{{c177::}}{{c178::}}{{c179::}}{{c180::}}{{c181::}}{{c182::}}{{c183::}}{{c184::}}{{c185::}}{{c186::}}{{c187::}}{{c188::}}{{c189::}}{{c190::}}{{c191::}}{{c192::}}{{c193::}}{{c194::}}{{c195::}}{{c196::}}{{c197::}}{{c198::}}{{c199::}}{{c200::}}{{c201::}}{{c202::}}{{c203::}}{{c204::}}{{c205::}}{{c206::}}{{c207::}}{{c208::}}{{c209::}}{{c210::}}{{c211::}}{{c212::}}{{c213::}}{{c214::}}{{c215::}}{{c216::}}{{c217::}}{{c218::}}{{c219::}}{{c220::}}{{c221::}}{{c222::}}{{c223::}}{{c224::}}{{c225::}}{{c226::}}{{c227::}}{{c228::}}{{c229::}}{{c230::}}{{c231::}}{{c232::}}{{c233::}}{{c234::}}{{c235::}}{{c236::}}{{c237::}}{{c238::}}{{c239::}}{{c240::}}{{c241::}}{{c242::}}{{c243::}}{{c244::}}{{c245::}}{{c246::}}</span>

### blending

Blend modes (or mixing modes[1]) in digital image editing and computer graphics are used to determine how two layers are blended with each other. 
Blend modes typically use values from 0 to 1 for the channels for the math.
When describing blend modes, t denotes the top layer and b the bottom layer
In general, when channel is specified, assume it is done to each channel.
normal|use alpha compositing
multiply|channel_t * channel_b|result will be darker (since two numbers less than 1 multiplied will always be smaller)
screen|1 - (1 - channel_t) (1 - channel_b)|result will be always be lighter

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
<img src="sm_hdd_w_labels.svg">
<img src="sm_1280px-Seagate_ST33232A_hard_disk_head_and_platters_detail.jpg"><img src="sm_220px-Laptop-hard-drive-exposed.jpg">
as of 2020, HDDs usually spin at 5400 or 7200 RPM.
as of 2020, HDDs are typically a few TB in size.

a HDD is made up of clusters which are made up of sectors.
A sector used to be 512 byte large normally; today, that is usually 4096 Bytes (4KiB)

((h:all;::<img src="sm_cyl_head_sect_dia.svg">))
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

<div class="onion-box"><span>((c:;::SSD chip))</span><div class="onion-box"><span>((c:;::block))</span><div class="onion-box"><span>((c:;::page))</span></div><div class="onion-box"><span>((c:;::page))</span></div><div class="onion-box"><span>((c:;::page))</span></div><div class="onion-box"><span>((c:;::...))</span></div></div><div class="onion-box"><span>((c:;::block))</span></div><div class="onion-box"><span>((c:;::...))</span></div></div>

## secondary memory organization

### devices

RAID = Redundant Array of Inexpensive/Independent Disks
SLED = Single Large Expensive disk
RAID <-> SLED
RAID uses multiple disks.
RAID disks are in some sort of configuration which aims to achieve one or more of the three aims reliability/redundancy, performance, capacity
RAID 0|Data is split among the drives (striped)|performance (r/w)
RAID 1|data is mirrored on all drives|reliability & some read performance

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
fsck checks/repairs a linux filesystem.

#### mounting

mouting is associating a device with a location in the directory tree.
/etc/fstab allows specifying default moun points for certain devices/partitions.
mount and unmount are the commands to mount/unmount things in linux using sudo.
mount may take both a device and a mountpoint.
mount may take just a device or mountpoint, in which case it will try to mount this in the way specified in /etc/fstab.
in contrast to mount, pmount allows one to mount a device without being root, but only if one conforms to a certain set of rules (its policy)

#### file info

stat|info about file
file|get file type and related info

### directory structure

{{c1::the directory structure}} is the way data is organized in a file system using directories.
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

mc ("midnight commander"), nnn are TUI file browsers.

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

realpath gets the absolute path for a file name
basename strips the path and suffix from a file name

###### find

find|find files
find-command ::= find {<global-option>} {<starting-point-path>} {<expression>}
If no starting point is specified for find, it takes the current working directory.
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
FHS (Filesystem Hierarchy Standard) is the Linux spec for {{c1::directory structure}}
source code should be in src for reference only

###### /sys

/sys provides a window to the kernel.
/sys/class|contains (a view of) different types of devices
/sys/class/power_supply|contains (a view of) the power supplies
/sys/class/power_supply/BAT<n>|information about the nth battery
/sys/class/backlight|contains (a view of) the screen backlights.

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

/var/opt contains variable data of programs installed in /opt

###### /run and /var/run

today, /var/run is deprecated in favor of and a symlink to /run
/run or /var/run contains runtime variable data that programs rely on that is cleaned or tirimmed at reboot

###### /usr

Data within /usr should be usable on any FHS-compliant host, ergo data specific to host or time should not go in /usr.
Data within /usr should be read-only

###### bins

whatever/bin is generally for executables
Originally and still in some unixes, /bin would have contained system-essential binaries, while /usr/bin and /usr/local/bin would have contained non-system essential bins (and analogously for lib)
today, /bin often just is a symlink to /usr/bin (and analogously for lib)
whatever/lib generally conains libraries for whatever/bin
/sbin is for binaries needing superuser priviledges/for system administration

###### /tmp

/tmp is for temporary files.
/tmp is sometimes emptied on process exit or on boot.
/var/tmp is like /tmp, but meant to last longer and thus autocleaned less or not at all

###### /etc

/etc contains confi files for all the programs that run on your Linux/Unix system
/etc/hosts
/etc/motd|contains the message of the day
/etc/machine-info contains machine metadata such as type of computer, deployment, location and pretty-printed hostname
/etc/hostname contains the usesrs static hostname.
hostnamectl administers the stuff in /etc/hostname and /etc/machine-info, i.e. all the hostnames and the machine metadata.
hostname - show or set the system's host name

###### /dev

/dev contains device files.
It makes sense to treat devices as just another file, as the operations they support (reading, writing or both) are the same as a file.
device files are files that are interfaces to device drivers (or more rarely other things).

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

####### character device files

/dev/stdin and /dev/stdout are symlinks to /dev/fd/0 and /dev/fd/1

##### Mac

((h:all;::<img src="sm_Screenshot%202020-07-09%20at%2014.36.21.jpg">))((c:2;::macOs))'s ((c:1;::/private)) folder contains ((c:3;::a few directories that would have been found in / on FHS-compliant devices)), namely ((s:1-3;::((c:4;::etc)), ((c:5;::tmp)), and ((c:6;::var))))
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}</span>

## files

### file operations regardless of contents

mv will silently overwrite if moving to something that already exists.
dd   copying (similar to cat/cp) with some low-level options
shred overwrites a file multiple times so it is difficult to recover, however this interacts badly with SSDs
touch|create emtpy file
mkdir|create empty directory

### files as binary

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


#### 7 types of files

In unix, there are 7 types of files.
Types of files in linux: {{c7::Regular file}} {{c6::Directory}} {{c5::Symlink}} {{c4::FIFO/named pipe}} {{c3::Socket}} {{c2::Device file (block)}} {{c1::Device file (character)}}

##### named pipe

named pipe = FIFO
mkfifo creates a new named pipe
named pipes are deleted via rm

##### links

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
Block device files grant random access.
Character device files grant sequential access.

#### special names

When config files are split up into multiple files, .d directory names are often used.
.d directory names are often used to give them a different names from normal files doing something  similar.
dotfiles are files starting with a dot.
Dotfiles are generally hidden by default.
Dotfiles are often used for config or metadata.


### file types by contents

#### binary

Binary files without a specification/documentation/parser are basically meaningless/unreadable.
What the binary files contents mean is defined by the file format.
Binary files are generally smaller and quicker to process than plaintext files

##### bitmaps

In the technical definition, a bitmap maps some domain to some bits.
In the technical definition, a pixmap is a bitmap mapping a pixel to a set of bits.
While in the technical definition, a pixmap is a hyponym of bitmap, they also may be treated synonymously, or sometimes a bitmap is seen as a hyponym of pixmap where one uses one bit per pixel.
The common file format for a pixmap image is BMP.
Pixmap images are very large, since they don't have any compression.

##### multimedia

(multi)media files are almost always binary files

###### images

#### plaintext

##### utilities

cat|output a file
wc|count words, characters and lines

wc output ordering
{{c1::lines}} {{c2::words}} {{c3::characters}}

bat is a more fancy version of cat with auto syntax highlighting, line numbers, git integration etc. implemented in rust.

##### types

Markup files are subset of plaintext files.
Markup files are written in markup languages.
markup languages consist of normal text and specific markup, which are intermingled.

###### toml xdg systemd

INI files inspired XDG desktop files.
XDG desktop files inspired systemd unit files.
TOML was inspired by INI, XDG and systemd unit files.
TOML|Tom's obvious, minimal language

###### m3u

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

###### ICAL/VCARD

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

###### dictionary-based

####### YAML

YAML|YAML Ain't Markup Language

####### JSON

JSON|JavaScript Object Notation
JSON is a plaintext file format.
JSON has the same syntax as JS object literals, with a few exceptions.
In JSON but not JS object literals, keys must be quoted.
In JSON but not JS object literals, functions are forbidden.
In JSON, the top-level item can either be an object or an array.

####### Schema

JSON schemas are schemas for JSON, YAML, usually written in JSON, though they can be written in different things.
top-level keys
title|title for the schema
description|description for the schema
$schema|URL of the version of JSON Schema this document adheres to 
$id|base url for the document, similar to <base> in HTML

####### jq yq

jq|process JSON
yq|process YAML & convert to/from JSON
yq -y/-Y roundtrip back to YAML
<code>yq {{c1::&lt;command&gt;}} {{c2::&lt;flags&gt;}} {{{c3::&lt;file&gt;}}}</code>
<code>yq {{c2::-t/--to-type}} {{c1::yaml}}/{{c1::json}}/...</code> {{c3::outputs the file as the specified file format}}

###### typesetting/just text

RTF|Rich Text Format

####### tex

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

###### subtitles

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

###### RISC instruciton pipelining

Instruction fetch > Instruction decode and register fetch > Execute > Memory access > Register write back 

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
Most but not all RISC ISAs, including ARM and RISC-V, are also load-store ISAs.
CPI = clocks/cycles per instruction
In general, a RISC ISA has 1 CPI, with fixed-length instructions.
{{c1::RISC-V}} is a {{c2::RISC}} instruction set architecture that is {{c3::open source}}.

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

# security

## crypt

{{c1::a cipher}} is an algorithm for performing encryption/decryption
Ciphertext is the text that is the result of {{c1::using a cipher}}
A substitution cipher is a cipher where an unit of plaintext is replaced by an unit of cipher text
The caesar cipher is a kind of substitution cipher where the replacement is done by rotating the entire alphabet by some number.
A brute-force attack is an attack of something such as a password {{c1::By trying until successful}}

### random numbers

C(S)PRNG  Cryptographically (secure) pseudorandom number generator
PRNG  pseudorandom number generator
RNG  random number generator

## network 

### DOS

DoS = denial of service
DDoS = distributed denial of service
In a DoS, the goal is to make a network resource unavailable.
In general, DoS succeed in making the network resource unavailable by taking up all its resources.
DoS may be performed by flooding the target with requests, or with some more sophisticated techniques.
A DDoS attack is a DoS performed from many different sources.

#### Low and Slow

##### Slow Loris



# *nix

## different *nixes

### POSIX

The Portable Operating System Interface (POSIX) is a family of standards specified by the IEEE Computer Society for maintaining compatibility between operating systems.
POSIX specifies both kernel- and user-level APIs as well as various shells and utilities.

### differences

Different *nixes have different versions of different command-line tools, on account of having descended in different ways from the original unix.
coreutils are the basic GNU file, shell and tex manipulation utilities.
the GNU versions of basic command-line tools is generally more featureful than other versions.
the GNU versions of basic command-line tools is generally the one that is assumed e.g. online.
You can install the GNU coreutils on non-GNU systems via homebrew.
If there is also a preexisting version of the command when the GNU coreutils are installed with homebrew, they are prefixed with g (e.g. gdir instead of dir).
If you need the normal names of the GNU coreutils when installed with homebrew (e.g. because they're being used in a preexisting script etc, add the directory they're in (/opt/homebrew/opt/coreutils/libexec/gnubin) to your $PATH

### what's in a *nix

#### GNU/Linux

GNU is the set of free software that accompanies the linux kernel in GNU/Linux.
GNU = GNU's not unix
The GPL was originally created for GNU
(GNU) GPL = GNU General Public License
Linux technically refers to the Linux kernel.
GNU software set + Linux kernel = GNU/Linux
Often, Linux alone is used (technically incorrectly) to refer to GNU/LInyx

A Linux distribution is GNU/Linux plus a set of other stuff, which depends on the flavor.

Android uses the Linux Kernel but not GNU or any of the other libraries.
From {{c3::android}} {{c1::1.0}} until {{c2::9}}, {{c3::android}} versions had {{c4::sweets}}-based names, with each name {{c5::going one further in the alphabet}}

### libraries & systems

#### linux

##### input

On Linux, input devices are often handled on linux by the library libinput, which is also the name of the command used to interface with it. 
libinput is native in wayland, but optional in X, which can also manage input devices directly, whose implementation you can interface with via xinput.

##### grapical display & related systems

pango is a linux library for international text rednering.

###### X

####### Login

A X display manager is a graphical login manager which starts a login session on an X server.
the GNOME X display manager is gnome's display manager.
GDM = GNOME display manager
LightDM is the most common alternative to GDM.

####### DE

D-Bus is a protocol/interface/middleware for messaging between processes (IPC).
AccountsService is a D-BUs service for accessing the list of user accounts and information attached to those accounts.

What Desktop Environment you're using   XDG_CURRENT_DESKTOP
What Desktop Environment you selected from the display manager (might be limited to gnome display manager)   GDMSESSION

####### CLI

xdotool allows automation of X windows
xclip allows interaction with the X clipboard

##### systemd

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

###### units

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

####### targets

reboot.target   The target for rebooting
poweroff.target   The target for turning off the computer
multi-user.target   multiuser (but no GUI)
graphical.target   multiuser <b>with GUI</b>
default.target   what the machine should try and aim for when booting (another target generally)

####### CLI

Passing systemctl a target (such as reboot) without the .target will execute that target
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

loginctl controls the systemd login manager

##### various subsystems & specs

###### NetworkManager

NetworkManager aims to provide an 'it just works' type network epxerience for linux
NetworkManager stores its saved connections in /etc/NetworkManager/system-connections/

###### Desktop Notification Spec

Spec for how notifications should work on linux   Desktop Notifications Specification
libnotify is the most common implementation of the Desktop Notifications Specification
To use libnotify, you need to also install a notification server/daemon.
dust is a minimal notification server/daemon.

###### bluetooth

hcitool is a command allowing noninteractive bluetooth config.
bluetoothctl is a command allowing interactive commincation with bluetooth.

###### sound

Linux's reasonably low-level sound interface is ALSA.
ALSA|Adavance Linux Sound Architecture
amixer is a command to control alsa.
PulseAudio is often layered on top of ALSA
pactl is a command to manage pulse audio
in linux soudn jargon, an output is a sink

###### language

ibus and fcitx are linux frameworks for multilingual input
mozc is a plugin for ibus/fcitx/whatever for japanese input.
ibus-daemon is the command for managing ibus
fcitx-configtool allows managing fcitx graphically.

## command-line 

### meta

most configurable commands are done so by a config file, either at ~/.commandname or XDG_CONFIG_HOME/commandname if following the XDG base directory specification, some also read from a global config file generally in /etc. Some commands also have a file ending in rc for config in those locations, though rc files generally specify commands to run beforehand more than settings.


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

#### bacvkup

borg, restic

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

#### misc

cal/ncal display a mini ascii calendar

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
nl|number lines

The commands head and tail print the first/last few lines of a file.
The amount of lines printed by head/tail defaults to 10

#### generation

fortune|display a random fortune

### media

#### generation

Default mac japanese voice is  Kyoko

#### processing

unpaper cleans/post-processes scanned pages
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

top is a process viewer.
htop is a more fancy version of top with a better TUI and interactivity.

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
termux-open   open something it its default application

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

### process relationshps

PPID|Parent Process ID
PID|Process ID
PGID|Process group ID

On unix, every process has a parent.


### process management

ps|list of processes
pstree|processes as a tree
kill kills a process, given its PID
killall kills a n processes, given a string that their name contains

procs is a more fancy version of ps written in rust

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

#### job control

<pre><code>^Z</code></pre> (as keyboard input)   Stop (not kill) the current program
the bg command takes a suspended command (e.g. one that was Ctrl-Z ed) and resumes its execution in the <b>background</b>
fg  resume stopped task in foreground
bg  resume stopped task in background
{{c1::&amp;}} at the {{c2::end of an command}} {{c3::puts it in the backround}} (but it {{c3::still continues running}})
jobs|show processes running in the background

#### terminal

A terminal may be a physical/hardware terminal, a terminal emulator = virtual terminal/console, or a terminal window.
A physical terminal is connected via cables to an UART driver.
drivers for screen, keyboard etc. are connected to a terminal emulator (not a window).
The UART driver or terminal emulator are connected to the line discipline.
The line discipline may be disabled, in which case the characters are sent directly and instantly to the process, the so called raw mode.
cooked/canonical mode is when the line discipline is enabled, which means that text is only sent to the application after a newline is sent.
cooked = canonical mode
The line discipline is typically disabled for TUI applications or similar and for the shell, which implements its own line discipline.
the line discipline is connected to the tty driver.
The tty driver is passive, while it has fields and methods, they need to be called from outside, e.g. via signals.
the tty driver seems to be the parent process of the session leader.

To the terminal, the shell is just one more process running within it.

Each physical terminal would have been its own separate thing, and so each terminal emulator is also its completely separate thing.
terminal emulators are represented by /dev/tty<n> files
terminal emulators are the things that are most often called ttys.
Terminal emulators may also be called virtual terminals/consoles, mainly in contrast to physical terminals.
virtual terminal = virtual console.
vt/vc is short for virtual terminal/console.
proper terminal emulators don't run within a GUI, but take over the whole screen (are the shell themselves, don't run within a shell)
/dev/tty<n> files are provided by the kernel.
/dev/tty0 represents the current controlling tty (virtual terminal).
When in a GUI, /dev/tty0 may be the terminal emulator the window server is running in.
On linux, pressing ctrl + alt + f<number> switches to tty<number>
Linux typically starts with 6 virtual consoles, and then one additional one (tty7) to run the window manager in.

/dev/tty represents the current terminal, regardless of what kind of terminal it is

In the past, many hardware/physical terminals might have been connected to one computer.
In the past, the system console would have been its own hardware/physical terminal connected directly to the computer.
Today, the system console is merely the device file /dev/console.
In most modern systems /dev/console is merely a symlink to /dev/tty

the tty command tells us which device file is implementing the current terminal

sometimes terminal emulator is used in the wider sense of 'any thing that emulates a hardware terminal', though I would consider this incorrect usage.

The default size in many cases for {{c3::terminal windows}} is {{c1::80 characters}} wide, and {{c2::24/25 lines}} high

stty administers the options for the tty driver.

##### signals

signals allow the kernel to communicate asynchronously with a process.
In the context of terminals, signals may be sent by/via TTY driver or some other part of the terminal subsystem.
In a terminal, any input, including stuff such as ^Z gets sent to the tty driver (or maybe the line discipline - I'm not quite sure, and people seem to be disagreeing). 
For some key combinations, such as ^Z, the tty driver will not transmit the input, but instead turn this into a signal and send this to the foreground process group.
For some key combinations, such as ^D, the tty driver will not transmit the input, but instead turn this into a different character and transmit this instead.
Other key combinations, including some ^<char> combinations may merely be passed on to the application.
Ergo some ^<char> combinations may always send the same signal (but leave it up to the application how to respond to the signal), some ^<char> combinations may send a different character (which will be treated by that application as that characer), and some ^<char> combinations will just send ^<char>, which the application may handle if it so chooses.
You can change which ^<char> the terminal driver handles how via stty.
^C|SIGINT|tty
^\|SIGQUIT|tty
^Z|SIGTSTP|tty
^D|EOT/EOF|tty
^L|FF|applications|often interpreted as 'clear the screen' (shells) or 'redraw the screen' (curses)

##### appearance

Things such as color and cursor movement in the terminal are implemented via control characters.

##### pseudo terminals

pseudo-terminals are terminals which are simulated within environments, especially within some kind of terminal.
A terminal window must be one level of emulation deeper than a terminal emulator, since it lives in a GUI which in linux at least itself lives within a terminal emulator.
Termux is a terminal window for android.

###### terminal window

terminal windows are generally connected to pseudo-terminals
A terminal emulated within a GUI is known as a terminal window
Alternative terminal window (mac)|iTerm2
xterm is the classic terminal window for the X window system.
most terminal windows are based of xterm
the default terminal window for gnome is gnome-terminal.
all the various terminal windows generally have a command of the same name to launch them/specify options
most terminal emulators take the -e argument to execute the command in the newly opened terminal window.

##### shell commands for terminal management

There are a number of shell commands that nevertheless still are concerned with terminals, and not with shells

###### terminal emulator

fgconsole   get the number of the current tty
fgconsole --next-avaliable   get next unallocated vt
deallocvt   remove unused virtual terminals
chvt N   change to ttyN

###### any terminal 


#### shell

the shell is typically the foreground process in a given terminal, buty may be the background process e.g. if we're using a TUI.
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

##### login shell

A login shell is is the first shell that executes after you `login`.
login indicates to the shell that the shell should be a login shell by prepending the name of the shell with a -, so that $0 will e.g. be -bash, not bash.
-l/--login forces bash to be a login shell (in this case), $0 will not be prefixed with -)
In bash, you can also use shopt login_shell to see if bash is a login shell.

##### startup files

pretty much all shells have a set of startup files that they run as normal shell code when starting a new shell.
when bash starts non-interactively, it looks for startup files in the paths listed in BASH_ENV.
when bash starts interactively, which files it reads from depends on if it thinks its a login shell.
if bash is not a login shell, it reads from ~/.bashrc
if bash is a login shell, it reads from /etc/profile, and then exactly one of ~/.bash_profile &gt; ~/.bash_login &gt; ~/.profile
It may be advisable to have one of the files loaded when something is a login shell load .bashrc, to ensure consistent behavior.
When an interactive login shell exits, or a non-interactive login shell executes the exit builtin command, Bash reads and executes commands from the file ~/.bash_logout, if it exists.

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
To use shell syntax with sudo permissions, the easiest way is to create a sudoed subshell (sudo bash -c "command")

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

.gitignore uses a similar syntax to globbing

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

### process relationships

A session is a collection of process groups.

## users and groups

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
visudo edits the sudoers file in a safe fashion with your configured VISUAL/EDITOR.
getpass is the C function that makes sure that password input is hidden (nothing is displayed) on the comamnd line
sudo usually caches the entered credentials for a short while.
The su utility requests appropriate user credentials and switches to that user ID (the default user is the superuser).  A shell is then executed.
su = substitute (in the past super) user
sudo = substitute (in the past super) user do

## projects

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

In computer science, a {{c4::session}} is {{c2::started at some point}}, {{c3::ends at some point}}, and during this time {{c1::maintaines state}}.
A browser session starts when the browser is opened and ends when the browser is closed (unless session restoring is used.)
A login session starts when a user logs in and ends when a user logs out or the existence of the session is otherwise terminated.

### proxy

((h:all;::<img src="Proxy_concept_en.svg">))
A {{c1::proxy (server)}} is a {{c2::server/server application}} that {{c3::acts as an intermediary between}} {{c4::a client requesting a resource}} and {{c4::the server providing that resource.}}
A reverse proxy is a proxy that appears to clients to be an ordinary server, but forwards requests to other servers in the background.
((h:all;::<img src="Reverse_proxy_h2g2bob.svg">))
Reverse proxies are sometimes called surrogates or gateways.

## interfaces 

An interface is a shared boundary across which information flows.

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

## protocols

A protocol is a set of rules that allows transmitting messages via a medium.
Protocols are often layered to produce a protocol stack.
While the medium over which a message may be transferred for a protocol may be an actual medium, in protocol stacks the medium is merely a lower protocol.
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
Mini and nonmini {{c4::DisplayPort}} is mainly for {{c1::video / audio}}, but can also carry {{c2::USB}} and {{c3::other data (e.g. thunderbolt)}}

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

### Internet Protocols

#### network admin tools

ifconfig is a linux tool to configure networke interfaces, though it is often deprecated in favor of iproute2.
iproute2 collects a bunch of legacy networking commands into a few commands, the most important of which are ip and tc.
speedtest-cli test the speed of your connection

#### model comparison

##### models

The OSI model remains useful, but unimplemented.
In both the OSI and the TCP/IP Model of how computers communicate, the application layer is the {{c1::top}} layer.
Internet protocol suite = TCP/IP
The internet protocol suite is a protocol stack
Instead of the OSI model, the TCP/IP model is used to model the communication on the internet today.
One of the first networks to implement the {{c1::TCP/IP protocol suite}} and one of the precursors to {{c2::the internet}} was {{c3::ARPANET}}

##### layers

OSI Model|TCP/IP Model|PDU (TCP/IP)
Applicatio|Application
Presentation
Session
Transport|Transport|segment (TCP) / datagram (UDP)
Network|Internet|Packet
Data Link|Link|frame
Physical

Frame contains IP packets contains segment/datagram contains application protocol message

TCP/UDP segments/datagrams are transmitted in IP packets between hosts.
IP packets are transfered in frames between routers.

##### hardware

layer no|layer name|device that moves things here
3|Network/Internet|Router
2|Data Link|Switch, Bridge, WAP
1|Physical|hub


Network hubs act to connect a network on the physical layer by mirroring an incoming signal to all other ports, thus seeming like a directly connected network on the data link layer.
Network bridges/switches act to connect multiple link-layer network segments, which thus aggregates them to a single network on the network/internet layer.
A wireless bridge is a network bridge used for wireless networks.
A network switch is a multiport network bridge.
A network switch uses the MAC addresses to make sure that the the frame is sent to only the host that needs it.
Routers pack IP packets into frames and forwards those to the next router.
A {{c1::wireless router}} performs the functions of {{c2::a router}} and of {{c2::a wireless acces point}} (and sometimes others as well)
Most commonly, a {{c1::(network) gateway}} is a {{c2::router}} that {{c3::provides access to (acts as a door to) a local network}}, but the term may also {{c4::refer to a bunch of other things}}
If a (normal office/home) computer user wants to load a web page, at least two network gateways are accessed—one to get from the office or home network to the Internet and one to get from the Internet to the computer that serves the web page.

While you may have as many Switches, bridges, and hubs as you like, to connect to the internet at large, you'll need a router.

Multilayer switches are switches that don't just operate on the data link layer, but also on higher layers (generally 3 and/or 4).
Content switches are multilayer switches that operate up to layer 7, and are often used in CDNs

###### alternative names

a {{c1::network switch}} is more rarely also called a {{c2::bridging}}/{{c2::switching}} {{c3::hub}} or a {{c4::MAC bridge}}

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

######## URN 

the path of URN URIs can theoretically be anything, however it typically has the following syntax
urn-path ::= <urn-namespace>:{<urn-subnamespace>:}<unique-id> 
urn-namespace ::= ISBN|ISSN|UUID|...
e.g. urn:oasis:names:specification:docbook:dtd:xml:4.1.2

######## origins

Two or more URLs that share a common origin (s/h/p tuple) are same-origin, all others are cross-origin

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

The leaf of a given FQDN is the host name
Domains to the left of a domain label are subdomains of that label.
Domain is a very ambiguous term: It may refer to everything but the hostname, any PQDN, or the FQDN.
a public suffix is a domain under which one can or at one point could register a domain name.
examples: .co.uk, .com, .tech
Many public suffixes are TLDs, but e.g. .co.uk is a public suffix but not a TLD, while some country codes are TLDs but not public suffixes (since authorities of some country code TLDs (e.g argentinia in the past) only allow registrations on subdomains such as .com.ar)
A registrable domain name consists of a single label plus a public suffix.
A registrable domain name is so called because it is or at one point would have been registrable

######### linux hostnames

Linux has three hostnames, static, transient, and pretty.
The pretty hostname can be pretty much anything
The static hostname is used for programmatic purposes, the transient hostname is used as a fallback.
While the pretty hostname can be pretty much anything, static and transient hostname are limited to 64 characters.

######## hotlinks, deeplinks

hotlinking = inline linking
Hotlinking is embedding a resource from {{c1::another fqdn}}
A deep link may be a link that links to any other page than the site's home page, a link that links to content within an installed app instead of a webpage (polysemy).
A link to the homepage of a page is called a surface link

###### applications

####### cURL

<br>---<br>
  §§ ((c:3;::cURL)) is a project for ((c:4;::transferring data)) using various ((c:5;::application protocols)). §<br>
§§ one half of ((c:6;::cURL)) is ((c:7;::the command-line tool)) ((c:8;::curl)). §<br>
§§ the other half of ((c:9;::cURL)) is ((c:10;::the library libcurl)) with ((c:11;::bindings for most major programming languages)). §<br>
§§ curl syntax: ((c:12;::curl)) ((c:13;::[options])) ((c:14;::{URLs))} §<br>
===<br>

<br>---<br>
  §§ ((c:15;s:16;::-i)) and ((c:16;s:15;::--include)) ((c:17;::show HTTP response headers)) §<br>
§§ To ((c:18;::set custom headers)) in curl, use ((c:19;s:20;::-H))/((c:20;s:19;::--header)) ((c:21;::"My-Header: My value")) §<br>
§§ To ((c:22;::set the query string)) to a certain value in curl, use ((c:23;s:44;::-d)) OR ((c:44;s:23;::--data)) ((c:24;::'key=value&amp;key2=value2')) §<br>
§§ To ((c:25;::simulate a filled in form)) with curl, use ((c:26;s:45;::-f)) or ((c:45;s:26;::--form)) ((c:27;::"key=value")) (supports ((c:28;::more fancy syntax for files etc.)) )  §<br>
§§ To make curl ((c:29;::fail on error)), use ((c:30;s:31;::-f)) or ((c:31;s:30;::--fail)) §<br>
§§ To ((c:32;::make a HTTP HEAD request (instead of the default GET))) with curl, use ((c:33;s:34;::-I)) or ((c:34;s:33;::--head)). §<br>
===<br>

<br>---<br>
  §§ To ((c:35;::make curl follow redirects (e.g. 301 Moved Permanently))), use ((c:36;s:37;::-L)) or ((c:37;s:36;::--location)) §<br>
§§ If ((c:38;::you've specified -L/--location)) for curl, ((c:39;::--max-redirs)) sets ((c:40;::how many redirects you want to follow)). ((c:41;::-1)) means ((c:42;::infinite redirects)) §<br>
===<br>

<br>---<br>
  §§ There are bunch of sites ((c:43;::designed to be <code>curl</code>ed)) to do something useful. §<br>
===<br>

<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th>Site</th>
    <th>Does what when <code>curl</code>ed?</th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:1;::wttr.in))</td> <td>((c:2;::get weather))</td></tr>
  </tbody>
</table>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}{{c28::}}{{c29::}}{{c30::}}{{c31::}}{{c32::}}{{c33::}}{{c34::}}{{c35::}}{{c36::}}{{c37::}}{{c38::}}{{c39::}}{{c40::}}{{c41::}}{{c42::}}{{c43::}}{{c44::}}{{c45::}}</span>


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

451|Unavailable For Legal Reasons (refrence to ray bradburry)

######## cache

<br>---<br>
  §§ A ((c:9;::cache)) is a thing that ((c:10;::stores data)) so that ((c:11;::future requests for that data)) ((c:12;::can be served more quickly)). §<br>
§§ With ((c:13;::caching and esp. with HTTP caching)), the guiding principle is that you want to ((c:14;::store the thing as long as possible)), but ((c:15;::update it as soon as it changes)). §<br>
===<br>

<br>---<br>
  §§ A ((c:16;::web cache)) AKA ((s:16;::((c:17;::HTTP cache)))) is ((c:18;::a cache for HTTP requests)). §<br>
§§ ((c:19;::web/HTTP caches)) can either be ((c:20;::shared)) or ((c:21;::local/private)). §<br>
§§ a ((c:22;::shared)) ((c:23;::HTTP cache)) sits ((c:24;::somewhere in the internet)) and ((c:25;::has many users)). §<br>
§§ a ((c:26;::local/private)) ((c:27;::HTTP cache)) sits ((c:28;::in your web browser)) and ((c:29;::is only used by you)). §<br>
§§ ((c:30;::Any HTTP request)) will ((c:31;::first be routed through)) ((c:32;::your browser cache)) and perhaps ((c:33;::a few network caches)) to see if ((c:34;::there is a fresh copy of the response available)). §<br>
===<br>

<br>---<br>
  §§ The main mechanism ((c:35;::HTTP caching)) uses is ((c:36;::the Cache-Control header)). §<br>
§§ In the days of ((c:37;::HTTP 1.0)), the ((c:38;::Pragma header)) was used for ((c:39;::caching)). §<br>
§§ The ((c:40;::Cache-Control header)) is sent ((c:41;::by the server)) and&nbsp;specifies ((c:44;::if a resource can be cached)), ((c:42;::who can cache it)), and ((c:43;::how long it can be cached)). §<br>
§§ The ((c:45;::Cache-Control header::caching)) consists of ((c:46;::a comma-separated list)), with either ((c:47;::boolean keywords)) or ((c:48;::key=value pairs)) ((h:all;::(cookie e.g. has a ; separated list) )). §<br>
§§ To specify ((c:49;::how long)) ((c:50;::a cache entry)) is ((c:49;::fresh (when it becomes stale))), one can either specify ((c:51;::max-age=value)) as ((c:52;::part of the Cache-Control header)) or ((c:53;::the separate Expires header)). §<br>
§§ ((c:54;::Maximum value)) for ((c:55;::Cache-Control:)) ((c:56;::max-age)) is ((c:57;::1 year)) §<br>
===<br>

<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th colspan="2">Keywords for Cache-Control for if to/who can cache a resource</th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:1;::public))</td> <td>((c:2;::Cache anything, even things that are not normally cached (weird HTTP status codes etc.)))</td></tr>
<tr><td>((c:3;::private))</td> <td>((c:4;::Don't cache in shared cache, only in private cache (e.g. browser)))</td></tr>
<tr><td>((c:5;::no-cache))</td> <td>((c:6;::Check with the server for change with each request (but don't redownload if unchanged)))</td></tr>
<tr><td>((c:7;::no-store))</td> <td>((c:8;::Do not cache the resource in any way))</td></tr>
  </tbody>
</table>

<br>---<br>
  §§ an ((c:58;::ETag)) is a mechanism for ((c:59;::judging whether a resouce has changed)). §<br>
§§ An ((c:60;::ETag)) is ((c:63;::a fingerprint)) for ((c:61;::a specific version)) of ((c:62;::a file)). §<br>
§§ An ((c:64;::ETag)) is ((c:65;::opaque)) to ((c:66;::the client)) but ((c:65;::transparent)) to ((c:66;::the server)) §<br>
§§ For ((c:72;::ETags)), the ((c:71;::server)) needs to decide on ((c:70;::a fingerprinting algorithm)) that ((c:68;::takes into account)) ((c:69;::the file and the version)) and ((c:68;::outputs)) ((c:67;::a fingerprint)). §<br>
§§ The ((c:73;::ETag fingerprint)) is sent along by ((c:76;::the server)) as ((c:74;::a part of the response)) in ((c:75;::an ETag header)). §<br>
§§ If we're using ((c:77;::ETags)) and ((c:78;::a resource expires)), the ((c:80;::client)) sends along the ((c:77;::ETag)) ((c:79;::fingerprint)) in ((c:79;::a If-None-Match header)). The ((c:80;::server)) uses this to check whether ((c:81;::the fingerprint)) still ((c:82;::corresponds to the current version of the file)), and returns ((c:83;::304 Not Modified)) if ((c:85;::true)), or ((c:85;::else)) a ((c:84;::normal 200 OK response)). §<br>
===<br>

<br>---<br>
  §§ There's no ((c:88;::built-in/non-hacky way)) in ((c:87;::HTTP)) to ((c:86;::notify a client that a resource has expired)) if they don't ask for it. §<br>
§§ ((c:89;::Cache busting)) AKA ((s:89;::((c:90;::revving)))) is a '((c:93;::hack))' to ((c:91;::force browsers to redownload new resources)) even if ((c:92;::they are not expired.)) §<br>
§§ ((c:94;::Cache busting)) sets ((c:95;::the longest possible max-age)) on resources, and if ((c:96;::there are changes)), it ((c:97;::renames the file in some way (e.g. a hash suffix))), which ((c:98;::forces the browser to redownload)). §<br>
§§ ((c:99;::Cache busting)) is generally done by ((c:100;::build tools such as Webpack automatically)) §<br>
===<br>

((h:all;::<img src="sm_tmpyvxwccqz.png">))

<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}{{c28::}}{{c29::}}{{c30::}}{{c31::}}{{c32::}}{{c33::}}{{c34::}}{{c35::}}{{c36::}}{{c37::}}{{c38::}}{{c39::}}{{c40::}}{{c41::}}{{c42::}}{{c43::}}{{c44::}}{{c45::}}{{c46::}}{{c47::}}{{c48::}}{{c49::}}{{c50::}}{{c51::}}{{c52::}}{{c53::}}{{c54::}}{{c55::}}{{c56::}}{{c57::}}{{c58::}}{{c59::}}{{c60::}}{{c61::}}{{c62::}}{{c63::}}{{c64::}}{{c65::}}{{c66::}}{{c67::}}{{c68::}}{{c69::}}{{c70::}}{{c71::}}{{c72::}}{{c73::}}{{c74::}}{{c75::}}{{c76::}}{{c77::}}{{c78::}}{{c79::}}{{c80::}}{{c81::}}{{c82::}}{{c83::}}{{c84::}}{{c85::}}{{c86::}}{{c87::}}{{c88::}}{{c89::}}{{c90::}}{{c91::}}{{c92::}}{{c93::}}{{c94::}}{{c95::}}{{c96::}}{{c97::}}{{c98::}}{{c99::}}{{c100::}}</span>

######## CDN

CDN = content delivery network or content distribution network
A CDN, is a geographically distributed network of proxy servers and their data centers. 
The goal of a CDN is to provide high availability and performance by distributing the service spatially relative to end users.
unpkg is a free &amp; open source CDN for npm packages

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

SSH allows using a short user@hostname form.
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
WebSocket use the scheme <code>ws:</code> (if unencrypted) or <code>wss:</code> (if encrypted)
To change from HTTP to WebSocket, the WebSocket handshake uses the HTTP Upgrade header

######## client

on the client side, sockets are created via the <code>WebSocket</code> constructor
the <code>WebSocket</code> constructor recieves the necessary argument of the url, and an optional argument of which sub-protocols to use
to send data on a <code>WebSocket</code>, use the method <code>send()</code>
To {{c3::react to incoming data}} {{c2::event handlers are registered}} on the WebSocket object
the four common events a <code>WebSocket</code> might recieve client-side are open, message, close, error

######## server 

the most common node web sockets library is <code>ws</code>

####### DHCP

DHCP = Dynamic Host Configuration Protocol

##### between application and transport

TLS/SSL are on top on the transport layer, but beneath the application layer, and are used as if they were the transport layer.
SSL is deprecated in favor of TLS, however TLS is often still called SSL

##### layer 4

###### nc

nc as a command is read netcat
nc allows you to make raw TCP/UDP connections.
nc [<options>] [<hostname>] [<port>]

###### ports

FTP|21

###### TCP

TCP = Transmission Control Protocol

####### handshake

TCP three-step handshake
Client --SYN--&gt; Server
Client &lt;--SYN-ACK-- Server
Client --ACK---&gt; Server

###### UDP

the UDP {{c1::datagram header}} consists of {{c2::4}} {{c3::fields}} of {{c2::2}} {{c3::bytes}} for a total of {{c2::8}} {{c3::bytes}} ({{c2::64}} {{c3::bit}})
of the UDP datagram header's four fields: 
source port|optional
destination port|mandatory
length|mandatory
checksum|mandatory in IPv6
<table>
  <tbody>
    <tr>
      <th>octets</th>
      <th>0 &amp; 1</th>
      <th>2 &amp; 3</th>
    </tr>
    <tr>
      <th>0</th>
      <td style="background-color: #fa9;">Source port</td>
      <td >Destination port</td>
    </tr>
    <tr>
      <th>4</th>
      <td >Length</td>
      <td style="background-color: #fa9;">Checksum</td>
    </tr>
  </tbody>
</table>
<span class="cloze-dump">{{c6::}}{{c7::}}{{c8::}}{{c9::}}</span>
the maximum size of a {{c2::UDP datagram}} is {{c1::2^16 bytes}} (although IPv6 {{c3::jumbograms}} do allow more, and {{c4::headers}} take up some of that)

##### layer 3

The ping utility uses the ICMP protocol's mandatory ECHO_REQUEST datagram to elicit an ICMP ECHO_RESPONSE from an IP.
the main protocol that lives on the network (OSI)/internet (TCP/IP) is IP.

###### IP

IP  Internet protocol
the {{c1::host URL element}} for the {{c2::loopback address}} is usually {{c3::localhost}}
the IP protocol data unit (the packet) is alternatively sometimes also called datagram.

####### address space

((h:all;::<img src="1024px-Regional_Internet_Registries_world_map.svg.png">))
RIR = Regional Internet Registry
NRO = Number Resource Organization
There are 5 RIRs.
the 5 RIRs are affiliated via the NRO
5 RIR areas:, one for Africa, most of NA, latin and central america + Mexico, Europe + Russia/West Asia, and one for most of Asia + Oceania

####### headers

the {{c3::IPv4 header}} consists of {{c1::14}} {{c2::different fields}}
TTL = Time To Live
TTL in IPv4 contexts was supposed to measure seconds, but was actually implemented as a hop count.
TTL as hop count was implmeneted by an 8-bit integer, usually starting at 64. When it reached 0, the packet was discarded and an ICMP time exeeded message was typically sent.
TTL exists amongst other reasons to prevent an infinite routing loop.
{{c1::TTL}} is called {{c2::hop limit}} in {{c3::IPv6}}

####### addr

######## IPv

The first major version of IP was IPv4, which is being succeeded by IPv6
The main reason IPv6 was introduced is that there are not enough IPv4 addresses

IPv4|32
IPv6|128

IPv4-addr = 1*3DIGIT "." 3("." 1*3DIGIT)

######## division

IP addresses have always been divided between network prefix and host identifier.
network prefix is also called routing prefix
host identifier is also called rest field or interface identifier

######### History


In the very beginning (until the 1980s) IP addresses were divided between the first octet as network prefix and the last 3 octets as host identifier.
In the very beginning (until the 1980s) what we call network prefix was called network number, and what we call host identifier was called rest field.

######### CIDR

CIDR = Classless Inter-Domain Routing
cidr-notation ::= [<IPv4-addr>]/<int-0-32>
/24 = an IPv4 network that has a 24-bit newtwork prefix and 8-bit host identifiers

######### broadcast & network identifier

A {{c1::subnet}}'s {{c2::broadcast}} address is the {{c3::all-ones}} version of the {{c4::host (any relevant IP address)/network (all-zeroes) identifier}}
Ergo, 255.255.255.255 (/0) is (theoretically) the broadcast address to all IP addresses in existence.
A godzillagram is theoretically a message to 255.255.255.255, which should theoretically broadcast to all IP addresses in existence.
Since gateways generally do not let godzillagrams pass, 255.255.255.255 generally merely boradcasts to your whole network.
Since network identifier addresses are generally aliases to broadcast addresses, 0.0.0.0/0 is an alias to the broacast address 255.255.255.255/0.
0.0.0.0/32 represents the undefined/NULL address, and may be used when one has not yet aquired an IP address or when accepting all incoming connections.

######### special IP addresses

of the IPv4 loopback addresses, generally 127.0.0.1 is used.
localhost = 127.0.0.1 (IPv4)
IPv6 reserves only a single loopback address, which is ­:­:1

The private IPv4 address blocks sorted from largetst to smallest are: {{c1::10.0.0.0}}/{{c2::8}}, {{c3::172.16.0.0}}/{{c4::12}}, {{c5::192.168.0.0}}/{{c6::16}}
(100000 = Prof X dual-wielding dual swords, 172160 = Android 17 outrunning a caravan of refugees, 192168 = Anakin skywalker outrunning a dragon)

####### NAT

NAT = Network Address Translation
{{c1::NAT}} {{c2::maps one IP address space to another}} by {{c3::modifying the info in the IP header}}
NAT (Network Address Translation)  allows mitigation of IPv4 address exhaustion because one IP address can be used for an entire network

####### tracing

traceroute and tracepathe are *nix utilities to measure IP paths and transit durations.
{{c1::tracepath}} is a {{c2::non-superuser}} version of {{c3::traceroute}}
tracepath/traceroute sends messages with adjusted TTL values and uses ICMP time exceeded messages to identify the routers traversed by packets from the source to the destination.

####### ICMP

ICMP = Internet Control Message Protocol
ICMP is used to send IP/routing-related error/control message.
ICMP messages are sent within an IP packet

##### layer 2 & 3 

ARP = Address Resolution Protocol
NDP

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

WLAN may run in {{c1::infrastructure}} or {{c2::ad-hoc mode}}
(WLAN) In infrastructure mode, clients connect to  {{c1::a central WAP (Wireless Access Point)}}
(WLAN) In ad-hoc network mode, clients connect {{c1::to each other peer to peer}}

####### Ethernet

The ethernet frame header contains quite a few fields, amonst which the most important might be destination MAC address and source mac address

IPoE is short for IP over Ethernet
PPPoE is short for Point-to-Point Protocol over Ethernet

### protocols higher than the OSI/TCP/IP

For HTTP APIs, the endpoint is most commonly an URL + request verb.

#### REST

##### six principles (alphabetical)

Cacheability
Client-server achitecture/decoupling
Code on demand
Layered system architecture
Statelessness
Uniform interface

##### HATEOAS

in a RESTful API following HATEOAS, the API may change its URLs without creating incompatibilites
in a RESTful API following HATEOAS, one hits an initial API URL and navigates via hyperlinks from there.

#### OAuth

OAuth 2.0 (grant type: Authorization code)
<img src="tmp7t5et6aw.png" />

### misc

MTP  Media transfer protocol
PTP  Picture transfer protocol

## networks

A network is a group of connected nodes that communicate via a medium, and almost always via a protocol.

### concepts

#### routing


An address is the identifier of an entity(ies) in a network, often relevant to a specific protocol.
A broadcast address is an address that identifies a subgroup of entities to target with a broacast transmission.
Loopback is the routing of signals/streams back to their source without intentional processing/modification.

##### routing schemes

#### topologies

A tree network may consist of star networks connected {{c1::via a bus network}}, or may be a tree just as a network.
In a bus, everyone attached recieves the transmission.
In a bus, only one entity can send at a time
A daisy chain is a topology where devices are linked in a line or ring.

### types

#### telegraphs

The first type of telegraph was the optical telegraph.
The electrical telegraph began to overtake optical telegraphs middle of the 19th century.
electrical telegraph is often just shortened to telegraph.
The electrical telegraph uses electrical pulses as a medium.
Telegraph stations were connected by wires.
The first telegraph was the needle telegraph, later replaced by the telegraph with key and sounder.
((h:all;::<img src="morse-vail-telegraph-key-1844-science-source.jpg">))A {{c1::telegraph key}} was/is a electrical switch where {{c2::pressing it}} would {{c3::produce a signal}} (and {{c4::holding it}} would {{c5::produce a longer one}}).
The telegraph sounder would have produced clicks from the electrical impulses.
Telegraphs were operated by telegraph operators until the advent of teh writing  pelegraphs.

#### telex

Telex was the network of teleprinters common in a large part of the 20th century.
Rough synonyms: {{c1::Teletype}}, {{c2::Teleprinter}}, {{c3::Telex <sub>theoretically the network standard, but in practice used mostly for the machine</sub>}}, {{c4::TTY}} (abk.), teletype(writer)
Teletypewriters/teleprinters/telex/ttys have keyboard for input and a printer for output.
Video terminals then came to replace teletypewriters especially for computer IO
Teletypewriters + video terminals = physical/hardware terminals.

#### the internet

On a basic level, the internet is a system of globally interconnected {{c1::computer}} {{c1::networks}}.
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

###### performance

Images used {{c3::on the web}} are typically {{c2::specifically compressed}} beforehand, e.g. {{c1::by using programs such as imageoptim}}
imageoptim exists as a GUI, a CLI (imageoptim-cli), and an API.

####### PRPL

Push/Preload the most important resources
Render the initial route ASAP
Pre-cache remaining assets
Lazy-load other routes and non-critical assets

####### defer & async

defer & async are two attriubtes for <script> that influence how it is loaded.
Ignoring speculative parsing, when the browser hits a <script> tag, it blocks until it's loaded, which is not ideal since scripts are quite large, and the browser could be loading things in parallel.
Instead of the default behavior, the <code>defer</code> and <code>async</code> attribute of scripts tells the browser to load the script in the background.
Between  the <code>defer</code> and <code>async</code> attributes, defer executes scripts loaded in the background {{c1::when the dom is fully built}}, in the order they were in the document
Between  the <code>defer</code> and <code>async</code> attributes, async executes scripts loaded in the background {{c1::as soon as possible}}, in the order in which they load, no matter source order.

####### minification

to indicate a source map, at the bottom of the optimized file, add a magic comment or use the http header
source map magic comment: //# sourceMappingURL=foo/bar.js.map 

####### Google speed

{{c1::Web Vitals}} are the stats that {{c2::google}} measures to judge {{c3::the user experience of your websites}}
{{c1::Core Web Vitals}} are the subset of {{c2::Web Vitals}} that {{c3::apply to all web pages (and are thus considered very important)}}
The current (2020 onwards) {{c4::Core Web Vitals}} are the {{c1::Largest Contentful Paint}}, the {{c2::First Input Delay}}, and the {{c3::Cumulative Layout Shift}}

A {{c1::layout shift}} is when a {{c2::visible element}} {{c3::shifts position}} between {{c4::render frames}} (in bad cases causing users to e.g. {{c5::click the wrong button}})
{{c1::Cumulative Layout Shift (CLS)}} is how google measures the {{c2::badness}} of the {{c3::layout shifts}} you've going on

CLS  Cumulative Layout Shift 
FCP  First Contentful Paint
FID  First Input Delay
LCP  Largest contentful paint

# applications

{{c1::Photoscape X}} is notable for being a {{c2::GUI}} program that has {{c3::batch editing of photos}}

## diff

<br>---<br>
  §§ ((c:4;::diff)) is a tool that ((c:5;::shows the differences between files)). §<br>
§§ ((c:6;::diff)) is originally ((c:7;::a cli program of the same name)). §<br>
§§ There are variants of ((c:8;::the original cli program diff)) that change how it work somewhat, e.g. ((c:9;::sdiff)) for ((c:10;::side-by-die diffs)) and ((c:11;::icdiff)) for ((c:12;::both colored and side-by-side diffs)) §<br>
§§ ((c:13;::diff)) is now offered as ((c:14;::a subcommand of)) ((c:15;::many other tools)). §<br>
§§ ((c:16;::npm)) ((c:2;::diff)) provides ((c:3;::diffs between packages)), some of which must be ((c:1;::published to the npm registry)) §<br>
§§ ((c:17;::git diff)) shows the difference between things ((c:18;::in/related to a git repository)). §<br>
===<br>

<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th></th>
    <th></th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td>((c:21;::no argument))</td> <td>((c:22;::show diff between unstaged and staged/committed))</td></tr>
<tr><td>((c:23;::--staged/--cached (synonyms)))</td> <td>((c:24;::show diff of staged changes with latest commit (or specified commit)))</td></tr>
  </tbody>
</table>

<br>---<br>
  §§ further, ((c:19;::diff-like output)) is now used in ((c:20;::a wide variety of gui applications)) §<br>
===<br>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}</span>

## media viewers

##### video 

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

SPDX is a format for software licneses

spdx-license-expression ::= <spdx-simple-expression>|(<spdx-license-expression> <operator> <spdx-license-expression>)|\(<spdx-license-expression>\) # slightly simplified
spdx-simple-expression ::= (<license-name>-<license-version>)[+]
Each SPDX license has a short and a long name.
The + at the end of a SPDX license indicates this version or later.

## versions

semver = semantic versioning
semantic-versioning-version ::= <major>.<minor>.<patch>
semantic-versioning-version-part ::= [<operator]<major>.<minor>.<patch>
semantic-versioning-version-specifier ::= 

Using semver, for each of major, minor or patch you can instead specify a * to indicate that any are acceptable.

## datetimes

Most common format is RFC 3339 / ISO 8601
RFC 3339 is almost the same as ISO 8601


# automation

The Amazon Mechanical Turk is a service that allows crowdsourcing menial tasks.
The Amazon Mechanical Turk pays way below the minimum wage.
The Amazon Mechanical Turk is sometimes used for study subjects.

# culture

## forum

OP|Original Poster

# programming (mostly)

## Expressions

An expression evaluates to = returns a value.
e.g. <code>6</code>, <code>6 * 2</code>, <code>true ? "foo" : "bar"</code>

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

<div class="cloze-group-children hide-if-inactive-children">
  §§ In ((c:3;::most programming languages)), a ((c:2;::block)) is a ((c:1;::statement)).  §<br>
§§ However, in ((c:4;::Rust)) (and in ruby to, though its weird, as blocks have the same syntax/are merely anon functions w/o arguments), ((c:5;::blocks)) are ((c:6;::expressions)). §<br>

§§ ((c:7;::Blocks)) ((c:8;::contain/consist of)) ((c:9;::one or more)) ((c:10;::statements)). §<br>
§§ ((c:11;::In/with)) ((c:11;::constructs)) or ((c:11;::languages)) that are ((c:12;::block-scoped)), ((c:13;::a block defines a scope)). §<br>
§§ ((c:14;::Curly-brace/bracket languages))&nbsp;are defined as languages that ((c:15;::use curly-braces)) ((c:16;::to define blocks)). §<br>
Many programming languages have been influenced by C, sometimes called C-family languages.
C was a curly-brace language, and so many C-family language are curly-brace languages.
(ba)sh is not generally a curly-brace language, but it still allows creating block statements via {} (but also via `()`)
bash calls its block statements command grouping.
bash block statements/command grouping is what is used by bash functions.
The difference between bash block statements using () and using {} is that () spawns a subshell and thus a new scope, while {} executes the commands in the current shell.
§§ Examples of ((c:17;::curly-brace/bracket languages)) I can write are ((c:18;::C#)), ((c:19;::ECMAScript)) -&gt; {((c:19;::Javascript)), ((c:19;::TypeScript))}, ((c:20;::Java)), ((c:21;::Perl)), ((c:22;::Rust)), SCSS (but not Sass). §<br>
§§ Most ((c:23;::curly-brace/bracket languages)) ((c:24;::are thus because they are strongly influenced by)) ((c:25;::C)). §<br>
In some programming languages (JS, Lua, ...?) blocks can stand alone, merely creating a scope. In other programming languages, blocks must follow a certain statement.
In lua, blocks end with <code>end</code> (outside of repeat...until). They are begun by <code>do</code> when standing alone, or when after a loop, by <code>then</code> after an if condition, and by nothing after a function signature
In bash, blocks for if are delimited by then ... (possible else etc.) fi, for for and while by do ... done, for case by in ... esac
In ruby, blocks end with <code>end</code>. begin begins a dedicated block statement (and is the keyword for the error handling statement), but no other blocks
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
An if/then(else) conditional is started by <code>if</code> in nearly all programming languages
the else arm of an if/then(else) conditional is started by <code>else</code> in nearly all programming languages

else if|C#|Java|JS|SCSS/Sass
elseif|lua
elsif|liquid|perl|ruby
elif|Python|(ba)sh
  
Anki has a if-like conditional to show something only if a field has content, indicated like: 
<pre><code data-codetype="text">{{c1::{​{}}{{c2::#FieldName}}{{c1::}​}}}
	Lorem Ipsum
{{c1::{​{}}{{c3::/FieldName}}{{c1::}​}}}</code></pre>

##### conditional operator

The ternary operator is a conditional which is typically an expression. 
The ternary operator is more properly called conditional operator. 
The conditional operator typically has the syntax &lt;condition&gt; ? &lt;iftrue&gt; : &lt;iffalse&gt;. 
The conditional operator comes from C (more properly an early ancestor of C), thus most programming languages that are inspired by C have it. 
  Example in JS:
  <code
    >let attack = enemy.isFireType() ? this.attacks.thundershock :
    this.attacks.inferno;</code
  >
Languages that I can write that <b>don't</b> have a ternary/conditional operator with the typical syntax are Bash (more precisely, only exists for arithmetic expressions), Lua, Python, and Rust.

##### others

An if statement/expression, but reversed in its truth value, is an unless statement/expression.
unless statements/expressions use the keyword unless.
unless statements exist in liquid, perl, ruby


Some languages (Perl, Ruby), allow a one-line conditional, where the syntax is &lt;expression&gt; &lt;conditional&gt; (we might term this a postfix notation)
for the postfix conditionals in perl, ruby

##### switch

switch is a type of conditional.
the switch conditional is generally a statement.
the switch conditional generally has one condition, and then n branches for possible values.
Besides the branches for possible values of the conditional, the switch conditional generally also allows for a default case.
The default for switch statements is optional in JS
In many languages switch conditionals feature fallthrough, which is where it will continue even after the case ends, until it hits a break/return statement.
switch conditioals are generally started by the <code>case</code> keyword.
Different cases for a switch conditional are started by <code>switch</code> in Java, JS and by <code>when</code> in liquid, ruby.
In liquid, ruby, multiple cases are separated by commas.
The default case for a switch conditional is <code>default</code>  in Java, JS, and <code>else</code> in liquid, ruby.
Bash has a fucked-up syntax: case &lt;expression&gt; in {&lt;case&gt;) &lt;command&gt; ;;} esac
Rust instead has match
In C-family languages, switch cases are generally syntactically equivalent to labels, and thus don't themselves create a new scope by default.

JS Syntax examples:

<pre><code>switch (expression) {
  {{c1::case}} {{c2::}}value1{{c2::}}{{c3:::}}
   //Statements;
   {{c4::default:}}
}</code></pre>

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
condition-controlled loops that test at the beginning of the loop are often started with the keyword <code>while</code> and are often called while-loops. 
condition-controlled loops that test at the end of the loop are often started with the keyword do, then a block, then end with the keyword while followed by the condition and are often called do-while-loops.
Most programming languages I know have while and do-while loops, in fact I don't think I know a programming language that doesn't have a while loop.
Perl and bash have an until loop: a while loop with an inverted condition (analogous to unless).
Lua also has a while loop with an inverted condition that tests at the end of the loop with the syntax repeat ... until



##### Collection-controlled loops 


A collection-controlled loop is a loop that loops over all elements of a thing.
Collection-controlled loops are commonly called foreach loops.
  Collection-controlled loops most commonly start with the keyword <code>for</code>, but then feature a different syntax than count-controlled loops. In perl, they instead start <code>foreach</code>.
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
In Rust, you can pass an argument to the break thing to have that be the return value of the block expression


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

## Comments

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
/\*foo\*/|CSS|C#|Java|JS|Rust
&lt;!-- foo -->|HTML
=begin foo =end|Ruby
{% comment %} ... {% endcomment %}|Liquid

Documentation
for the following thing|///|Rust
for the following thing|/**...*/|Java (Javadoc)
for the thing we are in right now|//!|Rust
for the thing we are in right now|"""foo"""|Python (docstring, must be first line in function, technically not a comment but performs similar function)

Rust documentation comments accept formatting in markdown. Code in code blocks there is executed as tests.

Documentation comments often generate HTML documentation

## Polymorphism

something is monomorphic if it works for one type
something is polymorphic if it works for several different types
monomorphization is a compile-time process in which polymorphic code is transformed into n monomorphic variants

ad-hoc polymorphism is polymorphism where different implementations are selected based on the type of the argument(s)
-> callable unit overloading, operator overloading

### dispatch (prob belongs somewhere else)

dispatch is choosing which method should be invoked in response to a method
displatch is based on the type of the thing
dispatch is only relevant if there are multiple implementations of a thing.

#### static dispatch

static dispatch is choosing an implementation of a polymorphic operation at compile time
callable unit overloading and operator overloading are forms of static dispatch, since the implementation is chosen based on the declared type of the parameters

#### dynamic dispatch

dynamic dispatch is choosing an implementation of a polymorphic operation at runtime
both single dispatch and multiple dispatch are forms of dynamic dispatch

single dispatch is where only the type of one parameter (the reciever of the message = the thing it was called on, mostly) is used to choose the implementation

multiple dispatch is where the type of multiple parameters (the reciever of the message = the thing it was called on) as well as the method parameters is used to choose the implementation

### parametric polymorphism

A generic is a stand-in for a type that is not yet specified or unknown. 
A generic may be constrained in some way.
Generics are most often specified via type parameters.
Parametric polymorphism is polymorphism that only uses one implementation, instead taking a generic (that is perhaps subject to some contraints) and performing one's operatons based on that.
Javas ArrayList, C# List and Rusts vec are dynamic arrays defined over a generic, and are thus parametrically polymorphic.
C# List and rusts vec are monomorphosized for each type usedas a generic; Javas ArrayList instead only generates a single implementation for ArrayList<Object> - therefore in Java all values in an ArrayList must be boxed.

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

### Name binding

Name binding is the association of entities with identifiers.
For an identifier to reference something is to the identifier bound to that thing.
Binding is intimately connected with scoping, as scope determines which names bind to which objects.
static = early binding is name binding during compile-time
dynamic = late binding is name binding during runtime

name resolution is the associating of identifiers with the correct things (e.g. variables)

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

exit allows you to exit the current (sub)shell, optionally specifying an exit code.

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
Assigning a value to a second variable invalidates the first reference.
When we assign a value to something different, thus changing the owner and invalidating the first reference/owner, we call this moving.
When a owner goes out of scope, a value is dropped.

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
e.g. match { Some(foo) => ... } will match Some() containing some value and assign that to foo

pattern matching checks if a thing matches a pattern.
In rust, the destructuring syntax is part of the larger idea of pattern matching. (and the syntax that we use for destructuring is a subset of the syntax of patterns)
Many pattern matching things can be used for destructuring (and are the equivalents of the destructuring constructs of other languages).
Beyond or at the same time as destructuring, pattern matching is used for match and if let conditions. 
In rust, patterns can either be
refutable|pattern can fail to match|Some(x) (does not match if value is not Some)
irrefutable|pattern cannot fail to match

match is a conditional that uses pattern matching for its conditions, and forces checking to be exhaustive.
Rust of the languages that I know has a match conditional (using the keyword match). Of the languages I don't know, the ML family and functional languages have match conditionals.

pattern1 bar pattern2|pattern 1 or pattern 2

Within rust pattern matching/destructuring, we even can destructure a thing out of a reference: let &foo = somereference

### Sigils### 

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

In rust, even variables are immutable by default, and the keyword mut makes them mutable.
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

Manifestly and statically typed languages can be more effort to write, but also dramatically lower the chance of bugs.

##### Type annotation

Specifying the type of a thing (esp. a variable/constant) by writing the type into the code is known as type annotation.
Languages with manifest typing generally require type annotation for variable/constant declarations, parameters as well as return types.
In most (esp. C-family) languages, type annotation goes before the variable/constant.
In Python, Rust and TS, type annotation looks like so `: type`
Python supports type annotation since Python .35

###### Type aliasees

Type aliases are names for types thsat abbreviate longer type descriptions.
Where type aliases exist, they generally use the type keyword.
`type ID  = number | string`

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
In TS, if {{c2::you know something about a type that TS doesn't}}, you can use {{c1::type assertions}}
TS type assertion syntax: prepending {{c2::&lt;some_type&gt;}} or appending {{c1::as some_type}}


#### Firstclassness

An entity is said to be first-class in programming if you can {{c1::Do most other things you can do with objects/values}}
typical features of entities that are first-class in a certain language are e.g. {{c1::Can be stored in variables/data structures, can be passed as a parameter to callable units, can be returned, tec.}}
An entity that is first-class is called a first-class citizen.
Lua: all values

#### Union type

A union type specifies a number of types that anything with the union type as type may take.
with {{c1::union}} types, you can only use things that {{c2::all of the relevent types can do}}, unless you {{c3::narrow them down}}
Syntax in Python and TS: type1 | type2 ...

#### Literal types

A literal type is a type that can take on exactly one value which is specified via the literal of another type (e.g. 4 or true or "ara ara")
A literal type is a type of unit type.

#### Top types and bottom types

A top type is the supertype of every othe type.
Any value can be assigned to the top type.
A bottom type is the subtype of every other type.
No value can be assigned to the bottom type.
Using the bottom type is useful when you want to specify a value with which you can do truly nothing.

A top type is often also the type that is at the top of the class hierarchy, in languages where such a thing exists

no bottom type|most languages
! (called the never type)|Rust
never|TS

object|Python
unknown|TS
UNIVERSAL|Perl
java.lang.Object|Java
System.Object|C#
BasicObject|Ruby


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
A dangling/wild reference is a reference
Link rot is the process of links becoming dangling/wild references.

Dereferencing takes a value that is a reference and returns the refernced value.
In most C-family languages (of the ones I can write, C# and Rust) to dereference you use the dereference operator *.
In Rust, the Trait that controls the behavior of the dereference operator is Deref, which has a method deref implementing dereferencing

### Null types

nil|lua|liquid|ruby
null|C#|Java|JS (secondary)
undefined|JS (primary)
there isn't one|Rust

Liquid has a special null-like type that is returned when accessing a deleted object called EmptyDrop
In JS a type is nullish if it is null or undefined.

####  nullable</h34>
Nullable types are a feature of some programming languages which allow the value to be set to the special value NULL instead of the usual possible values of the data type.

### Option type

An option type is a type that represents an optional value.
An option type can generally take on a state representing it is empty, or a state representing it is full, and wrapping around another value.
In rust, the option type is implemented as an enum.
In rust, the option type is 
pub enum Option<T> {
  None,
  Some(T),
}

In general, either option types or nullable types will be used to represent the absence of a value in a given language, but no both.

### boolean

A boolean data type is a type that has one of two possible values, indicating
truth values.

true/false|C#|Java|JavaScript|Lua|Ruby|Rust|TOML|YAML
True/False|Python|(YAML)
yes/no|YAML
no boolean type, only truthy/falsiness|Python

YAML is not boolean keyword case sensitive

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

{{c2::ES2020}} introduces the {{c1::BigInt}} datatype for numbers {{c3::larger than the previous maximum size}}
BigInt literal is indicated by ends in n

#### Integers

Integer literals generally not overtly marked

#### float and double

In Java and C#, to indicate a float literal you must add f as a suffix. any number containing a decimal point not explicitly indicated as a float will be a double
Most other languages don't distinguish between floats and doubles on a keyword level, merely by size (rust) or automatically
TODO: Check the above sentence and add more understanding on the difference between a float and a double-precision float on a conceptual level as distinct from how programming languages call them.

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

#### Access

Random access might be clearer if it was called direct access.
Random access allows access to arbitrary elements at will.
Sequential access only allows access in a certain sort of order.
<img src="sm_rand_seq_acc.svg">
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

### Set operations

Many languages/libraries have generalized set operations to something you can do to most/all collection types.
Python has set methods, but only allows them on sets.
JS has a Set class, which does not support set method

xor/union/intersection/difference(things...)|lodash/underscore(JS)

##### Associative collections

###### Associative array

An associative array is an abstract datatype composed of a collection of (key, value) pairs so that each possible key appears only once (as a key) = keys are unique.
Different programming language's implementations limit keys to only strings, strings or integers, all values, or something inbetween.

Some languages implement assoc arr via Objects, you then interact with them as you would with objects.
Some languages implement assoc arr as primitives, these then often have their own syntax for interaction.
Java implements associative arrays via things implementing the <code>Map</code> interface, e.g. <code>HashMap</code>, both defined over two generics.
JS implements associative arrays via the <code>Map</code> and <code>WeakMap</code> classes. objects (esp. object literals) also perform many of the operations we would expect of associative arrays. Specifically, Maps maintain insertion order, and support any key type, while Object coerces any key to a string (except Symbols). Objects are primitives, Maps need to be created with the new Map() constructor. Operations on map: get(), set()
In literals, key-value pairs are generally separated with , (e.g. keyval, keyval)
Lua implements associative arrays via tables (in fact, tables are the only data structure in lua). 
A lua table can be created the {} literal, like so {key = value, ...}
A lua table can be accessed via dot and square bracket notation. (Perhaps move this to its own thing-access section)
Perl implements and calls associative arrays as hashes. 
In perl, hash variables are marked by the % sigil.
In perl, keys and variables within hashes (perl assoc arr) can be separated by commas (as are the pairs, impairing readability), or separated by => for readability
In perl, hashes use the () or {} literals (is a diff, somethims something reference), {} when accessing
Python implements and calls associative arrays (as) dictionaries. 
Literals {}, accessing [], keyval sep :
Ruby: name hash table, {} literals, accessing [], keyval sep => if nonsymbol keys, : if symbol keys 
Rust: HashMap or BTreeMap, defined over two generics. Has the entry() function go get a Entry
C#: Dictionary, over two generics. Must be created via constructor.
YAML: either {} literals and keyval sep : or no surrounding literals, newline between items, and further indented. Calls them mappings.
TOML: keyval sep =, called tables, keys may be unquoted, or quoted if containing weird characters
SCSS/SASS: Calls them maps, keyval sep :, () literals (same as arrays)

adding a key, value pair
.Add(key, value)|C#
.set()|JS (map only)

deleting key
set it to null type|lua

Retrieval function
get()|Rust

Set a key to a value
[key] = value|most languages if primitive
insert(key, value)|Rust

Has key? 
key?|Ruby

Has value?
value?|Ruby

get array/iterator of key, value tuple/array/whatever:
pairs()|lua
items()|Python
entries()|JS (map only)

get array/iterator of keys
keys()|JS(only Map)|perl|Ruby|Python (returns a dict_keys object)
Object.keys(someobj)|JS

get array/iterator of values

values()|JS(only Map)|perl|Ruby|Python (returns a dict_values object)
Object.values(someObj)|JS

Amusingly, JS doesn't have the keys(), values(), entries()... functions for its assoc array type (objects), but does have them for arrays

merge two assoc. arrays
map-merge(foo, bar)|SCSS/Sass

commonly items are separated by ,

Computed property names allows you to put any expression on the left-hand side of a property within an object literal, if you wrap that thing in []

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

append one element to end 
push()|JS
append()|Python

remove an element from a lin coll by name
somelincoll.remove(elem)|Python

insert an element at a specific position
somelincoll.insert(elem, index)|JS

Fill the thing with the specified element
somelincol.fill(element[, start[, range]])|JS|Ruby
In Ruby, fill also may take a block to calculate the element to fill it.

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

somearray.splice({{c1::start}}, numberOfElementsToDelete, element1toInsert, ...); (odd, js only, returns array of removed elements which may be empty)

##### Strings as linear collections

TODO string as iterable
Strings are often implemented as linear collections (esp. arrays) of chars, or at least their semantics are similar enough that they work the same way.

##### Array##### 

An array (type) is a abstract datatype of an ordered linear collection of elemennts, selected by indices.


  |no indices (one value only)|zero-dimensional array (uncommon)|scalar
    |one index|(one-dimensional) array|vector
|two indices|two-dimensional array|matrix
|n indices|multidimensional array|tensor


Arrays may be dynamic = have variable size, or static = have fixed size.
Dynamic arrays are sometimes called arraylists.
Arrays are generally primitives in different programming languages, though they differ on syntax and what they call them.

dynamic arrays (one type only)

vector|rust
ArrayList|Java
List(yes, really)|C#

dynamic arrays (of whatever types)

list|python
array|perl|JS|ruby

Vectors, ArrayLists and Lists are Objects/Structs and defined over a generic

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

Array literals

In array literals, the invidual elements are generally separated by ',', except sh, which separates them by space

dynamic (of whatever types)
()|Perl (same as assoc. arr)|Shell
[]|JS|Python|Ruby

static, one type only
{}|C#|Java

static arrays (of diffent types), the compiler therefore knows the type of each index
()|rust
[]|TS

immutable static array (of whatever types)

()|SASS/Scss|Python (Though in python in reality it is the comma that creates a tuple. the parentheses are just often needed for grouping)
[]|TOML|YAML (if inline)

Most languages use the same syntax for one-dimensional, two-dimensional, or multidimensionall arrays, merely nesting the literals.
In C# the type for multidimensional arrays (e.g. for a three-dimensional array) is type&lt;delimiter&gt;,,&lt;delimiter&gt; (and for the constructor type&lt;delimiter&gt;length,length,length&lt;delimiter&gt;). These are different from merely arrays of arrays, as these have a uniform size (while arrays of arrays do not) 

YAML also has indentation delimited, newline separated, individual items marked by <code>- </code> version

In sh, referring to the whole array requires a special syntax my_array[@] which can only be used within ${}

In C# and Java, the builtin static arrays are objects, and thus must be created using the new operator. 
in languages with type annotation, the type of arrays is usually written as type[], e.g. int[] or String[]
When creating static arrays, the size must be given. In C# and Java, this is done in the [] of the array type in the constructor, e.g. new type[10];
In JS, one can create an array with a specfic size (and thus ergo empty slots) by using Array(n) or new Array(n)

access|O(1)
iterating|O(n)

##### Lists

Lists/Sequences are an abstract data type (specifically a collection), in which each element has a position (a first element, a second element), and that are finite.
Lists are always dynamically sized
C#: List, defined over one generic. must be created via constructor. Add to end of list .Add()

<img src="sm_408px-Singly-linked-list.svg.png">
A linked list is a data structure (implementing the ADT list) in which each node/vertex holds a reference to the next element.
To access a linked list, we merely need a reference to the first element.
A linked list in which the only node/vertex is a reference to the next element is a singly-linked list
<img src="sm_doubly_linked_list.svg">
A linked list with a backward reference too is a doubly-linked list.
access|O(n)

cons is short for construct function, and comes from lisp. 
To {{c4::cons something onto something}} is to take a {{c1::container}}, add {{c2::an element in front of it}}, and {{c3::put this in another container}}.
A singly linked list is functionally eqivalent to / can be modelled by a set of nested ordered pairs (foo, (bar, (quuz, nil))).
A cons list is a singly linked list constructed via nested ordered pairs.

###### vs arrays

slower access O(n) vs O(1)
more space consumption if no empty spaces in array due to pointers.
Re: modern CPUs, linked lists have the problem that they are stored non-contiguously and thus can't take advantage of CPU cache as well (priniple of spatial locality)

##### Streams

Streams are an abstract data type (specifically a linear collection), in which each element has a position (a first element, a second element), and that are infinite (or at least potentially so).

##### Stack

The anaogy of a stack historically comes from spring-loaded plate dispensers (e.g. in a mensa)
In a stack, the element you remove will be {{c1::the one you added most recently}}
LIFO = last in first out
A stack is a linear collection ADT with LIFO order, and the operations:
push: add to the top of the stack
pop: remove from top of the stack
peek: loop at top of stack
<img src="sm_Data_stack.svg">

##### Queue

FIFO = first in first out
A stack is a linear collection ADT with FIFO order, and the operations:
enqueue: add to the end of the queue
dequeue: remove from the front of the queue
peek: look a the next element that would be dequeued
<img src="sm_450px-Data_Queue.svg.png">


### Iterators

An iterator is an object (or similar) whose purpose is to iterate over some data. In general, an iterator has a next() method that returns the next element.
An iterable is generally something that can create an iterator of itself.
In ruby, iterables are called enumerables.
In most languages that have iterables, most collections are iterable, as are strings and ranges. Java Strings are not, JS objects aren't either.
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

### chars

The datatype storing a single character is generally called char.
In rust, a char contains a single UTF-32 encoded unicode codepoint.

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
YAML accepts unquoted strings if they don't interfere with other syntax, of which the most common case is them containing <code> :</code>
In some languages, strings are ended by the NULL (0x00) character, these are known as null-terminated strings.

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

#### String interpolation/String formatting#### 

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
{} or {0}, {1} ... interpolates within the string, if calling format() on the string. Interpolated expressions are args to format method, format specifiers go within {}, if passing to format by name, refer to these things like so {name}. If combining w/ format specifiers {name:format_specifier}
"Error code: {errno:x}".format(errno = ...
f-strings: allow arbitrary expression within {}. String must be prefixed by f
f"Hello, {name}"

Rust:
Syntax|Trait
{}|Display
{:?}|Debug
{:#?}|Debug, but pretty-print

##### C style string formatting

(C) format strings aka printf (print formatted) format strings are names for a specific type of string formatting syntax using % and originating from C.
Interpolate with what is called a format specifier: % followed by a char or a few chars to indicate the format. Which strings to interpolate where is determined positionally (the first string is interpolated ).
Format specifier syntax: %[parameter][flags][width][.precision][length]type
common types
x|lowercase hex
X|uppercase hex
d or i|signed int
f or F|decimal number

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
remove whitespace from beginning of string|trimStart()/trimLeft()|JS
remove whitespace from end of string|trimStart()/trimLeft()|Ruby
split string on foo|.split(foo)|Python|JS(empty string for char array)

#### String replacement

somestr.replace(foo, bar)|JS|Python

#### Join to string

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
Short-circuit evaluation  an expression stopping evaluating{{c1::as soon as it's outcome is determined}}
Short-circuit evaluation is most commonly found in the boolean operators of most programming languages
with short-circuiting of binary operators, the second argument is executed or evaluated only if the first argument does not suffice to determine the value of the expression.
specifically, expr1 LAND expr2 will not evaluate expr2 if expr1 is false/falsy
expr1 LOR expr2 will not evaluate expr2 if expr1 is true/truthy
Can be used to ensure a variable never gets assigned a falsy value by using logical/boolean or, since (only) if the first expression is falsy the second expression will be evaluated.
It is possible to create a kind of if statement using only short-circuiting operators: CONDITION && IFTRUE || IFFALSE
(ba)sh

### bitwise

Bitwise operations operate on the underlying binary value (regardless of type in the programming language).
Most C-family languages support bitwise operations.

bitwise not|~
left shift|&lt;&lt;
right shift|>>
bitwise XOR|^
bitwise OR|bar
bitwise AND|&


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
When not in callable unit parameters, JS spread and Ruby/Pythons splat transform an array into its constituent members
[... OR *[1,2,3], 4] == [1,2,3,4]

## Errors

Some languages distinguish between recoverable and unrecoverable errors.
recoverable errors e.g. not finding a file, unrecoverable errors e.g. stack overflow
Java and C# call recoverable errors exceptions and unrecoverable errors errors.
It can make sense to catch recoverable errors, but it is generally impossible to catch unrecoverable errors

### types

Errors can on one level be divided into {{c1::syntax}}, {{c2::static semantic,}} and {{c3::logic errors}}.

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
rusts {{c1::assert_eq!}} macro tests wheter {{c2::two expressions are equal}} (using the trait {{c2::PartialEq}}), and {{c3::panics if they are not}}
rusts {{c1::assert!}} macro tests whether {{c2::something is true}}, and {{c3::panics if it is not}}

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

### returning

Across most languages, the keyword to return whatever value is the <code>return</code> keyword.
The datatype of the thing that is returned from a callable unit is known  {{c1::The return type}}
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

A {{c1::closure}} is the combination of {{c2::a callable unit}} and {{c3::the lexical environment}} (= {{c4::any variables that were in scope}}) within which that function was declared.
Closures are created when the functions are created.
All callable units automatically create closures in JS, lua.
In rust, only closures create closures :P

### Call by...

Call by x and pass by x are synonyms
call by/pass by x is a distinction in how arguments are handled.
Languages may be call by/pass by x for everything always, or have some way of indicating which semantics to use, or handle different values differently.

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

### Anonymous functions

A callable unit not bound to an identifier is an anonymous function/callable unit.
First-class functions/callable units are callable units that are first-class citizens.
anonymous functios are almost always first-class functions, and are thus often passed as arguments, etc.
However, often non-anonymous functions can also be first-class functions

In ruby, anonymous first-class functions are called blocks.
In rust, anonymous first-class functions are called closures.
In JS, lua, python all functions are first-class. 
In JS, anonymous functions have no special syntax, you merely leave out the identifier.

In ruby and rust, parameters to blocks/closures are surrounded by |...|
In ruby and rust, blocks/closures are surrounded by {}
{|params| code...}
In ruby, blocks may also be surrounded by do ... end

in ruby, to call a passed block, use the yield keyword. 
Anything passed to the yield keyword will be available as arguments to the block
In ruby, the & operator converts a block to a proc object.
Calling #call on a proc object is similar to yielding a block
instead of a block with the syntax {|elem| elem.method} you can also pass &:method for the same effect

In JS, there is a special type of first-class anonymous function called an arrow function.
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

### Higher-order functions

A higher order function is a function that takes a function as an argument, or returns a function. All other functions are first-order functions.

There are many standard types of higher order functions.
In JS, the higher-order functions generally only work on Arrays, and the passed functions always recieve the arguments value, index, wholeArray.
In ruby, higher-order functions generally take blocks/procs

In JS, any higher-order function can take a thisArg, which is then the final argument. This argument will be what the passed fucntion recieves as this.

callable units passed to other callable units to be executed at some other point are also known as callbacks 

The deep nesting of callbacks that result in unreadability is known as callback hell or the pyramid of doom

Error-first callback look like  (err, value) => ...
Node generally takes error-first callbacks.

#### map

In many programming languages, map is the name of a higher-order function that applies a given function to each element of a collection, e.g. a list, returning a list of results in the same order. 
.map(func)|JS|Python|Ruby

#### sort

Sort is a higher-order function that takes a function which itself takes two arguments. Depending on the language, return values are handled differently.
JS function must return value smaller 0 if the first argument is to be first, larger 0 if the second argument is to be first, and 0 if it should not reorder.
The sort function passed must be deterministic.
In many languages, sort sorts with a predefined sorting algorithm if no sorting function is provided
In some languages sort does not take a sorting function, instead only using the predefined sorting algorithm, in those languages sort is not a higher-order function.

sorted(foo)|Python (takes an iterable)
foo.sort()|JS (takes an optional sort function, only Arrays)

#### filter

Filter is a higher-order function that processes a data structure to produce a new data structure containing exactly those elements which the passed function returns true.
filter()|JS

#### reduce

The reduce function/method takes a function known as the reducer function
The reducer function recieves the return value of the last execution of the reducer function, and the current element of the collection. 
The reducer function return a single value.
In effect, the reducer function applies an operation to the current element, and the accumulated result of all other elements.
Many languages allow specifying a 'previous result' element for the first time the reducer function runs, as there will not be one.
js has the variant reduceRight that starts from the end
reduce()|JS|Ruby|Python

#### some/every/

some is a higher order-function that takes a function and returns true if the passed function returns true even once.
every is a higher order-function that takes a function and returns true if the passed function returns true for all elements.
JS

#### find

find is a higher-order function that takes a function and returns the first element for which the passed function returns true. findIndex instead returns the index.
find()|JS|Ruby
findIndex()|JS
find_index()|Ruby



### Arguments

How are parameters and arguments are often used synonymously, although they are more properly not synonyms
for a callable unit,  {{c1::parameters}} are the values you specify the function will be passed, most commonly in its signature.
for a calllable unit, arguments are the values/variables you actually pass.
When passing things, using a car metaphor, you can think of the {{c1::parameter}} as a {{c2::parking space}} and the {{c1::argument}} as an {{c2::automobile}}
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
$# gets the amount of arguments passed.

#### Positional and named

A positional argument is one where the language knows which parameter to assign it to based on its position in the argument list.
A named argument is one where the language knows which parameter to assign it to because it directly refers to the name of the parameter.
Named arguments usually use normal assignment syntax

named parameters|Python|JS|SCSS/Sass @mixin, @function
positional parameters|pretty much all languages

#### Default parameters

A default parameter is one which will take on a default value if no argument for it is specified in the call.
In general, default parameters will also take on the default value if the argument passed is the language's null type. 
In JS, the default parameter will take on the default value if undefined is passed as an argument, but not if null is passed.
the general syntax is `paramname = defaultval` (within the parameter list)
Python, JS, SCSS/Sass @mixin, @function have default parameters TODO Check other languages

### Asynchronous callable units

Asynchrony, in computer programming, refers to the occurrence of events independent of the main program flow and ways to deal with such events.  

A promise is a proxy for a value that will eventually become available.
In JS, a promise is an object
You react to promises by calling the then() method on them.
In JS, something you can call then() on is called a thenable.
in JS, most interfaces for promises work on any thenables.
A promise can have the states {{c1::pending}}, {{c2::fulfilled}}, or {{c3::rejected}}.
A promise is called {{c1::settled}} if it is either {{c2::fulfilled}}, or {{c3::rejected}}.
Ergo a promise is either settled or pending.
We may return a rejected promise manually, additonally, if an error occurs in our async function, it will reject automatically.
Once a promise has settled, the attached thens will run as soon as possible / awaits will resolve.
If a promise is settled, and we then attach a then()/catch()/finally(), it will run immediately
While a promise is pending, thens will not yet run / awaits will not yet resolve.
A promise may have the fates resolved, unresolved.
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
Promise.race() takes n promises and runs the attached callback <b>once</b> the first promise resolves.
Promise.all()/allResolved() runs the attached callback once all passed promises are resolved. The attached callback will recieve all returned results as an array.
{{c1::Promise.allSettled()}} is like {{c1::Promise.all()}}, but the {{c2::former}} will {{c3::continue even if one rejects}}, the {{c2::latter}} will {{c3::not}}

in node, most functions are still designed for callbacks, however you can use util.promisify().
util.promisif()y takes a function following with a error-first callback as the last argument, and returns a version that returns promises.

Promisifying is making someting return a promise which wouldn't normally.

### Overloading

Overloading of callable units is creating multiple callable units with different callable unit signatures.
Languages I know that support overloading are C#, Java, TS.
When overloading, each signature generally has its own implementation, exept in TS.
In TS, function '{{c1::overloading}}' exists, but you specify {{c2::all possible signatures}} {{c3::first}}, and then the {{c4::implementation}} with a {{c5::signature}} that is {{c6::compatible with all the specified signature}} (e.g. using {{c7::optional parameters}}), and not compatible with {{c8::non-specified signatures}}
In TS, in general: prefer {{c1::union types}} over {{c2::overloads}}

### misc

Memoization is the form of caching that caches the return value of a deterministic callable unit

## Records

A record is a collection of fields, possibly of different data types, typically in a fixed number and sequence. 
A type that defines a record is a record type.
Most programming languages allow creation of instances of record types.

### Principles

Encapsulation refers to grouping together related things somehow, e.g. within records.
Information hiding is hiding the internals of a thing from the  outside.

### Class and instance entities

A class x is a x operates on/is defined on a class rather than an instance.
An instance x operates on/is defined on an instance of a record.
A class x may also be known as an associated function.
Class x ≈ static x
generally, one mainly talks of class, instance methods, which operate on classes/instances, and class, instance variables
class variables + instance variables = fields
Members are generally all methods and fields of a record, no matter if class or instance.
ergo: members = member fields + member bariables
A piece of data on a record is called a field

In rust, a class method/associated function is called by using the :: operator

static|Java|C#|JS
does not take self as argument|Rust


### Methods

A method is a callable unit that is a member of a record.
To make an object B do something, an object A must send a message.
in OOP, a method call is the way to send of message: The originator object is implicit, the target is specified manually, the method called is the message, and the arguments are well the arguments.
Ergo, in OOP objects generally use message passing to communicate.

In Rust, Python, methods must take self as the first argument.


#### Getters and setters

Also called accessors and getters.
A getter returns a field of a record.
A setter changes a field of a record.
Setters are often used to perfrom some sort of validation before changing the field of a record.
Getters and setters may help enforcing information hiding.

Ruby syntax:
def name=(value)...|setter

JS:
get foo()
set foo()
only within a class

You can only interact w/ ruby instance variables via getters and setters, trying to use it without those will give you a NoMethodError

### passive data structure

AKA plain old data structure (PDS)
Use of a data structure that contains fields w/ values, but no other object-oriented features


### Structs

Struct is not an incredibly well-defined term, but is generally a record with the possibility for methods, but not the whole inheritance etc. stuff of classes.
In rust, struct declarations use the keyword struct.
Both struct delcarations and initializations in rust use a very assoc-array like syntax.
struct User { username: String, ...}

### Tagged unions

A tagged union can hold a value that could take on several different but fixed types.
A tagged union can be thought of as a type that has several "cases", each of which should be handled correctly when that type is manipulated.
What rust calls enums is more properly a tagged union

### Classes & objects 

An object in object-oriented language is essentially a record that contains procedures specialized to handle that record; and object types are an elaboration of record types.

Keyword to declare a class is done by the keyword <code>class</code> in pretty much all programming languages which have it.

A singleton (AKA the singleton pattern) is a class that can only have a single instance of that class. It is useful when you don't need multiple instances of a thing (the null object, a logger), or to coordinate states.
A type that only allows one value (only allows a sigleton) is known as a unit type.

reference to the current record/other thing
self|Ruby|Rust
this|C#|Java|JS

method in lua function object:method(...)

in languages with type annotation, the type annotation of an object is generally its class (e.g. MyClass myObject = new myObject();)


#### Methods ruby

In ruby, methods that will return a boolean are marked by a ?
In ruby, methods that do something destructive are marked by a !

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
In most programming languages, you refer to your superclass=base class with the keyword <code>super</code>.
In most programming languages, you specify a subclass/superclass relationship like so: Subclass extends Superclass
In ruby, you specify a subclass/superclass relationship like so: Subclass < Superclass
In C#/Java, making a class final disallows a subclass from inheriting from it.
In C#/Java, making a method/static function final disallows a subclass from overriding it it.
Most languages only support single inheritance, some languages (among those I know Perl and Python) also allow multiple inheritance

#### abstract & static classes 

Abstract classes are generally declared with the abstract keyword. Within abstract classes, methods are also declared with the abstract keyword.
Both abstract and static classees are not instantiable.
Abstract classes are designed mainly to be inherited from.


#### Constructors/object creation

Creating a new object via a constructor is done by the new operator in most languages, but not in Ruby or Python.

A constructor is generally a callable unit and thus called with ()
Rust doesn't use any operator to create new Structs. In general, you use literals, some type provide a new() associated function.
In C#, Java, the constructor has the same name as the class.
In Ruby, the constructor is defined by the initialize function within the class (class SomeClass\n  def initialize(...), and called by calling the new() method on the class (SomeClass.new())
In JS, the constructor is named constructor
Many languages allow us to declare many different constructors with different arguments.
Most languages provide a default constructor if you don't provide one, which does nothing besides create the object.
In JS, you may not use arrow functions as constructors



#### type parameters and generics

The things that define {{c1::the types}} a function/object/... is defined over, which usually go in {{c2::angle brackets}}, are across programing languages usually called {{c3::type parameters}}.
Generally, multiple type parameters are separated by , 
Type parameters are generally written in UpperCamelCase
Generics are generally a single char only

#### Access modifier

Access modifiers (or access specifiers) are keywords in object-oriented languages that set the accessibility of classes, methods, and other members. 
In Java, members have default accessibility by default.
In Python, JS, members are public by default.
Most language with any kind of access modifiers have at least a public private distinction
public (most programming languages), pub (Rust)|any code
private|code within the class
Most languages with a public/private access modifier distinciton will use the public/private keyword to mark the one that is not the default anyway
JS is an exception, it marks private members with #

default||Java
protected|same mclass and subclasses|Java

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

Things using the ruby mixin Comparable must define <=> operator, and then gain access to the other comparison operators, as well as between? and clamp

##### Traits

Traits in Rust are broadly similar to intefaces in other programming languages.
Traits in Rust can be implemented for types you did not define.
However, the trait ∨ the thing its implemented on must be local to the crate
Traits allow for blanket implementations, that is implementing a trait for anything that implements one or more other traits

#### OOP

C#, Javaf

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

Most languages with objects have a tostring function to convert these to strings for debugging purposes.
It can often be useful to overwrite the default tostring implementation for more useful custom debugging.

toString()|Java|JS
ToStrng()|C#

#### Boxing

A box is a minimal object wrapper around another type.
The types that are most commonly boxed are primitives, sometimes boxing is restricted to this narrower definition.
putting values into a box is called boxing, the opposite unboxing
A wrapper is any entity that encapsulates/wraps around another thing.
Implementation-wise, it may be that the whole box is stored on the heap as an object would be, and we only have a pointer to the box, or as Rust seems to do it the Box may merely contain a pointer to whatever data, which is moved to the heap.
Memory-wise, since boxes are objects, boxed data will be stored on the heap.
Boxing primitives allows us to interact with them using a similar interface as other objects; this enables the Everything you operate on is a first-class Object constraint of pure OO, consequently most primitives are boxed in languages aspiring to pure OO such as Python, JS, Ruby...
Autoboxing is the conversion of primitves to boxed types when relevant.
Since boxed data will be stored on the heap, it is not necessary for it to have a constant size, thus boxed data allows more flexibility.

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


## Formatting

Official style guide/best practices
PEP 8|Python

## import/export

A module is as self-contained set of code, most commonly in a single file of code.
Packages and modules are sometimes synonyms.
conta
In python, a package is a collection of modules (and perhaps other packages).
In python, each .py file is a module.
A package must contain a __init__.py file

If you want to import/export multiple members, most languages have the syntax {member1 [as name1], member2 [as name2], ...}
Import/export anything uses * in most languages
in JS, you can only import/export within modules.

### module systems

#### JS

##### CommonJS

CommonJS is {{c1::a module ecosystem}} mainly used by node

let/var/const <name> = require(<path>)

##### ES Modules

To contrast with module systems such as CommonJS, the official implementation of modules in JS are known as ES Modules.
In JS, ES Module import/export statements can only be used within a module

###  Importing

Import statements tell whatever's executing the program to act as if the specified entities were part of the file, potentially renaming them.
In most languages, you can only import things that were first exported.
In most languages, import statements must be in the beginning of the file.
In most languages, you may only export top-level items.
Import statements have the general syntax

import <members> [as <name>] from <path>
in JS you can leave out <members> from if you only want the side effects

Python instead has the order from <path> import <members> [as <name>]

In vanilla CSS, you can import other stylesheets via the non-nested at rule @import.
@import syntax: @import <path> (<media-query>|<feature-query>);
For CSS, the <path> may be an <url> or a <string>

#### SCSS/Sass 

Three keywords: @use, @import, @forward (@include is not an import statement!)
Syntax alwas keyword <path> [as <name>]
@forward foo doesn't allow the current stylesheet bar to access the things in foo, but {{c1::allows anything @using bar to access them.}}


#### prelude

Most languages have a number of things that are automatically imported. Rust (and haskell) calls this prelude.

### exporting

Exporting is selecting entities for potential import.
In most languages, exporting is required so they can then be imported.
General syntax: export <members> [as <name>]

#### default exports

## Events

Technically, an event listener watches for an event, at which point it calls the event handler to deal with it.
In casual use, event listener and event handler are synonyms.

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

The lifetime of a variable or object is the time where it has valid memory.

### The stack and the heap

The call stack is often only called the stack.
The call stack implements the stack ADT
The call stack is made up of stack frames.
The stack frame usually includes at least {{c1::the arguments}}, the {{c2::return address}}, and {{c3::local variables}}.
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
In most languages, records are kept on the stack.
In most languages, since records are kept on the stack, a variable/constant merely stores a pointer to the record.
The stack is significantly faster than the heap, since it's implementation is far simpler.
The heap can become fragmented.
The heap is managed much less strictly than the stack.
For things on the heap, you typically have a pointer.

In general, there is one stack per thread and one heap per process (instance of a program)

### static, automatic and dynamic variables

An automatic variable is a variable that has its memory allocated and deallocated automatically when the program enters and leaves the variables scope.
Automatic variables have a lifetime of the variables scope.
Automatic variables are allocated on the stack, within a stack frame.
Any automatic variable can go out of scope.
A static variable is allocated for the entire lifetime of the program.
Static variables fall outside of the clear stack heap distincition.
Dynamic variables have a lifetime of your choosing: their memory is allocated and deallocated by you.
Dynamic variables are stored on the heap.
Def: Automatic/static/dynamic variables use automatic/static/dynamic memory allocation.

### memory management

Memory management is managing the memory of an application.
One of the main jobs of memory management is memory allocation and deallocation.
Memory management may be manual = performed by the programmer or automatic = performed by the programming language automatically.
Dynamic variables are handled by manual memory management or by automatic memory management.
Automatic variables are handled by automatic memory management.
Most higher-level programming languages have no manual memory management at all.

#### types of data

Garbage data is data that cannot be used anymore (e.g. reference out of scope)
The opposite of garbage data is live data.
Outside of programming, garbage data is sometimes used for data that is unusable in some way (e.g. corrputed, garbled)

#### garbage collection

Garbage collection is a form of automatic memory management in which a garbage collector deallocates garbage memory.

#### reference counting

(manual) reference counting is a form of manual memory management
automatic reference counting is a form of manual memory management
In reference counting, when no more references to a certain object exist, then it is destroyed
In reference counting, a thing as some kind of field indicating how many references to it exists.
In manual reference counting, we call increment and decrement methods to indicate how many references there are.
In automatic reference counting, increment/decrement methods for refrences are called automatically. 
Circular set of references are called reference circles.
reference circles can allow things in refrence counting to never reach reference count 0 and thus be destroyed.


## libraries


### web frameworks

A framework is a set of libraries where the framework itself has control by default, and only exposes an API.
A framework: Don't call us, we'll call you.
A web framework is a framework for use in web development.

#### commonalities

#### front-end frameworks

Express is the most popular server-side web framework for node.
Angular is the successor to AngularJS
Angular is sometimes called Angular 2
While AngularJS was written in JS, Angular (2) was written in typescript.
Angular and Vue.js are the two most popular front-end frameworks that are clearly frameworks.
React is often called a framework and would be the most popular front-end framework if it was, but is more like a library.
Svelte works like a front-end framework, but actually compiles in advance.

##### react 

###### react native


Native Components: React Components transformed into native views
Core components: Native Components that are part of React Natives standard library
React Native|HTML
&lt;View&gt;|a non-scrolling &lt;div&gt;
&lt;TextInput&gt;|&lt;input type="text"&gt;
&lt;Text&gt;|&lt;p&gt;
&lt;ScrollView&gt;|a scrolling &lt;div&gt;
&lt;Image&gt;|&lt;img&gt;

#### server

##### Python

Flask and Django are the most popular web frameworks for Python.


### IO

#### the enviornment

In ruby, {{c1::$stdin}} {{c2::represents stdin}} and {{c1::$stdout}} {{c2::represents stdout}}. They are both {{c3::streams}}, which means we {{c4::use the read method}} to read input&nbsp;
sys.stdin|python

Command-line arguments
@ARGV|Perl
process.argv|node

Environment variables
%ENV|Perl
process.env|Node

#### Print

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

echo options
-n|no trailing newline

Print functions using format strings
printf|(ba)sh|C (ofc)|Perl|Ruby
string.format|Lua
% syntax|Python

Print an error to console (but don't throw one)
console.error()|JS
@warn|SCSS/Sass

clear the console/terminal window
clear|sh
console.clear()|js
ø (no easy native solution)|python|ruby

console.count(foo)   count how many times a string foo has been printed

the sh printing commands all don't read from STDIN
besides taking format strings, printf has exit codes other than 0 (echo always exits 0), echo adds a "\n" at the end while printf doesn't

#### system

module for os access (syscalls, shells, environment, etc)
os|python

Run things in a system shell
system()|ruby
<system-module>.system()

#### visual

##### UI

widget tookit   library for creating UIs
gtk   GNU widget toolkit
qt (read cute)   cross-platform widget toolkit

##### Data visualization

d3 is a JS library for mainipulating/visualizing data

#### scientific computing

pandas|python

### dispose

The dispose pattern is a pattern for resource management.
In the dispose pattern, a resource is held by an object.
In the dispose pattern, a resource is typically aquired by calling a global function.
In the dispose pattern, a resource is used by calling methods on it.
In the dispose pattern, a resource is released by calling a method on the object.
The dispose pattern is common for interacting with files, in which case the resource is a file handle.
Dispose pattern for file handles:
An open() function takes a path and returns a file handle.
file handle methods
write()|write argument to file
read()|return whole file as string
readline()|return next line as string
close()|release the file handle

Languages that handle files based  on the dispose pattern: Python
For Python, the open method takes a named parameter mode:
r|read
w|overwrite (create if doesn't exit)
x|create but don't overwrite
a|append at end (create if doesn't exist)
For Python, the open method takes a named parameter of encodding

some languages have language constructs for the dispose pattern: 
with|Python
using|C#
Languages that have language constructs for the dispose pattern typically require the things they act on to implement a certain inteface with methods for aquiring and releasing the resources, which will then be called automatically.
The language constructs for the dispose pattern typically assign the resource to a local variable.
The language constructs for the dispose pattern typically only execute their code if the resource could be successfully aquired.
In python, the interface for the dispose pattern is a context manager object, which must have __enter__ and __exit__ methods.
python-construct-for-dispose-pattern ::= with <context-manager> as <variable-name>:
c#-construct-for-dispose-pattern ::= using(<type> <variable-name> = <thing-implementing-IDisposable>){...

### performance monitoring

time|measure elapsed time in executing a command|sh
console.time() & console.timeEnd()|measure elapsed time in running code.

### dates

most languages have a date object (or multiple different ones) that allows convenient manipulation of datetimes
In js, {{c2::Unix time}} is almost always interacted with in {{c1::milliseconds}}, 
as opposed seconds, which is more standard
the <code>{{c1::Date.parse()}}</code> method takes {{c2::a date in a few common formats}} and outputs {{c3::Unix time (in millis, as is common in JS)}}
<code>{{c1::new Date()}}</code> takes {{c2::Unix time milliseconds}} and returns {{c3::a <code>Date</code>}}
<code>{{c1::someDate.toISOString()}} </code> returns the datetime {{c2::as ISO 8601}}

### Standard library

A software solution that has everything that it needs to run out of the box is said to be batteries included.
A programming language that has a large standard library is said to be batteries included.

count occurrences of element
foo.count(bar)|Python|Ruby
no easy way|JS

get (first) index of element/substring in string or linear collection
foo.index(bar, optionalStartIndex)|Python
foo.indexOf(bar, optionalStartIndex)|JS (returns -1 if ti could not be found)

get (last) index of element/substring in string or linear collection
foo.lastIndexOf(bar, optionalStartIndex)|JS

get list of all functions a module/package supports
dir(foo)|Python

get a random number
&lt;mathobj&gt;.random()|JS

floor/ceiling function
&lt;mathobj&gt;.floor()/.ceil()|Python|JS
&lt;thingItself&gt;.floor()/.ceil()|Ruby

Is a thing an integer?
Number.isInteger(foo)|JS

get the smallest/largest of an amount of arguments
min()/max()|Python (also accepts an iterable as an argument)
Math.min()/Math.max()|JS

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

Get documentation information on the thing
help(foo)|Python

Sort the thing 


Move remove the first argument and shift all arguments one to the left
shift|Perl|sh

does the thing contain the thing?
include?|Ruby
includes()|JS

is x between foo and bar?
x.between?(foo, bar)|Ruby

Show an output popup
window.alert("mesg")

Concatenate multiple strings/ arrays at the end of an existing string/array
stringOrArray.concat(stringsOrArrays)|JS|Ruby

Is there a truthy value in an iterable
any(iterable)|Python

Are all the values in an iterable truthy 
all(iterable)|Python

Sum up all the elements in an iterable
sum(iterable)|Python
enumerableWhichIsJustASynonymForIterable.sum()|Ruby

#### assoc-array files

typically, most languages have modules/libraries called json/yaml for json/yaml processing.
JS calles its json/yaml libraries JSON/YAML.
<j-or-y-library-object-name>.load()|parse as JSON/YAML into assoc array structure|Python
<j-or-y-library-object-name>.parse()|parse as JSON/YAML into assoc array structure|JS (incl node)
<j-or-y-library-object-name>.dump(<assoc-arr>, <file>)|write assoc array as JSON/YAML|Python

to make sure that Python's JSON/YAML libraries insert newlines and indentation, pass the load method the named parameter indent with the relevant indent.

#### Modules/Objects/Namespaces

Object/Struct/whatever for standard math operations
Math|JS
math|Python

Filesystem handling
fs|node

#### Query for input

Generally, show a message, have a text input field, return the inputted text.

input(mesg)|Python
window.prompt(mesg, default)

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

### other libraries

#### presentations

complexity|write in|name|converts to
fancy|js|reveal.js
simple|md|remarkjs
simple|own markdown syntax|pandoc|5 html-based formats incl. reveal.js, latex beamer, ms powerpoint, pdf


## programming language categorization & history

A high-level programming language is a programming language with strong abstraction from the details of the computer.
A low-level programming language is a programming language with little to no abstraction from the details of the computer.

### Programming paradigms

Functional programming languages: {Haskell}

### Programming languages I don't know

COBOL is a programming language introduced in 1959 with an englisy-like syntax that is as of 2021 mainly used on {{c1::legacy mainframe computers}}
C was created in 1972.
*nix OSs are famously written in C.
tcl is a programming language where everything is a command.
tcl has a well-known widgeting toolkit known as tk.
wish is a tcl interpreter including its widgeting toolkit tk.

### programming language relationships

#### ECMA

JS = Javascript
ES = ECMAScript
JavaScript is a dialect/language that coforms to of the ECMAScript standard
others languages that conform to the ECMAScript standard are ActionScript / JScript. 
However, this distincition is often not made, and JavaScript and ECMAScript are often treated as synonyms. 
CoffeeScript is similar to and compiles down to JavaScript, but has more syntactic sugar/cleaner syntax.
ES2015|ES6

### Things programming languages do especially well

performance|rust

# CompSci

## concurrency

Concurrency is executing multiple things at the same time.

### multithreading

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
While a {{c2::dedicated worker}} is accessible from {{c3::a single script only}}, a {{c2::shared worker}} is accessible from {{c4::multiple scripts}}, even if {{c1::within different windows or frames}}
Because many JS APIs are not {{c2::threadsafe}}, {{c3::Web Workers}} have access to {{c1:: only a limited subset}}

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

A race condition is the condition of a system where the behavior of a system depends on the sequence/timing of uncontrollable events.
A race condition is often a flaw that may cause bugs.

## Programming language implementation

A programming language implementation is a system for executing computer programs written in a given programming language (s). 
There are two general approaches to programming language implementation: interpretation and compilation
While we might talk about {{c2::programming languages}} being {{c1::compiled or interpreted}}, but actually it's {{c3::the relevant implementation}} that is {{c1::a compiler or an interpreter}}.
A {{c1::reference implementation}} is an {{c2::implementation}} of a {{c2::specification}} generally written by {{c3::the creators}} of {{c5::the API/programming language/whatever}} to be {{c4::an example for other implementations}}

TS compiles to JS via the compiler, interfaced with the cli tsc.

$Something that happens during execution   runtime $something
$Something that happens during compiling   compile-time $something

### Types

A compiler translates one programming language into another in one step before execution.
Most commonly, a compiler translates a programming language into machine code/assembler.
An interpreter translates the code into another language (most commonly machine code/assembler) as it goes along.
JIT

#### Transpiling

A preprocessor most typically takes some input and transforms it into some output, often for further use of compilers.
While preprocessors generally don't transform the language, sometimes transpilers are called preprocessors, e.g. in the case of sass.
Babel is a transpiler that transpiles{{c1::newer JS (e.g. ES 2017, ES 2020) to older JS (e.g. ES5)}}

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

### interfaces for implementation

#### Language CLI

most languages have a CLI tool to interface with them, esp. with implementations

lua|lua
node|JS
python, python3|python
perl|perl
sass|sass/scss
rustc|rust

-c STRING|read program from string|python
-e STRING|read program from string|perl

##### REPL

REPL is short for read-eval-print loop
{{c3::REPLs}} are also called {{c1::interactive toplevel}} or {{c2::language shell}}

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

JavaScript is run by a JavaScript engine (e.g. V8, SpiderMonkey), which may differ by browser.
The chrominum javascript engine is v8, d8 is the developer shell for v8

## Boilerplate

Boilerplate code is repetitive code that is reused often, often also implying that it is unneccessary and would be better if it just wasn't necessary.

### document start/end indicators

--- the file ... |YAML (but optional, merely allow multiple documents per file)

# software engineering

Software engineering is term where the definition is often fought over.
Software engineering (roughly) is different from software development/programming in that it emphasizes a more holistic view including tools and processes used for development, and temporally not just the time writing code, but the time before and after too.

## software architecture

Software architecture refers to the fundamental structures of software/development and creating those structures.

### properties

#### coupling & cohesion

https://upload.wikimedia.org/wikipedia/commons/0/09/CouplingVsCohesion.svg
cohesion is the degree to which the elements inside a module belong together.
coupling is the degree of interdependence between software modules.
In general, cohesion is good and coupling is bad.
high coupling generally implies loose cohesion and v.v. 

A god object is an object that violates the single-responsibility principle by knowing too much or doing too much.
The single-responsibility priinciple states that (the implementation of) a thing should only change for one reason.

### solution stack

ME?N = MongoDB, Express.js, ?, Node.js
MEAN includes Angular
MERN includes React
MEVN includes Vue.js

## development practices

Rubber-duck debugging is problem-solving by explaining it out loud to an object or naive human.
functional requirement|function (relation between input and output)|system must do x
non-functional requirement|criteria of judgement, not specific behavior|system shall be x

### development paradigms

#### Agile

#### Scrum

### CI/CD

continuous delivery|software can be deployed on any commit
continuous deployment|software is deployed on any commit
{{c1::Continous deployment}} {{c3::relies on}} {{c2::continous delivery}}
A nightly build is one that is built every night, generally automatically

### code writing enviroments

Integrated development environment   IDE
An IDE is a software development tool that aims to include everything relevant to progragramming in a ceratin language.

## QA

{{c1::wave a dead chicken (over it)}}: To perform a ritual over {{c4::crashed software or hardware}} which one {{c2::believes to be futile}} but is {{c3::nonetheless obligatory so that others may be satisfied that an appropriate degree of effort has been expended.}}

### code review

Code review may be by any other peer or by some authority related to the project (depending on the purpose)
Code review is when another agent analyzes  the source code for bugs/errors/code quality
Code review may be performed by human agents or automated code review tools

### testing

#### things used

A test double is a thing that replaces a production thing in testing

#### types of tests

Unit tests test a unit of code (where that might be a module, function or record).
Unit tests are generally quite fast.
End to end testing tests that with a given input, the program will flow correctly and the correct final state will be reached

## principles

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

### mech pol

the mechanism   what can be done
the policy   what should be done
separation of mechanism and policy.

## documentation

### methods

Self-documenting code is code that uses names of identifiers and strucutre (rather than comments) in such a way that it is easy for a human to understand what it is doing.
In self-documenting code, identifiers indicate what the thing they are identifying does.

### generation

mdBook is a rust crate and command-line tool that produces books from markdown.
mdBook produces books similar to the rust book.
mdBook can easily be deployed to github pages.


## requirements engineering

A {{c1::user story}} is the {{c2::explanation of a feature}} {{c3::from the perspective of the user}}.
Hofstadter's Law: It always takes longer than you expect, even when you take into account Hofstadter's Law.
Parkinsaw's Law: Work expands to fill the available time
The law of triviality was originally developed as a corollary to parkinsons law.
Law of triviality: people within an organization/community/project typically give disproportionate weight to trivial issues.
Most common example of the law of triviality: the choice of materials for a bike shed taking up a disproportionate time during the construction of a nuclear power plant.
Bike-shedding is discussion that conforms to the law of triviality: Disproportionate discussion about relatively irrellevant issues.


## Modelling

### UML

UML  Unified Modeling Language
UML is a general modelling language most commonly used in the field of software engineering.

#### class

An UML class diagram generally consists of three parts, a class name on top, member variables in the middle, and member methods at the bottom.
<img src="sm_220px-BankAccount1.svg.jpg">

#### sequence

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


#### object

<img src="sm_paste-7a55c6f447e4be8da11b84f2d660fe36fa529dc8.jpg">
Objects in UML object diagrams at least contain a top field with the object name, the class name or both, often they also contain a field below that for instance varaibles

## toolchains

In general, a toolchain is a set of software tools used to do something.
In software development, a toolchain is a set of tools used in combination to develop and deploy software.
A task runner is used to run predefined tasks, which would otherwise be tedious or impossible.

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

#### package manifest

A package manifest (though different languages call it different things) specifies metadata and config for your package/project as well as dependencies.
In most package managers, besides the place where you specify your dependencies, there is also a lockfile.
While the package manifest or wherever is where you specify the versions of your dependencies you accept, the lockfile specifies the versions which are actually installed.

Cargo.toml|cargo
package.json|npm|yarn

package manifest top-level keys
dependencies|specify dependencies|Cargo.toml|package.json
package|general package information|Cargo.toml

package-lock.json|npm
Gemfile.lock|bundler

#### repositories

A repository is anything that stores software.
Often, a repository either stores the code of a VCS, or packages of a certain type.

### build tools

Build tools are the tools that create an executable application from source code.
A bundler is a tool that merges together all your JavaScript code and its dependencies into one js file, most commonly known as bundle.js
A bundler is a type of build tool.
There are more JS build tools than you can shake a stick at. The most common is webpack.
webpack-cli is the command for administering webpack

### contaienrs

Containerization isolates software from the rest of the environment it lives in, allowing interaction only through limited, specified channels.
A container often also includes software's dependencies within the container.
An application being contained in a container is said to be containerized.
Containerization improves security and portability.
Containerization is the standard for most mobile operating systems.
Containerization may limit functionality and increase size (since dependencies cannot be shared)

### mapping

different tools may perform one or more roles within a toolchain.

In latex the package manager is part of the tex distribution
The two most common latex distributions are {{c1::TeX Live}} and {{c1::MiKTeX}}
Anaconda is a batteries-included distribution of Python and R and a bunch of associated packages for scientific computing.

Most commonly, the CLI for a framework will also be a build tool.

cargo is the package manager and build tool for rust.
the official package repository for cargo is crates.io
There is no official task runner for rust, but one commonly used is cargo-make.
npm is the most common package manager for JS, followed by yarn. 
The official package hub for npm is the npm Registry.
npm scripts works as a task runner for JS.
pip is the package manager for python.
The official package hub for pip is PyPI.
The package format for python format .whl ('wheel')
apt is the package manager for Ubuntu.
In the past, one would have used apt-get as a way to interface with apt (but now deprecated).
PPA = Personal Package Archive
PPAs are repositories for apt pacakges that contain packages not dealt with by the official distro maintainers.
to add/remove other repositories with apt use add-apt-repository (--remove for removing)
dpkg is a package manager for .deb packages, but does not have a package repository, instead requiring you to download your packages yourself.
apt uses dpkg in the background.
homebrew (command: brew) and macports (command: port) are package managers for macos.
homebrew can also be used on linux, and is written in ruby.
ruby has two package managers, bundler, which mostly does dependency management, and RubyGems with the command gem which mostly does installation.
In ruby, packages are called gems.
The official package hub for RubyGems is rubygems.org
tlmgr is the package manager for tex if you are using the TeX Live distro.
The official package hub for tex is CTAN.
conda is the package manager for the anaconda software distribution.
metro is the bundler for React Native.
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
snap has a second linux file system in /snap/core, which it mounts in specific places at runtime




tap TAPNAME|add a repository|brew




bundler is kinda weird, since it is a ruby gem itself.
bundler manages the gemfile 
The gemfile contains dependencies
the gemfile is just a ruby file
In a gemfile, the first thing is a call to source, which establishes the global source
source is also a method which takes an url as the first and a block as the second argument if you want to establish additional sources
within the gemfile, gem dependencies are defined by `gem <name>, <version>`

tools to interact with framewokrs

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

# Misc/no place yet

most languages allow an arbitrary amount of spaces and tabs as indentation, YAML however only allows spaces

## Indexing

Most langauges I know start linear collection indices at 0, however lua starts them at 1
In most languages, providing negative indices counts from the back, with -1 being the last element.
Square bracket notation: most commonly used for array/linear collection indexing or accessing members in associative collection, esp. if primitives in language. SCSS/Sass is special in that maps are primitive in the language, but neverthelesss square bracket notation does not work, one must use map-get() (also not map.get, which its documentation still falsely refers to)
any key in a table lua, Ruby, JS, Py, Rust
In most languages, indexing a linear collection outside of its bounds produces an error, in JS it merely produces undefined
In most languages, referring to an associative array element that doesn't exist will get you an error, in Lua and JS you merely get undefined
TS changes referring to a lin col index outside of bounds or a nonextand assoc arr element to an error
JS allows indexing strings via the charAt method.

Dot notation {{c1::object}}{{c1::.}}{{c1::member}}
dot notation: TOML also 
string keys of tables lua
members of objects in lua
but: not method calls, use : instead
In Rust, of the collection types, tuples are accessed via dot notation, an arrays are accessed via square bracket notation

While JS will not error if you try to access a key or index that is nonexistant, it will return undefined, and if you then try to access something of undefined, it will return an error.
In JS, the ?. is called the optional chaining operator.
In JS, the optional chaining operator works like dot notation, except that if used on a nullish value, it will short-circuit and return undefined.
the optional chaining operator short-circuiting to undefined when after something that is nullish prevents attempted indexing of something nullish, which would otherwise cause an error.
The optional chaining operator can be used instead of dot notation, and before [] notation or method calls.

## Project Jupyter

Jupyter notebooks are multimedia documents.
Jupyter notebooks can contain code, markdown test, math, plots, media/images.
Code within Jupyter notebooks are run by kernels.
There Jupyter kernels for a bunch of different programming languages.
The python kernel for Jupyter notebooks is the ipython kernel.
Jupyter notebooks are in fact implemented via json files.
The file type of {{c1::jupyter notebooks}} is {{c2::.ipynb}}
The Jupyter Notebook App is a server-based application that allows editing and running notebook documents via a web browser.
The Jupyter Notebook App can be executed locally or can be installed on a remote server and accessed through the internet.
Jupyter Notebooks can be edited using many different programs, e.g. the official Jupyter Notebook App, but also VSCode
The thing managing all the Jupyter stuff is Project Jupyter




## misc

https://en.wikipedia.org/wiki/Type_theory#History

Associative arrays: names, literals, other construction methods, etc.



## Metacharacters & escapes 

A metacharacter is a character that has a special meaning to a computer program, such as a shell interpreter or a regular expression (regex) engine.

An escape character is a metacharacter that invokes an alternative interpretation of the following character(s)
An escape sequence is the combination of an escape character and the subsequent characters that has a specific meaning.
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




§§ HTML has ((c:1;::two ways)) of specifying ((c:2;::character escapes)). ((s:gb;::Both ((c:3;::start with an &amp;)) and ((c:4;::end with a semicolon ;)). They are both often used to ((c:5;::display reserved characters, invisible characters, or hard-to-type characters.))))  §<br>
§§ Of these, ((c:6;::numeric character references)) ((c:7;::refer to the character position within character set (most commmonly UTF-8))), ((s:gb;::they start ((c:8;::with # (after &amp;))) and can be specified in decimal or hex. ((h:gb;::(for example ((c:9;::&amp;#8203;))))))) §<br>
§§ ((c:10;::Character entity references)) ((c:11;::have a short, memorable name)) ((h:gb;::(for example ((c:12;::&amp;amp; or &amp;quot))))) §<br>
§§ This distinction is however often not made, and often ((c:13;::any name that is a combination of some of the name parts (e.g. HMTL entity, entity reference, character entity))) are used. §<br>

<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th>Character entity reference / Numeric character reference</th>
    <th>Displays as / creates?</th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr>
      <td>((c:16;::&amp;gt;))</td>
      <td>((c:17;::&gt;))</td>
    </tr>
    <tr>
      <td>((c:14;::&amp;lt;))</td>
      <td>((c:15;::&lt;))</td>
    </tr>
     <tr>
      <td>((c:18;::&amp;amp;))</td>
      <td>((c:19;::&amp;))</td>
    </tr>
    <tr>
      <td>((c:20;::&amp;shy;))</td>
      <td>((c:21;::A hyphen that works as a line break, but is only displayed when necessary for wrapping.))</td>
    </tr>
    <tr>
      <td>((c:22;::&amp;#8203;))</td>
      <td>((c:23;::A zero-width space that allows the browser to break there, when necessary))</td>
    </tr>
  </tbody>
</table>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}</span>

## text encoding

Text encodings (simplified): Morse -(early 1900s)-> Baudot-Murray -(1960s)-> ASCII -2000ish-> Unicode

### Morse

### ASCII

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

CRLF|Windows|The Internet
LF|Unixlike (Linux and modern mac)
CR|older macs

The bell character is sometimes used in command-line utilities for a notiification sound

### ISO/IEC 8859

The ISO/IEC 8859 encodings are based on ASCII but take up 8 bits instead of 7, with the extra 128 characters occupied by code pages for different languages

Garbled text due to character encoding errors is called <ruby>文字化<rp>(</rp><rt>もじば</rt><rp>)</rp></ruby>け, which was common in japanese due to a number of incompatible encodings existing.

### Unicode

Unicode is goverened by the unicode consortium.
While in encodings such as ASCII, a character is equivalent to a series of bits, in Unicode a codepoint is an abstract unit that can be realized in different encodings.
The fundamental unit in unicode is a codepoint.
All unicode codepoints are contained in the unicode codespace.
Currently, about 12% of the unicode codespace is used.
The unicode codespace consists of 17 planes. 
A unicode plane contains 2^16 = 65536 codepoints.
0|Basic Multilingual Plane|contains the most common unicode characters, such as most writing systems & symbols
1|Supplementary Multilingual Plane|assortment of different characters and emoji
2|Supplementary Ideographic Plane|bunch of extra, mostly historical/variant CJK characters
3|Tertiary Ideographic Plane|bunch of extra, mostly historical/variant CJK characters
4-13|Currently unassigned
14|Supplementary Special-purpose plane
15-16|Private Use Area planes
A plane in unicode consists of one or more blocks.
Since unicode blocks are contained within planes, they at most can be the size of a plane, i.e. 2^16=65536
Unicode blocks always sized in multiples of 16, therefore the first hex digit in an unicode block will always end 0, and the last digit will always end F.
Unicode blocks are always contiguous and disjoint with each other.
In general, an unicode block should be united by a common purpose in some way.

#### multiple characters

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
Unicode normalization takes two texts that are canonically equivalent or compatible and reduces them to the same sequence of codepoints.

#### encodings

There are three main unicode encodings: UTF-32, UTF-16 and UTF-8
UTF-32 encodes any codepoint as 4 bytes, and is thus very wasteful for something like latin text.
UTF-16 encodes a codepint either as 2 or 4 bytes.
UTF-8 may take 1-4 bytes to encode a cahracter.

Today, most things default to UTF-8, however a few things such as JS default to UTF-16.

##### UTF-8

UTF-8 encodes the 128 ASCII characters the same way as ASCII, but with a leading zero (since 8 not 7 bit)
First UTF-8 byte starts|character contains n bytes
0|1
110|2
1110|3
11110|4

##### Percent

(near) synonyms: {{c1::Percent encoding}}, {{c2::URL/I encoding}}

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

Case-preservation is whether something {{c1::stores or disregards case information}}
Case-sensitivity is whether something {{c1::differentiates based on case}}

## more misc

A bricked device is one that no longer can function at all (has become as useful as a brick)
SKU|Stock Keeping Unit
An instance is something that has been created on some sort of model.

## placeholder images

Placeholder images using kittens   placekitten.com
Placeholder images using boring boxes   via.placeholder.com

via.placeholder.com/{{c1::width}}[{{c2::x}}{{c3::height}}]
placekitten.com/{{c1::width}}{{c2::/}}{{c3::height}}

## non-humans

### robots

#### SEO

related to navigation, google will reward a site that has a navigation that is {{c1::sensible}}, uses {{c2::text (or e.g. aria tags)}}, but {{c3::does not go overboard in its complexity}}

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
