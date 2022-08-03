# types and languages

type system = ?

## typed and untyped

### basics

A typed/untyped language is a language where at least one of/none of variables and values have type.

### languages

All languages I know are typed except for sh, which is untyped, however bash is at least partially typed.

## type checking

### basics

Type checking is the enforcement of the constraints of types.
A type checker is something that does type-checking.

### static/dynamic/hybrid

Static/dynamic/hybrid type checking is type checking pre or at compile time/at runtime/both.
Static type checking cannot affect the running program anymore.
Something hybrid/dynamic is hybrid if static type checking is supported, and only dynamic otherwise.

### any

A primitive type check is a type check that tests for correspondence with a primitive⎵built-in⎵ type.

### static

#### when?

pre-compile/compile time type checking is static type checking that happens before/at compile time.

#### how?

##### type narrowing

Type narrowing is static type checking which changes the type of a variable to a subtype of that type based on which types could exist in that context.
A type guard is any type check that does type narrowing.
Bottom type narrowing (my term) is type narrowing to produce the bottom type, which happens if type checks require an impossible combination of types. 

### hybrid

#### type predicates




## what typed when how?

### basics

#### type checking when

Dynamic/static typing is when a language uses dynamic/static type checking.

#### what is typed?

Value/variable-typing is when values/values and variables have type.

### derived

Hybrid &lt;whatever&gt; typing features &lt;whatever1&gt; typing in some cases and &lt;whatever2&gt; typing in other cases.
Mainly &lt;whatever1&gt; typing features mainly &lt;whatever1&gt; typing but also some &lt;whatever2&gt; typing.

### relationships

explicit/implicit typing is variable-typing where variable type annotations are specified/not specified.
manifest/latent typing =syndef= explicit/implicit typing
Type inference⎵wide/narrow⎵ is implicit typing ø/in languages that generally use explict typing.






The more statically and explicitly typed a language is, the more cumbersome but the more error-proof and debuggable the language is.
declared/automatic type inference is type inference via a keyword/automatically.

## type indication

### basics

type indication is any information (even if implicit) that indicates the type of a thing.
Type determination is type indication that is mandatory.
Implicit/explicit type indication・determination is type indication・determination automatically/via some manual operation.
Static/dynamic/hybrid type indication・determination is type indication・determination for the purpose of static/dynamic/hybrid type checking.

### type annotation

A type annotation/hint is syntax for explicit type determination/indication.
A value・variable type annotation/hint is a type annotation/hint for a value・variable.
A mandatory・optional type annotation/hint is a type annotation/hint that is mandatory・optional.
^polysemy exists for some of these terms, e.g. Python uses type hint for type annotations

### types

#### type declaration

Type declaration is type determination at the beginning of the lifecycle of something.

#### type change

Type change (my term) is type determination for something that already has a type.
Type conversion is explicit hybrid/dynamic type change.
Type casting is explicit static type change.
Type coercion is implicit hybrid/dynamic type change.

## built-in/non-built-in data type

A built-in/non-built-in data type is a data type which has/does not have built-in language support.
