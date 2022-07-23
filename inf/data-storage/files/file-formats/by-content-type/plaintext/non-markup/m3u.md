# m3u

m3u is a plain-text file format for playlists
m3u merely has a de-facto standard.
There are two variants of m3u, one which is very basic and extended m3u, which allows for directives.
Careless handling of m3u has often lead to security flaws.

m3u-file ::= {‹entry›}
entry ::= [‹path›|‹URL›]‹CRLF›

extended-m3u-file ::= #EXTM3U‹CRLF›{‹entry›}
entry ::= [‹resource-entry›|‹directive›]‹CRLF›
resource-entry ::= (‹path›|‹URL›)[ #‹string›]
directive :: #‹directivename›[:‹argument›]