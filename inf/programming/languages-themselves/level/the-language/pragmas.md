
# Pragmas

In computer programming, a directive or pragma (from "pragmatic") is a language construct that specifies how a compiler (or other translator) should process its input
Perls pragmas have the syntax use ‹name›;
Perls pragma use warnings; causes the perl program to display warnings in certain circumstances.

## Strict mode

Both perl and JS have a strict mode pragma.
Strict mode pragmas cause programs to fail in certain cases.
Start strict mode in JS: "use strict";
in JS, non-strict mode code is called sloppy mode
In JS, modules and classes are strict by default
In JS, strict mode applies to the whole file if it's the first statement if the file, and to the whole function if it's the first statement in the function

Strict mode in JS:
- reserves certain keywords (for future proofing)

## shebangs

An interpreter directive is a type of pragma that specifies which interpreter to use for a thing.
On a unix-like OS, if a script starts with the shebang, followed by a path, this is an interpreter directive, and specifies with which binary to execute the script.
The shebang consists of the characters #!.

## attributes

Attributes are pragmas (mostly) for rust.
attribute begins|applies to
#!|whole crate
#|next item

attributes have four forms for taking arguments (or none)
ø|no arg
= "‹value›"|one arg
\(‹value›{, ‹value›}\)|one or more unnamed args
\(‹key› = "‹value›"{, ‹key› = "‹value›"}\)|one or more named args

rust-attribute ::= #[!]\[‹rust-attribute-name›‹rust-attribute-arguments›\]
rust-attribute-arguments ::= ø|(= "‹value›")|(\(‹value›{, ‹value›}\))|\(‹key› = "‹value›"{, ‹key› = "‹value›"}\)