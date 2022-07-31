# implementation

A programming language implementation is a system for executing computer programs written in a given programming language (s). 
There are two general approaches to programming language implementation: interpretation and compilation
While we might talk about ⟮programming languages⟯ being ⟮compiled or interpreted⟯, but actually it's ⟮the relevant implementation⟯ that is ⟮a compiler or an interpreter⟯.
A ⟮reference implementation⟯ is an ⟮implementation⟯ of a ⟮specification⟯ generally written by ⟮the creators⟯ of ⟮the API/programming language/whatever⟯ to be ⟮an example for other implementations⟯

TS compiles to JS via the compiler, interfaced with the cli tsc.

$Something that happens during execution   runtime $something
$Something that happens during compiling   compile-time $something

## Types

A compiler translates one programming language into another in one step before execution.
Most commonly, a compiler translates a programming language into machine code/assembler.
An interpreter translates the code into another language (most commonly machine code/assembler) as it goes along.
JIT = Just in time (compilation)
frequently when using JIT as a first step the code is compiled to bytecode
when using JIT, the code(/bytecode) is initially executed by an interpreter, but there is a monitor/profiler that constantly analyizes the code being executed and identifies parts of the code where the speedup gained from compilation or recompilation would outweigh the overhead of compiling that code, and then compiles this on the fly.

### Transpiling

Source-to-source translator/compiler    trans(com)piler
A transpiler compiles one (programming) language into another (programming) language, though the target language is generally not assemly.
A preprocessor most typically takes some input and transforms it into some output, often for further use of compilers.
While preprocessors generally don't transform the language, sometimes transpilers are called preprocessors, e.g. in the case of sass.

### compilers

Object code is the code that the compiler produces, generally machine code.
The object file is the file containing object code.


## Steps involved

1. lexical analiysis/tokenization/lexing
2. sytax analysis = parsing
3. semantic analysis

### lexical analysis

lexical analiysis = tokenization = lexing
Terminology around tokenization/lexical analysis is not always consistent.
Lexical analysis is converting a sequence of characteres into a sequence of lexical tokens.
Lexical tokens have some kind of meaning, relative to the language.
Lexical token is often shortened to just token
Tokens are lexical units/items in linguistic terms.
Tokens have a certain value (a string), and a certain type.
Token types that are common across programming languages are identifier, keywords, operator, literal ...
The analogue of token type in linguistics might be word class/syntactic category/part of speech
Compilers/interpeters store all the identifiers/symbols and info about them in the symbol table.
In the context of compiling/interpreting, identifier/name is a synonym for symbol.

### syntax analysis

### semantic analysis

### compiler optimizations

A compiler optmization is a feature of a compiler that tries to minimize or maximize some attributes of an executable computer program.
Optimization levels are compiler options specifying how much compiler optimizations to apply.
In the GCC C compiler and in Rust, there are four optimization levels, 0-3.
In rust, optimization levels are set via `opt-level'.

#### dead code

Dead code is code which is never or not usefully used.
Unreachable code is dead code which is dead because there is no control flow path that would lead to it.
Dead code elimination is a compiler optimization involving the removal of dead code.
In js, dead code elimination is kown as tree shaking.
unused variables are a type of dead code.
compilers and linters will typically warn about unused variables.
unused variables may be a code smell in that they are mistakenly not used.
in rust, to turn off warnings about unused variables for a certain variable, prefix it with a _.

#### call sites

A call site is the place where a callable unit is called.
Inlining is a compiler optimization that replaces a function call site with the body of the called function.

## interfaces for implementation

### Language CLI

most languages have a CLI tool to interface with them, esp. with implementations

interpreters/hybrid

lua|lua
node|JS (using node)
python, python3|python
perl|perl

compilers

sass|sass/scss
rustc|rust
tsc|ts

-c STRING|read program from string|python
-e STRING|read program from string|perl

by default, TS will ⟮compile⟯ even ⟮if there are compiler errors⟯, since it assumes ⟮you might have a good reason⟯, use --noEmitOnError to disable this.
by default, TS compiles down to ⟮ES3⟯, but you can change that with the ⟮--target⟯ flag

#### REPL

REPL is short for read-eval-print loop
⟮REPLs⟯ are also called ⟮interactive toplevel⟯ or ⟮language shell⟯

For most languages, invoking their CLI tool without arguments will open a REPL, if not
irb|ruby
tss-node|TS
is none|perl
jshell|java
csharp|C# (provided by mono)

Python calls being in the repl interactive mode
the value of the last expression
_|Python

### Shebangs

env (/usr/bin/env) can be passed a comand, in which case it will populate the environment variables (including PATH) and then run command with this environment. 
Using env in the shebang is to get the relevant executable on the path
so in general, you can specify the language of a script by doing 
#!/usr/bin/env language-command

## specific languages

### Python

CPython is the most common and reference implementation for Python.
CPython implicitly compiles Python to bytecode, and then runs the bytecode via an interpeter.
Python bytecode files produced by CPython are .pyc files.

### JS

JavaScript is run by a JavaScript engine (e.g. V8, SpiderMonkey), which may differ by browser.chromium|v8
firefox|spidermonkey
d8 is the developer shell for v8