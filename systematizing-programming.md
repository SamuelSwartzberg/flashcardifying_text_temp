<h2>Statements</h2>

A statement separator is used to demarcate boundaries between two separate statements. A statement terminator is used to demarcate the end of an individual statement.
Semicolons are used in programming languages for two things: statement separators and statement terminators. When a language uses semicolons as statement separators, this allows you to write more than one statement on the same line.
Semicolons as statement terminators aren’t optional and are used to definitively mark the end of a statement.

Typically, even if programming languages have semicolons as statement terminators, they don't go after block statements. JS is the exception to this, where you can but don't have to do this.

semicolons as statement separators and statement terminators|C#|Java|Perl|Rust
semicolons as statement separators, no statement terminators exist in language|Lua|Python|Ruby
semicolons as statement separators and statement terminators, complex exceptions apply|JS

<h3>Blocks</h3>

<div class="cloze-group-children hide-if-inactive-children">
  §§ In ((c:3;::most programming languages)), a ((c:2;::block)) is a ((c:1;::statement)).  §<br>
§§ However, in ((c:4;::Rust)) (and in ruby to, though its weird, as blocks have the same syntax/are merely anon functions w/o arguments), ((c:5;::blocks)) are ((c:6;::expressions)). §<br>

§§ ((c:7;::Blocks)) ((c:8;::contain/consist of)) ((c:9;::one or more)) ((c:10;::statements)). §<br>
§§ ((c:11;::In/with)) ((c:11;::constructs)) or ((c:11;::languages)) that are ((c:12;::block-scoped)), ((c:13;::a block defines a scope)). §<br>
  §§ ((c:14;::Curly-brace/bracket languages))&nbsp;are defined as languages that ((c:15;::use curly-braces)) ((c:16;::to define blocks)). §<br>
  (ba)sh is not generally a curly-brace language, but it still allows creating block statements via {}
