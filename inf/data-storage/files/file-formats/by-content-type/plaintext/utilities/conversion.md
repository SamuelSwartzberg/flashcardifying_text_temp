# conversion

## pandoc

Pandoc is a haskell-based powerful converter between text-based formats.
By default, pandoc acts as a filter.
Pandoc readers convert documents to an AST.
Pandoc filters modify the AST.
Pandoc writers convert its ASTs to a specific format.
Only features supported by pandoc markdown are guaranteed to survive pandoc conversion

The behavior of some of the readers and writers can be adjusted by enabling or disabling various extensions.
for pandoc extensions, + enables it and - disables it.
pandoc-format-specifier ::= ‹pandoc-format›{(+|-)‹pandoc-extensions›}

-s/--standalone produces valid standalone files such as HTML by adding header ＆ footer material via a specified template.

By default pandoc creates an output pdf by using latex as an intermediary, you can change this behavior with --pdf-engine.