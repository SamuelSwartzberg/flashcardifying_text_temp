
# values

A literal is a value which is written into the source code as-is and therefore is fixed.

## memory-management

### ownership

In rust, eveary value has exactly one owner.
Owners are variables(/constants).
Moving happens when we assign a value to a different owner and thus the first owner is invalidated.
Assigning a value to a second owner produces a move unless the type implements Copy, in which case it instead calls copy.
Rust says values that are moved when reassigned (= which don't implement Copy) have move semantics, values that are copied (= which implement Copy) implement copy semantics.
A type can implement Copy if all of its components (parts) implement Copy.
In rust, all primitves implement Copy
Assigning as an operation that forces moving includes passing to a function and returning from a function.
When a owner goes out of scope, a value is dropped.

to allow cloning(), implement the Trait `Clone`. This does not change the semantics, since clone() must be called manually

# variables

A variable is an identifier which is associated with a storage location which contains a value.

## declaration and initialization

Declaring something is saying what an identifier means.
In most languages, but not in JS and Python, declaration at the very least fixes the kind of entity the identifier refers to. 
In statically typed languages, declaration generally fixes the data type of an identifier.
To initialize something is to assign a value for the first time.

declaring: var bla;
initializing: bla = 5;
declaring and initializing: var bla = 5;

Trying to read from something undeclared in general produces an error in most programming languages, in sh however it merely produces an empty string.
In JS, a declared but unitialized variable has the value undefined. In most other languages, reading from an unitialized variable produces an error.
In python there is no such thing as variable declaration (however, using a name you haven't used before still creates an error)
Redeclaration may or may not produce an error. In JS, it does not produce an error for var, but does for const and let.

## assignment

Setting a variable/constant to a value is known as assignment.
= is used as the assignment operator in most programming languages
sh is special in its assignment operator, since it does not allows spaces on either side
SCSS/Sass uses : as the assignment operator.
In most languages, assignment expressions evaluate to the value assigned.
Many languages have combinations of their math/string concat and assignment operators to combine these two operations (e.g. +=)

### assigning multiple variables

a, b = 1, 2 (or e.g. returnTwoValues()) (lua, python)

### destructuring

Destructuring is binding variables to values in a way that does not correspond to the 1 variable - 1 value pattern

In many languages, the comma can be used for multiple assignment, most commonly like so:
a, b = 1, 2|Python|Ruby
This is often a form of destructuring under the hood.

[var1, var2] = [value1, value2] or preexisting array|JS|Python|Rust
var1, var2 = [value1, value2] or preexisting array |Python|Ruby
(var1, var2) = (value1, value2) or preexisting tuple|Rust

In general, you can destructure that language's linear collections (esp. if primitive) and iterables.
In JS you can also destructure the assoc array structure.

Destructuring an array(like) requires array delimiters ([]) in JS, python doesn't want any delimiters, and python wants a tuple, which may mean no delimiters or () if needed for nesting etc.
use normal default value syntax to assign default values in array destructuring|JS only
combine spread syntax/splat operator w/ destructuring|JS|Ruby|Python
var1, *var2 = [1,2,3]
[var1, ...var2] = [1, 2, 3];
=› var2 = [2, 3]
Ignore a single value in destructuring
, (e.g. var1,,var2)|JS
_, (e.g. var1,_,var2)|Python|Ruby|Rust

Ignore multiple values in destructuring
*_, (e.g. var1,_*,var2 )|Python|ruby
.. (e.g. var1, .., var2)|Rust
Not possible|JS

nested destructuring
((target, _), _) = [["foo", "bar"], "baz"]|Python
[[target]] = [["foo", "bar"], "baz"] |JS
not possible|ruby

Destructuring can be a cheeky way to swap variables

When destructuring out of assoc arrays in js, this looks like

{nameofkey: nameofvariableyouwantthevaluetoendupin} = {nameofkey: value}
If the nameofkey and the nameovariableyouwantthevariabletoendupin are the same, you can do:
{nameofkey} = {nameofkey:value}

In rust, there is a set of destructuring/pattern matching constructs that can only be used in enums or if let statements.

putting an enum or struct with variable names inside in a match or on the left of an if-let will assign the variables to the values contained within.
e.g. `match { Some(foo) =› ... }` will match Some() containing some value and assign that to foo
e.g. `match { Run{ distance: dist, direction: dir } =› ... }` will match a `Run` and assign its distance field to dist and its direction field to dir.

pattern matching checks if a thing matches a pattern.
In rust, the destructuring syntax is part of the larger idea of pattern matching. (and the syntax that we use for destructuring is a subset of the syntax of patterns)
Many pattern matching things can be used for destructuring (and are the equivalents of the destructuring constructs of other languages).
Beyond or at the same time as destructuring, pattern matching is used for match and if let conditions. 
In rust, patterns can either be
refutable|pattern can fail to match|Some(x) (does not match if value is not Some)
irrefutable|pattern cannot fail to match

match is a conditional that uses pattern matching for its conditions, and forces checking to be exhaustive.
Rust of the languages that I know has a match conditional (using the keyword match). Of the languages I don't know, the ML family and functional languages have match conditionals.
in rusts's match, condition and expression are separated =›

pattern1 bar pattern2|pattern 1 or pattern 2

Within rust pattern matching/destructuring, we even can destructure a thing out of a reference: let ＆foo = somereference

## sigils

In programming, a sigil is a symbol(s) affixed to a variable name.
Sigils are generally used to show that something is a variable, show its type, or ts scope.
In perl
\$|Scalars
@|Arrays
%|Associative Arrays (Perl calls them Hash)

In ruby
\$|global variables
@|instance variables
@@|class variables

In sh, $ is a sigil-like used for various kinds of expansion
In SCSS/Sass, any variable requires teh $ sigil
 

## constants (and not)

Mutability is whether something can be changed after inital creation. Something is mutable if it can be changed, and immutable if it can't.
Different things can have mutability: Objects, variables, (though generally not primitves).
Some languages make a difference in which keywords are used to declare constants and variables.
Constants are immutable, while variables are mutable.
In most languages, constants are written in all upper case.

Keyword for constants:
const|JS|Rust
final|Java

Keyword for variables:
let|Rust

In rust, even variables are immutable by default, and the keyword mut makes them mutable, the difference to consts being that consts cannot be declared mutable.
Rust requires its consts to always be type annotated.
In JS, consts are always block-scoped.
In some languages (JS), consts must be initialized in the same statement as they are declared.

The term magic number or magic constant refers to the anti-pattern of using numbers directly in source code. 
Instead of magic numbers (the antipattern), one should instead use constants.

## default variables

In Perl there is a special variable $_. There are many places in programming language Perl where if you do not explicitly specify a variable, the variable will be used $_. There are key words that read the values from this variable, and there are those which set of values in this variable. (also sometimes exists as @_ and %_)

# (data) types

A null pointer/reference/type/value indicates that we're not referring to a valid thing
Datatypes implemented in a programming language can either be scalar or compound/composite
Bash is fun in that it does not have data types at all, in truth all values are strings

To clamp a value is to specify an upper and a lower bound, and keep the number within those values.

## primitives and composites

Primitive may also refer to a type that has built-in language support.

#### primitive types in different languages

C#: int, float, bool, string, char, double
Java: byte, short, int, long, float, double, char, String, boolean
JS: Number, boolean, null, undefined, string, object, array
Rust: 
  scalar: integer, floating-point numbers, booleans, chars
  nonscalar: tuple, array
Python: integers, floats, complex numbers



## type Systems

A (data) type consists of a set of values that something with that type can assume.
In implementation, each value of a type has a unique (within the type) binary representation.
Typing can also be understood as how to interpret a series of bits.

### dynamic vs static typing

### type inference/manifest

Type inference in C#: var 
in TS and Rust, often type inference is possible automatically 
Type inference in TS/Rust is more likely to work for anonymous functions
In languages with manifest typing, variable declarations require typea annotation.

(literal) type widening is the fact that TS will infer a primitive type and not a literal type for literal values.

Often, when rust can't infer the type, we need to use turbofish notation ( :​:‹type›)

#### const assertions

In TS, const assertions are a special case of type assertions that influence type inference rather than specifying a specific type to cast to.
const-assertion ::= ‹type› as const;
Const assertions make TS infer the narrowest possible type. 
Specifically, const assertions make three things happen:
1. type widening.
2. object literals get readonly properties.
3. arrays become readonly tuples.

#### type narrowing

Type narrowing is a form of implicity type change where the type of a thing is made more precise based on which types could possibly exist in that context.
In TS, pretty much anything that could be reasonably assumed to narrow does.
Assigning to a variable with something of a more loose type undoes the narrowing performed that is narrower than that loose type.
Narrowing can produce the never type if the thing was narrowed to impossibility
A type guard is any check that narrows the type of a thing.
In TS, type guards for basic types uses typeof.
in TS, a type predicate is a function that returns a boolean value. The boolean value determines if the thing is the specified type.
A type predicate is specified by adding ` is ‹type›` to the end of the return type.
In effect, using a type predicate acts as a custom type guard.

#### type annotation

Specifying the type of a thing (esp. a variable/constant) by writing the type into the code is known as type annotation.
Languages with manifest typing generally require type annotation for variable/constant declarations, parameters as well as return types.
In most (esp. C-family) languages, type annotation goes before the identifier.
In Python, Rust and TS, type annotation looks like so `: type`
Python supports type annotation since Python 3.5

##### type aliasees

Type aliases are names for types thsat abbreviate longer type descriptions.
Where type aliases exist, they generally use the type keyword.
Type aliases exist in TS, Rust
`type ‹name› = ‹type-expression›`

##### interesting keywords

### type errors

Type safety is the dgree to which a programming language prevents logic-type type errors in favor of static-semantic type errors.
A logic-type type error is caused by treating a value as the wrong type.
A type-safe language is a language that throws more static semantic type type errors instead of logic errors.

### conversion, coercion, casting and context (plus truthy/falsiness)

Context is a term usely used in programming, and with much variation.
We can think of context related to types as creating a situation in which things will be coerced to certain types automatically.
In python, bool() is said to create a boolean context = convert a value to true or false depending on their truthy/falsiness.
Something is falsy if it evaluates to false in a boolean context, and truthy if it evaluates to true in a boolean context.
Most langauges treat at least their null type(s) and their false type as falsy.
JS additionally treats empty strings, 0 and NaN as falsy.
Languages like JS or Python establish a boolean context (coerce to boolean) within their conditions for loops, conditionals, etc. Other languages (C#, Java, Rust) treat using non-booleans in these situations as an error, i.e. not create a boolean context.
In perl, context is most often used with the scalar/list distinction.
scalar() generates a scalar context
Since (ba)sh doesn't have any types but strings, it needs specific contexts to do certain tings
math context is required to do math
math context|$(()), (()) and the command let

##### type annotation keywords

In general, certain types are generally indicated similarly across programming languages (though there is variation)
Integers|int|not Rust
Floating-point numbers|float|not Rust
Booleans|bool|C#, Rust
Booleans|boolean|Java
Characters|char|C#, Java, Rust
Double-precision floating-point numbers|double|C#, Java

#### conversion

Type conversion is explicitly using a function or the like to change the datatype of something.
All pythons types, called as a function, convert to that type (e.g. list(), bool(), int())
Ruby has a set of methods that have the syntax foo.to_‹char› that convert to that type (e.g. to_i, to_f, to_s, to_sym)

#### coercion

Type coercion is implicitly forcing a value to be treated as of a different datatype.
JS will coerce extensively in the case of operations w/ mismatched types.
Concatenation of non-string w/ string|coerces non-string to string
use of booleans w/ math operators|coerce to 0/1
In contrast, pythons operators rarely coerce.

#### casting

Type casting is asking the programming language implementation to treat a value as a certain datatype temporarily.
Casting will go wrong if the vlaue cannot be treated as teh casted type.

!!type value|YAML
(type) value|C#|Java

Type assertions in TS are the equivalent of type casting in other languages.
In TS, if ⟮you know something about a type that TS doesn't⟯, you can use ⟮type assertions⟯
TS type assertion syntax: prepending ⟮‹some_type›⟯ or appending ⟮as some_type⟯


### firstclassness

An entity is said to be first-class in programming if you can ⟮Do most other things you can do with objects/values⟯
typical features of entities that are first-class in a certain language are e.g. ⟮Can be stored in variables/data structures, can be passed as a parameter to callable units, can be returned, tec.⟯
An entity that is first-class is called a first-class citizen.
Lua: all values

## bottom type

A bottom type is the subtype of every other type.
A variable with bottom type can take no value. (there is no value that can be assigned to a variable with the bottom type.)
A thing with bottom type can be assigned to anything at all.

A bottom type is used to indicate noncomputability.

no bottom type|most languages
! (called the never type)|Rust
never|TS

## unit type

A unit type is a type that only allows a single value.
A variable with unit type only ever takes things of the unit type or the bottom type.
A thing with unit type is only assignable to other things with unit type or the top type.

()|Rust

Rust's () for the unit type is abstracted from the idea of a tuple with no elements.
In Rust, things without a return value implicitly return ()
In rust, a struct without fields is also an unit type, called the unit-like strct.

in TS, there are three unit-like types: `null`, `undefined` and `void`
in TS, `null` is the only proper unit type: only things of type `null` plus `never` and `any` (of course) are assignable assignable to `null`, and `null` can only be assinged to `null` plus `unknown` and `any`.
in TS, `undefined` is only unit-like, since besides the proper relationships one may also assing things of type `undefined` to variables of type `void`.
in TS `void` is only unit-like, since besides the proper relationships things of type `undefined` are assignable to variables of type `void`.
in TS, if `strictNullChecks` is enabled (which is not the default behavior, but my default assumption otherwise the type system becomes a mess) `null`, `undefined` and `void` act like unit types, such that nullable types need to be literally declared as option types.
in TS, if `strictNullChecks` are disabled, all types are nullable.

### literal types

A literal type is unit type whose value is specified via the literal of another type (e.g. 4 or true or "ara ara")
in TS, the types of constants are a literal type of thier value.

## combination of other types

### intersection types

An intersection type specifies a type which must satisfy all constraints that individual types satisfy.
While it would be technically possible to create intersection types of primitive types, it is pointless: There is no value that could possibly satisfy the constraints e.g. 'is a string' and 'is a number' at the same time, since they are disjoint.
intersection-type ::= ‹type› ＆ ‹type›

### union type

#### definition

A union type specifies a number of types that anything with the union type as type may take.
A union type can hold a value that could take on several different but fixed types.
A union type can be thought of as a type that has several "cases", each of which should be handled correctly when that type is manipulated.
In type theory, a union type is a sum type.

#### use

with ⟮union⟯ types, you can only use things that ⟮all of the relevent types can do⟯, unless you ⟮narrow them down⟯

#### in various languages

Common syntax: type1 | type2 ...
Syntax for creating arbitrary union types exist in Python, TS and graphQL

#### tagged unions

A tagged union type is a union type where each of the types has a tag, which is used to determine which type is currently in used.
What rust calls enums is more properly a tagged union.
in TS, a thing similar to tagged unions is called a discriminated union.
in TS, discriminated unions are implemented by a union type of other types with a shared field.
In a discriminated union, TS can narrow based on checking a shared field.

##### rust

in rust, tagged unions implements the tag by means of the name of the enum.
in rust, tagged union variants may be tuples, structs, or unit-like

###### strum

strum|enum ‹-› string manipulation

to make enums ready for use with strum, one needs to derive the relevant trait onto it, and also use attributes on the enum or the variants.
Strum attributes use strum()

Enum → str|derive strum_macros::ToString
Enum → str message|derive strum::EnumMessage|Enum.get_message() ＆ Enum.get_detailed_message() (return options)
str → Enum|derive strum::EnumString|Enum::from_str()

##### types with two possible states

###### option type

An option type is a type that represents an optional value.
An option type can generally take on a state representing it is empty, or a state representing it is full, and wrapping around another value.
In rust, the option type is its alternative for null, which it does not have.
In rust, the option type is implemented as an enum.
In rust, the option type is 
pub enum Option‹T› {
  None,
  Some(T),
}

In general, either option types or nullable types will be used to represent the absence of a value in a given language, but no both.

###### result type 

A result type is a type which can be either of two variants/states, a success type holding the result, or an error type holding the error message.
in rust, the result type is `Result`, looking like enum Result‹T, E› { Ok(T), Err(E)}

###### commonalities

####### logic with methods

|if None|if Some
‹OptionOrResult›.and(‹AnotherOptionOrResult›)|None/Err|‹AnotherOptionOrResult›
‹OptionOrResult›.and_then(‹callback›)|None/Err|‹callback›(‹OptionOrResult›)
‹OptionOrResult›.or(‹AnotherOptionOrResult›)|‹AnotherOptionOrResult›|None/Err
‹OptionOrResult›.or_else(‹callback›)|‹callback›|None/Err
‹OptionOrResult›.map(‹callback›)|None|call callback with contained value and return option with returned value
‹OptionOrResult›.map_or(‹default›, ‹callback›)|‹default›|call callback with contained value and return option with returned value

####### cloning and copying

the cloned/copied methods of Options/Results takes an Option‹＆T› or ‹＆mut T› or a Result‹＆T, E› or ‹＆mut T, E› and returns an Option‹T› or Result‹T, E› by cloning/copying

####### conversion

Result‹T, E›.ok() → Option‹T›

####### ? operator

In rust, the ? operator takes a `Result` or `Option`
In rust, the ? makes a `Result` evaluate to the value inside the `Ok` if `Ok` or exit out of the nearest function, returning an `Err`.
In rust, the ? makes a `Option` evaluate to the value inside the `Some` if `Some` or exit out of the nearest function, returning a `None`.
The ? is implemented via the trait std::ops::Try

####### unwrap ＆ expect

unwrap and expect can be called on options and results.
unwrap and expect are similar that they return the value if the type is Ok/Some, and panic otherwise.
the difference between unwrap and expect is that expect allows us to choose our error message.

#### nullable types

##### definitions

Null is not typically its own type (since it would be a useless unit type), instead other types are generally nullable.
A type being nullable means it can take a special value null/nil/undefined instead of the usual possible values.
We can understand nullable types as an union type between usual type | null type

##### keywords for the special value null

nil|lua|liquid|ruby
null|C#|Java|JS (secondary)
undefined|JS (primary)
None|Python
there isn't one|Rust

##### language peculiarties

###### liquid

Liquid has a special null-like type that is returned when accessing a deleted object called EmptyDrop

###### JS

In JS a type is nullish if it is null or undefined.

###### graphql

In GraphQL, an exclamation mark `!` afte a type indicates that the field is non-nullable.

### type manipulation

in most languages, types are limited in how they can be used:
contain predefined primitive types|all statically typed languages
new data structures create corresponding types|all statically typed languages (I know)
new records create new corresponding types|all statically typed languages (I know)
can create type aliases|Python, Rust, TS
can create types that are combinations of other types|TS
can create new types by reasoning about other types|TS

type manipulation is a not-so-common cover term for creating new types by reasoning about other types

the `keyof` operator takes an object type and returns a union type of its keys.
the TS-specific `typeof` operator returns the type of a non-type thing.
the TS type `ReturnType‹T›` corresponnds to the return type of T (T must be a function ＊type＊)
An indexed access type, given a key of a field, allows us to get the type of the value of a field of another type, much as indexing an assoc array with a key returns its value.
Indexed access types use the same [] syntax as normal accessing.
Conditional types evaluate to different types depending on an expression.
conditonal-type-specifier ::= ‹generic› extends ‹type› ? ‹type› : ‹type›;
the generic which is the first thing conditional type can be used in the true branch for further manipulation/selection.
in the ‹generic› extends ‹type› of a conditional type, within the ‹type› one may declare an additional generic via `infer ‹generic›`, which we than can use in the true branch
A mapped type maps all keys of another type to a certain type.
mapped-type-specifier ::= \[‹type› in keyof ‹type›\]: ‹type›;
more on mapped types: https://www.typescriptlang.org/docs/handbook/2/mapped-types.html
Template literal types use JS template literal syntax to expand to all possible string literal types that this could assume.

mapped types

### TS Utility types

TypeScript provides several utility types to facilitate common type transformations.

## top type

A top type is the supertype of every other type.
A variable with top type can take any possible value. (any possible thing can be assigned to a variable with top type)
A thing with top type can only be assigned to another variable with top type (in languages that have static typing).

A top type is often also the type that is at the top of the class hierarchy, in languages where such a thing exists

object|Python
unknown|TS
UNIVERSAL|Perl
java.lang.Object|Java
System.Object|C#
BasicObject|Ruby

In ruby Object inherits from BasicObject and generally acts as the top type for most purposes.

In TS, `any` is like a top type in that any value can be assigned to variables of type `any`.
in TS, `any` is like a bottom type in that things of type `any` can be assigned to anything.
Most languages with dynamic typing act as if everything had type `any`.
in TS, unless `noImplicitAny` is enabled, TS will often fall back to `any`, acting like default JS in these cases.
in TS, `{}`, `Object` are the same type.
in TS, `{}`/`Object` are nearly top types, you can assign everything but `null`, `undefined`, or of course `unknown` to `{}`/`Object`.
by contrast, `object` (notice the case) is any non-primitive type, and thus not even nearly a top type.

## object types, interfaces and classes in TS

object type = objects literals as types, generally declared with the type keyword if not inline.
in TS, object types, interfaces and to a certain extent classes share a lot of syntactic similarities.
object types, interfaces (and to a certain extent classes) both fundamentally a similar syntax to js objects.

type|keyword
object type|type
interface|interface
class|class

basic field|‹fieldname›: ‹value›,|object type, interface, class
optional field|‹fieldname›?: ‹value›,|object type, interface, class
methods|‹fieldname›: (‹ts-param-list›) =› ‹return-type›, (syntax 1/2)|object type, inteface
methods|‹fieldname›(‹ts-param-list›): ‹return-type›, (syntax 2/2)|object type, inteface
make thing itself callable (i.e. a function)|(‹ts-param-list›): ‹return-type›,|object type, interface
make thing itsef newable|new(‹ts-param-list›): ‹return-type›,|object type, interface

TS object types, interfaces and classes can all be defined over n generics.
prefixing a field of a object type or interface with `readonly` makes it a constant field.
in TS, object types, interfaces and classes all can have getters ＆ setters.

in TS, multiple interfaces with the same name will be merged into one, multiple object types or classees with the same name will throw an error
in TS, while interfaces can do many more things, interfaces can be implemented by classes just as in languages such as Java.
in TS, interfaces can be `extend`ed with other interfaces.
(TS) The main difference of using interfaces and extends vs intersections is that interfaces w/ extends will overwrite if there are properties with the same names but different signatures, while intersections will merge them.

(TS) An index signature specifies that for all keys of a specific type (in theory, but in fact I think they can only be string or int in ts anyway), the value will be of the specified type
Syntax of an index signature: [foo: sometype]: sometype2
The ⟮name⟯ of an index signature ⟮does not matter⟯.
^source: https://basarat.gitbook.io/typescript/type-system/index-signatures

Partial‹T›|Returns T where all keys have been set to optional
Required‹T›|Returns T where all keys have been set to required.
Readonly‹T›|Retunrs T where all keys have been set to readonly

## boolean

A boolean data type is a type that has one of two possible values, indicating
truth values.

true/false|C#|Java|JavaScript|Lua|Ruby|Rust|TOML|YAML
True/False|Python|(YAML)
yes/no|YAML
no boolean type, only truthy/falsiness|Python

YAML is not boolean keyword case sensitive

## symbols

Symbols as a datatype are guaranteed to be unique, and generally have a human-readable representation.
The fact that symbols are guaranteed to be uniqe mean that they are equal only to themselves.
In some languages, two symbol literals with the same name are equal to each other, for example in Ruby (:foo == :foo # true)
In some languages, two symbol literals with the same name are not equal to each other, for example in JS (Symbol("foo") === Symbol("foo") // false). Even in those languages, the same instance of a symbol is always equal to itself
Often, the main use of symbols is as object keys to avoid key collisons, or to act as alternatives to enums
Internally, symbols are often represented by a number.

:name|Ruby
Symbol("name")|JS

## references

A reference is a value that allows indirect access to another value.
A pointer is a type of reference that allows indirect access to a thing by storing its memory address.
Handle is an ambiguous concept, but is most commonly seem as a synonym to reference.
dangling reference/pointer = wild reference/pointer
A dangling/wild reference/pointer is a reference that doesn't reference/point to something valid
Link rot is the process of links becoming dangling/wild references.
Multiple indirection is having references to references (and so on).

A smart pointer is a pointer with some other features (e.g. automatic memory management or bounds checking).
A fat pointer is a pointer that stores some extra data besides the address.

What Rust and C++ call references are probably more like pointers.
In Rust and C++ the ＆ operator takes a reference of something.
In Rust, any references of a type have the type ＆‹type›, while in C++ they have the type ‹type›＆.
In Rust, to take a reference, one must prefix the thing one is taking a reference of with ＆, while in C++ reference-taking is implied if one assigns to a reference-type variable.
In Rust, a reference to an element in a data structure counts as a reference to the whole data structure for the purposes of borrow semantics.
In Rust, references are immutable by default, and must explicitly be declared mutable with ＆mut.
In Rust, the act of taking a reference is known as borrowing, since implements specific semantics/rules.
In Rust, correct use of borrow semantics are checked at compile time by the borrow checker.
Borrow rules:
1) borrows cannot last for a larger scope than the owner
2) you may only have n references to a resource or exactly one mutable reference to a resource, but not both at the same time.
Only having either n references or exactly mutable reference to a resource implies that you cannot assign to a variable borrowed elsewhere, since assigning requires an implicit mutable borrow (!).
x = 22 is equivalent to *(＆mut x) = 22
Dereferencing takes a thing that is a reference and returns the referenced thing, allowing you access to the value behind the reference.
you can also dereference on the left-hand side of an assignment to assign to the referenced piece of memory.
In most C-family languages (of the ones I can write, C# and Rust) to dereference you use the dereference operator *.
In Rust, the Trait that controls the behavior of the dereference operator is Deref, which has a method deref implementing dereferencing.

In Rust, a slice is a view into a block of memory by means of a pointer that also stores a length.
In Rust, any linear collection type can be sliced.
In Rust, slices are considered a reference and have the same semantics as references do.
Rust slices can bu used for the same reasons one would use slices in e.g. Python (though without the ability to step or reverse), but they are not copies, but fundamentally just views.
getting a slice: ＆[mut] ‹thing-being-sliced›\[‹n›(..|..=)‹m›\]
slices can be indexed just like anything else.
Slices' length may not be known at compile time, and so rust can't guarantee that indexing into a slice will not produce an error.

when cloning a reference ＆T, rust will return T.
to_owned() is part of the Trait ToOwned.
there is a blanket implementation for ToOwned for anything that implements Clone.
the reason to use to_owned() is for types where returning T of ＆T is not desirable, namely ＆str, hence to_owned() returns a String for str.

In rust, string literals are slices, specifically they are slices into the rodata section of the object file.
this means that instead of being ＆str, string literals are in fact ＆'static str
In rust, `String` and `str` are both UTF-8 byte sequences.
Since `String`/`str` are UTF-8 byte sequences, they cannot be indexed, as they could be indexed on a non character boundary (does allow slicing however, slices always have this problem potentially).
To get an iterator of the UTF-8 bytes of a String, use bytes().
In rust `String` represents string data allocated on the heap, while `str` represents string data somewhere in memory.
since rust's `String` is stored on the heap, it can be grown and shrunk.
Since we don't know where the string data of `str` will be and what size it can or cannot have, `str` itself cannot be owned, but instead can only be referred to as a reference.
A 'reference' ＆str is actually a slice, not just a mere reference. I presume that's because we need the feature of slices indicating the length, sice we need some way to know where the str stops (since `str`s can have any length, in contrast to other things like an array which we don't need to slice to reference it since we know where it ends at compile time)
Rusts treats references to strings ＆String and ＆str as the same in most cases, since there is not much difference between a reference to a string stored on the heap whose length we know, and a slice to a string stored somewhere whose length we know by virtue of it being a slice.
string.as_str returns a string slice ＆str of a string.
String slices ＆str and ＆String are type-compatible with ＆'static str, but of course work differently: they can't last longer than the original value.

String.from() gets a String from an ＆str.
String.new() creates a new empty string.
the + operator for strings requres a `String` on the left and a `＆str` on the right

## numeric types

Languages generally have at least a type for Integers and a type for numbers with fractional parts, most commonly floats. JS combines these into a single type Number.
C#, Java, Perl, Python, Ruby, Rust, TOML allow inserting underscores in numeric literals for readability.
In some languages, multiples subsequent underscores within a numeric literals, or underscores at the beginning or end of literals are not allowed]
Some languages have specific keywords for Infinity (JS, Ruby) or NaN (JS). More commonly, values such as these exist as constants on the Number/relevant numberic type class/object/whatever.
In some languages (JS, Ruby), you can recieve values such as Infinity or NaN via certain operations, e.g. dividing by zero. Other languages will throw errors in this case.
In JS, you can generate NaN by trying to do math with a non-number and non-boolean (unless using +, which will concatenate), multiplying Infinity * 0 or * Infinity, using unary plus on a non-number and non-boolean.
In JS, you can generate Infinity by dividing by zero
checking for NaN
Number.isNaN(num)|JS (true only for NaN)
checking for finity
Number.isFinite(num)|JS (false for all non-numbers and NaN/Infinity)
In CSS, the general numeric type is ‹number›, which supports decimal numbers also. ‹integer› is a speialization for integers.
In CSS, percentages are a special type, ‹percentage›. 
In CSS, ‹percentage› consists of a ‹number› followed by a %

### overflow

If a numeric type has arbitrary precision, it can store (nearly) infinitely large numbers (it will in practice be limited by the memory the application can get from the OS)
overflow/underflow occurs when a numeric value is to large/small for its container.
Numeric types either have arbitrary precsion, are subject to overflow/underflow, or need to throw an error if a calculation exeeds the size limit of a numeric type.
Rust throws an error in overflow/underflow scenarios when debugging, and wrap otherwise.

### size (not arbitrary precision)

In rust:
Numeric types: ‹type›‹size›
signed integer|i|i16, i128, isize,...
unsigned integer|u|u32, u64, usize,...
floating-point|f|f32, f64
size as part of the type annotation (usize, isize) indicates the system word size 

⟮ES2020⟯ introduces the ⟮BigInt⟯ datatype for numbers ⟮larger than the previous maximum size⟯
BigInt literal is indicated by ends in n

### integers

Integer literals generally not overtly marked

### float and double

In Java and C#, to indicate a float literal you must add f as a suffix. any number containing a decimal point not explicitly indicated as a float will be a double
Most other languages don't distinguish between floats and doubles on a keyword level, merely by size (rust) or automatically

#### single and double precision

single-precision floating point numbers are floating point numbers stored in 32 bit of storage.
double-precision floating point numbers are floating point numbers stored in 64 bit of storage.
A single-precision floating point number typically has 1 bit sign bit, 8 bits for the exponent, and 23 (stored) bits for the significand
A double-precision floating point number typically has 1 bit sign bit, 11 bits for the exponent, and 52 (stored) bits for the significand
In JS, all Numbers are double-precision floating points.

### methods

Object/Struct/whatever for standard math operations
Math|JS
math|Python

get a random number
‹mathobj›.random()|JS

floor/ceiling function
‹mathobj›.floor()/.ceil()|Python|JS
‹thingItself›.floor()/.ceil()|Ruby

Is a thing an integer?
Number.isInteger(foo)|JS

Truncate decimal places (not rounding)
‹mathobj›.trunc(num)|JS

Round to fixed amount of decimal places
somenumber.toFixed(num)|JS

Round a number
‹mathobj›.round()|JS|Python

Get absolute value of something
‹mathobj›.abs()|JS
abs()|Python (y, it's not on the math obj)

Square root
‹mathobj›.sqrt()|JS|Python

Is the thing an Integer?
Number.isInteger(foo)|JS

## enums

Enum is short for enumeration or enumerated datatype.
An enum is a datatype that can take on one of a finite set of values.
In stats terms, an enum is a categorical variable.
We may want to consider the boolean type an enum of {true, false}
Of the languages I know, C#, Java and TS allow creation of enums via the enum keyword.
Rust also uses the enum keyword, but for things more like tagged unions.
Python allows using enums via an external module
C#, Java enum syntax: enum ‹name› {
  ‹variant›,
  ‹variant2›,
  ...
}
In C# the syntax ‹variant› = ‹value› exists to apply values to enum variants
We may want to consider enums a special case of tagged unions, where enums can only stand for simple values.


## collections

Collections are an abstract data type that hold a number of data items.
Python calls its data structures that represent collection ADTs, well, collections.
Associative collections map keys to values. 
Js sets and maps use .size instead of .length
Java has the Collections Framework for collections 
Collections may be implemented in the language as primitives, but many are either transparently records or some syntactic sugar made up of literals over records; in some language everything is an object anyway and thus this distinction doesn't apply.

Rust only calls its non-primitive collections collections, which are stored in std::collections.
Rust collections (as in non-primitve collections) are stored on the heap and are variable size, primitive data structures are stored on the stack and are fixed-size.

### access

#### random and sequential

##### definitions

Random access might be clearer if it was called direct access.
Random access allows access to arbitrary elements at will.
Sequential access only allows access in a certain sort of order.

##### examples

flex-container:✫sm_rand_seq_acc.svg✫
book|random access (to pages)
scroll|sequential access

#### notation



### collection methods

#### clear a mutable collection

foo.clear()|not JS|Python|Ruby

#### flatten a nested thing ([[1]].flat() =› [1])

foo.flat(depth)|JS
foo.flatten(dept)|Ruby
nothing in py

### non-linear collections

Python: dictionary, set (and frozenset)

#### sets

ADT similar to sets in math = unique members, don't have order.
Python data structure: set (mutable), indicated by {}, frozenset (immutable).
JS: class Set, create via new Set(), add(), has()

##### set operations

Many languages/libraries have generalized set operations to something you can do to most/all collection types.
Python has set methods, but only allows them on sets.
JS has a Set class, which does not support set method

xor/union/intersection/difference(things...)|lodash/underscore(JS)

#### associative collections

##### associative array

###### definitions

An associative array is an abstract datatype composed of a collection of (key, value) pairs so that each possible key appears only once (as a key) = keys are unique.
A mapping is the term for a single key-value set (ordered pair).

###### keys

Different programming language's implementations limit keys to only strings, strings or integers, all values, or something inbetween.
In programming languages, string assoc arr keys are generally quoted. In TOML they may be unquoted for simple alphabetic keys.

####### computed property names

Computed property names allows you to put any expression on the left-hand side of a property within an object literal, if you wrap that thing in []
AFAIK only JS has computed property names

###### implementation

####### primitve vs records

Associative arrays are implemented as primitives in some languages, as records in others, or sometimes as both.
Languages with no associative array primitives: C#, Java, Rust
If languages implement assoc arr via records, you then interact with them as you would with records.
If languages implement assoc arr as primitives, these then often have their own syntax for interaction.

####### literals

######## delimiters

no literals at all|C#|TOML
{}|JS (objects)|Lua|Perl (1 of 2)|Python|Ruby|YAML
()|Perl (1 of 2)|SCSS/Sass (same as arrays)
newlines ＆ indentation|YAML

######## mapping separators

In associative array literals, the separator between 2 mappings is generally ,

######## key-value separators

=|lua|TOML
:|python|Ruby (symbols)|YAML
=›|Perl (1 of 2)|Ruby (non-symbols)
, (yes, really)|Perl (1 of 2)

######## assoc array names (if primitve)

table|lua|TOML
hash|perl
dictionary|python
hash table|Ruby
map|SCSS/Sass

In most languages with primitive associative arrays, accessing and assigning are handled by the usual indexing syntax also used for their primitive array type etc.

####### objects

Dictionary‹K, V›|C#
HashMap‹K, V›|Rust
BTreeMap‹K, V›|Rust
Map‹K, V› interface, e.g. HashMap‹K, V›|Java

####### JS

JS implements associative arrays via the `Map` and `WeakMap` classes. 
In JS objects (esp. object literals) also perform many of the operations we would expect of associative arrays. 
Specifically, Maps maintain insertion order, and support any key type, while Object coerces any key to a string (except Symbols). 
Objects are primitives, Maps need to be created with the new Map() constructor. 

###### properties

####### insertion order

There are both languages that do and do not guarantee insertion order to be maintained for their associative arrays.
In Rust, you need to use the `indexmap` crate to get an associative array that keeps insertion order.

###### operations

####### assigning

adding a key, value pair
.Add(‹key›, ‹value›)|C#
.set(‹key›, ‹value›)|JS (map only)
.put(‹key›, ‹value›)|Java
.insert(‹key›, ‹value›)|Rust

####### retrieval

get(‹key›)|Java|JS(map only)|Rust
[] indexing notation despite not being a primitive|C#

####### deletion

set it to null type|lua

####### checking for existence

######## has key? 

key?|Ruby

######## has value?

value?|Ruby

####### iterators/arrays of

######## key, value tuple/array/whatever

pairs()|lua
items()|Python
entries()|JS (map only)

########  keys

keys()|JS(only Map)|perl|Ruby|Rust|Python (returns a dict_keys object)
Object.keys(someobj)|JS

######## values

values()|JS(only Map)|perl|Ruby|Rust|Python (returns a dict_values object)
Object.values(someObj)|JS

######## JS

Amusingly, JS doesn't have the keys(), values(), entries()... functions for its assoc array type (objects), but does have them for arrays

####### merging

map-merge(foo, bar)|SCSS/Sass

###### derived structures

####### entries

An entry is a view into one item in a assoc array.
In rust, an `Entry` is an Enum with possible variants `Occupied`, `Bacant`
in rust `Entry.or_insert` insets the key into the map if map is empty.
Rust: Has the entry() function go get a Entry

###### assoc-array files

typically, most languages have modules/libraries called json/yaml for json/yaml processing.
JS and thus node calles its json/yaml libraries JSON/YAML.
‹j-or-y-library-object-name›.load()|parse as JSON/YAML into assoc array structure|Python
‹j-or-y-library-object-name›.parse()|parse as JSON/YAML into assoc array structure|JS (incl node)
‹j-or-y-library-object-name›.dump(‹assoc-arr›, ‹file›)|write assoc array as JSON/YAML|Python

to make sure that Python's JSON/YAML libraries insert newlines and indentation, pass the load method the named parameter indent with the relevant indent.

####### rust serde

serde is a rust crate for serializing/deserializing data structures from/to common formats.
serde uses additional crates to add support for formats, e.g. serde_json for json and serde_yaml for yaml.
trying to use serde-related features with indexmap will fail if you haven't specified the feature "serde"
you can make `ureq` support conversion to json via serde directly via the `json` feature.
serde represents anything with the `Value` enum
the `Value` enum has variants for each type supported by the file format. 
serde_yaml represents mappings as `Value::Mapping‹Value, Value›`
serde_json represents Objects as `Value::Map‹String, Value›`

`Value.as_‹type›` returns Option‹‹type››
`Value.is_‹type›` returns bool representing whether is ‹type›

using serde to parse, we may parse arbitrary data into a serde representation using from_str and then index into it as you would in JS with square bracket notation (but you may recieve `Value::Null`), or we may parse data into a predefined rust representation
to make serde support the derive macro, set the "derive" feature

###### peculiarities

####### lua

tables are actually the only data structure in lua

### linear collections/ADTs

Linear collections/ADTs are a sequence of items.
Python calls its data structres that are linear collections sequences.
Linear collections are the equivalents of sequences in math.
Python sequences: list, tuple, str

It seems to me that all non-array linear collections only allow sequential access.

#### linear collection methods

##### reverse the thing

reverse()|JS(in-place)|Perl|Python (in-place!)|Ruby

##### append a linear collection to a different linear collection

col1 + col2|Python (also works for strings)
col1 ‹‹ col2|Ruby (also works for strings)
col1.extend(col2)|Python

##### repeat the contents of a linear collection n times

col1 * n|Python

##### append one element to end of dynamic linear collection

push()|JS|Rust
append()|Python

##### remove an element from a lin coll by name

somelincoll.remove(elem)|Python

##### insert an element at a specific position

somelincoll.insert(elem, index)|JS

##### fill the thing with the specified element

somelincol.fill(element[, start[, range]])|JS|Ruby
In Ruby, fill also may take a block to calculate the element to fill it.
[element; length]|Rust (Arrays)
vec![element; length]|Rust (Vectors)

JS
Array() and Array.of() will create an array of a list of arguments.
The difference between Array.of() and Array() is in the handling of integer arguments: Array.of(7) creates an array with a single element, 7, whereas Array(7) creates an empty array with a length property of 7 (Note: this implies an array of 7 empty slots, not slots with actual undefined values).

The push() and pop() methods were borrowed from the Stack ADT to describe inserting/taking from the end of the linear collection in some languages, e.g. JS. 
Most commonly, pop/shift returns the element removed, while push/unshift returns the new length.
Shift and unshift are methods in JS, Ruby, Perl, Java that do the same as pop/push but for the beginning of the array.
Python extends the pop method to all collections, but it generally works weirdly, compared to other programming languages:
someset.pop()|a random element
someassocarray.pop(somekey)|the relevant value
somearr.pop(index)

somearray.splice(⟮start⟯, numberOfElementsToDelete, element1toInsert, ...); (odd, js only, returns array of removed elements which may be empty)

##### rust

In Rust, vectors can be indexed via the [] syntax, which will panic if the element doesn't exist, or via get(), which returns an Option‹＆T›

#### strings as linear collections

TODO string as iterable
Strings are often implemented as linear collections (esp. arrays) of chars, or at least their semantics are similar enough that they work the same way.
Since strings are semantically and often also by implementation similar to linear collections, their methods often are the same.

##### methods

get (first) index of element/substring in string or linear collection
foo.index(bar, optionalStartIndex)|Python
foo.indexOf(bar, optionalStartIndex)|JS (returns -1 if ti could not be found)

get (last) index of element/substring in string or linear collection
foo.lastIndexOf(bar, optionalStartIndex)|JS

Concatenate multiple strings/ arrays at the end of an existing string/array
stringOrArray.concat(stringsOrArrays)|JS|Ruby

#### array

An array (type) is a abstract datatype of an ordered linear collection of elemennts, selected by indices.


##### depth

no indices (one value only)|zero-dimensional array (uncommon)|scalar
one index|(one-dimensional) array|vector
two indices|two-dimensional array|matrix
n indices|multidimensional array|tensor

##### types, names, literals

###### primitiveness

Arrays are generally primitives in different programming languages, though they differ on syntax and what they call them.
In C# and Java, the builtin static arrays are objects, and thus must be created using the new operator. 

###### possibilities

Arrays may be dynamic = have variable size, or static = have fixed size.
Some languages have mutable static arrays, some languages have immutable static arrays, and some languages have both.
Some languages allow only one type in an array, and some languages allow multiple types in an array.
In static arrays, the compiler therefore knows the type of each index
Dynamic arrays are sometimes called arraylists.

###### names

####### dynamic arrays (one type only*)

Vec‹T›|rust
ArrayList‹T›|Java
List(yes, really)‹T›|C#

Rust Vectors, Java ArrayLists and C# Lists are Objects/Structs and defined over a generic
Different types in the dynamic arrays defined over a generic may be possible via parametric polymorphism.

####### dynamic arrays (of whatever types)

list|GraphQL|python
array|perl|JS|ruby
table|lua (though this is more properly the assoc array type, it just happens that an assoc array w/o keys will have numeric keys set up for it by lua, making it also the array type)

####### static arrays (one type only)

array|C#|Java|Rust

####### static arrays (of different types)

tuple|rust|TS

####### immutable static array (of whatever types)

sequence|yaml
array|liquid|TOML
tuple|Python
list|SASS/SCSS 

###### array literals

####### delimiter

dynamic (of whatever types)
()|Perl (same as assoc. arr)|Shell
[]|JS|GraphQL|Python|Ruby

static, one type only
{}|C#|Java

static arrays (of diffent types), the compiler therefore knows the type of each index
()|rust
[]|TS

dynamic (of a single type)
vec![]|Rust (creation only)

immutable static array (of whatever types)

()|SASS/Scss|Python (Though in python in reality it is the comma that creates a tuple. the parentheses are just often needed for grouping)
[]|TOML|YAML (if inline)

####### separator

In array literals, the invidual elements are generally separated by ',', except sh, which separates them by space

####### oddities

YAML also has indentation delimited, newline separated, individual items marked by `- ` version

####### nested

Most languages use the same syntax for one-dimensional, two-dimensional, or multidimensionall arrays, merely nesting the literals.

####### type annotation

In principle, type annotation for array types usually uses the same delimiter as the literal for that array type.

######## specific variants

static immutable arrays|‹delimiter›‹type›{, ‹type›}‹delimiter›
static mutable single-type arrays|‹delimiter›‹type›, ‹length›‹delimiter›
dynamic arryas|‹type›‹delimiter›‹delimiter›|TS
dynamic arrays|‹delimiter›‹type›‹delimiter›|GraphQL

######## language peculiarities

In C# the type for multidimensional arrays (e.g. for a three-dimensional array) is type‹delimiter›,,‹delimiter› (and for the constructor type‹delimiter›length,length,length‹delimiter›). These are different from merely arrays of arrays, as these have a uniform size (while arrays of arrays do not) 

in TS, ‹type›[] is syntactic sugar for Array\‹‹type›\›
in TS, readonly ‹type›[] is syntactic sugar for ReadonlyArray\‹‹type›\›

##### operations

In sh, referring to the whole array requires a special syntax my_array[@] which can only be used within ${}

###### fixed length

When creating static arrays, the size must be given. In C# and Java, this is done in the [] of the array type in the constructor, e.g. new type[10];
In JS, one can create an array with a specfic size (and thus ergo empty slots) by using Array(n) or new Array(n)

#### lists

Lists/Sequences are an abstract data type (specifically a collection), in which each element has a position (a first element, a second element), and that are finite.
Lists are always dynamically sized
C#: List, defined over one generic. must be created via constructor. Add to end of list .Add()

##### linked list

flex-container:✫sm_408px-Singly-linked-list.svg.png✫
A linked list is a data structure (implementing the ADT list) in which each node/vertex holds a reference to the next element.
To access a linked list, we merely need a reference to the first element.
A linked list in which the only node/vertex is a reference to the next element is a singly-linked list

flex-container:✫sm_doubly_linked_list.svg✫
A linked list with a backward reference too is a doubly-linked list.
access|O(n)

###### cons

cons is short for construct function, and comes from lisp. 
To ⟮cons something onto something⟯ is to take a ⟮container⟯, add ⟮an element in front of it⟯, and ⟮put this in another container⟯.
A singly linked list is functionally eqivalent to / can be modelled by a set of nested ordered pairs (foo, (bar, (quuz, nil))).
A cons list is a singly linked list constructed via nested ordered pairs.

###### blockchain

flex-container:✫blockchain.svg✫


A ⟮blockchain⟯ is a growing ⟮(linked) list⟯ of records called ⟮blocks⟯.
In a blockchain, each block contains ⟮a hash⟯ of ⟮the previous block⟯, a ⟮timestamp⟯, a ⟮nonce⟯, and ⟮transaction data⟯ represented as ⟮a merkle tree⟯.
Since ⟮blocks contain hashes of previous blocks⟯, ⟮changing a block⟯ would ⟮also require changing subsequent blocks.⟯

##### vs arrays

slower access O(n) vs O(1)
more space consumption if no empty spaces in array due to pointers.
Re: modern processors, linked lists have the problem that they are stored non-contiguously and thus can't take advantage of processor cache as well (priniple of spatial locality)

#### streams

Streams are an abstract data type (specifically a linear collection), in which each element has a position (a first element, a second element), and that are infinite (or at least potentially so).

#### stack

The anaogy of a stack historically comes from spring-loaded plate dispensers (e.g. in a mensa)
In a stack, the element you remove will be ⟮the one you added most recently⟯
LIFO = last in first out
A stack is a linear collection ADT with LIFO order, and the operations:
push: add to the top of the stack
pop: remove from top of the stack
peek: loop at top of stack

flex-container:✫sm_Data_stack.svg✫

#### queue

FIFO = first in first out
A stack is a linear collection ADT with FIFO order, and the operations:
enqueue: add to the end of the queue
dequeue: remove from the front of the queue
peek: look a the next element that would be dequeued

flex-container:✫sm_450px-Data_Queue.svg.png✫

## intersection of iterators, strings, linear collections

### slicing and ranges

Slice and range syntax is often similar.
For slicing, the slice syntax must generally be surrounded by the same brackets used for array indexing.
For ranges, different programming languages need them to be surrounded by () at different times.
start..end_incl|Ruby|Perl|Liquid (range only)
start..end_excl|Rust
start...end_excl|Ruby
start..=end_incl|Rust

#### slicing

Slicing is extracting a subset of elements from a data structure.
Slicing is most commonly performed on linear collections or strings.
In most cases, omitting the start defaults to 0, and omitting the end defaults to the maximum value (last element/slength)
In general, using a negative index for step will reverse the thing.
In python you can assign to slices, delete them, etc.

[start:end_excl:step]|Python
.slice(start, end_excl)|JS
.substring(start, end_excl)|JS (only strings, will not count from back, but will swap start and end if start is larger)
[start,length]Ruby

#### ranges

Ranges may be a syntax for generating iterators/arrays, or may be their own type. They may also be both, pythons range is an interable type that as all iterables generates an iterator if needed.
Step is pretty much always optional.

range(start, stop, step)|python|lodash/underscore (js)
seq start step stop|sh

Bash calls its range syntax a »sequence expression«.
Bash also supports characters as start and stop.

### misc

does the thing contain the thing?
include?|Ruby (Array, String, Enumerable)
includes()|JS (Array, String)

Is there a truthy value in an iterable
any(iterable)|Python

Are all the values in an iterable truthy 
all(iterable)|Python

Sum up all the elements in an iterable
sum(iterable)|Python
enumerableWhichIsJustASynonymForIterable.sum()|Ruby
Iterator.sum()|Rust


count occurrences of element
foo.count(bar)|Python|Ruby
no easy way|JS

## iterators

An iterator is an object (or similar) whose purpose is to iterate over some data. 
An iterator has a next() method that returns the next element.
Most other functionality that an iterator offers can be derived from the next() method
An iterable is generally something that can create an iterator of itself.
Something being iterable is generally implemented as an interface.
Something being an iterator may be implemented as a type or interface

### iterator implementation

`Iterator` trait/interface|Rust

In rust, to implement `Iterator` you only have to implement `next()`, and Rust will automatically implement a bunch of other methods for you.

### iterables


In ruby, iterables are called enumerables.
In most languages that have iterables, most collections are iterable, as are strings and ranges. 
Java Strings are not iterable, JS objects aren't either.

#### iterable ↔ iterator

Iterables generally require explicit or implicit conversion to become/spawn iterators.
iterables are always automatically converted to iterators|
iterables are only automatically converted to iterators in loop contexts, manual conversion otherwise|rust


In rust, you call `collect` on the iterator to turn it back into a data structure.

##### rust

In rust, iterators themselves must always be mutable, since calling next() changes the iterator.

‹iterable›.iter()|iterator of immutable references
‹iterable›.iter_mut()|iterator of mutable references
‹iterable›.into_iter()|iterator of owned values


### next()

in JS, the next() method returns an assoc array {
  done: bool,
  value: ...
}
In JS, Array.from() transforms a given iterable into an array. (list() does the same in Python and foo.to_a does it in ruby)

### generators

A generator is a form of iterator. Generators are created via a generator function (thus you control what the next() method returns), but otherwise behave like any other iterator.
In JS, generators are indicated by a * after the function keyword.
In JS at least, generators continue from where they left off after the last yield.
In JS, returning or encountering an error ends the generator.
In JS, the next() function of a generator's iterator can be passed an argument that will be assined to the yield expression.
Returning the current iterator element 
yield|JS

yield another generator (JS) yield*

### iterator methods

someIter.⟮zip⟯() takes ⟮two iterators⟯ and returns ⟮a new iterator⟯ which will for each call to ⟮next()⟯ return a ⟮tuple⟯ with the values ⟮the other two would have returned⟯ with ⟮next()⟯
In rust, methods (most of them higher-order functions) called on iterators are known  as adapters or consumers, depending on what they do.
Iterator adapters take an iterator and return another iterator
Iterator consumers take an iterator and return something else (thus consuming the iterator)

## strings

A string type is generally a type for an arbitrary sequence of characters.
Depending on the language, strings may be mutable or immutable.
In general, more languages lean to the immutable string direction.
Languages with mutable strings I know include Perl, Ruby.
While it may be tempting to change strings by assigning to indices, in languages with immutable strings, it does not work. However, in JS in non-strict mode it will not trow an error
If a language has immutable strings, string operations actually create a new string.
In many languages, especially those that do not have a char type, string literals can be indicated either with single or double quotes.
In languages that have a char type, the char type is generally indicated with single quotes, and the string type with double quotes. Examples: C#, Java, Rust
Some langauges that don't have a char type differentiate between string literals with single and double quotes (e.g. treating single quote string literals as raw strings, e.g. sh, Perl, Ruby), some languages (CSS, HTML, lua, liquid, python, JS) do not.
In languages that have single-quoted string literals, interpolation is generally also not allowd in them.
JS has a specific, especially featureful type of sting called a template literal, which are delimited by backticks (`foo`)
sh is a little special in that it accepts strings with no surrounding quotes in some cases.
YAML accepts unquoted strings if they don't interfere with other syntax, of which the most common case is them containing ` :`
In some languages, most notably C, strings are ended by the NULL (0x00) character, these are known as null-terminated strings.

A raw string is a string literal where character escapes have been disabled and so everything is a literal.
r or R"foo"|Python|Rust
String.raw`foo`|JS
'foo'|sh|Perl|Ruby|TOML

Multiline string delimiters
`containsnewlines`|JS
\[\[containsnewlines\]\]|Lua
"containsnewlines"|Rust (all strings are multiline)
"""containsnewlines"""|Python|TOML
|\nproper indentation|YAML

Strings that stretch over multiple lines in source code but are actually folded into a single line in the resulting thing (for source code readability)
›\nproper indentation|YAML

The type for css strings is ‹string›

### chars

The datatype storing a single character is generally called char.
In rust, a char contains a single UTF-32 encoded unicode codepoint.

### string interpolation/String formatting

String interpolation is evaluating a string with placeholders and replacing them with their values
String interpolation is a form of template processing (cf other cards)
In JS, string interpolation can only be performed within template literals.

\${expr}|JS|only in template literals
\#{expr}|Ruby|SCSS/SASS
‹sigil›{expr}|Perl
‹sigil›variable|Perl

sh's various $-introduced expressions are similar to string interpolation.
Python has three ways to perform string interpolation:
old-style stirng formatting: is just c-style string formatting. The whole string is followed by a % character, which itself is followed by a single value or a tuple of values to interpolate
new-style string formatting:
{} or {0}, {1} ... interpolates within the string, if calling format() on the string. Interpolated expressions are args to format method, format specifiers go within {}, if passing to format by name, refer to these things like so {name}. 
If combining w/ format specifiers \{‹name›[!‹conversion›][:‹format_specifier›]\}
"Error code: {errno:x}".format(errno = ...
f-strings: allow arbitrary expression within {}. String must be prefixed by f
f"Hello, {name}"

rust defines its format syntax in std::fmt, which largely tracks python's str.format() specifier
rust allows its std::fmt formatting syntax in its format! and println!/eprintln! macros, with the difference being that the former returns a string and the latter prints.
specifying a ? as the final element in a rust formatting syntax specifier makes it use the trait `Debug`, otherwise it will use the trait `Display`

#### C style string formatting

(C) format strings aka printf (print formatted) format strings are names for a specific type of string formatting syntax using % and originating from C.
C format strings specify the format of a given argument with a format specifier
format specifier: % followed by a char or a few chars to indicate the format.
Which strings to interpolate where is determined positionally (the first string is interpolated )
Positional arguments to interpolate are specified after the string separated by a %
c-format-string-format-specifier ::= %[‹parameter›]{‹flag›}[‹width›][.‹precision›][‹length›]‹type›
parameter ::= ‹n›$
flag ::= -|+| |0|'|#
width ::= ‹positive-integer› # specifies minimum width.
precision ::= ‹positive-integer› # specifies maximum width

flag meaning
-|left-align output
+|prepend a + sign for positive numbers
 |prepend a space for positive numbers
0|use zeroes when padding via width
'|The integer or exponent of a decimal has the thousands grouping separator applied. 
#|

for the types in c-style format strings, if there is an uppercase variant this normally uppercases the cahracters

common types
x or X|hex (unsigned numbers only)
o|octal (unsigned numbers only)
d or i|signed int
u|unsigned int
f or F|decimal number
e or E|use exponent based notation e±dd
g or G|decide between e/E and f/F depending on maginitude
s|string
%|percentage (python .format() only)
b|binary (python .format() only)

#### python-style string formatting

python's str.format() method takes a C format string inspired but somewhat different syntax.
[[‹fill›]‹align›][‹sign›][#][0][‹width›][‹group›][.‹precision›][‹type›]
where width, precision and type are the same as with C format strings
fill|what character to use to pad (takes a string)
align|what direction to align
sign|is a sign included for numeric values
#|causes an explicit base indicator to be shown for binary, octal, and hex
0|pads with 0
group|indicates a separator character for groups of numbers

align ::= \‹|\›|^|=

‹|align left
›|align right
^|center
=|place padding between number and sign

sign ::= +| |-

+|+ for positive numbers, - for negative numbers
-|nothing for positive numbers, - for negative numbers
 |space for positive numbers, - for negative numbers



### string multiplication

x n|Perl
* n|Python (can also be used for arrays)|Ruby (can also be used for arrays)
.repeat(n)|JS|Ruby

### string concatenation

string concatenation is joining strings together into a single string.

..|Lua
+|Java|C#|Python|Ruby|Rust|JS
.|Perl
.push_str()|Rust (for str + str)
.push()|Rust (for str + cahar)
Adjacent string literals are automatically concatenated|Python|Ruby

### regex matching

JS has regex literals: /‹regex›/‹flags› (which creates a RegExp object)
and a constructor: new RegExp("regex","flags"), often used if you need to construct the regex dynamically at runtime
In JS, you can both use methods on strings which take regexes, or methods on RegExp objects which take strings
The RegExp Object has a property lastIndex which indicates the offset that the RegExp will search for a match at next time (if the regex is global or sticky). This stays the same even if you switch the string in the meantime!

Does the string match the regex?
RegExpObject.test(string): boolean

RegExpObject.exec(string): {
  0: wholeMatch, 
  1: captureGroup1, 
  2: captureGroup2...,
  index: indexAtWhichTheMatchBegan,
  input: origialString
}

somestr.match() and .matchAll return string matches for a Regex.
somestr.replace() and .replaceAll replace the regex they got as a first arg with whatever is specified as a second arg, be that a string (using $1 etc. optionally) or a replacerFunction
The replacerFunction recieves the following arguments:
match|The matched substring.
p1, p2, ...|The nth string found by a parenthesized capture group
offset|The offset of the matched substring within the whole string being examined
string|The whole string being examined.
groups|named capture groups

the All() versions of the regex methods of strings both require the regex to be global and throw an error if it isn't.

What somestr.match(regexp) returns depend on whether the regex is global (g) or not:
If global, match() returns all matches, but no capturing groups. If not global, match() returns the same thing as RegExpObject.exec. matchAll() returns an iterator with individual things that are  the same thing as RegExpObject.exec returns.


### common string methods

Capitalizations

convert to uppercase|.upper()|Python
convert to lowercase|.lower()|Python
convert to uppercase|.toUpperCase()|JS
convert to lowercase|.toLowerCase()|JS
convert to uppercase|text-transform: uppercase|CSS
convert to lowercase|text-transform: lowercase|CSS
switch upper and lower case chars|.swapcase()|Python
capitalize all first letters|.title()|Python
capitalize all the first letters|text-transform: capitalize|CSS
capitalize the first letter of the string|.capitalize()|Python
capitalize the first letter of the string| bar capitalize|Liquid
pad stringth to specified length by adding to the left/right|.padStart/padEnd(‹length›, ‹pad-string›)
pad stringth to specified length by adding to the left/right|.rjust/ljust(‹length›, ‹pad-string›)


does a string start with?/end with?|somestr.startsWith/endsWith(searchstr)|JS (accepts an optional second arg of the index to start searching)
does a string start with/end with?|somestr.startswith/endswith(searchstr)|Python
remove whitespace from beginning and end of string|trim()|JS, Ruby
remove whitespace from beginning and end of string|strip()|Python
remove whitespace from beginning of string|trimStart()/trimLeft()|JS
remove whitespace from end of string|trimStart()/trimLeft()|Ruby
split string on foo|.split(foo)|Python|JS(empty string for char array)|Rust
split string on whitespace|.split_whitespace()|Rust
split string on newlines|.lines()|Rust

to char array/iterator
chars()|Rust

parse sting to other type
‹string-object›.parse()|Rust (Returns a `Result`, often requires turbofish annotation.)

SCSS/Sass
⟮unquote(foo) or string.unquote(foo⟯)|⟮unquote a string (so that css gets the value as the correct type, eg. when using maps⟯)
⟮quote(foo) or string.quote(foo⟯)|⟮return string, but quoted⟯



#### string replacement

somestr.replace(foo, bar)|JS|Python

#### join to string

separator.join(iterable)|Python
somearray.join(separator)|JS|Ruby

separator defaults to , for JS and to nothing for Ruby

### JS oddity: tag functions

Tag functions are functions prefixed to template literals (but not called)
Tag functions recieve a first argument an array of all constituent string parts of a template literal, and all interpolated values as following arguments.
Whatever the tag function returns will be what the string evaluates to.
Tag functions can return whatever.


# polymorphism

something is monomorphic if it works for one type
something is polymorphic if it works for several different types
monomorphization is a compile-time process in which polymorphic code is transformed into n monomorphic variants

ad-hoc polymorphism is polymorphism where different implementations are selected based on the type of the argument(s)
→ callable unit overloading, operator overloading

## dispatch

dispatch is choosing which method should be invoked in response to a method call.
displatch is based on the type of the thing
dispatch is only relevant if there are multiple implementations of a thing.

### static dispatch

static dispatch is choosing an implementation of a polymorphic operation at compile time
callable unit overloading and operator overloading are forms of static dispatch, since the implementation is chosen based on the declared type of the parameters

#### overloading

##### callable unit

Overloading of callable units is creating multiple callable units with different callable unit signatures.
Languages I know that support overloading are C#, Java, TS.
When overloading, each signature generally has its own implementation, exept in TS.
In TS, function '⟮overloading⟯' exists, but you specify ⟮all possible signatures⟯ ⟮first⟯, and then the ⟮implementation⟯ with a ⟮signature⟯ that is ⟮compatible with all the specified signature⟯ (e.g. using ⟮optional parameters⟯), and not compatible with ⟮non-specified signatures⟯
For TS ⟮overloaded⟯ functions, ⟮all but the last⟯ signature(s), which ⟮do(es)n't have any body⟯, is/are called ⟮overload signatures⟯
For TS ⟮overloaded⟯ functions, ⟮the last⟯ signature(s), which ⟮has the body and thus the implementation⟯, is/are called ⟮the implementation signature⟯
In TS, in general: prefer ⟮union types⟯ over ⟮overloads⟯
In TS, things that can be overloaded anything that is callable: functions, callable objects, methods (whether in object types, interfaces or classes), constructors/newables.

Operator overloading is where different operators have different implementations based on their operands.

### dynamic dispatch

dynamic dispatch is choosing an implementation of a polymorphic operation at runtime.
dynamic dispatch is accomplished by means of virtual methods/functions.
both single dispatch and multiple dispatch are forms of dynamic dispatch.

#### single ＆ multiple dispatch

single dispatch is where only the type of one parameter (the reciever of the message = the thing it was called on, mostly) is used to choose the implementation

multiple dispatch is where the type of multiple parameters (the reciever of the message = the thing it was called on as well as the method parameters) is used to choose the implementation
Overloading would be multiple dispatch if it was performed at runtime, but it isn't, so it isn't.

#### virtual method table

VMT = virtual method table
virtual method table is also called (virtual) function/call/dispatch table
virtual method/function/call table is sometimes abbreviated vftable or vtable.
A vtable contains all relevant virtual functions.

#### rust

In rust, `dyn ‹trait-bound›` is the type of a trait object.
A trait object is an opaque type of another type that implements a set of traits.
A trait object uses dynamic dispatch to select the implementation at runtime (in contrast to rusts' parametric polymorphism, which ofc uses static dispatch)
A trait object is a dynamically sized type, and thus we need a pointer to it such as ＆ or Box‹›.
For something to be object safe, the return type may not be `Self` and there may not be any generic type parameters.
A trait object must be object safe.
The reason a trait object may not have any gemeric type parameters is that these will already be monomorphosized away by compile-time.
The reason a method of a trait used in a trait object may not return `Self` is that we don't known `Self` at compile-time, thus we can't reason about its size and can't guarantee safety.
In rust, we can specify that we want dynamic dispatch where we chose an implementation of a trait at runtime by having a pointer (e.g. Box) to `dyn ‹trait-list›`

## parametric polymorphism

Parametric polymorphism is polymorphism that only uses one implementation, instead taking a generic (that is perhaps subject to some contraints) and performing one's operatons based on that.
A generic is a stand-in for a type that is not yet specified or unknown. 

### type parameters ＆ generics

A type parameter is a specifier of one or more types that a thing (callable unit, object, ...) is defined over.
Type parameters go in angle brackets.
Type parameters are generally written in UpperCamelCase
Within type parameters, multiple type specifiers are separated by `, `.
Generics are specified within type parameters.
Names of generics are typically single characters.
A generic of any type is typically indicated T

#### binding generics

Once the name of a generic is bound, any reference to that name refers to that generic.
Two generics of different names are independent, even if they may be filled by the same concrete type at runtime.
It may sometimes seem like a generic is being bound twice when it's actually being used the second time.
E.g. impl‹T› SomeStruct‹T› is saying that you're implementing SomeStruct such that SomeStruct's generic ‹T› (second mention) satisfies being any type ‹T› (first mention), which is of course not particularly informative, and would be equivalent to impl SomeStruct‹T›, if that were possible.
Binding ‹T› via the `impl` already allows one to do more interesting things.
e.g. `impl‹T: Copy› SomeStruct‹T, T›` for a `SomeStruct‹T, U›` is saying that you're implementing this for all SomeStructs whose type parameters are of the same type which implements copy.

### constrainment

Many languages have a way to specify contraints a generic should satisfy.
Rust specifies a set of traits as constraints for generics, these are called »trait bounds«.
Trait bounds are a set of traits that a generic must satisfy.
In rust, we may specify trait bounds by indicating it within a type parameter as \‹‹generic›: ‹trait-bound›\›, with a 'where clause', or by not using generics at all and instead writing the type as `impl ‹trait-list›`
trait-bound ::= ‹trait-name›{ + ‹trait-name›}
where-clause-syntax ::= where {‹generic›: ‹trait-list›‹newline›}
TS allows specifying constraints for generics via the `extends` keyword.
The TS `extends` keyword in type parameter contexts takes a type specifier to specify the constraints of the generic.

### implementation ＆ monomorphization

Javas ArrayList, C# List and Rusts vec are dynamic arrays defined over a generic, and are thus parametrically polymorphic.
C# List and rusts vec are monomorphosized for each type usedas a generic; Javas ArrayList instead only generates a single implementation for ArrayList‹Object› - therefore in Java all values in an ArrayList must be boxed.
In Rust, parametric polymorphism using generics is monomorphizised, so that Option‹T› with e.g. i32 and f64 produces the relaizations Option_i32 and Option_f64.

Interfaces/traits often enable parametric polymorphism.

## subtyping


# identifiers

In a wide sense, "name" is synonymous to identifier, in a narrow sense it is an identifier
An identifier is a thing that refers to/labels an object or class/set/collection of objects.
a unique identifier is an identifier that labels a thing uniquely in a given context.
UID   unique identifier
An identifier is opaque if it provides no information about the thing it identifies
A transparent identifier provides information about the thing it identifies.

Aliasing is referring to the same location in memory by multiple different identifiers.

UUIDs/GUIDs are formats for unique identifiers that make it very likely for them to be unique.
UUID|Universally Unique Identifier
GUID|Globally Unique Identifier
UUID=GUID
UUIDs/GUIDs are 128 bit long, which makes it very likely for them to be unique.

## name resolution

name resolution is the associating of identifiers with the correct things (e.g. variables)

### name binding

Name binding is the association of entities with identifiers.
For an identifier to reference something is to the identifier bound to that thing.
Binding is intimately connected with scoping, as scope determines which names bind to which objects.
static = early binding is name binding during compile-time
dynamic = late binding is name binding during runtime
dynamic/late binding enables duck typing
duck typing is calling a method without caring about its type, and seeing if it works.

### namespaces

a namespace is a context in which names are unique.
Names within a namespace are sometimes called local names.
a namespace itself generally has a name.
Within a namespace, only the local name is needed to refer to a thing.
Outside of the namespace, the namespace and the local name are needed to refer to the thing.
In hierarchical namespaces, namespaces are nested.

## scope

the scope of a name binding is the part of a program where the name binding is valid.
for something to have x-scope is to only have the name binding be valid within x.
a variable with foo-scope is often called an foo-variable

### lexical ＆ dynamic

Static scope is another name for lexical scope.
Lexical scope is where scope is determined by where in the source code (a reference to) a name binding is.
Lexical/static scope is contrasted with dynamic scope
Dynamic scope is where scope is determined by where on the stack something is.
Pretty much all programming languages today use lexcial scope. Bash is the example, using dynamic scope.

### global/local scope

The scope that is the entire program is global scope.
A variable that does not have global scope has local scope.

Local scope is often either block or function scope.

In some languages, things that live within global scope are properties of an object called a global object.
In JS in browsers, generally, the global object is Window.
within ⟮workers⟯, the ⟮global scope⟯ is `⟮WorkerGlobalScope⟯`
within ⟮service workers⟯, the ⟮global scope⟯ is `⟮ServiceWorkerGlobalScope⟯`
The mixin `⟮WindowOrWorkerGlobalScope⟯` describes ⟮the common features⟯ of `⟮Window⟯` and `⟮WorkerGlobalScope⟯`
The `self` property of a WorkerGlobalScope returns a reference to the WorkerGlobalScope itself.

Without ⟮crates/unsafe code/etc.⟯, ⟮globals⟯ in Rust can only be ⟮constants⟯.

#### variable scope

In general, if you declare block- or function-scoped variables on the top level, these will be global or at the least, global to the module.

Block-scoped variables
my|perl
local|lua
let|JS
ø|Ruby
ones defined within a block|C#|Java|Python

Function-scoped variables
var|JS

Global variables
ø|lua|perl
$|Ruby

Variable scope in python is not determined by keyword but by context.
In JS, variables declared without a keyword become properties of the global object

### shell scope

In (ba)sh, the thing that determines scope is the shell.

running a script spawns a new subshell, unless you source it.
Sourcing a thing is done by `source` or by `.`
environment variables have a scope that allows access in current shells and subshells.
shell variables have a scope of the current shell only.
Variables are shell variables by default.
Exporting a variable turns it from a shell variable to a environment variables.

env|show all environment variables

export|export a variable
export -n|unexport a variable

### shadowing

Masking = shadowing
Name masking/shadowing is when a name in a inner scope overrides that same name in an outer scope
Variable masking/shadowing is name shadowing involving variables
In rust, shadowing allows for 'changing' tye type of the variable (really merely declaring a new variable)


### hoisting

Hoisting moves declarations but not initializations to the top of the scope.
Hoisting is mainly a JS concept.
in JS, var variables and function declarations (but not function expressions) and hoisted.

## case

snake_case|variables, methods (, symbols)|ruby|python (use underscores sparingly)
UpperCamelCase|classes|C#|Javaruby
SCREAMING_SNAKE_CASE|constants|ruby
camelCase
snake_case|shell variables|(ba)sh
SCREAMING_SNAKE_CASE|environment variables|(ba)sh
_leading_underscore_snake_case|fake private variables|(ba)sh

most programming languages are case-sensitive as regards identifiers.

## naming

While there is variety in what is allowed in a identifier name, most commonly it is [a-zA-Z0-9_]
JS also allow $ in a non-sigil way in identifier names.
JS identifiers may not start with a number, but with any other allowed character.
In general, identifiers may not be keywords.
