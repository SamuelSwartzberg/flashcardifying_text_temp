
# errors

Some languages distinguish between recoverable and unrecoverable errors.
recoverable errors e.g. not finding a file, unrecoverable errors e.g. stack overflow
Java and C# call recoverable errors exceptions and unrecoverable errors errors.
It can make sense to catch recoverable errors, but it is generally impossible to catch unrecoverable errors

## types

Errors can on one level be divided into ⟮syntax⟯, ⟮static semantic,⟯ and ⟮logic errors⟯.

A syntax error is an expression which violates the syntax of the language (will be detected during syntax analysis)
forgetting a parenthesis
A static semantic error is an expression which is syntactically correct but semantically meaningless. (will be detected during semantic analysis)
3/"kawaisa"
A logic error is an error where the program runs without problems, but produces an unintended result. (will only be detected on running the program, generally)

Based on when they occur, we separate compile-time and runtime errors

## error handling

### throwing errors

Generally take an expression as arg.

keywords
die|perl
throw|JS|Java|C#
error()|lua
@error|SCSS?Sass
raise|Ruby
panic!()|Rust

for rust, panicking is throwing an unrecoverable error

### error handling control structures

most commonly: try ‹block› catch (‹error-specifier›) ‹block› finally ‹block›
In Ruby begin ‹block› rescue (‹error-specifier›) ‹block› ensure ‹block›
Rust is notable for not having any error handling of this kind.
In general, having a try and either a catch or a finally block is necessary for the construct to be syntacitcally correct.
In JS, the ‹error-specifier› for catch was necessary until ES2019, and has been optional since

### assert

Assertions are predicates that deliberatly crash the program if the predicate is false.
Assertions are generally used when something should be logically impossible to be false, and thus aren't handled by error handling.
Assertions are typically only used during development.
Rust implements assertions via macros.
rusts ⟮assert_eq!⟯ macro tests wheter ⟮two expressions are equal⟯ (using the trait ⟮PartialEq⟯), and ⟮panics if they are not⟯
rusts ⟮assert!⟯ macro tests whether ⟮something is true⟯, and ⟮panics if it is not⟯
