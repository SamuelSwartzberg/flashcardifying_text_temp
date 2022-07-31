
# conventions

## commands

most configurable commands are done so by a config file, either at ~/.commandname or XDG_CONFIG_HOME/commandname if following the XDG base directory specification, some also read from a global config file generally in /etc. Some commands also have a file ending in rc for config in those locations, though rc files generally specify commands to run beforehand more than settings.

The unix philosophy says each program should do one thing well and be designed to work together with other programs, most commonly by accepting text as IO.

### common syntax considerations

-o PATH|generally short for/equiv to --out or --output
-O|output to current directory with same name. (curl, wget)
-(-)out, --output PATH|Write the output to a path (presumably, instead of STDOUT). Mac accept some sort of string interpolation, e.g. via C format string|curl, say, youtube-dl
--progress|show an indicator of progress|say
-f THINGY|generally short for/equiv to --file, sometimes also --from or --format
--file FILE|Use the file as input|say
-t SECONDS|Specify a length of caffeination in seconds|caffeinate (macOs only)
-t THINGY|Generally short for --to
-r|generally short for/equiv to --recursive
-R|generally short for/equiv to --recursive|chown
--recursive
-v|generally short for/equiv to --verbose or --version more rarely for --voice
--voice VOICE|speak whaterver with the relevant voice (generally only for things on mac that can use `say` in the background)
--verbose|verbose output
--version|show the version
-h|generally short for/equiv to --human-readable or --help
--human-readable|human readable output
--help|show a short set of info/options, generally shorter than man
-i|generally short for/equiv to --interactive, may also be short for --in-place, --include, --ignore-case/--case-insensitve
--include|
--interactive|prompt before doing something
--in-place|edit in-place, i.e. don't emit an extra file
-n NUMBER|amount of something
-n|generally short for --number
-d|prevent display from sleeping|caffeinate (macOs only)
-s|generally short for/equiv to --set
-u|generally short for/equiv to --unset
--dry-run|show what would happen withou changing anything
-a|show dotfiles or archive mode = preserve various attributes ＆ structures
-E|use ERE instead of BRE (Only where applicable, obv)
--lines|count/specify the number of lines

Options ≈ switches ≈ flags are indicated by hyphen(s) followed by characters
By convention, an option started by a single hyphen is one character long.
By convention, an option started by two hyphens is multiple characters long.
Generally, multiple single character flags can be joined into one: -h -a = -ha
In general, mac only features short flags, while linux also has long ones (this presumably has a deeper reason that I currently don't know)
In general commands that do something from a source to a target (e.g. cp, mv) have the default syntax SOURCE TARGET
⟮c1;⟯
-- normally ends the list of flag arguments and allows you to pass plain arguments


## man

Most CLI commands have a manual page, which can be diplayd with man.
When we want a man entry for a composite command (e.g. git log, jekyll serve), the man entry headword (by convention) is the same, but hyphenated (git-log, jekyll-serve)
The numbers in parenthesis after the names of things (xterm(1), efence(3)) come from sections of the manual
The standard sections of the manual include:
1      User Commands
2      System Calls
3      C Library Functions
4      Devices and Special Files
5      File Formats and Conventions
6      Games et. Al.
7      Miscellanea
8      System Administration tools and Deamons

## pagers

a ⟮pager⟯ is ⟮a terminal program⟯ that ⟮paginates⟯ its input. 
the ⟮default pager⟯ for the terminal is set in the env variable ⟮PAGER⟯. 
`⟮less⟯` is the most common ⟮pager⟯. 




