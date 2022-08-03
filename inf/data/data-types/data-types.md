# data types

## basics

Data type is ambiguous between abstract data type and concrete data type.
An abstract data type is a subset of all possible values, and a specification of their behavior.
A concrete data type is an abstract data type together with the method of its implementation.
A value is an element of the set of all possible values.

## primitive vs. composite

### basics

A primitive/composite data type⎵compositionality⎵ does not consist of/consists of other data types.
An primitive/composite abstract・concrete data type⎵compositionality⎵ is a primitive/composite data type⎵compositionality⎵ where the data types in question are abstract・concrete data types.
primitive/non-primitive⎵language support⎵ =syndef= primitive/composite concrete data type⎵compositionality⎵

### primitive data type⎵compositionality⎵

scalar =syndef= primitive/composite data type⎵compositionality⎵

### composite data type⎵compositionality⎵

## set-based

### subsets

#### basics

A supertype/subtype is a data type whose possible values are a superset/subset of those of another data type.

#### interesting cases

##### top/bottom

The top/bottom type is the supertype/subtype of all other types.
A thing with top/bottom type accepts all/no values and can itself be assigned to nothing/anything at all.
Never type ≈syndef≈ bottom type.
!/never =ident for=> bottom type

##### unit

A unit type is a type that has a single value.
A thing with unit type is accepts things with the unit or bottom type and can itself be assigned to things with the unit or top type.
A literal type is a unit type whose single value is an element of another type.
The narrowest type a constant can assume is the literal type of their value.

### union, intersection

#### basics

An intersection/union type is a type that is the intersection/union of the extensions of the included types.
^the intersection type of primitive types is always the bottom type.
intersection/union-type ::= ‹type› ＆/| ‹type›
Intersection/union types have the union/intersection of each other's properties and behaviors.
^ {color: string, taste: string} & {color: string, radius: number} has the properties { color: string, taste: string, radius: number }
^ {color: string, taste: string} | {color: string, radius: number} has the properties { color: string }, though in effect we can still access the individual fields if we narrow.

#### tagged union

##### basics

A tagged union type is a union type where each of the types has a tag, which is used to determine which type is currently in use.

##### option type

An option type is a tagged union with two states none, some representing an optional value.
Typically, none/some of an option type is empty/contains the value.

##### result type

A result type is a tagged union with two states success, failue.
Typically success/failure of a result type contains the result/a failure message

## type identifiers and expressions

A type identifier is an identifier for a certain data type.
A type expression is an expression consisting of type identifiers and other type expressions.
A type alias is a type identifier for a type expression.
^since an expression can consist only of one type identifier, potentially only a single other type identifier
