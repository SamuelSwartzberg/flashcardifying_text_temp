
# shell

the shell is typically the foreground process in a given terminal, but may be the background process e.g. if we're using a TUI.
The shell runs in the foreground of a terminal if its being used interactively.
The shell is a special kind of program.
The shell is the interpreter that executes the commands.
For bash, there are two commands that allow changing settings of the shell, set and shopt.
The difference between set and shopt is that set is a POSIX-compliant command originally from the original bourne shell, while shopt is bash-only.
SHELLOPTS|options set via set
BASHOPTS|options set via shopt

## variants

The first shell, introduced in 1971, was called the thompson shell with the executable sh.
the pwb/masey shell was introduced in 1977 and built on top of the thompson shell, keeping the executable sh.
The bourne shell was introduced in 1979 and also had/has the executable sh.
Today, the executable sh most often is a sym- or hardlink to a different shell, e.g. bash or csh.
csh is a more c-like shell developed from the thompson shell.
tcsh itself is a more advanced version csh.
Today, csh is most often a sym- or hardlink to tcsh.
ash, bash, ksh, and zsh are descendants of the bourne shell.
bash is the shell of GNU, and perhaps the most common shell as of 2020.
bash = bourne again shell

## history

history can be en/disabled via the history parameter of set.
The history list is a list of commands that the shell internally stores.
the HISTSIZE environment variable determines how much of a the history list will be saved on exit.
the histfile stores the command history as a file. 
The path of the histfile is determined by the HISTFILE environment variable.
For bash, the default history path is ~/.pash_history.
the HISTFILESIZE environment variable detrmines the maximum length of the histfile.
When the shell starts up, the HISTFILE is truncated to HISTFILESIZE and then loaded into the bash history list.
When the shell exits, it saves the last HISTSIZE lines of the history list to HISTFILE, either overwriting the contents, or appeding if the histappend option is set. afterwards, the HISTFILE is truncated to HISTFILESIZE.
If the HISTTIMEFORMAT is set, the time stamp information associated with each history entry is written to the history file, marked with the history comment character. 

The HISTCONTROL and HISTIGNORE variables may be set to cause the shell to save only a subset of the commands entered.

The builtin command fc may be used to list or edit and re-execute a portion of the history list. 
The history builtin may be used to display or modify the history list and manipulate the history file.
With no options, history displays the history list with line numbers.

## various features

### The directory stack

in nix, there is a stack of directories called the directory stack.
in nix, you can push/pop from the directory stack with the commands pushd/popd.
pushd not only pushes the specified directory to the stack, but also cds there.
The dirs command shows the contents of the directory stack.
dirs, pushd and popd all take a positional argument +/-‹n›, which do something with the nth directory counting from zero and from the start/end respecitvely
dirs +/-‹n›|display the nth directory counting from the start/end
pushd +/-‹n›|bring the nth directory counting from the start/end to the top of the stack by rotating the stack
popd +/-‹n›|remove the nth directory counting from the start/end from the directory stack (without cding)

## Prepopulated environment variables

PWD|current directory
OLDPWD|directory before last pwd
DIRSTACK|everything on the directory stack
PAGER|set the pager
HOME|user home directory
BROWSER|web browser

EDITOR and VISUAL are shell environement variables ⟮setting the default editors⟯


command prompt is often just shortened to prompt.
The command prompt is one or more characters indicating the command-line is ready to accept input.
The PS‹n› environment variables set the command promt in different circumstances.
PS‹n› exist from 1-4.
PS1|default command prompt
PS2|prompt for following lines for multiline commands
PS3|options for `select`
PS4|execution of shell script debugging trace (whatever that is)
Bash additionally executes the content of the PROMPT_COMMAND just before displaying the PS1 variable.
for PS‹n›, ash supports a set of \ initiated special escape sequences for things such as the time, hostname, number of current jobs etc.

## login shell

