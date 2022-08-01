# non-databases 

A non-database is a dataset molded by a data model not seen as a monolith.

## data files

### basics

A data file⎵data management⎵ is a non-database that is a file.
a &lt;name&gt; data file⎵data management⎵ is a data file whose data structure⎵data model⎵ is &lt;name&gt; data structure⎵data model⎵.

### types

#### tabular data file⎵data management⎵

##### general

A table/record/field separator is the separator (to be defined elsewhere) for tables/records⎵table⎵/fields.

##### tsv/csv

tsv/csv =short for=> tab/comma-separated values
tsv/csv are both formats for tabular data file⎵data management⎵s.
tsv/csv record separtor = EOL (to be defined elsewhere)
tsv/csv field separator = an arbitrary character, but generally tabs/commas
The ⟮first line⟯ of ⟮csv/tsv⟯ may be ⟮a header⟯. 

name|separates fields how
⟮csv⟯|⟮with commas⟯, sometimes also ⟮arbitrary different characters⟯
⟮tsv⟯|⟮with tags⟯

Neither ⟮csv⟯ nor ⟮tsv⟯ are ⟮fully standardized⟯, or rather ⟮the specs aren't always followed⟯. 
In ⟮csv/tsv⟯, ⟮wrapping a field in double quotes⟯ commonly allows ⟮the field separator to be included in the field⟯. 
If in csv/tsv ⟮a field is wrapped in double quotes to allow the field separator to be included in the fields⟯, ⟮double qoutes⟯ are then excaped by ⟮double double quotes⟯. 
⟮Trailing newlines⟯ at the ⟮end of documents⟯ are ⟮optional⟯ for ⟮csv/tsv⟯, ⟮field separators⟯ at ⟮the end of the line⟯ will ⟮create empty fields⟯. 

##### viewers

tidy-viewer is a FOSS rust-based csv viewer 
-s ‹char›|delimiters