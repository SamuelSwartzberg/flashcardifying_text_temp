# links

The content between the tags should be descriptive of what the link does.

The ‹link› HTML element specifies relationships between the current document and an external resource. This element is most commonly used to link to stylesheets, but is also used to establish site icons (both "favicon" style icons and icons for the home screen and apps on mobile devices) among other things.

The rel attribute defines the relationship between a linked resource and the current document. Valid on ‹link›, ‹a›, ‹area›, and ‹form›, the supported values depend on the element on which the attribute is found.

rel=opener/noopener create a top-level browsing context that is/is not a auxiliary browsing context if the hyperlink would create either of those, to begin with (i.e., has an appropriatetargetattribute value).
rel=nofollow indicates that the current document's original author or publisher does not endorse the referenced document, and thus doesn't confer some of your sites reputation onto the linked sites reputation.
Comment sections may have rel=nofollow by default
rel=noreferrer: No HTTP Referer header will be included. Additionally, has the same effect as noopener.	 

## ‹link›

rel="icon"|specifies an icon representing the current document
rel="stylesheet"|indicates a stylesheet for the document

If rel="icon", the sizes attribute of link specifies which sizes are applicable.
link-sizes-values ::= any|(‹size-spec›{ ‹size-spec›})
size-spec ::= ‹width›(x|X)‹height›

the type attribute of ‹link› specifies the mime type of the resource; however this is generally omitted except for rel="icon"

rel="alternate" indicates that the link is to an alternate version of your site, e.g. in a different language.
if rel="alternate" is linking to a version in a different language, it should have a hreflang of whatever BCP 47 lang code
rel="alternate" indicates a canonical URL for a page, useful if you have multiple urls for the same page and want crawlers etc. to use a specific one.

## hyperlinks

The two elements that create hyperlinks are ‹area› and ‹a›.
use the attribute href for ‹area› and ‹a› to specify an URL of the links target.
The target attribute of ‹area›/‹a› specifies in which browsing context to open the link.
_self|current browsing context
_blank|new window/tab
_parent|parent browsing context
_top|root node browsing context
for ‹form›, the target attribute represents where to display the response after submitting the form  

### a

the download attribute of ‹a› Prompts the user to save the linked URL instead of navigating to it. 
the download attribute of ‹a› Can be used with or without a value.
the download attribute of ‹a› used without a value will prompt the browser to suggest a file type.
the download attribute of ‹a› used with a value will prompt the browser to save it with the specfied name as a prefilled suggestion.