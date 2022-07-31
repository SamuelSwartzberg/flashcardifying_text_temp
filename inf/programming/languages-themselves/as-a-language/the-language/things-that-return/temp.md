# expressions

An expression evaluates to = returns a value.
e.g. `6`, `6 * 2`, `true ? "foo" : "bar"`

# operators

overloading
In Ruby, all operators are actually just syntactic sugar for methods. that is, + 3 is .+(3), somearr[1] is somearr.[](1), !3 is 3.! etc.

## precedence

Operator precedence in programming mirrors the math concept of order of operations.
Operator precedence / order of operations is in which order to apply operations.
In most programming languages, math operations have the same operator precedence as they would in math itself.
Parentheses can modify the order of operations just as in math.
The power operator has unclear order of operations for historical reasons (in other programming languages), so JS throws an error if you use it without parentheses where it would make a difference
In liquid, the order of operatons is right to left, parentheses are forbidden.

## relational opearators

In computer science, a relational operator is an operator that tests or defines some kind of relation between two entities. These include numerical equality (e.g., 5 = 5) and inequalities (e.g., 4 ≥ 3).

### standard relational operators

~=|not equals|lua
!=|not equals|C#|Java|JS
==|equals|most programming languages
‹=|less than or equals|most programming languages
›=|greater than or equals|most programming languages
›|greater than|most programming languages
‹|less than|most programming languages
‹=›|returns 1 if left arg is larger, -1 if right arg is larger, and 0 if both are equal|Perl|Ruby

### types of equality

For anything that is a data structure, there can be two kinds of equality (using Kotlin terminology)
structural equality = equivalent content
referential equality = same reference
Most languages use structural equality for scalars.
comparison operators for non-scalars use...
referential equality|JS, Java, C#
structural equality|Ruby, Python, TS

#### `is`

Python uses the `is` operator for referential equality

### strings

greater/smaller with strings is generally relative to their position in unicode, which for latin characters tracks ASCII and thus "Z" ‹ "a"

### in different languages

#### JS

JS has versions of the equality operators with one extra =. The shorter ones coerce before comparisons. Specifically, any of the shorter ops containing ‹ or › coerce to string or numbers (including null, but not undefined). == coercion is more complicated, but will coerce null to undefined.

#### test

since relational operators are handled by test in sh, they are actually all arguments to test.

test uses the normal equality operators (e.g. !=, ›, etc.) for strings, but has a different set of operators for integer equality.
test uses the single (!) = sign for string comparison, though bash has a non-POSIX extension that allows for the more standard ==

##### integer equality

-ne|is not equal to
-lt|is less than
-le|less than or equal to
-gt|is greater than
-ge|greater than or equal to
-eq|is equal to
Perl uses sh-style comparison operator without the leading -

##### fs equality/existence

test has a number of options/operators for file existence and type

-e foo|foo exists and is a file
-d foo|foo exists and is a directory
-r foo|allowed to read foo

##### [[

