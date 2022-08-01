# relational data model itself

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

# database

a relational database is a database with a relational data model.
In a relationnship database each n-tuple/row has its own unique key known as the primary key.
A foreign key is a column used in a relational database to link tables/relations by referencing a primary key of a row in a different relation/table.
A child table uses a foreign key to reference a primary key in the parent table. (parent ← child)
Foreign keys can be used for one-to-one or one-to-many relationships

# tabular data

A table is an accepted visual representation of a relation.
TODO revise in light of above info
tsv|tab-separated values
csv|comma-separated values

⟮A table⟯ (e.g. in ⟮database or spreadsheet⟯ contexts) is ⟮a collection/sequence/whatever of⟯ ⟮records⟯. 
⟮A record⟯ is ⟮a collection/sequence/whatever of⟯ ⟮fields⟯, which ⟮each contain an item of data⟯. 
A ⟮record⟯ is ⟮more or less kinda⟯ synonymous to ⟮row⟯. 
⟮Field⟯ is ⟮sometimes used⟯ as a synonym for ⟮column⟯, though following ⟮the above differentiation⟯, this is of course ⟮incorrect⟯. 
⟮csv⟯ and ⟮tsv⟯ both store ⟮tables/tabular data⟯. 
⟮csv/tsv⟯ separate ⟮records⟯ via ⟮newlines (generally CRLF⟯) 
The ⟮first line⟯ of ⟮csv/tsv⟯ may be ⟮a header⟯. 
⟮the csv/tsv header⟯ should have ⟮as many fields⟯ ⟮as the other records in the documents⟯. 

name|separates fields how
⟮csv⟯|⟮with commas⟯, sometimes also ⟮arbitrary different characters⟯
⟮tsv⟯|⟮with tags⟯

Neither ⟮csv⟯ nor ⟮tsv⟯ are ⟮fully standardized⟯, or rather ⟮the specs aren't always followed⟯. 
In ⟮csv/tsv⟯, ⟮wrapping a field in double quotes⟯ commonly allows ⟮the field separator to be included in the field⟯. 
If in csv/tsv ⟮a field is wrapped in double quotes to allow the field separator to be included in the fields⟯, ⟮double qoutes⟯ are then excaped by ⟮double double quotes⟯. 
⟮Trailing newlines⟯ at the ⟮end of documents⟯ are ⟮optional⟯ for ⟮csv/tsv⟯, ⟮field separators⟯ at ⟮the end of the line⟯ will ⟮create empty fields⟯. 

tidy-viewer is a FOSS rust-based csv viewer 
-s ‹char›|delimiters