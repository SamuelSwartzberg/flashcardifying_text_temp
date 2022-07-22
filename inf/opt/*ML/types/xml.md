# XML

## special element types

### PI

PI is short for processing instruction.
A processing instruction is an arbitrary, not further defined instruction to the processor of the XML document.
Processing instructions are mainly used to associate CSS with XML documents.
'Tag name' of the ⟮processing instruction⟯ to ⟮link a stylesheet to an xml document⟯ is ⟮xml-stylesheet⟯ 

#### delimiters

⟮Begins a processing instruction⟯|⟮c+;‹?⟯
⟮Ends a processing instruction⟯|⟮c+;?›⟯

### CDATA

⟮CDATA⟯ is short for ⟮Character data⟯) 
⟮CDATA⟯ ⟮tells the parser not to parse the content as XML markup⟯ 
⟮CDATA⟯ allows us to ⟮use characters with a special meaning in XML⟯ without ⟮confusing the parser⟯, for example, ⟮sb;this would allow us to ⟮include HTML within XML without a problem⟯.⟯ 
⟮CDATA⟯ syntax: `⟮‹![⟯⟮CDATA⟯⟮[⟯content...⟮]]›⟯` 
