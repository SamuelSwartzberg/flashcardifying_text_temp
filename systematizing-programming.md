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
§§ However, in ((c:4;::Rust)), ((c:5;::blocks)) are ((c:6;::expressions)). §<br>
§§ ((c:7;::Blocks)) ((c:8;::contain/consist of)) ((c:9;::one or more)) ((c:10;::statements)). §<br>
§§ ((c:11;::In/with)) ((c:11;::constructs)) or ((c:11;::languages)) that are ((c:12;::block-scoped)), ((c:13;::a block defines a scope)). §<br>
  §§ ((c:14;::Curly-brace/bracket languages))&nbsp;are defined as languages that ((c:15;::use curly-braces)) ((c:16;::to define blocks)). §<br>
§§ Examples of ((c:17;::curly-brace/bracket languages)) I can write are ((c:18;::C#)), ((c:19;::ECMAScript)) -&gt; {((c:19;::Javascript)), ((c:19;::TypeScript))}, ((c:20;::Java)), ((c:21;::Perl)), ((c:22;::Rust)). §<br>
§§ Most ((c:23;::curly-brace/bracket languages)) ((c:24;::are thus because they are strongly influenced by)) ((c:25;::C)). §<br>
In some programming languages (JS, Lua, ...?) blocks can stand alone, merely creating a scope. In other programming languages, blocks must follow a certain statement.
In lua, blocks end with <code>end</code> (outside of repeat...until). They are begun by <code>do</code> when standing alone, or when after a loop, by <code>then</code> after an if condition, and by nothing after a function signature
In ruby, blocks end with <code>end</code>

    liquid|{% keyword %} ... {% endkeyword %}
  <table>
  <thead>
    <tr>
      <th>Language</th>
      <th>Defines blocks how?</th>
    </tr>
  </thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr>
      <td><span class="c26-cloze">Python</span></td>
      <td><span class="c27-cloze">Indentation</span></td>
    </tr></tbody>
</table>

</div>
<span class="cloze-dump">{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}</span>

<h2> control flow</h2>
The default control flow is linear from top to bottom, this is called sequencing.

<h2>control structures</h2>

<span class='line'>A thing that modifies control flow is a control structure. 
</span>
<span class='line'>A control structure takes the normally linear flow of code and makes it somehow nonlinear.</span>
<span class='line'>In javascript or JS, most control structures take one statement after it, which can either be a normal statement or a block statement. A statement that does nothing is an empty statement</span>
If control structures have conditions, they are delimited by... 

<table>
  <thead>
    <th></th>
    <th></th>
  </thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr><td><span class="c1-cloze">()</span></td> <td><span class="c2-cloze">C</span></td> <td><span class="c3-cloze">JS</span></td> <td><span class="c4-cloze">Java</span></td> <td><span class="c5-cloze">C#</span></td> <td><span class="c6-cloze">Perl</span></td></tr>
<tr><td><span class="c7-cloze">nothing</span></td> <td><span class="c8-cloze">Python</span></td> <td><span class="c9-cloze">Ruby</span></td> <td><span class="c10-cloze">Rust</span></td> <td><span class="c11-cloze">Lua</span></td></tr>
<tr><td><span class="c12-cloze">[]</span></td> <td><span class="c13-cloze">Shell (is actually just test symlinked as  [)</span></td></tr>
  </tbody>
</table>
<span class='cloze-dump'>{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}</span>

<h3>choice/selection control structures</h3>

<p>
  <span class='line'>choice/selection control structures allows choosing between several alternatives based one or more conditons.</span>
  <span class='line'>choice/selection control structures constructs are also just called conditionals.</span>
  <span class='line'>In conditionals, any of the possible paths is called a branch.</span>
</p>

<section>
  <span class='line'>  The most common conditional is if/then/else. 
  </span>
  <span class='line'>the if/then/(else) conditional is typically a statement (in rust, it's an expression).</span>
  An if/then(else) conditional is started by <code>if</code> in nearly all programming languages
  the else arm of an if/then(else) conditional is started by <code>else</code> in nearly all programming languages
  elsif|liquid|perl|ruby
  elif|Python
  elseif|lua

</section>
<section>
  <span class='line'>  The ternary operator is a conditional which is typically an expression. 
  </span>
  <span class='line'>  The ternary operator is more properly called conditional operator. 
  </span>
  <span class='line'>The conditional operator typically has the syntax &lt;condition&gt; ? &lt;iftrue&gt; : &lt;iffalse&gt;. </span>
  <span class='line'>The conditional operator comes from C (more properly an early ancestor of C), thus most programming languages that are inspired by C have it. </span>
  Example in JS:
  <code
    >let attack = enemy.isFireType() ? this.attacks.thundershock :
    this.attacks.inferno;</code
  >
  <span class='line'>Languages that I can write that <b>don't</b> have a ternary/conditional operator with the typical syntax are Bash (more precisely, only exists for arithmetic expressions), Lua, Python, and Rust.</span>
</section>

<section class="cloze-group-children hide-if-inactive-children">
  <span class="line">An if statement/expression, but reversed in its truth value, is an unless statement/expression.</span>
<span class="line">unless statements/expressions use the keyword unless.</span>
<span class="line">unless statements exist in liquid, perl, ruby</span>
</section>



<section class="cloze-group-children hide-if-inactive-children">
  <span class="line">switch is a type of conditional.</span>
<span class="line">the switch conditional is generally a statement.</span>
<span class="line">the switch conditional generally has one condition, and then n branches for possible values.</span>
<span class="line">Besides the branches for possible values of the conditional, the switch conditional generally also allows for a default case.</span>
<span class="line">The default for switch statements is optional in JS</span>
<span class="line">In many languages switch conditionals feature fallthrough, which is where it will continue even after the case ends, until it hits a break/return statement.</span>
switch conditioals are generally started by the <code>case</code> keyword.
Different cases for a switch conditional are started by <code>switch</code> in Java, JS and by <code>when</code> in liquid, ruby.
In liquid, ruby, multiple cases are separated by commas.
The default case for a switch conditional is <code>default</code>  in Java, JS, and <code>else</code> in liquid, ruby.
</section>


JS Syntax examples:

<h2>switch</h2>
<pre><code>switch (expression) {
  {{c1::case}} {{c2::}}value1{{c2::}}{{c3:::}}
   //Statements;
   {{c4::default:}}
}</code></pre>

<h3>Iteration/Loop control structure </h3>

Control flow that repeats the code a number of times is called iteration/looping

<section class="cloze-group-children hide-if-inactive-children">
  <span class="line">Count-controlled loops</span>
<span class="line">Count-controlled loops are loops that repeat a piece of code a certain number of times.</span>
<span class="line">Count-controlled loops are often started with the keyword for.</span>
<span class="line">Count-controlled loops are often called for-loops.</span>
</section>



Condition-controlled loops

<section class="cloze-group-children hide-if-inactive-children">
  <span class="line">A condition-controlled loop is aloop that repeats until a condition changes.</span>
<span class="line">condition-controlled loops can begin or end with their condtion, in which case they will run at least 0 or at least 1 time.</span>
<span class="line">condition-controlled loops that test at the beginning of the loop are often started with the keyword <code>while</code> and are often called while-loops. </span>
<span class="line">condition-controlled loops that test at the end of the loop are often started with the keyword do, then a block, then end with the keyword while followed by the condition and are often called do-while-loops.</span>
Most programming languages I know have while and do-while loops.
Perl has a while loop with an inverted condition (analogous to unless) called until.
Lua has a while loop with an inverted condition that tests at the end of the loop with the syntax repeat ... until
</section>


Collection-controlled loops 

<section class="cloze-group-children hide-if-inactive-children">
  <span class="line">A collection-controlled loop is a loop that loops over all elements of a thing.</span>
<span class="line">Collection-controlled loops are commonly called foreach loops.</span>
  Collection-controlled loops most commonly start with the keyword <code>for</code>, but then feature a different syntax than count-controlled loops. In perl, they instead start <code>foreach</code>.
  Collection-controlled loops generally work on iterators, or by transforming the thing into an iterator implicitly.
  Lua: for &lt;expression&gt; do
  Python: for <expression> in <iterable>:
</section>

Infinite loop

loop|Ruby|Ust




<section class="cloze-group-children hide-if-inactive-children">
  <span class="line">Many languages provide a statement which allows skipping the current (continuing with the next) iteration of a loop.</span>
<span class="line">Most languages use the continue statement to continue with the next loop, Perl and Ruby use the next statement.</span>
<span class="line">Many languages provide a statement which allows ending/exiting the loop.</span>
<span class="line">Most languages use the break statement to end/exit the loop, Perl uses the last statement.</span>
</section>

Sometimes, loops have an else clause. In python, this runs at the end if we never break out of the loop. In liquid, this runs if the loop is empty

lang|count-cont|cond-cont|col-cont
lua|1|2|1
liquid|0|0|1


<h2>other statements</h2>

Empty statements are useful if a statement is required syntactically, but there is nothing to do, e.g. when writing outlines

<table>
  <thead>
    <tr>
      <th>function</th>
      <th>syntax</th>
      <th>languages</th>
    </tr>
  </thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr>
      <td><span class="c1-cloze">Empty statement</span></td>
      <td><span class="c2-cloze">;</span></td>
      <td><span class="c2-cloze">JS</span>, <span class="c-cloze">C#</span></td>
    </tr>
    <tr>
      <td><span class="c1-cloze">Empty statement</span></td>
      <td><span class="c2-cloze">pass</span></td>
      <td><span class="c2-cloze">Python</span></td>
    </tr>
    <tr>
      <td><span class="c1-cloze">Empty statement</span></td>
      <td><span class="c2-cloze">:</span></td>
      <td><span class="c2-cloze">(ba)sh</span></td>
    </tr>
  </tbody>
</table>

<h2>Comments</h2>

Comments in programming are (generally) ignored by compilers/interpreters.
But: Conditional comments are conditional statements interpreted by Microsoft Internet Explorer versions 5 through 9 in HTML source code. They can be used to provide and hide code to and from these versions of Internet Explorer. 
Comments are written primarily for humans


Single line:
--|lua
//|C#|Java|JS|Rust
\#|cron|gitignore|hosts|i3 config|Markdown|Perl|Python|Ruby|sh|YAML
%|Latex

Multiline:
--\[\[foo]]|lua
/\*foo\*/|C#|Java|JS|Rust
&lt;!-- foo -->|HTML
=begin foo =end|Ruby
{% comment %} ... {% endcomment %}|Liquid

Documentation
for the following thing|///|Rust
for the thing we are in right now|//!|Rust

<h2>Identifiers</h2>

<h3>Case</h3>

snake_case|variables, methods (, symbols)|ruby
UpperCamelCase|classes|ruby
SCREAMING_SNAKE_CASE|constants|ruby

<h2>Variables</h2>

In lua, values are typed, but variables are not. 

Block-scoped variables
my|perl
local|lua

Global variables
ø|lua|perl

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


<h3>Declaring multiple variables</h3>

a, b = 1, 2 (or e.g. returnTwoValues()) (lua)

<h2>(Data) types</h2>

An abstract data type is defined in terms of its behavior or more specifically its semantics, instead of in terms of its syntax.
Lua boolean
literals: true/false A null pointer/reference/type/value indicates that we're
not referring to a valid thing
Datatypes implemented in a programming language can either be scalar or compound/composite


<h3>Keywords of specific languages</h3>
C#: int, float, bool, string, char, double
Java: byte, short, int, long, float, double, char, String, boolean

<h3>Dynamic vs Static typing</h3>

Dynamic typigng: type checking at runtime ≈ values have type
Static typing: type checking at compile time ≈ variables have type

Dynamically typed languages I know: JavaScript, Lua, Python, Ruby
Statically typed languages I know: C#, Java, Perl (with regards to the scalar, array, hash distinction)

<h3>Type inference/manifest</h3>

Explicit/manifest typing is a feature of a type system where the type has to be explicitly declared.
Implicit/latent typing is a feature of a type system where the type is not explicitly declared.
Implicit/latent typing  <-> Explicit/manifest typing 
Type inference is a rough synonym for implict/latent typing, but is often used in contexts where the language is otherwise generally explicitly/manifestly typed.
Only statically typed languages can usefully be explicitly/manifestly typed
Type inference in C#: var 

<h3>Firstclassness</h3>

Lua: all values

<h3>Null types</h3>

nil|lua|liquid|ruby
null|C#|Java|JS
undefined|JS
there isn't one|Rust

<h3>boolean</h3>

A boolean data type is a type that has one of two possible values, indicating
truth values.

true/false|C#|Java|JavaScript|Lua
True/False|Python

<h3>float</h3>

In Java and C#, to indicate a float literal you must add f as a suffix.

<h3>falsiness</h3>

Something is falsy if it evaluates to false in a boolean context.
Most langauges treat at least their null type and their false type as falsy.


<section class="cloze-group-children hide-if-inactive-children">
  <span class="line">Enum is short for enumeration or enumerated datatype.</span>
<span class="line">An enum is a datatype that can take on one of a finite set of values.</span>
<span class="line">In stats terms, an enum is a categorical variable.</span>
<span class="line">We may want to consider the boolean type an enum of {true, false}</span>
<span class="line">Of the languages I know, C#, Java and TS allow creation of enums via the enum keyword.</span>
<span class="line">Rust also uses the enum keyword, but for things more like tagged unions.</span>
<span class="line">Python allows using enums via an external module</span>
C#, Java enum syntax: enum &lt;name> {
  &lt;variant>,
  &lt;variant2>,
  ...
}
In C# the syntax &lt;variant> = &lt;value> exists to apply values to enum variants
</section>

<h3>Collections</h3>

Collections are an abstract data type that hold a number of data items.
Associative collections map keys to values. 

<h4>Associative arary</h4>

An associative array is an abstract datatype composed of a collection of (key, value) pairs so that each possible key appears only once (as a key).
Different programming language's implementations limit keys to only strings, strings or integers, all values, or something inbetween.

Some languages implement assoc arr via Objects, you then interact with them as you would with objects.
Some languages implement assoc arr as primitives, these then often have their own syntax for interaction.
Java implements associative arrays via things implementing the <code>Map</code> interface, e.g. <code>HashMap</code>, both defined over two generics.
JS implements associative arrays via the <code>Map</code> and <code>WeakMap</code> classes. objects (esp. object literals) also perform many of the operations we would expect of associative arrays.
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

deleting key
set it to null type|lua

Retrieval function
get()|Rust

Array/Iterator of keys
keys()|Ruby

Has key? 
key?|Ruby

Has value?
value?|Ruby

get array/iterator of key, value tuple/array/whatever:
pairs()|lua

get array/iterator of keys
keys()|perl
values()|perl

commonly items are separated by ,

<h4>Array<h4>

An array (type) is a abstract datatype of a collection of elemennts, selected by indices.

<table>
  <thead>
    <th></th>
    <th></th>
  </thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
  <tr><td><span class="c1-cloze">no indices (one value only)</span></td> <td><span class="c2-cloze">zero-dimensional array (uncommon)</span></td> <td><span class="c3-cloze">scalar</span></td></tr>
    <tr><td><span class="c1-cloze">one index</span></td> <td><span class="c2-cloze">(one-dimensional) array</span></td> <td><span class="c3-cloze">vector</span></td></tr>
<tr><td><span class="c4-cloze">two indices</span></td> <td><span class="c5-cloze">two-dimensional array</span></td> <td><span class="c6-cloze">matrix</span></td></tr>
<tr><td><span class="c7-cloze">n indices</span></td> <td><span class="c8-cloze">multidimensional array</span></td> <td><span class="c9-cloze">tensor</span></td></tr>
  </tbody>
</table>
<span class='cloze-dump'>{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}</span>

Arrays may be dynamic = have variable size, or static = have fixed size.
Dynamic arrays are sometimes called arraylists.
Arrays are generally primitives in different programming languages, though they differ on syntax and what they call them.

dynamic arrays

array|perl|JS|ruby
vector|rust
ArrayList|Java

static arrays

array|C#|Java|Rust
list|python

both/N/A

sequence|yaml
array|liquid



table|lua (though this is more properly the assoc array type, it just happens that an assoc array w/o keys will have numeric keys set up for it by lua, making it also the array type)

Array literals

In array literals, the invidual elements are generally separated by ',', except sh, which separates them by space

()|Perl (same as assoc. arr), Shell
[]|YAML (if inline)
{}|C#|Java

Most languages use the same syntax for one-dimensional, two-dimensional, or multidimensionall arrays, merely nesting the literals.

YAML also has indentation delimited, newline separated, individual items marked by <code>- </code> version

Array indexing

Most langauges start array indices at 0, however lua starts them at 1

<h4>Lists</h4>

Lists/Sequences are an abstract data type (specifically a collection), in which each element has a position (a first element, a second element), and that are finite.
Lists are always dynamically sized
C#: List, defined over one generic. must be created via constructor.

<h4>Streams</h4>

Lists/Sequences are an abstract data type (specifically a collection), in which each element has a position (a first element, a second element), and that are infinite (or at least potentially so).


<h3>Iterators</h3>

An iterator is an object (or similar) whose purpose is to iterate over some data. In general, an iterator has a next() method that returns the next element.
An iterable is generally something that can create an iterator of itself.

<h4>Generators</h4>

A generator is a form of iterator. Generators are created via a generator function (thus you control what the next() method returns), but otherwise behave like any other iterator.

<h3>Numbers<h3>

<h4>Integers</h4>

Integer literals generally not overtly marked

<h3>Strings<h3>

In many languages, especially those that do not have a char type, string literals can be indicated either with single or double quotes.
Some langauges differentiate between string literals with single and double quotes, some languages (lua, liquid) do not.
In many languages, single-quoted string literals act as raw string literals.

strings are immutable|python

A raw string is a string literal where character escapes have been disabled and so everything is a literal.
r"foo"|Python|Rust
String.raw`foo`|JS
'foo'|sh|Perl|Ruby

Multiline string delimiters
`containsnewlines`|JS
\[\[containsnewlines\]\]|Lua
"containsnewlines"|Rust (all strings are multiline)
"""containsnewlines"""|Python

<h2>operators</h2>

overloading
In liquid, the order of operatons is right to left. Parentheses are forbidden.

<h3>assignment</h3>

= is used as the assignment operator in most programming languages

<h3>equality</h3>

~=|not equals|lua
!=|not equals|C#|Java
==|equals|most programming languages
<=|less than or equals|most programming languages
&gt;=|greater than or equals|most programming languages
&gt;|greater than|most programming languages
&lt;|less than|most programming languages
<=>|returns 1 if left arg is larger, -1 if right arg is larger, and 0 if both are equal|Ruby

Python uses the `is` operator when comparing equality of location in memory

<h3>logic</h3>

logical and|and|python|liquid|lua|Ruby (lower precendence)
logical and|&&|C#|Java|JS|Ruby (higher precendence)|(ba)sh
logical or|or|python|liquid|lua|Ruby (lower precendence)
logical or|barbar|C#|Java|JS|Ruby (higher precendence)|(ba)sh
logical not|not|python
logical not|!|C#|Java|JS

<h4>short-circuiting</h4>

(ba)sh

<h3>bitwise</h3>

bitwise not|~
left shift|&lt;&lt;
right shift|>>

<h3>math</h3>

addition|+
multiplication|*
subtraction|-
division|/|Python: always returns a float
floor division|//
remainder|%
power|**

<h3>comma</h3>

In the C and thus in JS, Perl, the comma operator (represented by the token ,) is a binary operator that evaluates its first operand and discards the result, and then evaluates the second operand and returns this value (and type).


<h3>element in collection/substring in string?</h3>

contains|liquid
in|Python

<h3>remove element from collection</h3>

del|python

<h3>Slicing</h3>

Slicing is extracting a subset of elements from a data structure.
Slicing is most commonly performed on arrays or strings.
In most cases, omitting the start defaults to 0, and omitting the end defaults to the maximum value (last element/slength)

[start:end_excl:step]|Python
.slice(start, end_excl)|JS
[start..end_incl]|Ruby
[start...end_excl]Ruby
[start,length]Ruby
[start..end_excl]Rust
[start..=end_inc]|Rust

Part delimiters
:|Python
..|Perl

Order/parts
(start,stop,step) (3-tuple)|Python

<h3>Length of strings, arrays, etc.</h3>

.length|C#|Java|JS|Ruby
len(somestr)|Python
#foo|lua

<h3>String interpolation<h3>

String interpolation is evaluating a string with placeholders and replacing them with their values
String interpolation is a form of template processing (cf other cards)

\${expr}|JS|only in template literals
\#{}|Ruby|SCSS/SASS
\$variable|sh|only with variable names
\${epxr}|sh|more feature-full


<h3>String multiplication</h3>

x|Perl
*|Python

<h3>String concatenation</h3>

<table>
  <thead>
    <tr>
      <th>syntax</th>
      <th>languages</th>
    </tr>
  </thead>
  <tbody class="cloze-group-children hide-if-inactive-children">
    <tr>
      <td><span class="c2-cloze">..</span></td>
      <td><span class="c3-cloze">Lua</span></td>
    </tr>
    +|Java|C#|Python|Ruby|Rust|JS
    .|Perl
  </tbody>
</table>

<h3>common string methods</h3>

convert to uppercase|.upper()|Python
convert to lowercase|.lower()|Python
convert to uppercase|.toUpperCase()|JS
convert to lowercase|.toLowerCase()|JS
split string on foo|.split(foo)|Python

<h2>Error handling<h2>


<h3>Throwing errors</h3>

keywords
die|perl
throw|JS|Java|C#
error()|lua

<h2>Callable units</h2>

Callable units generally can take arguments if specified.

Keyword to create a callable unit
function|JS|Lua
fn|Rust
def|python
sub|perl

<h3>returning</h3>

Across most languages, the keyword to return whatever value is the <code>return</code> keyword.
Multiple values: separated by comma|lua

<h3>Closures</h3>

All callable units automatically create closures in JS, lua.

<h3>Call by...</h3>


sharing|lua|JS|Java

<h3>Anonymous functions</h3>

A callable unit not bound to an identifier is an anonymous function/callable unit.
First-class functions/callable units are callable units that are first-class citizens.
anonymous functios are almost always first-class functions, and are thus often passed as arguments, etc.
However, often non-anonymous functions can also be first-class functions

In ruby, anonymous first-class functions are called blocks.
In JS, lua, all functions are first-class. 
In JS, anonymous functions have no special syntax, you merely leave out the identifier.

<h3>Arguments<h3>

most languages require the possible parameters defined in a callable unit definition to be wrapped in parantheses.
sh doesn't allow specifying parameters at all
most languages require the arguments to a function call to be wrapped in parentheses.
most languages separate both the parameteres and arguments with commas.

Exceptions:
1 arg doesn't need parens|lua
always optional|ruby|perl
never|sh


<h2>Classes & objects </h2>

Keyword to declare a class is done by the keyword <code>class</code> in pretty much all programming languages which have it.
In most programming languages, you refer to your superclass=base class with the keyword <code>super</code>.
In most programming languages, you specify a subclass/superclass relationship like so: Subclass extends Superclass
In ruby, you specify a subclass/superclass relationship like so: Subclass < Superclass

reference to the current object/construct
self|Ruby|Rust
this|C#|Java|JS

method in lua function object:method(...)

<h3>Constructors/object creation</h3>

Creating a new object via a constructor is done by the new operator in most languages.
A constructor is generally a callable unit and thus called with ()
Rust doesn't use any operator to create new Structs. In general, you use literals, some type provide a new() associated function.

<h3>type parameters and generics</h3>

The things that define {{c1::the types}} a function/object/... is defined over, which usually go in {{c2::angle brackets}}, are across programing languages usually called {{c3::type parameters}}.
Generally, multiple type parameters are separated by , 

<h3>Access modifier</h3>

<h2>IO</h2>



<h2>import/export</h2>

<h2>Standard library</h2>

count occurrences of element
foo.count(bar)|Python|Ruby
no easy way|JS

get index of element
foo.index(bar)|Python
foo.indexOf(bar)|JS

<h3>Print</h3>

Print functions in different languages

print()|lua|perl|python
console.log()|JS
System.out.prinln()|Java
echo|liquid (within liquid block)|(ba)sh

<h3>ranges</h3>

Ranges may be a syntax for generating iterators/arrays, or may be their own type

range(start, stop, step)|python
(start..stop)|liquid









<span class="line">https://en.wikipedia.org/wiki/Type_theory#History</span>

Associative arrays: names, literals, other construction methods, etc.



Square bracket notation
any key in a table lua

dot notation: lua
string keys of tables lua
members of objects in lua
but: not method calls, use : instead



A metacharacter is a character that has a special meaning to a computer program, such as a shell interpreter or a regular expression (regex) engine.

An escape character is a metacharacter that invokes an alternative interpretation of the following character(s)
An escape sequence is the combination of an escape character and the subsequent characters that has a specific meaning.
In most programming languages, \ acts as a/the escape character.
In HTML, & acts as a/the escape character.
Liquid is rare in that escape sequences don't exist at all.
Generally, most languages will require using an escape sequence for their metacharacters, or at least the ones that could have meaning in a given context, this is known as character quoting.
Besides character quoting, escape sequences are often used for characters that cannot (easily) be typed on a keywboard.

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

Newline may refer to the newline character or any newline

even?|Is the thing even|Integer
next|get the next element|Integer, String
sort|sort the thing|
class|get the class this is an object of|any object
methods|get the methods the object has|any object



In computer programming, a directive or pragma (from "pragmatic") is a language construct that specifies how a compiler (or other translator) should process its input