A login shell is is the first shell that executes after you `login`.
login indicates to the shell that the shell should be a login shell by prepending the name of the shell with a -, so that $0 will e.g. be -bash, not bash.
-l/--login forces bash to be a login shell (in this case), $0 will not be prefixed with -)
In bash, you can also use shopt login_shell to see if bash is a login shell.
On mac, all interactive shells become login shells, meaning that .bashrc is not ever automatically read.
linux can rely on the login shell startup files being executed since the login shell is started before the OS has become interactive
mac cannot rely on the login shell startup files being executed before the first shell has been opened.

## startup files

pretty much all shells have a set of startup files that they run as normal shell code when starting a new shell.
when bash starts non-interactively, it looks for startup files in the paths listed in BASH_ENV.
when bash starts interactively, which files it reads from depends on if it thinks its a login shell.
if bash is not a login shell, it reads from ~/.bashrc and on some versions of bash also from /etc/bash.bashrc
if bash is a login shell, it reads from /etc/profile, and then exactly one of ~/.bash_profile › ~/.bash_login › ~/.profile
It may be advisable to have one of the files loaded when something is a login shell load .bashrc, to ensure consistent behavior.
When an interactive login shell exits, or a non-interactive login shell executes the exit builtin command, Bash reads and executes commands from the file ~/.bash_logout, if it exists.

There are other files for environment variables that may be read at different times unrelated to the shell: .pam_environment, /etc/environment

## Shell lifecycle

0. The shell may get its input from a file, a string, or the terminal, and splits it into lines.
1. The shell performs history expansion
2. the shell tokenizes the input
3. the shell parses the input into commands
4. The shell performs expansions
5. the shell performs redirections
6. the commands are executed
7. the shell waits for the commands to complete and collects its exit status

since shell syntax (such as filename expansion) are performed far before something like sudo is executed, if you lack permission to see things those things will not work.
To use shell syntax/features with sudo permissions, the easiest way is to create a sudoed subshell (sudo bash -c "command")

### whence commands?

#### interactive shell

Bash uses a simple heuristic to determine if the shell is interactive: (if neither an non-option argument nor -c or -s is specified and error/iput are connected to terminals) OR (-i is specified), it is interactive.
While an interactive shell is meant to read/write to a terminal, there is no guarantee it is in a terminal if you force it with -i.
if a shell is interactive, $- will contain i, and $PS1 will be set (otherwise unset).
Interactive shells have a bunch of unique rules and semantics.

##### readline

An interactive shell will typically use the GNU readline library to allow line-editing of entered commands.
While GNU readline is most commonly used in interactive shells, it may be used in may different places.
GNU readline has both emacs and vi editing modes, with emacs editing mode enabled by default.
The emacs and vi arguments for set allow switching between those two modes.

##### tab completion

compgen generates potential autocompletes for a certain string based on its option

#### noninteractive shell

bash -s|read commands from standard input
bash -c|read commands from following string
shell scripts execute in their own shell by default
Unless you force it, the shell a script will execute in is a noninteractive shell.

### history expansion

history expansion allows us to splice parts of the history list into the current input stream
In history expansion, the line from the history list that is used is called the event.
In history expansion, the parts of the event that are included are the words (broken into words with normal bash tokenization ＆ parsing).
In history expasnion, various modifiers are available to modify words.
history-expansion ::= !‹event-designator›[‹word-designator›]{:‹modifier›}
If the histverify shell option is enabled, and Readline is being used, history substitutions are not immediately passed to the shell parser. Instead, the expanded line is reloaded into the Readline editing buffer for further modification. If Readline is being used, and the histreedit shell option is enabled, a failed history expansion will be reloaded into the Readline editing buffer for correction.
only ‘\’ and ‘'’ may be used to escape the history expansion character, but the history expansion character is also treated as quoted if it immediately precedes the closing double quote in a double-quoted string.
Event designators allow the selection of the event for history expansion.
‹n›|nth command in history list
-‹n›|nth last command from current command
!|last command (synonym for -1)
‹string›|most recent command preceding the current position in the history list starting with string.
?‹string›|most recent command with string before a newline
?‹string›?|most recent command containing string
#|the entirety of the command line as typed so far
word-designator ::= ‹positional-selector›|*|‹integer›*
positional-selector ::= ‹position›[-‹position›]
position ::= ‹integer›|$|^|%
‹integer› corresponds to an index of a word starting at zero
^ and $ corresponding to the first and last argument (not words!)
% corresponds to  first word matched by the most recent ‘?string?’ search

