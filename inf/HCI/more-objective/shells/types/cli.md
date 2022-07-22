# CLI

A command-line shell/interface is a type of shell (in the wide sense, it is decidedly not a type of shell in the sense of the interpreter such as bash, csh) where actions are accomplished by entering commands.
The shell living within the terminal is interacted with via a CLI, but so does e.g. vim, or various cheat consoles in games.

## syntax

There seem to be roughly two kinds of CLIs, ones that do most of their stuff via --arguments, and ones that do most of their stuff with a sentence-like syntax.
CLIs that have a sentence-like syntax have (after the command that indicates this is what we're interfacing with, perhaps roughly equivalent to a vocative) a syntax consisting of ‹verb(s)› and ‹object(s)›
The most common forms a sentence-like cli syntax takes on is either a ‹addressee› ‹object› ‹verb› {‹objects›} syntax or a ‹addressee› ‹verb› ‹object› {‹objects›} syntax
topic-object-verb-object CLIs
gh|github|gh issue view 12
nmcli|NetworkManager|nmcli con add type ethernet ...
⟮c1;⟯