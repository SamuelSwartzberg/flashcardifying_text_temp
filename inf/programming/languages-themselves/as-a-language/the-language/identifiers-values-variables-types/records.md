
# records

A record is a collection of fields, possibly of different data types, typically in a fixed number and sequence. 
A type that defines a record is a record type.
Most programming languages allow creation of instances of record types.

## principles

Encapsulation refers to grouping together related things somehow, e.g. within records.
In OOP, encapsulation is often used to mean bundling the data and the methods that operate on it in one construct
Information hiding is hiding the internals of a thing from the  outside.

## class and instance entities

A class x is a x operates on/is defined on a class rather than an instance.
An instance x operates on/is defined on an instance of a record.
A class function may also be known as an associated function.
Class x ≈ static x
generally, one mainly talks of class, instance methods, which operate on classes/instances, and class, instance variables
class variables + instance variables = fields
Members are generally all methods and fields of a record, no matter if class or instance.
ergo: members = member fields + member bariables
A piece of data on a record is called a field

In rust, a class method/associated function is called by using the :: operator

static|Java|C#|JS
does not take self as argument|Rust

## self-reference

self/this are keywords to reference the current record/other thing

### self/this in different languages

self|Python|Ruby|Rust
this|C#|Java|JS

### typeof self

In rust, `Self` is the type of the current record.
In rust, `self` has the type `Self` (or `＆Self` if borrowed)

### self/this binding

Many languages bind self/this automatically in methods, all others typically bind self/this explicitly by taking self/this as their first arguments.
In JS, any function binds this, even those that are not methods. Outside of a function, this refers to the global object.
to refer to the this representing the global object even within places that bind this to something else, use `globalThis`.

#### self and methods/assocated functions

In certain languages (Rust, Python), methods must take self as the first argument, else they are class methods/associated functions.
In rust, taking `self` takes ownership and thus invalidates previous references, ergo one generally wants to take ＆self or ＆mut self.
In rust, one uses :: instead of . to call associated functions

## methods

A method is a callable unit that is a member of a record.
To make an object B do something, an object A must send a message.
in OOP, a method call is the way to send of message: The originator object is implicit, the target is specified manually, the method called is the message, and the arguments are well the arguments.
Ergo, in OOP objects generally use message passing to communicate.
In JS, methods are specified without using `function`, merely name and param list.
There is an older version of specifying methods in JS that is ‹name›: ‹anonymous-function›, this only works for object literals.

### getters and setters

Also called accessors and getters.
A getter returns a field of a record.
A setter changes a field of a record.
Setters are often used to perfrom some sort of validation before changing the field of a record.
Getters and setters may help enforcing information hiding.

Ruby syntax:
def name=(value)...|setter

JS ＆ TS:
get foo()
set foo()
only within a class

You can only interact w/ ruby instance variables via getters and setters, trying to use it without those will give you a NoMethodError

## passive data structure

AKA plain old data structure (PDS)
A passive data structure is a data structure, especially a record with fields but no other object-oriented features.

## structs

Struct is not an incredibly well-defined term, but is generally a record with the possibility for methods, but not the whole inheritance etc. stuff of classes.
In rust, struct declarations use the keyword struct.
Both struct delcarations and initializations in rust use a very assoc-array like syntax.
struct User { username: String, ...}
Tuple structs are either 'tuples with a name which can be instantiated' or 'structs with anonymous but ordered fields'.
if a variable and a struct field have the same name, you can write `foo,` instead of `foo: foo,`

## impl

Rust allows implementing methods or associated functions for structs, tagged unions (enums) and traits via the impl keyword.
when used for implementing things on structs/enums/traits, the construct used is called an impl block
the syntax for impl blocks for structs and enums is `impl ‹name› ‹block›`
the syntax for impl blocks implementing traits for structs is `impl ‹traitname› for ‹thingname› ‹block›`
Any thing may have as many impl blocks as you like.
For any impl block, we may indicate that we only want to implement it for something whose generics either are of a certain type or implement certain traits.
When we implement something, we can only rely on other things of the thing we're implementing existing, plus whatever trait bounds we've established.
we may `impl` a Trait without any `for` clause to provide a default implementation.
`impl ‹trait-list›` does not start an impl block and instead refers to a type that implements trait-list, with the advantage that this syntax can be used outside of a type parameter.

## fields 

