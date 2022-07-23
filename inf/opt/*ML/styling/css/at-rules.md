# at-rules

## nested at-rules

### @font-face

@font-face defines a font face for use within the document.
@font-face takes at least a font-family: foo, which is the name we will use to refer to it, and a src, which provides the file for the font itself.
@font-faces src syntax: (‹font-face-name›|‹url› [format(‹string›)]) {‹url› [format(‹string›)]}
font-face-name: local(‹string›) # where the string is the name of a locally-installed font.
calls to local() for @font-faces src should go first since if it finds the font locally, it does not have to load it fron the URL.
for @font-faces src, the first call to local() or url() that is usable will be used.
For the @font-face src call, the format() function takes a string specifying the format of the font, where the font will only be loaded if the browser supports that format.
for @font-face, since you're specifying fonts and not font-families, for different font-weights and font-styles, you must specify multiple @font-face declarations, and within those, specify which font-weight or font-style this is specifying. Only fonts actually used will be loaded. This does not apply to variable fonts.

unicode-range: some-range will only load the font if the document uses the font for at least one character within the range

### @keyframes

Keyframes at-rule syntax: @keyframes ‹keyframes-name› \{ ‹keyframe-block-list› \}
‹keyframes-name› ::= ‹custom-ident›|‹string›
‹keyframe-block-list› ::= {‹keyframe-block›}
‹keyframe-block› ::= ‹keyframe-selector-list›‹declaration-block›
‹keyframes-selector-list›  ::= ‹keyframe-selector›{,‹keyframe-selector›}
‹keyframe-selector› ::= from|to|‹percentage›

from is an alias of 0% and to is an alias of 100%
Properties that aren't specified in every keyframe are interpolated if possible — properties that can't be interpolated are dropped from the animation.

if you mark something with !important in a keyframe, ⟮That value will be ignored⟯ (since !important can't be used in keyframes)
if you don't provide a from/0% andor a to/100% it will ⟮Animate to/from the elements existing styles⟯
If you specify multiple @keyframes with the same name, ⟮The last one encountered will be used⟯

### @page

@page syntax: @page ‹page-selector-list›\{‹page-body›\}
page-selector-list ::= ‹page-pseudo-class›{, ‹page-pseudo-class›} #maybe it's not a comma? I couldn't find any documentation this
page-pseudo-class ::= :first|:blank|:left|:right
page-body :: ‹page-declaration›;|‹margin-at-rule›
currently supported properties for the page declaration are margins, orphans, widows and break
margin-at-rule = @‹margin-at-rule-name›‹declaration-block›

flex-container:✫page_margin_at_rules.png✫

### @counter-style

@counter-style produces values of type ‹@counter-style›
@namespace is an at-rule that defines XML namespaces to be used in a CSS style sheet.

## non-nested at-rules

@charset "‹charset›"; declares the charset, though this is often unnecessary if UTF-8 is desired, as the browser will assume UTF-8 if no charset decaration is present.
@charset must be the first statement in the document if present.
