
# dictionary-based

## TOML

in ⟮TOML⟯, ⟮the top-level table⟯ starts at ⟮the beginning of the document⟯ and ends before/at ⟮the first table header⟯ 
in ⟮TOML⟯, a ⟮header⟯ looks like ⟮[foo]⟯ 
in TOML, ⟮a header (on its own line⟯) ⟮starts a table⟯ TOML: ⟮standard tables⟯ continue until ⟮the next table (or EOF⟯) 
to ⟮create subtables⟯ via the standard table syntax, you use ⟮dot notation within the header⟯. 
to create ⟮an array of⟯ ⟮standard tables,⟯ you ⟮surround the header with double braces like so: [[header]]⟯ 
TOML also supports ⟮JSON style tables⟯, (though ⟮they use = instead of :⟯), but only if ⟮they do not contain a newline⟯. 
TOML: ⟮fruit.apple.color = "red"⟯ produces ⟮a table named fruit that has a table named apple that has a key color with the value red⟯ 

### toml xdg systemd

INI files inspired XDG desktop files.
XDG desktop files inspired systemd unit files.
TOML was inspired by INI, XDG and systemd unit files.
TOML|Tom's obvious, minimal language

## YAML

YAML|YAML Ain't Markup Language

### Anchors ＆ merge keys

YAML ⟮anchors⟯ ⟮save a reference to a value⟯, which ⟮then can be included in a different location⟯ via ⟮an alias.⟯ 
⟮A merge key⟯ ⟮merges the values of an anchor⟯ ⟮into the current leve⟯l, thus allowing ⟮overwriting some of the values if necessary⟯. 
A YAML ⟮alias⟯ goe⟮s where a value would normally⟯ 
A YAML ⟮anchor⟯ goes ⟮between key and value⟯ 
A YAML ⟮merge key⟯ goes ⟮instead of a key⟯, and ⟮takes an alias as a value⟯. 
⟮c+;＆foo⟯|⟮anchor⟯
⟮*foo⟯|⟮alias⟯
⟮c+;‹‹⟯|⟮Merge key⟯


## JSON

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

## Schema

JSON schemas are schemas for data formats JSON, YAML, etc.
JSON schemas are usually written in JSON, though they can be written in any language that supports it

### top-level keys

title|title for the schema
description|description for the schema
$schema|URL of the version of JSON Schema this document adheres to 
$id|base url for the document, similar to ‹base› in HTML

### child keys

\$ref allows you to refer to another schema to implement the element, rather than definining it here, by passing a JSON pointer.
format|force string to have specific format (e.g. ISO 8061)
format: date|time|datet-time|force string to be a valid date, time or datetime
enum|specify an enum of allowed values 
pattern|specify a regex that the value must conform to
default|specify a default value that should be assumed if a value is missing

in JSON Schema, to specify that there are multiple relevant specifications for a type in the sense of AND, OR, XOR, there are the keywords allOf, anyOf, oneOf

### integration with other languages

to use your ⟮JSON Schemas⟯ as ⟮TS typeings⟯ use the ⟮npm package⟯ ⟮json-schema-to-typescript⟯

## jq yq

jq|process JSON
yq|process YAML ＆ convert to/from JSON
yq -y/-Y roundtrip back to YAML
`yq ⟮‹command›⟯ ⟮‹flags›⟯ {⟮‹file›⟯}`
`yq ⟮-t/--to-type⟯ ⟮yaml⟯/⟮json⟯/...` ⟮outputs the file as the specified file format⟯