§§ Examples of ((c:17;::curly-brace/bracket languages)) I can write are ((c:18;::C#)), ((c:19;::ECMAScript)) -&gt; {((c:19;::Javascript)), ((c:19;::TypeScript))}, ((c:20;::Java)), ((c:21;::Perl)), ((c:22;::Rust)), SCSS (but not Sass). §<br>
§§ Most ((c:23;::curly-brace/bracket languages)) ((c:24;::are thus because they are strongly influenced by)) ((c:25;::C)). §<br>
In some programming languages (JS, Lua, ...?) blocks can stand alone, merely creating a scope. In other programming languages, blocks must follow a certain statement.
In lua, blocks end with <code>end</code> (outside of repeat...until). They are begun by <code>do</code> when standing alone, or when after a loop, by <code>then</code> after an if condition, and by nothing after a function signature
In bash, blocks for if are delimited by then ... (possible else etc.) fi, for for and while by do ... done, for case by in ... esac
In ruby, blocks end with <code>end</code>. begin begins a dedicated block statement (and is the keyword for the error handling statement), but no other blocks
In python, pretty much anything (control structure, function, etc) that precedes a block ends with `:`. In Ruby by contrast (which otherwise may look pretty similar), nothing ends with `:`
In some languages, notably Ruby and Rust, block expression return the value of the last statement

liquid|{% keyword %} ... {% endkeyword %}
python|Sass|indentation

<h2> control flow</h2>
The default control flow is linear from top to bottom, this is called sequencing.

<h2>control structures</h2>

<span class='line'>A thing that modifies control flow is a control structure. 

<span class='line'>A control structure takes the normally linear flow of code and makes it somehow nonlinear.
Control structures are typically statements, however in Ruby and Rust, they are expressions.
<span class='line'>In javascript or JS, most control structures take one statement after it, which can either be a normal statement or a block statement. A statement that does nothing is an empty statement
If control structures have conditions, they are delimited by...

()|C|JS|Java|C#|Perl
nothing|Python|Ruby|Rust|Lua
[]|Shell (is actually just test symlinked as  [)

(ba)sh requires all operators and the [] themselves to be separated by spaces, since [ is actually just a symlink for test, and thus all of these are actually arguments for a command.

<h3>choice/selection control structures</h3>

<p>
choice/selection control structures allows choosing between several alternatives based one or more conditons.
choice/selection control structures constructs are also just called conditionals.
In conditionals, any of the possible paths is called a branch.
</p>


The most common conditional is if/then/else. 
  
the if/then/(else) conditional is typically a statement (in rust, it's an expression).
  An if/then(else) conditional is started by <code>if</code> in nearly all programming languages
  the else arm of an if/then(else) conditional is started by <code>else</code> in nearly all programming languages
  elsif|liquid|perl|ruby
  elif|Python|(ba)sh
  elseif|lua
  else if|C#|Java|JS|SCSS?Ass



The ternary operator is a conditional which is typically an expression. 
  
The ternary operator is more properly called conditional operator. 
  
The conditional operator typically has the syntax &lt;condition&gt; ? &lt;iftrue&gt; : &lt;iffalse&gt;. 
The conditional operator comes from C (more properly an early ancestor of C), thus most programming languages that are inspired by C have it. 
  Example in JS:
  <code
    >let attack = enemy.isFireType() ? this.attacks.thundershock :
    this.attacks.inferno;</code
  >
Languages that I can write that <b>don't</b> have a ternary/conditional operator with the typical syntax are Bash (more precisely, only exists for arithmetic expressions), Lua, Python, and Rust.



An if statement/expression, but reversed in its truth value, is an unless statement/expression.
unless statements/expressions use the keyword unless.
unless statements exist in liquid, perl, ruby


Some languages (Perl, Ruby), allow a one-line conditional, where the syntax is &lt;expression&gt; &lt;conditional&gt; (we might term this a postfix notation)
for the postfix conditionals in perl, ruby




switch is a type of conditional.
the switch conditional is generally a statement.
the switch conditional generally has one condition, and then n branches for possible values.
Besides the branches for possible values of the conditional, the switch conditional generally also allows for a default case.
The default for switch statements is optional in JS
In many languages switch conditionals feature fallthrough, which is where it will continue even after the case ends, until it hits a break/return statement.
switch conditioals are generally started by the <code>case</code> keyword.
Different cases for a switch conditional are started by <code>switch</code> in Java, JS and by <code>when</code> in liquid, ruby.
In liquid, ruby, multiple cases are separated by commas.
The default case for a switch conditional is <code>default</code>  in Java, JS, and <code>else</code> in liquid, ruby.
Bash has a fucked-up syntax: case &lt;expression&gt; in {&lt;case&gt;) &lt;command&gt; ;;} esac
Rust instead has match

JS Syntax examples:

<h2>switch</h2>
<pre><code>switch (expression) {
  {{c1::case}} {{c2::}}value1{{c2::}}{{c3:::}}
   //Statements;
   {{c4::default:}}
}</code></pre>

<h3>Iteration/Loop control structure </h3>

Control flow that repeats the code a number of times is called iteration/looping


Count-controlled loops
Count-controlled loops are loops that repeat a piece of code a certain number of times.
Count-controlled loops are often started with the keyword for.
Count-controlled loops are often called for-loops.
The typical syntax for count-controlled loops inheriting from C (e.g. C#, Java, JS, Perl) is 
for &lt;delimiter&gt; counter initialization; counter end condition; counter change per loop &lt;delimiter&gt; block
SCSS/Sass instead has the syntax @for <variable> from <lowerbound> to (excl)/through (incl) <upperbound>


Condition-controlled loops


A condition-controlled loop is aloop that repeats until a condition changes.
condition-controlled loops can begin or end with their condtion, in which case they will run at least 0 or at least 1 time.
condition-controlled loops that test at the beginning of the loop are often started with the keyword <code>while</code> and are often called while-loops. 
condition-controlled loops that test at the end of the loop are often started with the keyword do, then a block, then end with the keyword while followed by the condition and are often called do-while-loops.
Most programming languages I know have while and do-while loops, in fact I don't think I know a programming language that doesn't have a while loop.
Perl has a while loop with an inverted condition (analogous to unless) called until.
Lua also has a while loop with an inverted condition that tests at the end of the loop with the syntax repeat ... until



Collection-controlled loops 


A collection-controlled loop is a loop that loops over all elements of a thing.
Collection-controlled loops are commonly called foreach loops.
  Collection-controlled loops most commonly start with the keyword <code>for</code>, but then feature a different syntax than count-controlled loops. In perl, they instead start <code>foreach</code>.
  Collection-controlled loops generally work on iterators, or by transforming the thing into an iterator implicitly.
  Lua: for &lt;expression&gt; do
  bash, Liquid, Python, Ruby, Rust: for <expression> in <iterable> ...
  Java: for (<type> <element> : <iterable>) ...
  JS: for (<variable> in <object>) ... (only used to iterate over all key-value pairs of an assoc array)
  for (<variable> of <iterable>) ...
  SCSS: @each <variable> in  <iterable>
Some languages have collection-controlled loops that are called as methods on a collection or iterable (these are higher-order fucntions)
iterable/enumerable.each(block)|Ruby
somearr.forEach(anonFunc)|JS

When iterating through something that returns multiple values, the expression may need to destructure the values out, or may just list n variables with commas, depending on the language

bash for in is actually the only loop using for that it has. It's also weird in that what it loops through is an $IFS separated list

Infinite loop

loop|Ruby|Rust

takes a block in ruby




Many languages provide a statement which allows skipping the current (continuing with the next) iteration of a loop.
Most languages use the continue statement to continue with the next loop, Perl and Ruby use the next statement.
Many languages provide a statement which allows ending/exiting the loop.
Most languages use the break statement to end/exit the loop, Perl uses the last statement.
In Rust, you can pass an argument to the break thing to have that be the return value of the block expression


Sometimes, loops have an else clause. In python, this runs at the end if we never break out of the loop. In liquid, this runs if the loop is empty

(loops with reversed condition do not count as separate kinds of loops)
lang|count-cont|cond-cont|col-cont|infinite
lua|1|2|1|0
liquid|0|0|1|0
Python|0|1|1|0
JS|1|1|2|0
SCSS|1|1|1|0
Rust|0|1|1|1

<h3>Labels</h3>

A label in a programming language is a sequence of characters that identifies a location within source code. In most languages labels take the form of an identifier, often followed by a punctuation character (e.g., a colon). 
JS and C have labels.
JS label syntax: <name>:
Labels can be used to break out of a loop that is not the enclosing one.

<h2>other statements</h2>

Empty statements are useful if a statement is required syntactically, but there is nothing to do, e.g. when writing outlines

;|JS|C#
pass|Python
:|(ba)sh

: is actually more complicated. It is kinda similar to true, and is therefore used as a condition for an infinite while loop.

<h2>Comments</h2>

Comments in programming are (generally) ignored by compilers/interpreters.
But: Conditional comments are conditional statements interpreted by Microsoft Internet Explorer versions 5 through 9 in HTML source code. They can be used to provide and hide code to and from these versions of Internet Explorer. 
Comments are written primarily for humans
Generally, single line comments go to the end of the line

Single line:
--|lua
//|C#|Java|JS|Rust|SCSS/sass ('silent', will not end up compiling to CSS)
\#|cron|gitignore|hosts|i3 config|Markdown|m3u|Perl|Python|Ruby|sh|TOML|YAML
%|Latex
(?#foo)|Regex
(* foo *)|ENBF

Multiline:
--\[\[foo]]|lua
/\*foo\*/|CSS|C#|Java|JS|Rust
&lt;!-- foo -->|HTML
=begin foo =end|Ruby
{% comment %} ... {% endcomment %}|Liquid

Documentation
for the following thing|///|Rust
for the following thing|/**...*/|Java (Javadoc)
for the thing we are in right now|//!|Rust
for the thing we are in right now|"""foo"""|Python (docstring, must be first line in function, technically not a comment but performs similar function)

Rust documentation comments accept formatting in markdown. Code in code blocks there is executed as tests.

Documentation comments often generate HTML documentation

<h2>Polymorphism</h2>

something is monomorphic if it works for one type
something is polymorphic if it works for several different types
monomorphization is a compile-time process in which polymorphic code is transformed into n monomorphic variants

ad-hoc polymorphism is polymorphism where different implementations are selected based on the type of the argument(s)
-> callable unit overloading, operator overloading

<h3>dispatch (prob belongs somewhere else)</h3>

dispatch is choosing which method should be invoked in response to a method
displatch is based on the type of the thing
dispatch is only relevant if there are multiple implementations of a thing.

<h4>static dispatch</h4>

static dispatch is choosing an implementation of a polymorphic operation at compile time
callable unit overloading and operator overloading are forms of static dispatch, since the implementation is chosen based on the declared type of the parameters

<h4>dynamic dispatch</h4>

dynamic dispatch is choosing an implementation of a polymorphic operation at runtime
both single dispatch and multiple dispatch are forms of dynamic dispatch

single dispatch is where only the type of one parameter (the reciever of the message = the thing it was called on, mostly) is used to choose the implementation

multiple dispatch is where the type of multiple parameters (the reciever of the message = the thing it was called on) as well as the method parameters is used to choose the implementation

<h3>parametric polymorphism</h3>

A generic is a stand-in for a type that is not yet specified or unknown. 
A generic may be constrained in some way.
Generics are most often specified via type parameters.
Parametric polymorphism is polymorphism that only uses one implementation, instead taking a generic (that is perhaps subject to some contraints) and performing one's operatons based on that.

<h3>subtyping</h3>

<h2>Identifiers</h2>

An identifier is opaque if it provides no information about the thing it identifies
A transparent identifier provides information about the thing it identifies.

<h3>Name binding</h3>

Name binding is the association of entities with identifiers.
For an identifier to reference something is to the identifier bound to that thing.
Binding is intimately connected with scoping, as scope determines which names bind to which objects.
static = early binding is name binding during compile-time
dynamic = late binding is name binding during runtime



<h3>Scope</h3>

the scope of a name binding is the part of a program where the name binding is valid.

<h4>Lexical & dynamic</h4>

<h4>Shadowing</h4>

Name masking/shadowing is when a name in a inner scope overrides that same name in an outer scope
Variable masking/shadowing is name shadowing involving variables

<h4>Variable Keywords</h4>

Block-scoped variables
my|perl
local|lua
let|JS
ø|Ruby

Global variables
ø|lua|perl
$|Ruby

Function-scoped variables
var|JS

Variable scope in python is not determined by keyword but by context.
In JS, variables declared without a keyword become properties of the global object


<h4>Hoisting</h4>

Hoisting moves declarations but not initializations to the top of the scope.
in JS, var variables and function declarations (but not function expressions) and hoisted.

<h3>Case</h3>

snake_case|variables, methods (, symbols)|ruby|python (use underscores sparingly)
UpperCamelCase|classes|C#|Javaruby
SCREAMING_SNAKE_CASE|constants|ruby
camelCase
snake_case|shell variables|(ba)sh
SCREAMING_SNAKE_CASE|environment variables|(ba)sh
_leading_underscore_snake_case|fake private variables|(ba)sh

most programming languages are case-sensitive as regards identifiers.

<h3>Naming</h3>

While there is variety in what is allowed in a identifier name, most commonly it is [a-zA-Z0-9_]
JS also allow $ in a non-sigil way in identifier names.
JS identifiers may not start with a number, but with any other allowed character.
In general, identifiers may not be keywords.

<h3>Shadowing</h3>

In rust, shadowing allows for 'changing' tye type of the variable (really merely declaring a new variable)

<h2>Values</h2>

<h3>Memory-management</h3>

<h4>Ownership</h4>

In rust, eveary value has exactly one owner.
Owners are variables(/constants).
Assigning a value to a second variable invalidates the first reference.
When we assign a value to something different, thus changing the owner and invalidating the first reference/owner, we call this moving.
When a owner goes out of scope, a value is dropped.

<h2>Variables</h2>

In lua, values are typed, but variables are not. 



<h3>Declaration and initialization</h3>

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

<h3>assignment</h3>

= is used as the assignment operator in most programming languages
sh is special in its assignment operator, since it does not allows spaces on either side
SCSS/Sass uses : as the assignment operator.
In most languages, assignment expressions evaluate to the value assigned.
Many languages have combinations of their math/string concat and assignment operators to combine these two operations (e.g. +=)

<h4>Destructuring</h4>

Destructuring is binding variables to values in a way that does not correspond to the 1 variable - 1 value pattern

In many languages, the comma can be used for multiple assignment, most commonly like so:
a, b = 1, 2|Python|Ruby
This is often a form of destructuring under the hood.

[var1, var2] = [value1, value2] or preexisting array|JS|Python
var1, var2 = [value1, value2] or preexisting array |Python|Ruby

In general, you can destructure that language's linear collections (esp. if primitive) and iterables.
In JS you can also destructure the assoc array structure.
Destructuring an array(like) requires array delimiters ([]) in JS, python doesn't want any delimiters, and python wants a tuple, which may mean no delimiters or () if needed for nesting etc.
use normal default value syntax to assign default values in array destructuring|JS only
combine spread syntax/splat operator w/ destructuring|JS|Ruby|Python
var1, *var2 = [1,2,3]
[var1, ...var2] = [1, 2, 3];
=> var2 = [2, 3]
Ignore a single value in destructuring
, (e.g. var1,,var2)|JS
_, (e.g. var1,_,var2)|Python|Ruby

Ignore multiple values in destructuring
*_, (e.g. var1,_*,var2 )|Python|ruby
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

<h3>Sigils<h3>

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

in sh, referring to a variable outside of a ${} context requires the $ sigil, however assigning to a variable does not use the $ sigil
In SCSS/Sass, any variable requires teh $ sigil
 

<h3>Declaring multiple variables</h3>

a, b = 1, 2 (or e.g. returnTwoValues()) (lua, python)

<h3>Constants (and not)</h3>

Mutability is whether something can be changed after inital creation. Something is mutable if it can be changed, and immutable if it can't.
Different things can have mutability: Objects, variables, (though generally not primitves).
Some languages make a difference in which keywords are used to declare constants and variables.
Constants are immutable, while variables are mutable.

Keyword for constants:
const|JS|Rust
final|Java

Keyword for variables:
let|Rust

In rust, even variables are immutable by default, and the keyword mut makes them mutable.
In JS, consts are always block-scoped.
In some languages (JS), consts must be initialized in the same statement as they are declared.

<h3>Default variables</h3>

In Perl there is a special variable $_. There are many places in programming language Perl where if you do not explicitly specify a variable, the variable will be used $_. There are key words that read the values from this variable, and there are those which set of values in this variable. (also sometimes exists as @_ and %_)

<h2>(Data) types</h2>

An abstract data type is defined in terms of its behavior or more specifically its semantics, instead of in terms of its syntax.
If an abstract data type is a description of what something does, a data structure is how something does it.
Lua boolean
literals: true/false A null pointer/reference/type/value indicates that we're
not referring to a valid thing
Datatypes implemented in a programming language can either be scalar or compound/composite
Bash is fun in that it does not have data types at all, in truth all values are strings

<h3>primitives and composites</h3>

Primitive may refer to a data type that is provided in a programming language as a basic building block.
Composite data types are built from primitive data types. 
Primitive may also refer to a type that has built-in language support.

<h5>primitive types in different languages</h5>

C#: int, float, bool, string, char, double
Java: byte, short, int, long, float, double, char, String, boolean
JS: Number, boolean, null, undefined, string, object, array
Rust: 
scalar: integer, floating-point numbers, booleans, chars
nonscalar: tuple, array
Python: integers, floats, complex numbers



<h3>Type Systems</h3>

A (data) type consists of a set of values that something with that type can assume.
A datatype T1 whose set of values is a subset of a datatype T2 is a subtype of T2.
A datatype T1 whose set of values is a superset of a datatype T2 is a supertype of T2.

<h4>Dynamic vs Static typing</h4>

Dynamic typigng: type checking at runtime ≈ values have type
Static typing: type checking at compile time ≈ variables have type

Dynamically typed languages I know: JavaScript, Lua, Python, Ruby
Statically typed languages I know: C#, Java, Perl (with regards to the scalar, array, hash distinction), Rust, TS
TS makes the normally dynamically typed JS statically typed

<h4>Type inference/manifest</h4>

Explicit/manifest typing is a feature of a type system where the type has to be explicitly declared.
Implicit/latent typing is a feature of a type system where the type is not explicitly declared.
Implicit/latent typing  <-> Explicit/manifest typing 
Type inference is a rough synonym for implict/latent typing, but is often used in contexts where the language is otherwise generally explicitly/manifestly typed.
Only statically typed languages can usefully be explicitly/manifestly typed
Type inference in C#: var 
in TS and Rust, often type inference is possible automatically 
Type inference in TS/Rust is more likely to work for anonymous functions

Manifestly and statically typed languages can be more effort to write, but also dramatically lower the chance of bugs.

<h5>Type annotation</h5>

Specifying the type of a thing (esp. a variable/constant) by writing the type into the code is known as type annotation.
Languages with manifest typing generally require type annotation for variable/constants/parameters as well as return types.
In most (esp. C-influenced) languages, type annotation goes before the variable/constant.
In Python, Rust and TS, type annotation looks like so `: type`
Python supports type annotation since Python .35

<h6>Type aliasees</h6>

Type aliases are names for types thsat abbreviate longer type descriptions.
Where type aliases exist, they generally use the type keyword.
`type ID  = number | string`

<h6>Interesting keywords</h6>

<h4>Conversion, coercion, casting and context (plus truthy/falsiness)</h4>

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

<h6>Type annotation keywords</h6>

In general, certain types are generally indicated similarly across programming languages (though there is variation)
Integers|int|not Rust
Floating-point numbers|float|not Rust
Booleans|bool|C#, Rust
Booleans|boolean|Java
Characters|char|C#, Java, Rust
Double-precision floating-point numbers|double|C#, Java

In rust:
Numeric types: &lt;type&gt;&lt;size&gt;
signed integer|i|i16, i128, isize,...
unsigned integer|u|u32, u64, usize,...
floating-point|f|f32, f64
size as part of the type annotation (usize, isize) indicates the system word size 

<h5>Conversion</h5>

All pythons types, called as a function, convert to that type (e.g. list(), bool(), int())
Ruby has a set of methods that have the syntax foo.to_&lt;char&gt; that convert to that type (e.g. to_i, to_f, to_s, to_sym)

<h5>Coercion</h5>

JS will coerce extensively in the case of operations w/ mismatched types.
Concatenation of non-string w/ string|coerces non-string to string
use of booleans w/ math operators|coerce to 0/1
In contrast, pythons operators rarely coerce.

<h5>Casting</h5>

!!type|YAML
(type)|JS

Type assertions in TS are the equivalent of type casting in other languages.
In TS, if {{c2::you know something about a type that TS doesn't}}, you can use {{c1::type assertions}}
TS type assertion syntax: prepending {{c2::&lt;some_type&gt;}} or appending {{c1::as some_type}}


<h4>Firstclassness</h4>

Lua: all values

<h4>Union type</h4>

A union type specifies a number of types that anything with the union type as type may take.
with {{c1::union}} types, you can only use things that {{c2::all of the relevent types can do}}, unless you {{c3::narrow them down}}
Syntax in Python and TS: type1 | type2 ...

<h4>Literal types</h4>

A literal type is a type that can take on exactly one value which is specified via the literal of another type (e.g. 4 or true or "ara ara")
A literal type is a type of unit type.

<h4>Top types and bottom types</h4>

A top type is the supertype of every othe type.
Any value can be assigned to the top type.
A bottom type is the subtype of every other type.
No value can be assigned to the bottom type.
Using the bottom type is useful when you want to specify a value with which you can do truly nothing.

A top type is often also the type that is at the top of the class hierarchy, in languages where such a thing exists

no bottom type|most languages
! (called the never type)|Rust
never|TS

object|Python
unknown|TS
UNIVERSAL|Perl
java.lang.Object|Java
System.Object|C#
BasicObject|Ruby


<h3>Symbols</h3>

Symbols as a datatype are guaranteed to be unique, and generally have a human-readable representation.
The fact that symbols are guaranteed to be uniqe mean that they are equal only to themselves.
In some languages, two symbol literals with the same name are equal to each other, for example in Ruby (:foo == :foo # true)
In some languages, two symbol literals with the same name are not equal to each other, for example in JS (Symbol("foo") === Symbol("foo") // false). Even in those languages, the same instance of a symbol is always equal to itself
Often, the main use of symbols is as object keys to avoid key collisons, or to act as alternatives to enums
Internally, symbols are often represented by a number.

:name|Ruby
Symbol("name")|JS

<h3>Dates</h3>

Most common format is RFC 3339 / ISO 8601

<h3>Null types</h3>

nil|lua|liquid|ruby
null|C#|Java|JS (secondary)
undefined|JS (primary)
there isn't one|Rust

Liquid has a special null-like type that is returned when accessing a deleted object called EmptyDrop
In JS a type is nullish if it is null or undefined.

<h4> nullable</h34>
Nullable types are a feature of some programming languages which allow the value to be set to the special value NULL instead of the usual possible values of the data type.

<h3>Option type</h3>

An option type is a type that represents an optional value.
An option type can generally take on a state representing it is empty, or a state representing it is full, and wrapping around another value.
In rust, the option type is implemented as an enum.
In rust, the option type is 
pub enum Option<T> {
  None,
  Some(T),
}

In general, either option types or nullable types will be used to represent the absence of a value in a given language, but no both.

<h3>boolean</h3>

A boolean data type is a type that has one of two possible values, indicating
truth values.

true/false|C#|Java|JavaScript|Lua|Ruby|Rust|TOML|YAML
True/False|Python|(YAML)
yes/no|YAML
no boolean type, only truthy/falsiness|Python

YAML is not boolean keyword case sensitive

<h3>Numeric types</h3>

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

<h4>Overflow</h4>

If a numeric type has arbitrary precision, it can store (nearly) infinitely large numbers (it will in practice be limited by the memory the application can get from the OS)
overflow/underflow occurs when a numeric value is to large/small for its container.
Numeric types either have arbitrary precsion, are subject to overflow/underflow, or need to throw an error if a calculation exeeds the size limit of a numeric type.
Rust throws an error in overflow/underflow scenarios when debugging, and wrap otherwise.

<h4>Integers</h4>

Integer literals generally not overtly marked

<h4>float and double</h4>

In Java and C#, to indicate a float literal you must add f as a suffix. any number containing a decimal point not explicitly indicated as a float will be a double
Most other languages don't distinguish between floats and doubles on a keyword level, merely by size (rust) or automatically
TODO: Check the above sentence and add more understanding on the difference between a float and a double-precision float on a conceptual level as distinct from how programming languages call them.

<h3>enums</h3>

Enum is short for enumeration or enumerated datatype.
An enum is a datatype that can take on one of a finite set of values.
In stats terms, an enum is a categorical variable.
We may want to consider the boolean type an enum of {true, false}
Of the languages I know, C#, Java and TS allow creation of enums via the enum keyword.
Rust also uses the enum keyword, but for things more like tagged unions.
Python allows using enums via an external module
C#, Java enum syntax: enum &lt;name> {
  &lt;variant>,
  &lt;variant2>,
  ...
}
In C# the syntax &lt;variant> = &lt;value> exists to apply values to enum variants
We may want to consider enums a special case of tagged unions, where enums can only stand for simple values.


<h3>Collections</h3>

Collections are an abstract data type that hold a number of data items.
Python calls its data structures that represent collection ADTs, well, collections.
Associative collections map keys to values. 
Js sets and maps use .size instead of .length

<h4>Collection methods</h4>

Clear a mutable collection
foo.clear()|not JS|Python|Ruby

Flatten a nested thing ([[1]].flat() => [1])
foo.flat(depth)|JS
foo.flatten(dept)|Ruby
nothing in py

<h4>Non-linear collections</h4>

Python: dictionary, set (and frozenset)

<h5>Sets</h5>

ADT similar to sets in math = unique members, don't have order.
Python data structure: set (mutable), indicated by {}, frozenset (immutable).
JS: class Set, create via new Set(), add(), has()

<h3>Set operations</h3>

Many languages/libraries have generalized set operations to something you can do to most/all collection types.
Python has set methods, but only allows them on sets.
JS has a Set class, which does not support set method

xor/union/intersection/difference(things...)|lodash/underscore(JS)

<h5>Associative collections</h5>

<h6>Associative array</h6>

An associative array is an abstract datatype composed of a collection of (key, value) pairs so that each possible key appears only once (as a key) = keys are unique.
Different programming language's implementations limit keys to only strings, strings or integers, all values, or something inbetween.

Some languages implement assoc arr via Objects, you then interact with them as you would with objects.
Some languages implement assoc arr as primitives, these then often have their own syntax for interaction.
Java implements associative arrays via things implementing the <code>Map</code> interface, e.g. <code>HashMap</code>, both defined over two generics.
JS implements associative arrays via the <code>Map</code> and <code>WeakMap</code> classes. objects (esp. object literals) also perform many of the operations we would expect of associative arrays. Specifically, Maps maintain insertion order, and support any key type, while Object coerces any key to a string (except Symbols). Objects are primitives, Maps need to be created with the new Map() constructor. Operations on map: get(), set()
In literals, key-value pairs are generally separated with , (e.g. keyval, keyval)
Lua implements associative arrays via tables (in fact, tables are the only data structure in lua). 
A lua table can be created the {} literal, like so {key = value, ...}
A lua table can be accessed via dot and square bracket notation. (Perhaps move this to its own thing-access section)
Perl implements and calls associative arrays as hashes. 
In perl, hash variables are marked by the % sigil.
In perl, keys and variables within hashes (perl assoc arr) can be separated by commas (as are the pairs, impairing readability), or separated by => for readability
In perl, hashes use the () or {} literals (is a diff, somethims something reference), {} when accessing
Python implements and calls associative arrays (as) dictionaries. 
Literals {}, accessing [], keyval sep :
Ruby: name hash table, {} literals, accessing [], keyval sep => if nonsymbol keys, : if symbol keys 
Rust: HashMap or BTreeMap, defined over two generics. Has the entry() function go get a Entry
C#: Dictionary, over two generics. Must be created via constructor.
YAML: either {} literals and keyval sep : or no surrounding literals, newline between items, and further indented. Calls them mappings.
TOML: keyval sep =, called tables, keys may be unquoted, or quoted if containing weird characters
SCSS/SASS: Calls them maps, keyval sep :, () literals (same as arrays)

adding a key, value pair
.Add(key, value)|C#
.set()|JS (map only)

deleting key
set it to null type|lua

Retrieval function
get()|Rust

Set a key to a value
[key] = value|most languages if primitive
insert(key, value)|Rust

Has key? 
key?|Ruby

Has value?
value?|Ruby

get array/iterator of key, value tuple/array/whatever:
pairs()|lua
items()|Python
entries()|JS (map only)

get array/iterator of keys
keys()|JS(only Map)|perl|Ruby|Python (returns a dict_keys object)
values()|JS(only Map)|perl|Ruby|Python (returns a dict_values object)
Object.keys(someobj)|JS

Amusingly, JS doesn't have the keys(), values(), entries()... functions for its assoc array type (objects), but does have them for arrays

merge two assoc. arrays
map-merge(foo, bar)|SCSS/Sass

commonly items are separated by ,

Computed property names allows you to put any expression on the left-hand side of a property within an object literal, if you wrap that thing in []

<h4>Linear collections/ADTs</h4>

Linear collections/ADTs are a sequence of items.
Python calls its data structres that are linear collections sequences.
Python sequences: list, tuple, str

<h5>Linear collection methods</h5>

sort the thing
sort()|Perl|Python (in-place!)|Ruby

reverse the thing
reverse()|JS(in-place)|Perl|Python (in-place!)|Ruby

Append a linear collection to a different linear collection 
col1 + col2|Python (also works for strings)
col1 << col2|Ruby (also works for strings)
col1.extend(col2)|Python

Repeat the contents of a linear collection n times
col1 * n|Python

append one element to end 
push()|JS
append()|Python

remove an element from a lin coll by name
somelincoll.remove(elem)|Python

insert an element at a specific position
somelincoll.insert(elem, index)|JS

Fill the thing with the specified element
somelincol.fill(element[, start[, range]])|JS|Ruby
In Ruby, fill also may take a block to calculate the element to fill it.

The push() and pop() methods were borrowed from the Stack ADT to describe inserting/taking from the end of the linear collection in some languages, e.g. JS. 
Most commonly, pop/shift returns the element removed, while push/unshift returns the new length.
Shift and unshift are methods in JS, Ruby, Perl, Java that do the same as pop/push but for the beginning of the array.
Python extends the pop method to all collections, but it generally works weirdly, compared to other programming languages:
someset.pop()|a random element
someassocarray.pop(somekey)|the relevant value
somearr.pop(index)

somearray.splice({{c1::start}}, numberOfElementsToDelete, element1toInsert, ...); (odd, js only, returns array of removed elements which may be empty)

<h5>Strings as linear collections</h5>

Strings are often implemented as linear collections (esp. arrays) of chars, or at least their semantics are similar enough that they work the same way.

<h5>Array<h5>

An array (type) is a abstract datatype of an ordered linear collection of elemennts, selected by indices.


  |no indices (one value only)|zero-dimensional array (uncommon)|scalar
    |one index|(one-dimensional) array|vector
|two indices|two-dimensional array|matrix
|n indices|multidimensional array|tensor


Arrays may be dynamic = have variable size, or static = have fixed size.
Dynamic arrays are sometimes called arraylists.
Arrays are generally primitives in different programming languages, though they differ on syntax and what they call them.

dynamic arrays (one type only)

vector|rust
ArrayList|Java
List(yes, really)|C#

dynamic arrays (of whatever types)

list|python
array|perl|JS|ruby

Vectors, ArrayLists and Lists are Objects/Structs and defined over a generic

static arrays (one type only)

array|C#|Java|Rust

static arrays (of different types), the compiler therefore knows the type of each index

tuple|rust|TS

immutable static array (of whatever types)

sequence|yaml
array|liquid|TOML
tuple|Python
list|SASS/SCSS 

table|lua (though this is more properly the assoc array type, it just happens that an assoc array w/o keys will have numeric keys set up for it by lua, making it also the array type)

Array literals

In array literals, the invidual elements are generally separated by ',', except sh, which separates them by space

dynamic (of whatever types)
()|Perl (same as assoc. arr)|Shell
[]|JS|Python|Ruby

static, one type only
{}|C#|Java

static arrays (of diffent types), the compiler therefore knows the type of each index
()|rust
[]|TS

immutable static array (of whatever types)

()|SASS/Scss|Python (Though in python in reality it is the comma that creates a tuple. the parentheses are just often needed for grouping)
[]|TOML|YAML (if inline)

Most languages use the same syntax for one-dimensional, two-dimensional, or multidimensionall arrays, merely nesting the literals.
In C# the type for multidimensional arrays (e.g. for a three-dimensional array) is type&lt;delimiter&gt;,,&lt;delimiter&gt; (and for the constructor type&lt;delimiter&gt;length,length,length&lt;delimiter&gt;). These are different from merely arrays of arrays, as these have a uniform size (while arrays of arrays do not) 

YAML also has indentation delimited, newline separated, individual items marked by <code>- </code> version

In sh, referring to the whole array requires a special syntax my_array[@] which can only be used within ${}

In C# and Java, the builtin static arrays are objects, and thus must be created using the new operator. 
in languages with type annotation, the type of arrays is usually written as type[], e.g. int[] or String[]
When creating static arrays, the size must be given. In C# and Java, this is done in the [] of the array type in the constructor, e.g. new type[10];
In JS, one can create an array with a specfic size (and thus ergo empty slots) by using Array(n) or new Array(n)

<h5>Lists</h5>

Lists/Sequences are an abstract data type (specifically a collection), in which each element has a position (a first element, a second element), and that are finite.
Lists are always dynamically sized
C#: List, defined over one generic. must be created via constructor. Add to end of list .Add()

<h5>Streams</h5>

Lists/Sequences are an abstract data type (specifically a linear collection), in which each element has a position (a first element, a second element), and that are infinite (or at least potentially so).

<h5>Stack</h5>

A stack is a linear collection ADT with LIFO order, and the operations:
push: add to the top of the stack
pop: remove from top of the stack
peek: loop at top of stack

<h5>Queue</h5>

A stack is a linear collection ADT with FIFO order, and the operations:
enqueue: add to the end of the queue
dequeue: remove from the front of the queue
peek: look a the next element that would be dequeued


<h3>Iterators</h3>

An iterator is an object (or similar) whose purpose is to iterate over some data. In general, an iterator has a next() method that returns the next element.
An iterable is generally something that can create an iterator of itself.
In ruby, iterables are called enumerables.
In most languages that have iterables, most collections are iterable, as are strings and ranges. Java Strings are not, JS objects aren't either.
in JS, the next() method returns an assoc array {
  done: bool,
  value: ...
}
In JS, Array.from() transforms a given iterable into an array. (list() does the same in Python and foo.to_a does it in ruby)

<h4>Generators</h4>

A generator is a form of iterator. Generators are created via a generator function (thus you control what the next() method returns), but otherwise behave like any other iterator.
In JS, generators are indicated by a * after the function keyword.
In JS at least, generators continue from where they left off after the last yield.
In JS, returning or encountering an error ends the generator.
In JS, the next() function of a generator's iterator can be passed an argument that will be assined to the yield expression.
Returning the current iterator element 
yield|JS

yield another generator (JS) yield*

<h3>chars</h3>

In rust, a char contains a single UTF-32 encoded unicode codepoint.

<h3>Strings<h3>

In many languages, especially those that do not have a char type, string literals can be indicated either with single or double quotes.
In languages that have a char type, the char type is generally indicated with single quotes, and the string type with double quotes. Examples: C#, Java, Rust
Some langauges that don't have a char type differentiate between string literals with single and double quotes (e.g. treating single quote string literals as raw strings, e.g. sh, Perl, Ruby), some languages (CSS, HTML, lua, liquid, python, JS) do not.
In languages that have single-quoted string literals, interpolation is generally also not allowd in them.
JS has a specific, especially featureful type of sting called a template literal, which are delimited by backticks (`foo`)
sh is a little special in that it accepts strings with no surrounding quotes in some cases.
YAML accepts unquoted strings if they don't interfere with other syntax, of which the most common case is them containing <code> :</code>

strings are immutable|python

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
>\nproper indentation|YAML

<h4>String interpolation/String formatting<h4>

String interpolation is evaluating a string with placeholders and replacing them with their values
String interpolation is a form of template processing (cf other cards)
In JS, string interpolation can only be performed within template literals.

\${expr}|JS|only in template literals
\#{expr}|Ruby|SCSS/SASS
\$variable|sh|only with variable names
\${epxr}|sh|more feature-full
&lt;sigil&gt;{expr}|Perl
&lt;sigil&gt;variable|Perl

Python has three ways to perform string interpolation:
old-style stirng formatting: is just c-style string formatting. The whole string is followed by a % character, which itself is followed by a single value or a tuple of values to interpolate
new-style string formatting:
{} or {0}, {1} ... interpolates within the string, if calling format() on the string. Interpolated expressions are args to format method, format specifiers go within {}, if passing to format by name, refer to these things like so {name}. If combining w/ format specifiers {name:format_specifier}
"Error code: {errno:x}".format(errno = ...
f-strings: allow arbitrary expression within {}. String must be prefixed by f
f"Hello, {name}"

Rust:
Syntax|Trait
{}|Display
{:?}|Debug
{:#?}|Debug, but pretty-print

<h5>C style string formatting</h5>

(C) format strings aka printf (print formatted) format strings are names for a specific type of string formatting syntax using % and originating from C.
Interpolate with what is called a format specifier: % followed by a char or a few chars to indicate the format. Which strings to interpolate where is determined positionally (the first string is interpolated ).
Format specifier syntax: %[parameter][flags][width][.precision][length]type
common types
x|lowercase hex
X|uppercase hex
d or i|signed int
f or F|decimal number

<h4>String multiplication</h4>

x n|Perl
* n|Python (can also be used for arrays)|Ruby (can also be used for arrays)
.repeat(n)|JS|Ruby

<h4>String concatenation</h4>

string concatenation is joining strings together into a single string.

..|Lua
+|Java|C#|Python|Ruby|Rust|JS
.|Perl
.push_str()|Rust (for str + str)
.push()|Rust (for str + cahar)
Adjacent string literals are automatically concatenated|Python|Ruby

<h4>String replacement</h4>

bash
general pattern (replace first instance) ${SOME_STRING_VAR/find/replace}
//find/replace|replace all instance
/#find/replace|replace if at beginning of string
/%find/replace|replace if at end of string

<h4>Regex matching</h4>

JS has regex literals: /<regex>/<flags> (which creates a RegExp object)
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


<h4>common string methods</h4>

convert to uppercase|.upper()|Python
convert to lowercase|.lower()|Python
convert to uppercase|.toUpperCase()|JS
convert to lowercase|.toLowerCase()|JS
switch upper and lower case chars|.swapcase()|Python
capitalize all first letters|.title()|Python
capitalize the first letter of the string|.capitalize()|Python
capitalize the first letter of the string| bar capitalize|Liquid
does a string start with?/end with?|somestr.startsWith/endsWith(searchstr)|JS (accepts an optional second arg of the index to start searching)
does a string start with/end with?|somestr.startswith/endswith(searchstr)|Python
remove whitespace from beginning and end of string|trim()|JS, Ruby
remove whitespace from beginning of string|trimStart()/trimLeft()|JS
remove whitespace from end of string|trimStart()/trimLeft()|Ruby
split string on foo|.split(foo)|Python|JS(empty string for char array)

<h4>String replacement</h4>

somestr.replace(foo, bar)|JS|Python

<h4>Join to string</h4>

separator.join(iterable)|Python
somearray.join(separator)|JS|Ruby

separator defaults to , for JS and to nothing for Ruby

<h4>JS oddity: tag functions</h4>

Tag functions are functions prefixed to template literals (but not called)
Tag functions recieve a first argument an array of all constituent string parts of a template literal, and all interpolated values as following arguments.
Whatever the tag function returns will be what the string evaluates to.
Tag functions can return whatever.

<h2>operators</h2>

overloading
In Ruby, all operators are actually just syntactic sugar for methods. that is, + 3 is .+(3), somearr[1] is somearr.[](1), !3 is 3.! etc.

<h3>precedence</h3>

Operator precedence in programming mirrors the math concept of order of operations.
Operator precedence / order of operations is in which order to apply operations.
In most programming languages, math operations have the same operator precedence as they would in math itself.
Parentheses can modify the order of operations just as in math.
The power operator has unclear order of operations for historical reasons (in other programming languages), so JS throws an error if you use it without parentheses where it would make a difference
In liquid, the order of operatons is right to left, parentheses are forbidden.

<h3>relational opearators</h3>

In computer science, a relational operator is an operator that tests or defines some kind of relation between two entities. These include numerical equality (e.g., 5 = 5) and inequalities (e.g., 4 ≥ 3).

~=|not equals|lua
!=|not equals|C#|Java|JS
==|equals|most programming languages
<=|less than or equals|most programming languages
&gt;=|greater than or equals|most programming languages
&gt;|greater than|most programming languages
&lt;|less than|most programming languages
<=>|returns 1 if left arg is larger, -1 if right arg is larger, and 0 if both are equal|Perl|Ruby

Python uses the `is` operator when comparing equality of location in memory

JS has versions of the equality operators with one extra =. The shorter ones coerce before comparisons. Specifically, any of the shorter ops containing < or > coerce to string or numbers (including null, but not undefined). == coercion is more complicated, but will coerce null to undefined.

For anything that is a data structure, there can be two kinds of equality (using Kotlin terminology)
structural equality = equivalent content
referential equality = same reference
JS, Java, C# use referential equality on non-scalars
Ruby and Python use structural equality on non-scalars (arrays and assoc. arrays)

sh has a different set of operators for string equality:
-ne|is not equal to
-lt|is less than
-le|less than or equal to
-gt|is greater than
-ge|greater than or equal to
-eq|is equal to
Perl uses sh-style comparison operator without the leading -

greater/smaller with strings is generally relative to their position in unicode, which for latin characters tracks ASCII and thus "Z" < "a"
Comparing a thing with itself is always true, except for: 
in JS, NaN

<h3>boolean operators</h3>

logical and|and|python|liquid|lua|Ruby (lower precedence)
logical and|&&|C#|Java|JS|Ruby (higher precedence)|(ba)sh
logical or|or|python|liquid|lua|Ruby (lower precedence)
logical or|barbar|C#|Java|JS|Ruby (higher precedence)|(ba)sh
logical not|not|python
logical not|!|C#|Java|JS

In ruby, between and/or and &&/|| the former have lower precedence, and even have lower precedence than the equality operator.
Double not can generally be used to get the truthiness/falsiness of a thing, even outside of a boolean context.

<h4>short-circuiting</h4>

Short circuiting is more properly short-circuit evaluation.
Short-circuit evaluation is the property of boolean operators in some/most programming languages in which the second argument is executed or evaluated only if the first argument does not suffice to determine the value of the expression.
specifically, expr1 LAND expr2 will not evaluate expr2 if expr1 is false/falsy
expr1 LOR expr2 will not evaluate expr2 if expr1 is true/truthy
Can be used to ensure a variable never gets assigned a falsy value by using logical/boolean or, since (only) if the first expression is falsy the second expression will be evaluated.
It is possible to create a kind of if statement using only short-circuiting operators: CONDITION && IFTRUE || IFFALSE
(ba)sh

<h3>bitwise</h3>

bitwise not|~
left shift|&lt;&lt;
right shift|>>
bitwise XOR|^
bitwise OR|bar
bitwise AND|&


<h3>math</h3>

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

<h3>comma</h3>

In the C and thus in JS, Perl, the comma operator (represented by the token ,) is a binary operator that evaluates its first operand and discards the result, and then evaluates the second operand and returns this value (and type).

<h3>element in collection/substring in string?</h3>

stringOrColl contains elem|liquid
elem in stringOrColl|Python|JS
stringOrColl.includes(elem, optionalSearchStartPos)

`in` in JS works amusingly if used on arrays: it will look for integer keys, and not for values, so that it will return false for "foo" in ["foo"] but true for 0 in ["foo"] (this is because arrays are objects, and thus the integer keys are actually object keys)

<h3>remove element from collection</h3>

del|python
delete|JS

<h3>Type of element</h3>

typeof foo|JS
type(foo)|Python

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

<h3>Slicing</h3>

Slicing is extracting a subset of elements from a data structure.
Slicing is most commonly performed on linear collections or strings.
In most cases, omitting the start defaults to 0, and omitting the end defaults to the maximum value (last element/slength)
In general, using a negative index for step will reverse the thing.
In python you can assign to slices, delete them, etc.

[start:end_excl:step]|Python
.slice(start, end_excl)|JS
.substring(start, end_excl)|JS (only strings, will not count from back, but will swap start and end if start is larger)
[start..end_incl]|Ruby|Perl
[start...end_excl]Ruby
[start,length]Ruby
[start..end_excl]Rust
[start..=end_inc]|Rust
${STRING_VAR:start:length}|Bash

Part delimiters
:|Python
..|Perl

<h3>Length of strings, collections, etc.</h3>

foo.length|Java|JS|Ruby
foo.Length|C#
len(foo)|Python
#foo|lua|sh (must be surrounded by ${}, and followed by [@] if an array)

length() for strings in perl, merely generating a scalar context is enough for arrays

<h3>Spread operator/Rest syntax</h3>

Both JS and Ruby have an operator that allows them to do similar things in relation to arguments and arrays.
Ruby calls this operator the splat operator, while js calls it a rest operator in the context of callable unit parameters (not arguments), and spread syntax otherwise

...|JS
*|Ruby|python

In the context of callable unit parameters, JS rest syntax and Ruby/Pythons's Splat both gather the remaining arguments into an array. the parameter so marked must be the last in the list.
funcName(1,2,3)
&lt;keyword&gt; funcName(... OR *foo)
foo will now be [1,2,3]
When not in callable unit parameters, JS spread and Ruby/Pythons splat transform an array into its constituent members
[... OR *[1,2,3], 4] == [1,2,3,4]

<h2>Error handling<h2>


<h3>Throwing errors</h3>

Generally take an expression as arg.

keywords
die|perl
throw|JS|Java|C#
error()|lua
@error|SCSS?Sass
raise|Ruby
panic!()|Rust

<h3>Error handling control structures</h3>

most commonly: try &lt;block&gt; catch (&lt;error-specifier&gt;) &lt;block&gt; finally &lt;block&gt;
In Ruby begin &lt;block&gt; rescue (&lt;error-specifier&gt;) &lt;block&gt; ensure &lt;block&gt;
Rust is notable for not having any error handling of this kind.
In general, having a try and either a catch or a finally block is necessary for the construct to be syntacitcally correct.

<h3>assert</h3>

Assertions are predicates that deliberatly crash the program if the predicate is false.
Assertions are generally used when something should be logically impossible to be false, and thus aren't handled by error handling.
Assertions are typically only used during development.
Rust implements assertions via macros.
rusts {{c1::assert_eq!}} macro tests wheter {{c2::two expressions are equal}} (using the trait {{c2::PartialEq}}), and {{c3::panics if they are not}}
rusts {{c1::assert!}} macro tests whether {{c2::something is true}}, and {{c3::panics if it is not}}

<h2>Callable units</h2>

Callable units generally can take arguments if specified.

Keyword to start a callable unit
function|JS|Lua|sh|SCSS/Sass (@function ofc)
fn|Rust
def|python|Ruby
sub|perl
no keyword|C#|Java

Callable units can generally be split into method signature and method body. The method signature usually specifies at least return type, name, and parameters, as well as the keyword if necessary. In sh, a method signature contains nothing but the keyword and name
In java, the method signature also specifies parameter type, access modifier, and optionally staticness/finalness/abstractness.
In JS, function keyword defined callable units generate their own this, while arrow functions do not.

<h3>Declaration</h3>

In most languages, functions can only be declared in statements, however languages that have functions as first-class citizens often also allow declaration via expressions.
function expressions are generally assigned to variables for later usage.
JS calls function declarations that are statements function declarations, and function declarations that are expressions function expressions.

<h3>signatures</h3>

Languages with manifest typing typically require the returned type to be declared in callable unit signatures.
void is commonly used for no return type in languages that require a return type to be specified.
return type is indicated:
-> <type> at the end of signature|rust

<h3>returning</h3>

Across most languages, the keyword to return whatever value is the <code>return</code> keyword.
In non-manifestly typed languages, the default return value of a function is the null type
In general, using the return keyword without a value returns the languages null type.
Multiple values: separated by comma|lua
In Rust, using the return keyword is frowned upon, as blocks return their final expression anyway.

<h3>Closures</h3>

A {{c1::closure}} is the combination of {{c2::a callable unit}} and {{c3::the lexical environment}} (= {{c4::any variables that were in scope}}) within which that function was declared.
Closures are created when the functions are created.
All callable units automatically create closures in JS, lua.
In rust, only closures create closures :P

<h3>Call by...</h3>


sharing|lua|JS|Java

<h3>Anonymous functions</h3>

A callable unit not bound to an identifier is an anonymous function/callable unit.
First-class functions/callable units are callable units that are first-class citizens.
anonymous functios are almost always first-class functions, and are thus often passed as arguments, etc.
However, often non-anonymous functions can also be first-class functions

In ruby, anonymous first-class functions are called blocks.
In rust, anonymous first-class functions are called closures.
In JS, lua, python all functions are first-class. 
In JS, anonymous functions have no special syntax, you merely leave out the identifier.

In ruby and rust, parameters to blocks/closures are surrounded by |...|
In ruby and rust, blocks/closures are surrounded by {}
{|params| code...}
In ruby, blocks may also be surrounded by do ... end

in ruby, to call a passed block, use the yield keyword. 
Anything passed to the yield keyword will be available as arguments to the block
In ruby, the & operator converts a block to a proc object.
Calling #call on a proc object is similar to yielding a block
instead of a block with the syntax {|elem| elem.method} you can also pass &:method for the same effect

In JS, there is a special type of first-class anonymous function called an arrow function.
Arrow functions function similarly to normal js functions, but have a shorter syntax: (<params>) => <block>.
Instead of a block, you may also specify a single expression, whose value will be returned. 
The parentheses are optional if there is a single param

<h4>IIFE</h4>

An immediately invoked function expression (IIFE) uses function scoping to create a fake block scope.
IIFEs were used for the same reasons as block scope is used generally, and preventing hoisting.
IIFEs generally use anonymous functions.
in JS IIFEs need to force an expression to be able to immediately invoke it (since a declaration cannot be immediately invoked)
The most common way to force functions to be expressions is via surrounding them in (), but other ways are possible.
With the introduction ES6 let and const, IIFEs have become mostly irrelevant.

<h3>Higher-order functions</h3>

A higher order function is a function that takes a function as an argument, or returns a function. All other functions are first-order functions.

There are many standard types of higher order functions.
In JS, the higher-order functions generally only work on Arrays, and the passed functions always recieve the arguments value, index, wholeArray.
In ruby, higher-order functions generally take blocks/procs

In JS, any higher-order function can take a thisArg, which is then the final argument. This argument will be what the passed fucntion recieves as this.

callable units passed to other functions are also known as callbacks 
The deep nesting of callbacks that result in unreadability is known as callback hell or the pyramid of doom

<h4>map</h4>

In many programming languages, map is the name of a higher-order function that applies a given function to each element of a collection, e.g. a list, returning a list of results in the same order. 
.map(func)|JS|Python|Ruby

<h4>sort</h4>

Sort is a higher-order function that takes a function which itself takes two arguments. Depending on the language, return values are handled differently.
JS function must return value smaller 0 if the first argument is to be first, larger 0 if the second argument is to be first, and 0 if it should not reorder.
The sort function passed must be deterministic.
In many languages, sort sorts with a predefined sorting algorithm if no sorting function is provided
In some languages sort does not take a sorting function, instead only using the predefined sorting algorithm, in those languages sort is not a higher-order function.

sorted(foo)|Python (takes an iterable)
foo.sort()|JS (takes an optional sort function, only Arrays)

<h4>filter</h4>

Filter is a higher-order function that processes a data structure to produce a new data structure containing exactly those elements which the passed function returns true.
filter()|JS

<h4>reduce</h4>

The reduce function/method takes a function known as the reducer function
The reducer function recieves the return value of the last execution of the reducer function, and the current element of the collection. 
The reducer function return a single value.
In effect, the reducer function applies an operation to the current element, and the accumulated result of all other elements.
Many languages allow specifying a 'previous result' element for the first time the reducer function runs, as there will not be one.
js has the variant reduceRight that starts from the end
reduce()|JS|Ruby|Python

<h4>some/every/</h4>

some is a higher order-function that takes a function and returns true if the passed function returns true even once.
every is a higher order-function that takes a function and returns true if the passed function returns true for all elements.
JS

<h4>find</h4>

find is a higher-order function that takes a function and returns the first element for which the passed function returns true. findIndex instead returns the index.
find()|JS|Ruby
findIndex()|JS
find_index()|Ruby



<h3>Arguments<h3>

most languages require the possible parameters defined in a callable unit definition to be wrapped in parantheses.
sh doesn't allow specifying parameters at all
most languages require the arguments to a function call to be wrapped in parentheses.
sh does not wrap arguments at all
most languages separate both the parameteres and arguments with commas.
sh separates arguments with space

Exceptions:
1 arg doesn't need parens|lua
always optional|ruby|perl
never|sh

refer to all passed arguments as an array
$@|(ba)sh
arguments|JS (not arrow functions)

In sh, instead of parameters having names, you refer to them positionally via $0...$9. 
$# gets the amount of arguments passed.

<h4>Positional and named</h4>

named parameters|Python|JS|SCSS/Sass @mixin, @function
positional parameters|pretty much all languages

<h4>Default parameters</h4>

A default parameter is one which will take on a default value if no argument for it is specified in the call.
In general, default parameters will also take on the default value if the argument passed is the language's null type. 
In JS, the default parameter will take on the default value if undefined is passed as an argument, but not if null is passed.
the general syntax is `paramname = defaultval` (within the parameter list)
Python, JS, SCSS/Sass @mixin, @function have default parameters TODO Check other languages

<h3>Asynchronous callable units</h3>

Asynchrony, in computer programming, refers to the occurrence of events independent of the main program flow and ways to deal with such events.  

A promise is a proxy for a value that will eventually become available.
In JS, a promise is an object
You react to promises by calling the then() method on them.
In JS, something you can call then() on is called a thenable.
in JS, most interfaces for promises work on any thenables.
A promise can have the states {{c1::pending}}, {{c2::fulfilled}}, or {{c3::rejected}}.
A promise is called {{c1::settled}} if it is either {{c2::fulfilled}}, or {{c3::rejected}}.
Ergo a promise is either settled or pending.
We may return a rejected promise manually, additonally, if an error occurs in our async function, it will reject automatically.
Once a promise has settled, the attached thens will run as soon as possible / awaits will resolve.
If a promise is settled, and we then attach a then()/catch()/finally(), it will run immediately
While a promise is pending, thens will not yet run / awaits will not yet resolve.
A promise may have the fates resolved, unresolved.
//generally true, not jus js

In many languages, the async keyword marks the callable unit as asynchronous and allows it to call asynchronous functions.
await is a keyword/function available in many programming languages that calls an asynchronous function and then returns the value the function returns once it does.
In JS (and other languages w/ promises), await takes a promise (and is the rough equivalent of calling then() on it)

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


<h3>Overloading</h3>

Overloading of callable units is creating multiple callable units with different callable unit signatures.
Languages I know that support overloading are C#, Java, TS.
When overloading, each signature generally has its own implementation, exept in TS.
In TS, function '{{c1::overloading}}' exists, but you specify {{c2::all possible signatures}} {{c3::first}}, and then the {{c4::implementation}} with a {{c5::signature}} that is {{c6::compatible with all the specified signature}} (e.g. using {{c7::optional parameters}}), and not compatible with {{c8::non-specified signatures}}
In TS, in general: prefer {{c1::union types}} over {{c2::overloads}}

<h2>Records</h2>

A record is a collection of fields, possibly of different data types, typically in a fixed number and sequence. The fields of a record may also be called members.
A type that defines a record is a record type.
Most programming languages allow creation of instances of record types.

<h3>Methods</h3>

To make an object B do something, an object A must send a message.
A message in OOP consists of the target object, the name of the method to perform, and the argumetns passed.

In Rust, Python, methods must take self as the first argument.

<h4>Class methods</h4>

A class method is a method called on a class rather than an instance.
A class method may also be known as an associated function.
In rust, a class method/associated function is called by using the :: operator

static|Java|C#|JS
does not take self as argument|Rust

<h3>passive data structure</h3>

Use of a data structure that contains fields w/ values, but no other object-oriented features


<h3>Structs</h3>

Struct is not an incredibly well-defined term, but is generally a record with the possibility for methods, but not the whole inheritance etc. stuff of classes.
In rust, struct declarations use the keyword struct.
Both struct delcarations and initializations in rust use a very assoc-array like syntax.
struct User { username: String, ...}

<h3>Tagged unions</h3>

A tagged union can hold a value that could take on several different but fixed types.
A tagged union can be thought of as a type that has several "cases", each of which should be handled correctly when that type is manipulated.
What rust calls enums is more properly a tagged union

<h3>Classes & objects </h3>

An object in object-oriented language is essentially a record that contains procedures specialized to handle that record; and object types are an elaboration of record types.

Keyword to declare a class is done by the keyword <code>class</code> in pretty much all programming languages which have it.

A singleton (AKA the singleton pattern) is a class that can only have a single instance of that class. It is useful when you don't need multiple instances of a thing (the null object, a logger), or to coordinate states.
A type that only allows one value (only allows a sigleton) is known as a unit type.

reference to the current object/construct
self|Ruby|Rust
this|C#|Java|JS

method in lua function object:method(...)

in languages with type annotation, the type annotation of an object is generally its class (e.g. MyClass myObject = new myObject();)


<h4>Methods ruby</h4>

In ruby, methods that will return a boolean are marked by a ?
In ruby, methods that do something destructive are marked by a !

<h4>pure OO</h4>

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

<h4>Inheritance</h4>
In most programming languages, you refer to your superclass=base class with the keyword <code>super</code>.
In most programming languages, you specify a subclass/superclass relationship like so: Subclass extends Superclass
In ruby, you specify a subclass/superclass relationship like so: Subclass < Superclass
In C#/Java, making a class final disallows a subclass from inheriting from it.
In C#/Java, making a method/static function final disallows a subclass from overriding it it.

<h4>abstract & static classes </h4>

Abstract classes are generally declared with the abstract keyword. Within abstract classes, methods are also declared with the abstract keyword.
Both abstract and static classees are not instantiable.
Abstract classes are designed mainly to be inherited from.


<h4>Constructors/object creation</h4>

Creating a new object via a constructor is done by the new operator in most languages, but not in Ruby or Python.

A constructor is generally a callable unit and thus called with ()
Rust doesn't use any operator to create new Structs. In general, you use literals, some type provide a new() associated function.
In C#, Java, the constructor has the same name as the class.
In Ruby, the constructor is defined by the initialize function within the class (class SomeClass\n  def initialize(...), and called by calling the new() method on the class (SomeClass.new())
In JS, the constructor is named constructor
Many languages allow us to declare many different constructors with different arguments.
Most languages provide a default constructor if you don't provide one, which does nothing besides create the object.
In JS, you may not use arrow functions as constructors



<h4>type parameters and generics</h4>

The things that define {{c1::the types}} a function/object/... is defined over, which usually go in {{c2::angle brackets}}, are across programing languages usually called {{c3::type parameters}}.
Generally, multiple type parameters are separated by , 

<h4>Access modifier</h4>

Access modifiers (or access specifiers) are keywords in object-oriented languages that set the accessibility of classes, methods, and other members. 
In Java, members have default accessibility by default.
In Python, JS, members are public by default.
Most language with any kind of access modifiers have at least a public private distinction
public|any code
private|code within the class
Most languages with a public/private access modifier distinciton will use the public/private keyword to mark the one that is not the default anyway
JS is an exception, it marks private members with #

default||Java
protected||Java

<h4>Getters and setters</h4>

Ruby syntax:
def name=(value)...|setter

JS:
get foo()
set foo()
only within a class

You can only interact w/ ruby instance variables via getters and setters, trying to use it without those will give you a NoMethodError

<h4>Interfaces</h4>

mixins are pretty similar concepts.
In OOP an interface is a set of methods that anything that implements that interface must also implement.
If a given programming language has syntax for them, generally keyword interface.
Indicating that one follows an interface is generally done with the implements keyword.
If something implements an interface, it generally must implement all methods of that interface.
In the past, Java did not allow variables in interfaces. as of today, they are allowed, but subject to heavy restrictions.
In interfaces in Java/C#, you most commonly merely specify method stubs. (in the past this is the only thing you could do, this is no longer true)
Method stubs are method signatures without the implementation, in Java/C#, they are followed by a ;.

Things using the ruby mixin Comparable must define <=> operator, and then gain access to the other comparison operators, as well as between? and clamp

<h5>Traits</h5>

Traits in Rust are broadly similar to intefaces in other programming languages.
Traits in Rust can be implemented for types you did not define.
However, the trait ∨ the thing its implemented on must be local to the crate
Traits allow for blanket implementations, that is implementing a trait for anything that implements one or more other traits

<h4>OOP</h4>

C#, Javaf

<h4>is X an object of Y</h4>

someobj instanceof class|JS

<h4>Duplication/Replication</h4>


shallow copy
copy (module copy).copy(foo)|Python
foo.copy()|Python (only collections)|Rust

deep copy
copy (module copy).deepcopy(foo)|Python
foo.clone()|Rust

<h4>toString()</h4>

Most languages with objects have a tostring function to convert these to strings for debugging purposes.
It can often be useful to overwrite the default tostring implementation for more useful custom debugging.

toString()|JS


<h2>Pragmas</h2>

In computer programming, a directive or pragma (from "pragmatic") is a language construct that specifies how a compiler (or other translator) should process its input
Perls pragmas have the syntax use &lt;name&gt;;
Perls pragma use warnings; causes the perl program to display warnings in certain circumstances.

<h3>Strict mode</h3>

Both perl and JS have a strict mode pragma.
Strict mode pragmas cause programs to fail in certain cases.
Start strict mode in JS: "use strict";
in JS, non-strict mode code is called sloppy mode
In JS, modules and classes are strict by default
In JS, strict mode applies to the whole file if it's the first statement if the file, and to the whole function if it's the first statement in the function

Strict mode in JS:
- reserves certain keywords (for future proofing)

<h2>IO</h2>

In ruby, {{c1::$stdin}} {{c2::represents stdin}} and {{c1::$stdout}} {{c2::represents stdout}}. They are both {{c3::streams}}, which means we {{c4::use the read method}} to read input&nbsp;
sys.stdin|python

Command-line arguments
@ARGV|Perl
process.argv|node

Environment variables
%ENV|Perl
process.env|Node

<h2>Formatting</h2>

Official style guide/best practices
PEP 8|Python

<h2>import/export</h2>

A module is as self-contained set of code, most commonly in a single file of code.
Packages and modules are sometimes synonyms.
conta
In python, a package is a collection of modules (and perhaps other packages).
In python, each .py file is a module.
A package must contain a __init__.py file

If you want to import/export multiple members, most languages have the syntax {member1 [as name1], member2 [as name2], ...}
Import/export anything uses * in most languages
in JS, you can only import/export within modules.

<h3> Importing</h3>

In most languages, you can only import things that were first exported.
In most languages, import statements must be in the beginning of the file.
In most languages, you may only export top-level items.
Import statements have the general syntax

import <members> [as <name>] from <path>
in JS you can leave out <members> from if you only want the side effects

Python instead has the order from <path> import <members> [as <name>]



SCSS/Sass 

Three keywords: @use, @import, @forward (@include is not an import statement!)
Syntax alwas keyword <path> [as <name>]
@forward foo doesn't allow the current stylesheet bar to access the things in foo, but {{c1::allows anything @using bar to access them.}}

CommonJS

CommonJS is {{c1::a module ecosystem}} mainly used by node

let/var/const <name> = require(<path>)

<h4>prelude</h4>

Most languages have a number of things that are automatically imported. Rust (and haskell) calls this prelude.

<h3>exporting</h3>

In most languages, exporting is required so they can then be imported.
General syntax: export <members> [as <name>]

<h4>default exports</h4>

<h2>lifecycle</h2>

<h3>Entry point</h3>

In computer programming, an entry point is a point in a program where the execution of a program begins, and where the program has access to command line arguments. 
The entry point of many programming languages is the main function:
public static void main(String[] args)|Java
main()|rust

<h2>Standard library</h2>

A software solution that has everything that it needs to run out of the box is said to be batteries included.
A programming language that has a large standard library is said to be batteries included.

count occurrences of element
foo.count(bar)|Python|Ruby
no easy way|JS

get (first) index of element/substring in string or linear collection
foo.index(bar, optionalStartIndex)|Python
foo.indexOf(bar, optionalStartIndex)|JS (returns -1 if ti could not be found)

get (last) index of element/substring in string or linear collection
foo.lastIndexOf(bar, optionalStartIndex)|JS

get list of all functions a module/package supports
dir(foo)|Python

get a random number
&lt;mathobj&gt;.random()|JS

floor/ceiling function
&lt;mathobj&gt;.floor()/.ceil()|Python|JS
&lt;thingItself&gt;.floor()/.ceil()|Ruby

Is a thing an integer?
Number.isInteger(foo)|JS

get the smallest/largest of an amount of arguments
min()/max()|Python (also accepts an iterable as an argument)
Math.min()/Math.max()|JS

Truncate decimal places (not rounding)
&lt;mathobj&gt;.trunc(num)|JS

Round to fixed amount of decimal places
somenumber.toFixed(num)|JS

Round a number
&lt;mathobj&gt;.round()|JS|Python

Get absolute value of something
&lt;mathobj&gt;.abs()|JS
abs()|Python (y, it's not on the math obj)

Square root
&lt;mathobj&gt;.sqrt()|JS|Python

Is the thing an Integer?
Number.isInteger(foo)|JS

Get documentation information on the thing
help(foo)|Python

Sort the thing 


Move remove the first argument and shift all arguments one to the left
shift|Perl|sh

does the thing contain the thing?
include?|Ruby
includes()|JS

is x between foo and bar?
x.between?(foo, bar)|Ruby

Show an output popup
window.alert("mesg")

Concatenate multiple strings/ arrays at the end of an existing string/array
stringOrArray.concat(stringsOrArrays)|JS|Ruby

Is there a truthy value in an iterable
any(iterable)|Python

Are all the values in an iterable truthy 
all(iterable)|Python

Sum up all the elements in an iterable
sum(iterable)|Python
enumerableWhichIsJustASynonymForIterable.sum()|Ruby

<h3>Modules/Objects/Namespaces</h3>

Object/Struct/whatever for standard math operations
Math|JS
math|Python

Filesystem handling
fs|node

<h3>Print</h3>

Print functions in different languages

print()|lua|perl (no final newline)|python|Ruby (no final newline)
say()|perl (final newline)
puts|Ruby (final newline)
console.log()|JS
@debug|SCSS/Sass
System.out.prinln()|Java
Console.WriteLine|C#
echo|liquid (within liquid block)|(ba)sh

Print functions using format strings
printf|(ba)sh|C (ofc)|Perl|Ruby
string.format|Lua
% syntax|Python

Print an error to console (but don't throw one)
console.error()|JS
@warn|SCSS/Sass

<h3>Query for input</h3>

Generally, show a message, have a text input field, return the inputted text.

input(mesg)|Python
window.prompt(mesg, default)

<h3>ranges</h3>

Ranges may be a syntax for generating iterators/arrays, or may be their own type. They may also be both, pythons range is an interable type that as all iterables generates an iterator if needed.

range(start, stop, step)|python|lodash/underscore (js)
(start..stop)|liquid|perl|ruby
start..stop|Rust
{start..stop..step}|bash
seq start step stop|sh

<h2>Programming language implementation</h2>

A programming language implementation is a system for executing computer programs. There are two general approaches to programming language implementation: interpretation and compilation

TS compiles to JS via the compiler, interfaced with the cli tsc.

<h3>Transpiling</h3>

Babel is a transpiler that transpiles{{c1::newer JS (e.g. ES 2017, ES 2020) to older JS (e.g. ES5)}}

<h3>REPL</h3>

irb|ruby
lua|lua
node|JS
python, python3|python
tss-node|TS

Python calls being in the repl interactive mode
the value of the last expression
_|Python

<h3>Shebangs</h3>

env (/usr/bin/env) can be passed a comand, in which case it will populate the environment variables (including PATH) and then run command with this environment. 
Using env in the shebang is to get the relevant executable on the path
so in general, you can specify the language of a script by doing 
#!/usr/bin/env language-command


<h2>Boilerplate</h2>

Boilerplate code is repetitive code that is reused often, often also implying that it is unneccessary and would be better if it just wasn't necessary.

<h3>document start/end indicators</h3>

--- the file ... |YAML (but optional, merely allow multiple documents per file)

<h2>Misc/no place yet</h2>

most languages allow an arbitrary amount of spaces and tabs as indentation, YAML however only allows spaces

<h3>Indexing</h3>

Most langauges I know start linear collection indices at 0, however lua starts them at 1
In most languages, providing negative indices counts from the back, with -1 being the last element.
Square bracket notation: most commonly used for array/linear collection indexing or accessing members in associative collection, esp. if primitives in language. SCSS/Sass is special in that maps are primitive in the language, but neverthelesss square bracket notation does not work, one must use map-get() (also not map.get, which its documentation still falsely refers to)
any key in a table lua, Ruby, JS, Py, Rust
In most languages, indexing a linear collection outside of its bounds produces an error, in JS it merely produces undefined
In most languages, referring to an associative array element that doesn't exist will get you an error, in Lua and JS you merely get undefined
TS changes referring to a lin col index outside of bounds or a nonextand assoc arr element to an error
JS allows indexing strings via the charAt method.

dot notation: TOML also 
string keys of tables lua
members of objects in lua
but: not method calls, use : instead
In Rust, of the collection types, tuples are accessed via dot notation, an arrays are accessed via square bracket notation

While JS will not error if you try to access a key or index that is nonexistant, it will return undefined, and if you then try to access something of undefined, it will return an error.
In JS, the ?. is called the optional chaining operator.
In JS, the optional chaining operator works like dot notation, except that if used on a nullish value, it will short-circuit and return undefined.
the optional chaining operator short-circuiting to undefined when after something that is nullish prevents attempted indexing of something nullish, which would otherwise cause an error.
The optional chaining operator can be used instead of dot notation, and before [] notation or method calls.

<h2>Things programming languages do especially well</h2>

performance|rust





https://en.wikipedia.org/wiki/Type_theory#History

Associative arrays: names, literals, other construction methods, etc.








A metacharacter is a character that has a special meaning to a computer program, such as a shell interpreter or a regular expression (regex) engine.

An escape character is a metacharacter that invokes an alternative interpretation of the following character(s)
An escape sequence is the combination of an escape character and the subsequent characters that has a specific meaning.
In most programming languages, \ acts as a/the escape character, this includes latex, at least for basic things such as % and &.
In HTML, & acts as a/the escape character.
Liquid is rare in that escape sequences don't exist at all.
Generally, most languages will require using an escape sequence for their metacharacters, or at least the ones that could have meaning in a given context, this is known as character quoting.
Besides character quoting, escape sequences are often used for characters that cannot (easily) be typed on a keywboard.
Escape sequences for unicode codepoints:
\uXXXX|JS

The most common escape sequences (not character quoting)
\n|new line|LF|0x0A|any newline character
\r|carriage return|CR|0x0D
\f|form feed|FF|0x0C
\t|(horizontal) tab|HT|0x09
\v|(vertical) tab|VT|0x0B
\b|backspace|BS|0x08
\a|bell|BEL|0x08
\e|escape|ESC|0x1B
\0|null|NUL|0x00
|end of transmission|EOT|0x04

CRLF|Windows|The Internet
LF|Unixlike (Linux and modern mac)
CR|older macs

§§ HTML has ((c:1;::two ways)) of specifying ((c:2;::character escapes)). ((s:gb;::Both ((c:3;::start with an &amp;)) and ((c:4;::end with a semicolon ;)). They are both often used to ((c:5;::display reserved characters, invisible characters, or hard-to-type characters.))))  §<br>
§§ Of these, ((c:6;::numeric character references)) ((c:7;::refer to the character position within character set (most commmonly UTF-8))), ((s:gb;::they start ((c:8;::with # (after &amp;))) and can be specified in decimal or hex. ((h:gb;::(for example ((c:9;::&amp;#8203;))))))) §<br>
§§ ((c:10;::Character entity references)) ((c:11;::have a short, memorable name)) ((h:gb;::(for example ((c:12;::&amp;amp; or &amp;quot))))) §<br>
§§ This distinction is however often not made, and often ((c:13;::any name that is a combination of some of the name parts (e.g. HMTL entity, entity reference, character entity))) are used. §<br>

<table class="cloze-group hide-if-inactive">
  <thead>
    <tr><th>Character entity reference / Numeric character reference</th>
    <th>Displays as / creates?</th>
  </tr></thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr>
      <td>((c:16;::&amp;gt;))</td>
      <td>((c:17;::&gt;))</td>
    </tr>
    <tr>
      <td>((c:14;::&amp;lt;))</td>
      <td>((c:15;::&lt;))</td>
    </tr>
     <tr>
      <td>((c:18;::&amp;amp;))</td>
      <td>((c:19;::&amp;))</td>
    </tr>
    <tr>
      <td>((c:20;::&amp;shy;))</td>
      <td>((c:21;::A hyphen that works as a line break, but is only displayed when necessary for wrapping.))</td>
    </tr>
    <tr>
      <td>((c:22;::&amp;#8203;))</td>
      <td>((c:23;::A zero-width space that allows the browser to break there, when necessary))</td>
    </tr>
  </tbody>
</table>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}</span>

Newline may refer to the newline character or any newline

even?|Is the thing even|Integer
next|get the next element|Integer, String
class|get the class this is an object of|any object
methods|get the methods the object has|any object



