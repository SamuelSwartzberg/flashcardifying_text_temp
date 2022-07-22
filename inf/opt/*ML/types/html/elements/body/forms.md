# forms

Form-associated content is a subset of flow content comprising elements that have a form owner, exposed by a form attribute, and can be used everywhere flow content is expected. A form owner is either the containing ‹form› element or the element whose id is specified in the form attribute.

‹button›
‹fieldset›
‹input›
‹keygen›
‹label›
‹meter›
‹object›
‹output›
‹progress›
‹select›
‹textarea›

Form-associated content does not necessarily always have to be within a form.

This category contains several sub-categories:

listed
Elements that are listed in the form.elements and fieldset.elements IDL collections. Contains ‹button›, ‹fieldset›, ‹input›, ‹keygen›, ‹object›, ‹output›, ‹select›, and ‹textarea›.

labelable
Elements that can be associated with ‹label› elements. Contains ‹button›, ‹input›, ‹keygen›, ‹meter›, ‹output›, ‹progress›, ‹select›, and ‹textarea›.

submittable
Elements that can be used for constructing the form data set when the form is submitted. Contains ‹button›, ‹input›, ‹keygen›, ‹object›, ‹select›, and ‹textarea›.

resettable
Elements that can be affected when a form is reset. Contains ‹input›, ‹keygen›, ‹output›,‹select›, and ‹textarea›.

## form itself

A ‹form› element represents a form.
the method attribute of form accepts post|get|dialog.
post/get|use the POST/GET methods
// for dialog see ‹dialog›
The action attribute for form specifies the URL to which the form should be submitted.
Forms may not be nested.

## fieldset

A ‹fieldset› is an HTML element used to group multiple inputs (and their labels)
The first child of a fieldset may be a ‹legend› (this is the only place it may appear), which captions its parent fieldset

## button

The ‹button› HTML element represents a clickable button
the type attribute for ‹button› represents the default functionality
submit|submit form data to server
reset|reset form data
button|no default behavior, must manually be implemented

A button should have text content, or if not, it needs to be specified by aria-label

## textarea

textarea represents a multiline text input field
textarea is not an empty element, and in fact the content can be used to provide a default value.

## label

A ‹label› provides a caption/label for a thing, most commonly an ‹input›
There are two ways of associating an ‹input› with a label, either nest the input within the label, or set the for attribute of the label to the id of the input.
Any input should have exactly one ‹label›, or alternatively a non ‹label› referred to by aria-labelledby

## input

specifying the value property of an input element in HTML sets its initial value.
As the state of ‹input›s changes, the value property in JS is updated.
The validation states of an input are contained in the ValidationState API and corresponding property./

### types

type="color" for colors
type="hidden" does not show the control, but still submits the data.

#### radio ＆ checkbox

A radio button is a graphical control element that allows the user to choose only one of a predefined set of mutually exclusive options. 
In HTML, a radio button is realized by ‹input type="radio"›
In HTML, multiple radio buttons are linked by assigning them the same number.
radio and checkbox input accept the attribute checked to specfiy if they are checked


Bootstrap:

.form-check # set of radio buttons
.form-check-label   define a label for a checkbox/radio button
.form-check-input   define a checkbox/radio button

#### text

‹input type="text"› is single-line only
There are a set of input types that act similarly text, but force a certain type of validation and change the soft keyboard/add input helpers, similar to inputmode:
time-related: date, datetime-local, month, time, week
number: number
other: email, password, tel, search, url
On any text-like input which is not time-related and not 'number' as well as on textarea, you may specify the minlength and maxlength attributes to contstrain the amount of UTF-16 code units.
On any non-time-related, non-number text-like input, you may specify the attribute `pattern`, providing a regex against which to match the input.
most text-only input fields may have the readonly attribute specfied, which shows the inital value but doesn't allow the user to modify it
the time-related and number text-like inputs plus range accept a step argument.

#### file

inputs of type file accept an attribute accept (lol) which takes a CSL of unique file type specifiers
an unique file type specfier is either a filename extension starting with a period, or a valid MIME type.
valid for the file input type only, the capture attribute defines which media—microphone, video, or camera—should be used to capture a new file for upload with file upload control in supporting scenarios.
input type file return a `FileList`, which is a linear collection of `File`s

#### image

Input type image supports the attributes ‹img› supports, in addition to the usual ones of input.
When clicked, input type="image" behaves like submit, but also sends the coordinates of the area being clicked.
The coordinates of an input type="image" will be submitted as ‹name›.x=‹coord›＆name.y=‹coord›

#### submit

### attributes

the boolean multiple attribute may be set on input type email/file and ‹select› elements.
When the multiple attribute is set for input type email, emails are separated with the comma.
Any input may have a form attribute to associate it with the id of its form owner.
The list attribute of most text-like input types plus range and color accepts an id of a ‹datalist›, which represents a list of predefined values.
The ‹datalist› HTML element contains a set of ‹option› to indicate a predefined value each.
For most input types, the value attribute merely indicates an initial default, for input type radio/checkbox/image, the value attribute specicifies the value that will be sent if that thing is checked
A checkbox or radio button with no value property will be sent as name=on.
Radio buttons/checkbox inputs are only sent if they are checked.
In a form, the name attribute becomes the key that the value being sent is associated with
If the name of a thing in a form is not specified, the value is not sent.
autofocus
A Boolean attribute which, if present, indicates that the input should automatically have focus when the page has finished loading (or when the ‹dialog› containing the element has been displayed).

# formlike but not limited to forms

## select, option

The ‹select› HTML element represents a control that provides a menu of options:
The ‹option› HTML element is used to define an item contained in a ‹select›, an ‹optgroup›, or a ‹datalist› element. 
The ‹optgroup› HTML element creates a grouping of options within a ‹select› element.
to set the default option, specify the selected attribute on the option.

By default, ⟮html `‹select›`⟯s will usually ⟮display as as a dropwdown⟯, and only ⟮become a list box⟯ if `⟮multiple⟯` (⟮allowing multiple selection::purpose⟯) or `⟮size⟯` (⟮specifying how many items to show at once::purpose⟯) is specified‹/span›

## output

The ‹output› HTML element is a container element into which a site or app can inject the results of a calculation or the outcome of a user action.
‹output› are often used within forms, however tehy are not submitted with the form.