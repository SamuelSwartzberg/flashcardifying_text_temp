
# Accessibility

⟮Accessibility⟯ is ⟮designing things⟯ ⟮so as to be usable by people with disabilities (with a variety of bodies⟯)
Accessibility improvements often do not merely benefit the disabled, but also non-human users (e.g. web crawlers and thus SEO), users with different input methods (such as the keyboard)
For accessibility purposes, audio/video should have captions, and lighthouse will chide you if it doesn't

## WAI ＆ WCAG basics

⟮the Web Accessibility Initiative (WAI)⟯ is the W3C initiative supporting accessibility.
the WCAG (Web Content Accessibility Guidelines) are guidelines for web accessibility published by the WAI.
The WCAG consists of principles, guidelines, successs criteria, and techniques.
WCAG principles are the general ideas underlying web accessibility: percievable, operable, undertandable, robust.
Each WCAG principle is broken up into one or more guidlines.
Each WCAG guideline has one or more successs criteria, which are characterized by being testable.
For each guideline and success criterion the WCAG also includes a wide variety of techinques for (better) achieving these.
WCAG techniques may either be »sufficient«, i.e. enough to meet a success criterion, or be »advisory«, which is going beyond the success criterion to better address the guideline behind it. Additionally, WCAG techniques may document common failures.
The WCAG defines three levels of conformance, A, AA, And AAA, for each success criterion.
In some countries websites, especially those of public sector bodies must conform with certain WCAG levels.
the WAI published the WCAG ⟮2.1⟯ version in ⟮2018⟯, and is expected to publish WCAG ⟮2.2⟯ in ⟮2021⟯ 
According to the WCAG ⟮level AA⟯, color should have a ⟮contrast ratio⟯ of at least ⟮3:1⟯ for ⟮large⟯ and ⟮4.5:1⟯ for ⟮normal⟯ text 
According to the WCAG ⟮level AAA⟯, color should have a ⟮contrast ratio⟯ of at least ⟮4.5:1⟯ for ⟮large⟯ and ⟮7:1⟯ for ⟮normal⟯ text 

## WCAG success critera

The text of a link should be descriptive of the purpose of the link, even out of context.

### Non-text content

the alt text should be blank if the image is merely presentational, don't just not specifiy it, or screen readers might e.g. read out the url
iframes and frames should have a title (doing what alt text would do for images)

## WCAG techniques

Based off ⟮the DOM tree⟯, the browser builds the ⟮accessibility tree⟯ containing ⟮all accessibility-relevant information⟯

### Semantic HTML

Semantic HTML is HTML where the tags contain semantic information about the content
Semantic HTML includes elements like ‹article›, ‹nav›, ‹summary›, contrasting with elements like ‹div›, ‹span›


### aria

ARIA attributes fall under the umbrella of WCAG techniques.
ARIA  Accessible Rich Internet Applications
ARIA is mainly realized in HTML attributes.
⟮Where available⟯, prefer ⟮semantic HTML⟯ over ⟮ARIA⟯
ARIA attributes change the accessibility tree, but nothing else.
There are three types of attributes that ⟮ARIA⟯ has: ⟮Roles⟯, ⟮States⟯ and ⟮Properties⟯
ARIA ⟮roles⟯ define the ⟮main type of component⟯, e.g. ⟮toolbar, banner⟯
ARIA ⟮states⟯ define some property ⟮that can change⟯
ARIA ⟮properties⟯ define some property ⟮that is expected to stay the same⟯
There are four types of aria ⟮states⟯ ＆ ⟮properties⟯: ⟮drag-and-drop⟯, ⟮live region⟯, ⟮relationship⟯, and ⟮widgets⟯

the ⟮aria-label⟯ ⟮attribute⟯ is for adding ⟮a text description⟯ of ⟮what something does⟯ where ⟮the actual content doesn't suffice⟯
a reason for using aria-label might be e.g. because a close button is realized ⟮with an icon font/an x⟯