[[ is an extension of `test`\[ which allows for a syntax superset (mostly)
specifically, [[ but not test/[ allow for ＆＆ and || for multiple conditions, () for grouping, pattern matching on the right hand side of =/== and the use of ~= for regex matching.
^in fact, POSIX test also doesn't support ‹ and › natively, but these are so commonly supplemented that it's kinda pointless to claim that test doesn't have them
^in fact, POSIX does support grouping with \(\) and and/or with -a, -o, but both of these features are super limited, error-prone, and are marked deprecated, so it makes more sense to say `test` doesn't have them.
Within [[]], in contrast with test/[], there will be no word splitting or globbing.
[[]] and most versions of test allow `!` to negate an entire expression

### comparison with self

Comparing a thing with itself is always true, except for: 
in JS, NaN

### interfaces

Things using the ruby mixin Comparable must define ‹=› operator, and then gain access to the other comparison operators, as well as between? and clamp

is x between foo and bar?
x.between?(foo, bar)|Ruby

### string relational operators used in a set of a language

e.g. CSS attribute selectors, youtube-dl 

^=|begins with value
$=|ends with value
*=|contains value at some point

~=|attr is a whitespace-separated list of words, one of which is exactly value.
bar=|attr  is exactly value or begins with value immediately followed by a hyphen. It is often used for language subcode matches.

## boolean operators

logical and|and|python|liquid|lua|Ruby (lower precedence)
logical and|＆＆|C#|Java|JS|Ruby (higher precedence)|(ba)sh
logical or|or|python|liquid|lua|Ruby (lower precedence)
logical or|barbar|C#|Java|JS|Ruby (higher precedence)|(ba)sh
logical not|not|python
logical not|!|C#|Java|JS

In ruby, between and/or and ＆＆/|| the former have lower precedence, and even have lower precedence than the equality operator.
Double not can generally be used to get the truthiness/falsiness of a thing, even outside of a boolean context.

### short-circuiting

Short circuiting is more properly short-circuit evaluation.
Short-circuit evaluation  an expression stopping evaluating⟮as soon as it's outcome is determined⟯
Short-circuit evaluation is most commonly found in the boolean operators of most programming languages
with short-circuiting of binary operators, the second argument is executed or evaluated only if the first argument does not suffice to determine the value of the expression.
specifically, expr1 LAND expr2 will not evaluate expr2 if expr1 is false/falsy
expr1 LOR expr2 will not evaluate expr2 if expr1 is true/truthy
Can be used to ensure a variable never gets assigned a falsy value by using logical/boolean or, since (only) if the first expression is falsy the second expression will be evaluated.
It is possible to create a kind of if statement using only short-circuiting operators: CONDITION ＆＆ IFTRUE || IFFALSE
(ba)sh

⟮??⟯ is like ⟮||⟯ but ⟮only returns its right-hand value on nullish values⟯

## bitwise

Bitwise operations operate on the underlying binary value (regardless of type in the programming language).
Most C-family languages support bitwise operations.

bitwise not|~
left shift|‹‹ ‹n›
right shift|›› ‹n›
bitwise XOR|^
bitwise OR|bar
bitwise AND|＆

when using the left shift operator, the newly created places will be filled by zero

## math

addition|+
multiplication|*
subtraction|-
division|/|Python: always returns a float, JS: it depends (but no distinction between floats and ints anyway)
floor division|//
remainder|%
power|**
increment|++
decrement|--

unary plus does different things in different languages: in some it does nothing (with numeric types) or throws an error (with non-numeric types). In JS it converts it to an number.


The increment and decrement operators do not exist in python.
The increment and decrement operators behave differently based on their position in relation to the number in some languages: 
++somevar or --somevar will crement first, and then evaluate, somevar++ or somevar-- will evaluate first, and then crement

## comma

In the C and thus in JS, Perl, the comma operator (represented by the token ,) is a binary operator that evaluates its first operand and discards the result, and then evaluates the second operand and returns this value (and type). (this is distinct from the comma e.g. in parameter lists)

A trailing comma is a comma at the end of a list of arguments, array elements, etc. 
In most programming languages (all of them I know), trailing commas are ignored (do not produce an error or empty elements).
In JS, trailing commas produced errors in some situations until recently (the newer ES versions such as 2017)

## element in collection/substring in string?

stringOrColl contains elem|liquid
elem in stringOrColl|Python|JS
stringOrColl.includes(elem, optionalSearchStartPos)

`in` in JS works amusingly if used on arrays: it will look for integer keys, and not for values, so that it will return false for "foo" in ["foo"] but true for 0 in ["foo"] (this is because arrays are objects, and thus the integer keys are actually object keys)

## remove element from collection

del|python
delete|JS

## type of element

typeof foo|JS
type(foo)|Python
std::any::type_name(foo)|Rust

typeof in JS returns a string, and can return 'number', 'string', 'boolean', 'undefined', 'object' or 'function'

typeof...
{a: 1}|'object';
undefined|'undefined';
true|'boolean';
null|'object';
new Date()|'object';
function() {}|'function';
[1, 2, 4]|'object';
NaN|'number';
Infinity|'number';
37|'number';
3.14|'number';
/regex/|'object';
"something"|'string';
""|'string';
!!342|'boolean';
"1"|'string';

To test whether sth is an array in JS, you need to use Array.isArray()

## length of strings, collections, etc.

foo.length|Java|JS|Ruby
foo.Length|C#
len(foo)|Python
#foo|lua|sh (must be surrounded by ${}, and followed by [@] if an array)

length() for strings in perl, merely generating a scalar context is enough for arrays

## spread operator/rest syntax

Both JS and Ruby have an operator that allows them to do similar things in relation to arguments and arrays.
Ruby calls this operator the splat operator, while js calls it a rest operator in the context of callable unit parameters (not arguments), and spread syntax otherwise

...|JS
*|Ruby|python

In the context of callable unit parameters, JS rest syntax and Ruby/Pythons's Splat both gather the remaining arguments into an array. the parameter so marked must be the last in the list.
funcName(1,2,3)
‹keyword› funcName(... OR *foo)
foo will now be [1,2,3]
When not in callable unit parameters, JS spread and Ruby/Pythons splat transform an array into its constituent members, or in the case of assoc arrays into its constituent mappings.
Ruby uses a double splat operator for associative array destructuring.
[... OR *[1,2,3], 4] == [1,2,3,4]
{**{:foo =› 1, :bar =› 2}, :quuz =› 3} == {:foo=›1, :bar=›2, :quuz=›3} and {...{foo: 1, bar:2}, quuz:3} === { foo: 1, bar: 2, quuz: 3 }
Rust's struct update syntax has some similarities to JS associative array destructuring
Rust's struct update syntax uses the oparator ..
for including all values of a struct instance into the current struct instance, use struct update sytnax.

## traits/interfaces/methods that implement math operators

Add|Rust


# callable units

Callable unit is a cover term for anything that can be called, be that functions, methods, procedures...
A call is a thing that executes a callable unit.
Callable units generally can take arguments if specified.

Keyword to start a callable unit
function|JS|Lua|sh|SCSS/Sass (@function ofc)
fn|Rust
def|python|Ruby
sub|perl
no keyword|C#|Java

Callable units can generally be split into callable unit signature and callable unit body. The callable unit signature usually specifies at least return type, name, and parameters, as well as the keyword if necessary. In sh, a callable unit signature contains nothing but the keyword and name/
The body of the callablue unit contains the code to execute.
In java, the callable unit signature also specifies parameter type, access modifier, and optionally staticness/finalness/abstractness.
In JS, function keyword defined callable units generate their own this, while arrow functions do not.

## declaration

In most languages, functions can only be declared in statements, however languages that have functions as first-class citizens often also allow declaration via expressions.
function expressions are generally assigned to variables for later usage.
JS calls function declarations that are statements function declarations, and function declarations that are expressions function expressions.
since classes in JS are merely syntactic sugar for functions, there are also class declarations and class expressions

## signatures

Languages with manifest typing typically require the returned type to be declared in callable unit signatures.
void is commonly used for no return type in languages that require a return type to be specified.
return type is indicated:
-› ‹type› at the end of signature|rust
: ‹type› at the end of signature|TS
‹access-modifier› [static|abstract] ‹type› ‹callable-unit-name›|C#|Java

## returning

Across most languages, the keyword to return whatever value is the `return` keyword.
The datatype of the thing that is returned from a callable unit is known  ⟮The return type⟯
In non-manifestly typed languages, the default return value of a function is the null type
In general, using the return keyword without a value returns the languages null type.
Multiple values: separated by comma|lua
In Rust, using the return keyword is frowned upon, as blocks return their final expression anyway.

### returning and side effects

A side effect is a modification of the state of something that is outside of the local environment the operation is performed in.
A callable unit must return something or have side effects, else it does nothing.
A procedure (using a narrow definition) is a callable unit that does not return a value, instead causing side effects.
A function is a callable unit that returns a value.
A pure function is idempotent and has no side effects.


## closures

A ⟮closure⟯ is the combination of ⟮a callable unit⟯ and ⟮the lexical environment⟯ (= ⟮any variables that were in scope⟯) within which that function was declared.
Closures are created when the functions are created.
All callable units automatically create closures in JS, lua.

### rust

In rust, only closures create closures.
In rust, there are three traits that indicate closures: Fn, FnMut and FnOnce.
Rust decides whether our closure is fn, Fn, FnMut or FnOnce by looking at what the closure does
the keyword `move` before a closure forces the closure to become `FnOnce` (take ownership).
Rust only closes over the environment actually used
In rust, closures don't necessarily need type annotations, however once a closure has been used with a certain type, rust fixes the types and other types become impermissible.
fn|does not form closure (but still can be used as first-class value)
Fn|forms closure of immutable references
FnMut|forms closure of mutable references
FnOnce|forms closure of owned values

## anonymous, first-class, higher-order functions and callbacks

### distinguising

A callable unit not bound to an identifier is an anonymous function/callable unit.
First-class functions/callable units are callable units that are first-class citizens.
A higher order function is a function that takes a first-class function as an argument, or returns a function. All other functions are first-order functions.
callbacks are first-class functions passed to other callable units to be executed at some other point

### relationships

anonymous functios are almost always first-class functions, and are thus often passed as arguments, etc.
However, often non-anonymous functions can also be first-class functions
callback functions are typically also anonymous

### callbacks

The deep nesting of callbacks that result in unreadability is known as callback hell or the pyramid of doom
Error-first callback look like  (err, value) =› ...
Node generally takes error-first callbacks.

### first-class functions

#### which functions are first-class

In JS, lua, python, rust all functions are first-class. 
In Ruby, only functions created with a special syntax are first-class.
While in rust only closures form closures, all functions are in fact first class. Even things written with the closure syntax actually become `fn` type functions if they don't actually close over anything. (tested)

#### types of first-class functions in statically typed languages

In statically typed languages, first-class functions must have a type that describes them.
\(‹ts-param-list›\) =› ‹return-type›|TS
(fn|Fn|FnMut|FnOnce|fn)\([‹param-type›]{, ‹param-type›}\) -› ‹return-type›|Rust

‹ts-param-list› ::= [‹param-name›: ‹param-type›]{, ‹param-name›: ‹param-type›}

### anonymous functions

In JS, anonymous functions have no special syntax, you merely leave out the identifier.

### anonymous first-class functions

#### name

In ruby, anonymous first-class functions are called blocks.
In rust, anonymous first-class functions are called closures.
In JS, there is a special type of first-class anonymous function called an arrow function.

#### syntax

In ruby and rust, parameters to blocks/closures are surrounded by |...|
In ruby and rust, blocks/closures are surrounded by {}
{|params| code...}
In ruby, blocks may also be surrounded by do ... end
In rust, one-line closures may have their curly braces left out.

#### ruby

in ruby, to call a passed block, use the yield keyword. 
Anything passed to the yield keyword will be available as arguments to the block
In ruby, the ＆ operator converts a block to a proc object.
Calling #call on a proc object is similar to yielding a block
instead of a block with the syntax {|elem| elem.method} you can also pass ＆:method for the same effect

#### JS

Arrow functions function similarly to normal js functions, but have a shorter syntax: (‹params›) =› ‹block›.
Instead of a block, you may also specify a single expression, whose value will be returned. 
The parentheses are optional if there is a single param

### IIFE

An immediately invoked function expression (IIFE) uses function scoping to create a fake block scope.
IIFEs were used for the same reasons as block scope is used generally, and preventing hoisting.
IIFEs generally use anonymous functions.
in JS IIFEs need to force an expression to be able to immediately invoke it (since a declaration cannot be immediately invoked)
The most common way to force functions to be expressions is via surrounding them in (), but other ways are possible.
With the introduction ES6 let and const, IIFEs have become mostly irrelevant.



### common higher-order functions

There are many built-in higher order functions, generally as methods on data structure types.
since higher-order functions must take first-class functions as arguments, in languages that only have a special type of anonymous function as a first-class function, a higher-order function must take these.


language|higher-order functions are called on
JS|Arrays
Rust|Iterators


language|higher-order function recieves arguments
JS|value, index wholeArray


In JS, any higher-order function can take a thisArg, which is then the final argument. This argument will be what the passed fucntion recieves as this.

#### map

In many programming languages, map is the name of a higher-order function that applies a given function to each element of a collection, e.g. a list, returning a list of results in the same order. 
thing.map(func)|Java|JS|Ruby|Rust
map(func, iterator)|Perl (is list not iterator though)|Python
Select(func)|C#
no map function|sh|SCSS/Sass

Thing map is called on
arrays (or ggf. other iterables), not iterators|JS|Ruby|C#
iterators, not arrays|Rust
streams (whatever that is, but not the same as an iterator)|Java
globally|Perl|Python

##### flatmap

A flatmap function is a map function which may return an array and which flattens all elements of the array into the resulting thing.
effectively, flatmap is merely map with flat called on the array returned.
Most languages that have map function have a flatmap (flatMap) version of it, except for Python,. C# calls it SelectMany. Perls ordinary map is actually a flatmap, so really perl doesn't have a map.

#### sort

Sort is a higher-order function that takes a function which itself takes two arguments. Depending on the language, return values are handled differently.
JS function must return value smaller 0 if the first argument is to be first, larger 0 if the second argument is to be first, and 0 if it should not reorder.
The sort function passed must be deterministic.
In many languages, sort sorts with a predefined sorting algorithm if no sorting function is provided
In some languages sort does not take a sorting function, instead only using the predefined sorting algorithm, in those languages sort is not a higher-order function.

sorted(foo)|Python (takes an iterable)
foo.sort(callback)|JS (takes an optional sort function, only Arrays)
foo.sort()|Python (in-place!)
foo.sort(may be callback or nothing)|Ruby


#### filter

Filter in a narrow sense is a higher-order function that processes a data structure to produce a new data structure containing exactly those elements which the passed function returns true.
filter()|JS|Rust

#### reduce

The reduce function/method takes a function known as the reducer function
The reducer function recieves the return value of the last execution of the reducer function, and the current element of the collection. 
The reducer function return a single value.
In effect, the reducer function applies an operation to the current element, and the accumulated result of all other elements.
Many languages allow specifying a 'previous result' element for the first time the reducer function runs, as there will not be one.
js has the variant reduceRight that starts from the end
reduce()|JS|Ruby|Python

#### some/every/

some is a higher order-function that takes a function and returns true if the passed function returns true even once.
every is a higher order-function that takes a function and returns true if the passed function returns true for all elements.
JS

python has the functions any(iterable) and all(iterable), that merely return the result of calling bool() on each item, not taking any higher-order function

#### find

find is a higher-order function that takes a function and returns the first element for which the passed function returns true. findIndex instead returns the index.
find()|JS|Ruby
findIndex()|JS
find_index()|Ruby



## arguments ＆ parameters

### arguments vs parameters

How are parameters and arguments are often used synonymously, although they are more properly not synonyms
for a callable unit,  ⟮parameters⟯ are the values you specify the function will be passed, most commonly in its signature.
for a calllable unit, arguments are the values/variables you actually pass.
When passing things, using a car metaphor, you can think of the ⟮parameter⟯ as a ⟮parking space⟯ and the ⟮argument⟯ as an ⟮automobile⟯
function foo(a, b){...
foo(12, "whistles") 
a, b are parameters, 12, "whistles" are arguments

### syntax

#### both

most languages separate both the parameteres and arguments with commas.
sh separates arguments with space

#### parameters

most languages require the possible parameters defined in a callable unit definition to be wrapped in parantheses.
sh doesn't allow specifying parameters at all

#### arguments

most languages require the arguments to a function call to be wrapped in parentheses.
sh does not wrap arguments at all

Exceptions:
1 arg doesn't need parens|lua
always optional|ruby|perl
never|sh

### operations

#### refer to all passed arguments as an array

$@|(ba)sh
arguments|JS (not arrow functions)

#### amount of arguments passed

\$#|(ba)sh

### positional and named

#### definition

A positional argument is one where the language knows which parameter to assign it to based on its position in the argument list.
A named argument is one where the language knows which parameter to assign it to because it directly refers to the name of the parameter.
While arguments may be positional or named, the parameters themselves nearly always have names. However, in sh parameters do not have names, instead you refer to them positionally via $0...$9. 

#### in languages

positional parameters exist in pretty much all languages, except GraphQL
named parameters exist in GraphQL, Python, SCSS/Sass @mixin, @function

#### positional

##### operations

###### move

Move remove the first positional argument and shift all arguments one to the left
shift|Perl|sh

#### named

Named arguments usually use normal assignment syntax

### default parameters

#### definition

A default parameter is one which will take on a default value if no argument for it is specified in the call.

#### syntax

the general syntax is `paramname = defaultval` (within the parameter list)

#### in languages

GraphQL, Python, JS, SCSS/Sass @mixin, @function have default parameters TODO Check other languages

#### interaction with null

In general, default parameters will also take on the default value if the argument passed is the language's null type. 
In JS, the default parameter will take on the default value if undefined is passed as an argument, but not if null is passed.

### optional

#### general situation

In most languages, callable units must be recieve the exact amount of arguments specified as parameters, unless things like the splat operator or default parameters are used.

#### JS ＆ TS

JS does not require the same number of arguments as parameters, it will assign unpassed parameters `undefined`, and put all arguments into the array-like `arguments`, allowing for retrieval of extra arguments.
TS moves JS in line with other programming languages, requiring arguments for parameters by default, and only accepting the not-passing of arguments if the parameter is optional.

#### marking as optional

in TS, optional parameters and optional fields are marked with a ? after the name, which changes their type to be whatever | undefined

### evaluation strategy

An evaluation strategy is a set of rules for evaluating expressions.
Evaluation is equivalent to reduction in math.
The concern most of interest within the evaluation strategy is the parameter-passing strategy.
The fundamental parameter passing strategy distinction is between strict/eager evaluation/applicative order and non-strict/lazy evaluation/normal order.
The parameter passing strategy may be the same for all constructs in a language, there may be keywords or other constructs to indicate the parameter passing strategy, or the strategy may differ by context/value.
Different implementations of parameter-passing strategies are often called call by x or pass by x.

Arguments are generally bound to parameters. 

A function is strict if it evaluates to ⊥ if one of its arguments evaluates to ⊥
= A function is strict if it fails to evaluate/terminate if one of its arguments also fails to evaluate/terminate.
Strict evaluation is evaluation that guarantees a function is stict.
Applicative order makes sure a function is strict by evaluating its arguments before the function is applied.
A function is non-strict if does not necessarily evaluate to ⊥ if one of its arguments evaluates to ⊥
A function is non-strict if it does not necessarily fail to evaluate/terminate if one of its arguments also fails to evaluate/terminate.
Non-strict evaluation is evaluation that does not guarantee that a function is strict
Normal order implements non-strictness by evaluating its arguments only once they are used within the function.
In math, strict reduction proceeds from the inside out, so that hitting a bottom type will always be encountered.
In math, non-strict reduction proceeds from the outside in, so that something containing a bottom type may have already been eliminated by outer reductions.
Applicative order is a rough synonym to eager evaluation.
Normal order is a rough synonym to lazy evaluation

Call-by name implemens normal order by substituting the arguments of a function into the function body.
Call-by-need is a memoized version of call-by-name.

##### extracurricular binding

JS's bind() method has the potential to change the idea that arguments passed to a function call are bound to parameters.
JS's bind() is called on a function.
JS's bind() method binds the first argument that it is passed to the this of the function, and any following arguments to the parameters of the function it was called on.

##### applicative order

call/pass-by-value/-reference/sharing are all forms of strict evaluation.

call/pass-by-value|pass the value of the expression/variable (= copying)|changes to passed variable will be lost if not returned
call/pass-by-reference|pass the reference of variable (i.e. the loc in memory)|changes to passed variable (incl reassignments) will be preserved even if not returned
call/pass-by-sharing/object/object-reference|pass by value, but only the object reference for objects|changes to passed variables contents will be preserved even if not returned if object, reassignments will not.

Most popular languages with objects that are said to be pass-by-value are actually pass-by-sharing.
In purely functional languages, cb/pb value ＆ reference are the same.
In purely functional languages, everything is immutable, so while the semantics are similar to pb value fron the outside, inside actually only references are passed (since it's cheaper), thus it is actually pb reference
Call by sharing is a term that is kinda rarely used.
In call-by-sharing

sharing|lua|JS|Java

moving seems like copying b/c you can't mess with it after, but in fact ofc only the reference changes hand.

##### non-strict binding

## asynchronous callable units

Asynchrony, in computer programming, refers to the occurrence of events independent of the main program flow and ways to deal with such events.  

A process that is blocked is one that is waiting for some event, such as a resource becoming available or the completion of an I/O operation.
A blocked process cannot do anything in the meantime.
Asynchrony is a common way to deal with blocking.

A promise is a proxy for a value that will eventually become available.
In JS, a promise is an object
You react to promises by calling the then() method on them.
In JS, something you can call then() on is called a thenable.
in JS, most interfaces for promises work on any thenables.
A promise can have the states ⟮pending⟯, ⟮fulfilled⟯, or ⟮rejected⟯.
A promise is called ⟮settled⟯ if it is either ⟮fulfilled⟯, or ⟮rejected⟯.
Ergo a promise is either settled or pending.
We may return a rejected promise manually, additonally, if an error occurs in our async function, it will reject automatically.
Once a promise has settled, the attached thens will run as soon as possible / awaits will resolve.
If a promise is settled, and we then attach a then()/catch()/finally(), it will run immediately
While a promise is pending, thens will not yet run / awaits will not yet resolve.
A promise may have the fates resolved, unresolved.
Whether a promise is resolved depends on whether we can still resolve it: If we can still resolve a promise, it is unresolved, otherwise resolved.
A promise being resolved means that its outcome is already determined, even if we may not yet have the outcome.
Promises with the states fulfilled or rejected also have the fate resolved.
A promise with the state pending is resolved if it has been resolved to a itself pending Promise, else a promise that is pending is also unresovled.
//generally true, not jus js

In many languages, the async keyword marks the callable unit as asynchronous and allows it to call asynchronous functions.
await is a keyword/function available in many programming languages that calls an asynchronous function and then returns the value the function returns once it does.
In JS (and other languages w/ promises), await takes a promise (and is the rough equivalent of calling then() on it)
to handle errors resulting from await, use try/catch as normal.

In JS, then() takes two callbacks, one to run in case fullfilment and one to run in case rejection.
then(), catch() and finally() themselves return thenables, which allow them to be chained.
is the thing the last promise returned is what then(), catch(), and finally() get as an argument. What they get depends on if the callback running is one for rejection or one for fulfillment
In JS, catch() is a version of then() with only the callback to run in case of rejection, finally() is a version whose callback will run no matter if rejeciton or fulfillment
In JS, async functions always return promises.

you can create promises in a number of ways
create a promise that is already rejected: Promise.reject(reason)
create a promise that is already resolved: Promise.resolve(value)
If it is passed a non-promise, it will immediately be fulfilled w/ that value, if it is passed a promise it will be resolved to that promise

creating a new promise (that is not auto-rejected/resolve)is done via the promise constructor.
The promise constructor takes a callback known as the executor function.
the executor function itself takes the arguments resolutionFunc, rejectionFunc.
We do not implement resolutionFunc and rejectionFunc ourselves, the executor function will get them passed in when necessary.
The only thing we do with the executor functions argumetns resolutionFunc and rejectionFunc is call them when we want to resolve/reject.
As with the Promise.resolve and .reject, you pass the rejectionFunc the reason for rejecting, and the resolutionFunc the thing you want to fulfill with, or another promise

JS has a few methods for acting on multiple promises at once:
Promise.race() takes n promises and runs the attached callback ⁑once⁑ the first promise resolves.
Promise.all()/allResolved() runs the attached callback once all passed promises are resolved. The attached callback will recieve all returned results as an array.
⟮Promise.allSettled()⟯ is like ⟮Promise.all()⟯, but the ⟮former⟯ will ⟮continue even if one rejects⟯, the ⟮latter⟯ will ⟮not⟯

Pretty much all operations of the fs module in node have an ⟮async⟯ and a ⟮synchronous⟯ method, where if the ⟮async⟯ method is called `⟮foo⟯` the ⟮synchronous⟯ method is called `⟮fooSync⟯`
In node, asynchrony is by default implemented via callbacks.
In node, any asynchronous operation that could fail takes a error callback.
In node, any asynchronous operation that could return something useful takes a success callback.
in node, most functions are still designed for callbacks, however you can use util.promisify().
util.promisif()y takes a function following with a error-first callback as the last argument, and returns a version that returns promises.

Promisifying is making someting return a promise which wouldn't normally.

### asynchronous techniques

hooks and event handlers are asynchronous programming techniqyes.

#### hooks

A hook is an action that is defined on a thing and is called when the thing is in a certain state, e.g. before a function call.

#### events

Technically, an event listener watches for an event, at which point it calls the event handler to deal with it.
In casual use, event listener and event handler are synonyms.

## misc

Memoization is the form of caching that caches the return value of a deterministic callable unit

### recursion

recursion ≈ self-inclusion