In JS, fields themselves have properties (such as enumerable).
In JS, enumerable fields are those that will be enumerated over in a `for-in` loop.
generally, properties added 'normally' are also enumerable
‹object›.propertyIsEnumerable(‹name›)
properties that are not inherited (that is, they are there not because of the prototype chain, they of course then be inherited by other things) are called own properties
‹object›.hasOwnProperty(‹name›) 
The ⟮Object⟯.⟮assign⟯⟮(foo, bar)⟯ method ⟮copies⟯ all ⟮enumerable⟯ ⟮own⟯ ⟮properties⟯ from ⟮one or more source objects⟯ to ⟮a target object.⟯ 

## classes ＆ objects 

An object in object-oriented language is essentially a record that contains procedures specialized to handle that record; and object types are an elaboration of record types.

Keyword to declare a class is done by the keyword `class` in pretty much all programming languages which have it.

A singleton (AKA the singleton pattern) is a class that can only have a single instance of that class. It is useful when you don't need multiple instances of a thing (the null object, a logger), or to coordinate states.

method in lua function object:method(...)

in languages with type annotation, the type annotation of an object is generally its class (e.g. MyClass myObject = new myObject();)


### methods ruby

In ruby, methods that will return a boolean are marked by a ?
In ruby, methods that do something destructive are marked by a !

In ⟮documentation⟯, these methods are referenced...|
⟮class methods⟯|⟮.method or :​:method⟯
⟮instance methods⟯|⟮#method⟯



### pure OO

A pure object oriented language is one where everything is treated as an object.
There is much discussion on what it means to be 'treated as an object' for pure OO languages, but most commonly, it is at least:
1) Everything you operate on is a first-class Object
2) The only thing you can do with an object is call a method on it.
Therefore, 
1) Methods may only return other objects.
2) Operators (if they exist) are syntactic sugar for methods.
It is a matter of debate which languages are sufficiently pure OO to qualify: 
Ruby, Python, and JS allow methods to be called on pretty much anything, even primitives, since all primitves are boxed.
Only Ruby (of the languages I know) is quite pure enough to be called a pure object oriented language, I think

### inheritance

Superclass aka base class
subclass aka derived class
In most programming languages, you refer to your superclass=base class with the keyword `super`.
In most programming languages, you specify a subclass/superclass relationship like so: Subclass extends Superclass
In ruby, you specify a subclass/superclass relationship like so: Subclass ‹ Superclass
In C#/Java, making a class final disallows a subclass from inheriting from it.
In C#/Java, making a method/static function final disallows a subclass from overriding it it.
Most languages only support single inheritance, some languages (among those I know Perl and Python) also allow multiple inheritance

### abstract ＆ static classes 

Abstract classes are generally declared with the abstract keyword. 
Within abstract classes, members are also declared with the abstract keyword.
Both abstract and static classes/members are not instantiable.
Abstract classes/members are designed mainly to be inherited from.
Since abstract classes/members cannot be instantiated, they must be overriden to be used.
JS does not support abstact things, however you can simulate it by using the @abstract/@virtual JSDoc tag.

### constructors/object creation

Creating a new object via a constructor is done by the new operator in most languages, but not in Ruby or Python.
TS calles things that can be used to create new things `newable`.

