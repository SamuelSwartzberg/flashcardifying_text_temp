#### primitive⎵language support⎵ types in different languages

C#: int, float, bool, string, char, double
Java: byte, short, int, long, float, double, char, String, boolean
JS: Number, boolean, null, undefined, string, object, array
Rust: 
  scalar: integer, floating-point numbers, booleans, chars
  nonscalar: tuple, array
Python: integers, floats, complex numbers


### languages

table:typing|languages
Dynamic, value, no type annotations or hints|JavaScript, Lua, Ruby
Mainly dynamic, mainly value, 
Static typing|statically typed C-family language (this should be defined elsewhere, but of the ones I know, Java, C# and Rust), TS
Hybrid typing|Perl (with regards to the scalar, array, hash distinction)


## unit type

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

### union type

#### use

#### in various languages

Syntax for creating arbitrary union types exist in Python, TS and graphQL

#### tagged unions

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

In rust, the option type is implemented as an enum.
In rust, the option type is 
pub enum Option‹T› {
  None,
  Some(T),
}

###### result type 

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
