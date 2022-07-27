# editors

a stream editor is a filter used to do text transformations
a line editor is a stream editor that applies its commands to some or all of the lines.
original line editor for linux: ed
ex was a line editor then based on ed.
In contrast to sed, ed → ex could be used both interactively and noninteractively
sed was based of the noninteractive features of ed.
vi was based on the interactive features of ex.
vim is a more-reature rich of vi.
nvim is a refactor of vim which aims to be even more feature rich
nvim = neovim
To a large extent, nvim is backwards compatible with vim
To a large extent, vim is backwards compatible with vi.
vi/vim/nvim is largely mode-based.

sed claims to be a stream editor, but is more specifically a line editor.

sed ‹options› ‹command› {‹file›}
command ::= [‹addr›]‹command-char›[‹options›]
addr ::= ‹int-or-regex›[,‹int-w-op-or-regex›[!]]
int-or-regex ::= ‹int›|/‹regex›/
int-w-op-or-regex ::= ([‹operator›]‹int›)|(‹regex-delim-start›‹regex›‹regex-delim-end›)
regex-delim-start ::= /|\\‹char›
regex-delim-emd ::= /|‹char›

sed command-char|function|options
s|regex
y|char transliteration|/{‹char›}/{‹char›}/|replace any of the first chars with the corresponding char in the second set of chars| transliterate ‘a-j’ into ‘0-9’: 'y/abcdefghij/0123456789/'

sed's y/... command is similar to the standalone program tr.
Ruby and Perl have a string method tr that works similar to sed's y/... / the program tr.

For sed, specifying a regex within an addr selects lines that match the regex
For sed, using the \‹char› syntax as a regex starting delimiter must then continue using ‹char› as a delimiter, allowing one not to have to escape \

nano|basic cmd-line text editor