the special word designator * corresponds to 1-$
the special word designator ‹integer›* corresponds to ‹integer›-$

modifiers for history expansion

h ＆ t remove everything from a pathname but the head/tail
r / e remove a suffix .suffix / remove everything but the suffix
p prints the new command but does not execute it
s/old/new/ regex like substitution
(more exist)

indexes for ! for repeating start at 1 for the first command and go from there

### tokenization

to the shell, a word is a sequence of characters treated as a unit by the shell. words are separated by whitespace or the characters ‘|’, ‘＆’, ‘;’, ‘(’, ‘)’, ‘‹’, or ‘›’. (this has nothing to do with IFS)

### parsing (quoting)

since bash allows strings without quotes, double quotes actually perform a function somewhat similar to raw strings/escaping, except that the constructions starting with the metacharacters $, `, and ! still work.
In bash, $'...' treats the contents as raw strings, but allows for C-style escape seuqences.
In bash, $"..." translates the string according to the current locale settings

### Expansion

Expansion is replacing a thing with another thing or things.

Expansions are performed in the order: brace › tilde › parameter › command substitution › arithmetic › process substitution › word splitting › filename expansion › quote removal 

Only brace expansion, word splitting, and filename expansion can increase the number of words of the expansion; other expansions expand a single word to a single word. The only exceptions to this are the expansions of "$@" and $* (see Special Parameters), and "${name[@]}" and ${name[*]} (see Arrays).

#### Brace expansion

Brace expansion is similar to filename expansion, but things expanded to need not exist as files.
Brace expansion is a mechanism for generating strings.
Brace expansion syntax: [‹preamble›]\{(‹comma-separated-strings›|‹sequence-expression›\}[‹postscript›]
comma-separated-strings: ‹string›{,‹string›} 
sequence-expression: ‹start›..‹stop›[..‹step›]
Bash calls its range syntax a »sequence expression«.
a{d,c,b}e results in ade ace abe
For brace expansion, bash generates all string alternatives, separated by spaces.
Since bash does brace expansion before anything else, it can contain other metacharacters, e.g. * or _, but they will be interpeted at the appropriate step later.

#### Tilde expansion

tilde expansion is performed if a word begins with a tilde.
tilde expansion takes an argument that is specified between the tilde and the next /
With tilde expansion, if no argument is given, the tilde will merely evaluate to $HOME
~foo|the home directory of the user with the name foo
~+/foo|$PWD/foo
~-/foo|$OLDPWD/foo
~‹n› as well as ~+‹n›|what would be displayed by dirs +‹n› (ie the nth directory on the directory stack)
~-‹n›|what would be displayed by dirs -‹n› (ie the nth directory on the directory stack counting from the back)

The ‘$’ character introduces parameter expansion, command substitution, or arithmetic expansion. 

#### Shell parameter expansion

While parameter expansion is disabled within '', it works in "", but also in unquoted strings.
In shell parameter expansion, the thing being expanded may be enclosed in curly braces, which is optional in some circumstances, and mandatory in others.
Assinging to a variable does not require the $ character, but referring to a variable is a form of parameter expansion and therefore does.
Bash supports a bunch of fancy parameter expansion features, which all require there to be {} surrounding them.

Within parametere expansion, prefixing a parameter with ! indicates indirection.
Indirection in parameter expansion means that if your parameter expands to another parameter name, it will then recursively expand this (to one level of depth)

Within parameter expansion, * and @ are nearly equivalent.
Within parameter expansion, to refer to an entire array, use arrayname[@/*]
Within parameter expansion, to refer to the special parameters $* or $@, use just * or @.

Bash allows specifying defaults for parameters within parameter expansion.
Bash's three operators for specifying defaults within parameter expasion are :-, :+ and :=.
Bash default for parameter syntax: parameter(:-|:+|:=)default
:- and := within parameter expansion evaluate to the parameter if not unset or null, or to the alternative otherwise.
The difference between :- and := is that :- will leave parameter unchanged, while := will substitute the value of parameter with the default.
:+ is the exact inverse of :-, it will only evaluate to the default if it is not null or unset.

Bash's slicing feature is performed within parameter expansion:
Bash slice syntax: ${parameter:start:length}

Many parameter expansions allow a pattern which is evaluated according to the usual pattern matching rules.

Bash's replacing within string is performed within parameter expansion:
general pattern (replace first instance) ${parameter/find/replace}
//pattern/replace|replace all instance
/#pattern/replace|replace if at beginning of string
/%pattern/replace|replace if at end of string

parameter#pattern get the shortest substring that matches pattern at the beginning
parameter##pattern get the longest substring that matches pattern at the beginning
parameter%pattern get the shortest substring that matches pattern at the end
parameter%%pattern get the longest substring that matches pattern at the end
parameter^pattern test each single character against the pattern, and uppercase the first one that matches
parameter^^pattern test each single character against the pattern, and uppercase all that match
parameter,pattern test each single character against the pattern, and lowercase the first one that matches
parameter,,pattern test each single character against the pattern, and lowercase all that match

parameter@operator do different things with the string depending on the operator
parameter@U|uppercase the string
parameter@u|uppercase the first character
parameter@L|lowercase all characters
parameter@Q|quote the parameter

Getting the length of something is done within parameter expansion: #parameter

#### Command substitution

Command substitution takes a command and replaces it (and the syntax) with its output.
Command substitution is performed in the modern syntax with $(command).
Command substitution is performed in the older, deprected syntax with `command`.
Command substitution may be nested.

#### Arithmetic expansion

Arithmetic expansion evaluates arithmetic and replaces it (and the syntax) with the result.
Arithmetic expansion is performed by $(())

#### Process substitution

Process substitution allws referring to the in or output of another process as a file.
To implement process substitution, bash creates an anonymous pipe with two file descriptors.
anonymous pipes file descriptors start at /dev/fd/63 and count downards
Process substitution runs asynchronously.
‹(command) provides the output of command as a file for further use.
\›(command) provides a 'file' for a command to write to that will be used as stdin for the provided command. 
command1 ›(command2) is equivalent to command1 | command2 if command1 supoorts outputting to sdout
e.g. a command doesn't output to stdout, but just a file
‹() is used more commonly than ›() because it is more common that a program expects multiple inputs as files than that it outputs multiple outputs as files.

#### Word splitting

Word Splitting	  	How the results of expansion are split into separate arguments.
the shell scans the results of parameter expansion, command substitution, and arithmetic expansion, if they did not occur within double quotes, for word splitting.
Word splitting means splitting the things mentioned above into words using $IFS
IFS is a prepopulated environment variable specifying what counts as a word separator.
IFS is used by a number of commands and control structures (e.g. looping) by default.
IFS is short for internal field separator.
The default value of IFS is whatespace.


#### File name expansion

filename expansion expands strings containing wildcards to pathnames.
filename expansion is perfomed using an utility/syntax known as glob.
The process of filename expansion is also known as globbing.
globbing recognizes wildcards.
a wildcard is a character(s) that expand to something else but their literal value.
a word containing a wildcard is known as a pattern

In the file name expansion stage, bash scans each word for a pattern and replaces it with an alphabetically sorted list of filenames matching the pattern.
In the file name expansion stage, bash retains patterns that didn't match anything as-is by default.
nullglob makes patterns disappear if they don't match anything
failglob makes patterns fail if they don't match anything.
When a pattern is used for filename expansion, the character ‘.’ at the start of a filename or immediately following a slash must be matched explicitly, unless the shell option dotglob is set. The filenames ‘.’ and ‘..’ must always be matched explicitly, even if dotglob is set. 
To see what a command will actually get from a file name expansion, you can prefix it with `echo`

wildcard|matches
*|matches 0-n arbitrary characters, excluding directory separators
**|0 - infinity characters, including directory separators
?|matches 1 arbitrary character
@(foo|bar|baz)|one of the options foo, bar, baz
?(foo|bar|baz)|zero or one of the options foo, bar, baz
+(foo|bar|baz)|one ⁑or more⁑ of the options foo, bar, baz
!(foo|bar|baz)|none of the options foo, bar, baz
*(foo|bar|baz)|zero or more of the options foo, bar, baz
[^‹characters›]   one character that is none of ‹characters›
[!‹characters›]   one character that is none of ‹characters›
[aml]   one of the characters a, m, l
[a-m]   one character in range of characters a-m

to activate bash wildcards using (), you have to enable extglob with shopt

.gitignore uses a similar syntax to globbing

#### Quote removal

After the preceding expansions, all unquoted occurrences of the characters ‘\’, ‘'’, and ‘"’ that did not result from one of the above expansions are removed. 

### Redirection

Before a command is executed, its input and output may be redirected using a special notation interpreted by the shell. 

redirecting input [‹n›]‹[＆](‹path›|‹n›)
redirecting output [‹n›]›[›|\|][＆](‹path›|‹n›)

redirecting input opens the file for reading at file descriptor ‹n› (most commonly standard input)
redirecting output opens the file for writing at file descriptor ‹n› (most commonly standard input)
clobbering a file is to overwrite its contents.
redirecting ouptut will clobber by default, unless noclobber is enabled, in which case › must be followed by | to force clobbering
redirecting output will append instead of clobber if › is used instead of ››
if one wants to redirect standard output and error at the same time, there is the short form ＆›‹path› or ›＆‹path›, of which the first is preferred. adding another › appends instead, as per usual.
‹n›‹＆‹n› ‹n››＆‹n› make the first file descriptor ‹n› refer to the same file as the second file descriptor ‹n› is pointing to.
e.g. 1›out.txt 2›＆1  make the file descriptor 1 refer to the same file as the file descriptor 2
‹n››＆- or ‹n›‹＆- close the file descriptor ‹n›.
‹n››＆‹n›- or ‹n›‹＆‹n›- make the first file descriptor ‹n› refer to the same file as the second file descriptor ‹n› is pointing to, and then close the second file descriptor ‹n› (basically a move)
using ‹› instead of ‹ or › opens the file in read＆write mode
using ‹› and ＆ allows one to read from and write to the same file

for redirecting, the ‹n› before the ‹ or › may be the number of any file descriptor, though the standard streams are most common.

1› may be abbreviated › 
0‹ may be abbreviated ‹

if a file is to be used as input to a command, there is often no reason to do cat file | command, since one could also do command ‹ file

### command execution

#### aliases

alias-command ::= alias{ name=vale}
the alias command with no arguments lists available aliases
aliases are only replaced if they are the first word of a simple command.
Aliases have very error-prone semantics, so using shell functions is almost always preferred.
sometimes an extra file bash_aliases is created for storing aliases, however bash does not itself read from bash_aliases so it needs to be sourced from other files.

#### pipelines

the character indicating an anonymous pipe is |
In a general sense, a ⟮filter⟯ ⟮takes some input⟯, ⟮transforms it⟯, and ⟮produces some output⟯.
In shell contexts, filters are combined with anonymous pipes.
Multiple filters combinded by anonymous pipes are a pipeline.
In shell contexts, filters normally recieve their input from STDIN and output it to STDOUT.
Well-behaved programs should operate as filters inf possible.
|＆ is the same as |, but it also outputs its standard error thrugh the pipe.
While they are often called merely pipes, the pipes in pipelines are actually anonymous pipes.
anonymous pipes ↔ named pipes.

Pipes, whether anonymous or named, basically consist of two file descriptors (one read, one write) and a buffer.
pipes are simplex in direction.
The default behavior in a pipe is for the writing and reading ends of a pipe is to exhibit blocking behavior. 
When in a pipeline, the write file descriptor is connected to the stdout of the first process and the read file descriptor is connected to the stdin of the second process.

When the second process reads from the buffer created by a pipe, this is called draining the pipe.

theoretically, any program that reads from stdin should read from terminal input if given no standard input (as cat does), however some programs don't.

##### liquid (semantically appropriate)

Liquid also features filters prominently to transform values, and also uses the pipe | as a separator.
filter name (liquid)|filter action|constraints
⟮date: "formatstring"⟯|⟮date formatting⟯
⟮markdownify⟯|⟮transform from markdown⟯|⟮jekyll only⟯
⟮append: foo⟯|⟮append foo to the string⟯
⟮prepend: foo⟯|⟮prepend foo to the string⟯

#### command search

When the shell encounters something it thinks it is a command, if it does not contain slashes, it first searches shell functions, then builtins, then $PATH, if it does contain slashes, it executes the path as a command. If the execution fails but the file is not a directory, it assumes the file is a shell script and tries to execute it thus.
The environment variable PATH provides a set of locations of where to search for commands.
PATH contains, well, paths, separated by colons.
For anything in PATH we can execute it by just using its name, to execute anything else we would have to use its path.
`⟮which⟯` takes ⟮a string⟯ and ⟮searches⟯ ⟮the PATH⟯ to see ⟮what the path of the binary of this command is.⟯
npx ‹name› allows execuution of a binary ‹name› within an npm project without having to specify a path (e.g. a local version of a build tool or sth.)
npx can also be used to run a specific version of a npm binary.

#### exit status

exit allows you to exit the current (sub)shell, optionally specifying an exit code.
success|0 
some kind of failure|not 0
miscellaneous error|1
(bash builtins) incorrect usage (invalid/missing arguments)|2

## concepts

### Parameters

In bash, a parameter is an entity that stores a value.
In bash (as in other languages), a positional parameter one passed by position (indicated by $1 ... $9)
In bash, there is a special set of parameters that is auto-set.
In bash, a variable is a type of parameter, specifically one denoted by a name.
In bash, a parameter may be indicated by a name (names are the usual type of [a-zA-Z0-9_]), by a number, or by a special character.
In bash assignment statements, only some forms of expansion are performed, specificaly tilde, parameter, command and arithmetic (ergo not brace and filename)
Bash assignmet statements may appear as arguments to the declaration commands
In the context where an assignment statement is assigning a value to a shell variable or array index (see Arrays), the ‘+=’ operator can be used to append to or add to the variable’s previous value.
+= in bash may add, append to array or append to string depending on the context.

Besides the positional parameters, shell has a set of special parameters which are auto-populated, but to which cannot be assigned.
*/@|expands to all positional parameters. They are the same when unquoted, when quoted $* expands to a single word separated by IFS, and $@ expands to separate words "$1" "$2"...
#|amount of positional parameters
?|exit status of most recent command/pipeline (foreground)
$|PID of shell, except in (), where it still has the PID of the shell and not the subshell
!|PID of job in background
0|name of shell or shell script
-|options the shell was launched with

NOT CONTENT JUST STOPPING THE PARSER FROM FREAKING OUT $

### declaration commands

declaration commands = {alias, declare, typeset, export, readonly, local}

declare-command ::= declare {‹option›} {‹name›[=value]}

-f|functions with definitions
-F|functions without definitions
-r|readonly

in bash, declare prints the variables to which a given option applies if no names are given, or applies the option to the given names if some are given.
Thus the declare builtin can be used for a light form of typing.
for declare options, using + instead of - turns off the attribute instead (yes, really)
The typeset command is supplied for compatibility with the Korn shell. It is a synonym for the declare builtin command.
the type command indicates what it would be interpeted as if used as a command name (e.g. is a shell builtin, is a function, etc.).
