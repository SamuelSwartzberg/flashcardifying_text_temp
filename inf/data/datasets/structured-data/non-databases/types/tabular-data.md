
# tabular data file⎵data management⎵

## general

A table/record/field separator is the separator (to be defined elsewhere) for tables/records⎵table⎵/fields.

## *sv

### basics

tsv/csv/asv/usv =short for=> tab/comma/ascii/unicode-separated values
*sv = any of tsv/csv/asv/usv
*sv are formats for tabular data file⎵data management⎵s.
The ⟮first line⟯ of *sv files may be ⟮a header⟯. 

### tsv/csv

tsv/csv record separtor = EOL (to be defined elsewhere)
tsv/csv field separator = an arbitrary character, but generally tabs/commas
In tsv/csv, wrapping a field in double quotes allows the field separator to exist in the fields, where then double quotes are escaped by double double quotes
For tsv/csv, trailing record separators are ignored, trailing field separators produce empty fields

### asv/usv

#### separator control characters

The separator control characters are four encoded characters (to be defined elswhere) encoded in ascii and thus unicode.
The separator control characters occupy ascii 28-31.
file/group/record/unit separator⎵encoded⎵ =syndef= separator control character 28/29/30/31
group and unit separator⎵encoded⎵ are in fact mostly meant as table and field separator.
file/group/record/unit separator⎵encoded⎵ =short=> FS/GS/RS/US

#### asv/usv

asv/usv record・field separator = ø/unicode control picture of record・unit separator

## viewers

tidy-viewer is a FOSS rust-based csv viewer 
-s ‹char›|delimiters