# tables

table › tbody/thead/tfoot (optional level, but if used, any tr must be within it)
tbody/thead/tfoot › tr
tr › th/td

caption  optional child of table

to make a td/th occupy multiple columns/rows, use colspan/rowspan="‹integer›"
HTML tables are for tabular data, not for layout

The ‹colgroup› HTML element defines a group of columns within a table, e.g. for styling.
The ‹colgroup› is made up of ‹col› elements
The ‹col› element takes a span attribute indicating how many columns are being targeted.
The ‹colgroup› element must be the first child of ‹table› (besides ‹caption›, if it is present)