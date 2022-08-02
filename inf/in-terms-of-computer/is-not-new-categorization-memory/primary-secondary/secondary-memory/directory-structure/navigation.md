
# navigation


## traversal

autojump is a tool that remembers which places you've navigated to, and allows quick jumping to the most commmonly used place.
j foo| jump to most commonly used directory containing foo
jc foo|jump to most commonly used **child** directory containing foo

cd|move to specified directory

cd without an argument moves back to your home directory
cd - moves back to previous directory (not parent directory)

### file manager/browser

file browser = file manager
a file manager/browser is a program that provides an user interface for managing files and folders.
mc ("midnight commander"), nnn are TUI file browsers.
Nautilus is file manager for GNOME.

flex-container:✫sm_Screenshot%202020-02-23%20at%2018.08.49%20(1).jpg✫

For ⟮Finder⟯, ⟮whenever you search anything in the top right bar⟯, ⟮a Searching/Find window opens⟯. ⟮hb;To ⟮add filters to the search⟯, ⟮click the small plus in the top right corner⟯. ⟮hb;You can use this to search ⟮pretty much any of the files properties⟯ with ⟮fine granularity⟯.⟯⟯ 

## information

pwd|print path of current directory
tree|print a directory tree
tree -L ‹n›|go to depth n
ls|list file in directory

ls detects if it's in a terminal and outputs with newlines as separators if its not, and with spacing if it is.

-s|display files and directories with their sizes
-S|sorting by size in output
-F|list all files and directoreis annotated with /*@

something/|directory
something@|symlink
something*|executable

exa is a reinplementation of ls in rust with more features and opinionated defaults.

fzf is a shell filter which takes an input of a list of files, allows interactive fuzzy search and selection, and outputs the selection.

du ＆ dust estimate storage usage of files in current directory.
`-d / --max-depth (for du) --depth (for dust)`   only go to the specified depth

realpath gets the absolute path for a file name
basename strips the path and suffix from a file name

### find

find|find files
find-command ::= find {‹global-option›} {‹starting-point-path›} {‹expression›}
If no starting point is specified for find, it takes the current working directory.

-type CHAR (e.g. b, c)   find files that are of one of the 7 unix file types 
-size SIZE   find files that are larger than SIZE
-name foo   find files that contain foo in their name (case-sensitive)
-iname foo   find files that contain foo in their name (case-⁑insensitive⁑)
! expression   true if expression is false 
-printf PATTERN   print the filename according to PATTERN

fd is a simpler and faster version of find implemented in rust.
fdupes finds duplicate files.

### grep

grep is a tool that takes a regex, applies it to a set of files, and prints the lines that match.
There are tons of grep variants:
agrep|grep with fuzzy matches

There are also many alternative variants of grep using more modern regexes, and also significantly faster:
speed: rg › ag › ack

greps exit status if it finds a match is 0, if it does not find a match, it is 1.
grep -c count the produced lines.
grep -v = grep --invert-match
grep -F/--fixed-strings interpet pattern as fixed string, not as regex
`-C NUM/--context=NUM`   show this much context