A constructor is generally a callable unit and thus called with ()
Rust doesn't use any operator to create new Structs. In general, you use literals, some type provide a new() associated function.
In C#, Java, the constructor has the same name as the class.
In Ruby, the constructor is defined by the initialize function within the class (class SomeClass\n  def initialize(...), and called by calling the new() method on the class (SomeClass.new())
In JS, the constructor is named constructor
Many languages allow us to declare many different constructors with different arguments.
Most languages provide a default constructor if you don't provide one, which does nothing besides create the object.
In JS, you may not use arrow functions as constructors

A factory function is any callable unit which is not a class/constructor that returns a new object.
Ergo, factory functions create things without using the new keyword.
in Rust, many things are created by a factory function `new()`, which is an associated function of the struct.

### immutable objects

an immutable object is an object which cannot be changed once it's been created.
in JS, Object.freeze(obj) makes the object an immutable object.
In TS, Readonly ‹T› constructs a version of T whose properties are all set to readonly, making it a immutable object.

### access modifier

Access modifiers (or access specifiers) are keywords in object-oriented languages that set the accessibility of classes, methods, and other members. 

default accessibility|language
default (= package)|Java
public|Python, JS
private|Rust
Most language with any kind of access modifiers have at least a public private distinction
public (most programming languages), pub (Rust)|any code
private|code within the class
Most languages with a public/private access modifier distinciton will use the public/private keyword to mark the one that is not the default anyway
JS is an exception, it marks private members with #

protected|same class and subclasses|Java
package|within the same package|Java
in java, the package access modifier is the default
JSDoc allows the simulating of the four access modifiers that Java has by using @access ‹access-modifier› or @‹access-modifier›

A ⟮private item⟯ can be accessed by ⟮its immediate parent module⟯ and ⟮all its child modules⟯
A public item can be accessed as a private item can, and additionally also through a chain through its ancestors.
In rust, each field of a struct has its own access modifier, which must be set to public if desired.

### interfaces

mixins are pretty similar concepts.
In OOP an interface is a set of methods that anything that implements that interface must also implement.
Interfaces in programming standartize behavior
If a given programming language has syntax for them, generally keyword interface.
Indicating that one follows an interface is generally done with the implements keyword.
Something conforming to an interface is generally said to implememnt it.
If something implements an interface, it generally must implement all methods of that interface.
In the past, Java did not allow variables in interfaces. as of today, they are allowed, but subject to heavy restrictions.
In interfaces in Java/C#, you most commonly merely specify method stubs. (in the past this is the only thing you could do, this is no longer true)
Method stubs are method signatures without the implementation, in Java/C#, they are followed by a ;.
In most languages, a record may implement multiple interfaces/traits.

#### traits

Traits in Rust are broadly similar to intefaces in other programming languages.
Traits in Rust can be implemented for types you did not define.
However, the trait ∨ the thing its implemented on must be local to the crate
Traits allow for blanket implementations, that is implementing a trait for anything that implements one or more other traits.
impl‹T› ToString for T where
    T: Display + ?Sized,
{ ... }
In rust, the keyword to declare a trait is `trait`
`trait ‹name› ‹block›` 
blocks of trait declarations contain method signatures.
In rust, deriving a trait is automaticallly generating trait implementations for a given thing.
In rust, derive is implemented via an annotation that takes a list of Traits.

In rust, the orphan rule says that either a trait or the thing it is being implemented on must be local to our crate.
In rust, the reason for the orphan rule is that otherwise when using multiple crates, they may end up trying to implement the same trait on the same type in different ways, creating conflicts (and dependency hell)

In rust, traits may exist in a supertrait/subtrait relationship.
A supertrait S of trait T means that any type implementing T must also implement S.
A subtrait S of trait T means that any type implementing S is also guaranteed to implement T.

syntax for declaring a trait with a supertrait: `trait ‹subtrait› : ‹trait-bound›`

### OOP

C#, Java

### is X an object of Y

someobj instanceof class|JS

### duplication/replication

A deep copy is a copy of a data structure where things referenced in the original data structure are also copied.
A shallow copy is a copy of a data structure where references in the original data structure are merely copied, and still refer to the same thing.
Deep copying is recursive and more computationally expensive.

shallow copy
copy (module copy).copy(foo)|Python
foo.copy()|Python (only collections)|Rust

deep copy
copy (module copy).deepcopy(foo)|Python
foo.clone()|Rust

### toString()

Most languages with objects have a tostring method to convert these to strings for debugging purposes.
It can often be useful to overwrite the default tostring implementation for more useful custom debugging.
tostring methods are often called implicitly during coercion.

‹thing›.toString()|Java|JS
‹thing›.ToString()|C#
‹thing›.to_string()|Rust
‹thing›.__str__(), called via str(‹thing›)|Python
‹thing›.to_s() or .to_str()|Ruby

The difference between Ruby's to_s() and to_str() is that to_s() is implemented in the (almost) top type (Object), and is called for some coercions only, while to_str() indicates that we want to treat the thing as a string in most cases, and thus allows for coercion in more circumstances.

to_string() is part of the ToString trait.

### boxing

A box is a minimal object wrapper around another type.
The types that are most commonly boxed are primitives, sometimes boxing is restricted to this narrower definition.
putting values into a box is called boxing, the opposite unboxing
A wrapper is any entity that encapsulates/wraps around another thing.
Implementation-wise, it may be that the whole box is stored on the heap as an object would be, and we only have a pointer to the box, or as Rust seems to do it the Box may merely contain a pointer to whatever data, which is moved to the heap. (though I wonder if these are different)
Memory-wise, since boxes are objects, boxed data will be stored on the heap.
Boxing primitives allows us to interact with them using a similar interface as other objects; this enables the Everything you operate on is a first-class Object constraint of pure OO, consequently most primitives are boxed in languages aspiring to pure OO such as Python, JS, Ruby...
Autoboxing is the conversion of primitves to boxed types when relevant.
Since boxed data will be stored on the heap, it is not necessary for it to have a constant size, thus boxed data allows more flexibility.

Rust's construct for boxing is Box‹T›.

