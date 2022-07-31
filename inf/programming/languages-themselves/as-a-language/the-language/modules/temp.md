
# modules

The main purpose of modules is encapsulation.
A module is as self-contained set of code.
Most commonly, a module is defined by each code file.
In Rust, modules are instead defined manually via mod ‹name› { ... }, or via `mod ‹filename›`
Packages and modules are sometimes synonyms.
conta
In python, a package is a collection of modules (and perhaps other packages).
In python, each .py file is a module.
A package must contain a __init__.py file

If you want to import/export multiple members, most languages have the syntax {member1 [as name1], member2 [as name2], ...}
In some languages, when you're importin multiple members and want to bring the module itself into scope, you can include the keyword for self-reference (this or self) in the list of things to im-/export.
Import/export anything uses * in most languages
in JS, you can only import/export within modules.

## prelude

Most languages have a number of things that are automatically imported. Rust (and haskell) calls this prelude.

## module systems

### rust

Rust allows nesting of modules in a module tree.
In rust, the root node of the module tree is `crate`, sometimes called the crate root.
The crate root serves as the entry point for the rust compiler.
rust allows for both `use`ing/referring absolute and relative paths for the module tree, where absolute paths start at the crate root, and relative paths start at the current module.
Rust's module nesting is defined either directly by nesting `mod ‹name› {...}`s or by a combination of file hierarch and `mod ‹filename›`
calling `mod ‹filename›` without a block argument integrates an existing rust file as a child of the module we're currently in in the module tree, however the file structure must also reflect this.

Rust also allows having multiple crates with independent module trees in the same package.
In rust, there are two types of crates, binary and library.
A package can contain 0-1 library crates and 0-∞ binary crates.
the crate root for binary crates is called main.rs.
the crate root for library crates is called lib.rs

### JS

#### CommonJS

CommonJS is ⟮a module ecosystem⟯ mainly used by node

let/var/const ‹name› = require(‹path›)

#### ES Modules

To contrast with module systems such as CommonJS, the official implementation of modules in JS are known as ES Modules.
In JS, ES Module import/export statements can only be used within a module.
Modules are declared in script tags by adding type="module".

## importing

Import statements tell whatever's executing the program to act as if the specified entities were part of the file, potentially renaming them.
In most languages, you can only import things that were first exported.
In most languages, import statements must be in the beginning of the file.
In most languages, you may only export top-level items.
Import statements have the general syntax
import ‹members› [as ‹name›] from ‹path›
In many systems module/index.‹suffix›  can be imported as just module

### runtime importing

JS supports an import() function that allows dynamic runtime imports.
import() returns a promise.

### in various languages

#### JS

in JS you can leave out `‹members› from` if you only want the side effects

#### python

Python instead has the order from ‹path› import ‹members› [as ‹name›]

#### CSS

In vanilla CSS, you can import other stylesheets via the non-nested at rule @import.
@import syntax: @import ‹path› (‹media-query›|‹feature-query›);
For CSS, the ‹path› may be an ‹url› or a ‹string›

#### rust

Rust uses `use` instead of import.



### SCSS/Sass 

Three keywords: @use, @import, @forward (@include is not an import statement!)
Syntax alwas keyword ‹path› [as ‹name›]
@forward foo doesn't allow the current stylesheet bar to access the things in foo, but ⟮allows anything @using bar to access them.⟯

### latex

⟮\input⟯ and ⟮\include⟯ both ⟮import latex code into the current file⟯. 
⟮\input, \include⟯ are useful if ⟮you want to split up you latex into multiple files⟯. 
both ⟮\input⟯ and ⟮\include⟯ take ⟮a path of the file to import⟯. 
⟮\include⟯ but not ⟮\import⟯ ⟮adds a \clearpage when importing⟯, and thus ⟮can't be used in the preamble⟯ 
using ⟮\include⟯ allows you to use ⟮\includeonly⟯, which takes ⟮an argument⟯ of ⟮a list⟯ and will ⟮only import the \includes listed within⟯, cutting down on ⟮compile time⟯. 

## exporting

Exporting is selecting entities for potential import.
In most languages, exporting is required so they can then be imported.
General syntax: export ‹members› [as ‹name›] [from ‹path›]
re-exporting members is exporting members from a different (generally child) module.

JS allows one default export per module. The default export is the only thing that may be imported without curly braces, and can be renamed without `as`.
JS default exports are funtionality-wise not super useful, but be useful in indicating that it is the most important export / only relevant export.
In JS, non-default exports are known as normal/named exports.
In JS, using the from ‹path› component of exports allows for re-exporting.
JS re-exporting allows aggregating exports in a single file.

In rust, re-exporting works by making a `use` itself public.

In commonJS, exports are declared as properties of the module.exports object.

### default exports
