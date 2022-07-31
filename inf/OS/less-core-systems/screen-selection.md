# screen selection

slop|queries for a selection from the user and prints the region to stdout
maim|screenshot-taking-utility

slop or maim -s 
-t float / --tolerance=float   How far in pixels the mouse can move after clicking, and still be detected as a normal click instead of a click-and-drag
-t 9 999 999 / --tolerance=9 999 999 (spaces only for readability)   force the selection of a window (by cursor)

maim
-i string / --window=string   cature the desired window (name could be gotten dynamically via various x utilities for example)
-g string / --geometry=string   capture the selected geometry rect