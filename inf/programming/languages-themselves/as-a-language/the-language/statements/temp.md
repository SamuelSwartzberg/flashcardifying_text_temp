
# statements

Statements are the fundamental unit of programming in imperative programming languages (used in some restricted sense).
Ergo, imperative programming languages (in some restricted sense) are those that use statements as their fundamental unit, in this sense a program consits of n statements.
Statements do not return a value.
Since statements do not return a value, they either do nothing or cause side effects.
var test = 2 + 6; → side effect of initializing a variable test
An expression statement is a statement that consists of a single expression.

## imperativeness

Imperative vs. declarative may be understood as a spectrum.
If imperative/declarative is understood as a spectrum, the more imperative something is, the more you're specifying the actual steps necessary for something to happen.
If imperative/declarative is understood as a spectrum, the more declarative something is, the more you're merely specifying what you want to happen, unconcerned about the steps.
On the imperative/declarative spectrum, functional languages are quite far on the declarative side.
Markup languages such as HTML are quite far on the declarative side of the imperative/declarative spectrum.

## statement separators and terminators

A statement separator is used to demarcate boundaries between two separate statements. A statement terminator is used to demarcate the end of an individual statement.
Semicolons are used in programming languages for two things: statement separators and statement terminators. When a language uses semicolons as statement separators, this allows you to write more than one statement on the same line.
Semicolons as statement terminators aren’t optional and are used to definitively mark the end of a statement.

Typically, even if programming languages have semicolons as statement terminators, they don't go after block statements. JS is the exception to this, where you can but don't have to do this.

semicolons as statement separators and statement terminators|C#|Java|Perl|Rust
semicolons as statement separators, newlines as statement terminators|Lua|Python|Ruby|sh
semicolons as statement separators and statement terminators, complex exceptions apply|JS

In languages which have newlines as statement terminators, typically the statement-terminating newlines can be escaped (generally by \ ) 
e.g. print("foo" + \
"bar")

## blocks

In ⟮most programming languages⟯, a ⟮block⟯ is a ⟮statement⟯.  
However, in ⟮Rust⟯ (and in ruby to, though its weird, as blocks have the same syntax/are merely anon functions w/o arguments), ⟮blocks⟯ are ⟮expressions⟯. 

⟮Blocks⟯ ⟮contain/consist of⟯ ⟮one or more⟯ ⟮statements⟯. 
⟮In/with⟯ ⟮constructs⟯ or ⟮languages⟯ that are ⟮block-scoped⟯, ⟮a block defines a scope⟯. 
⟮Curly-brace/bracket languages⟯ are defined as languages that ⟮use curly-braces⟯ ⟮to define blocks⟯. 
Many programming languages have been influenced by C, sometimes called C-family languages.
C was a curly-brace language, and so many C-family language are curly-brace languages.

Examples of ⟮curly-brace/bracket languages⟯ I can write are ⟮C#⟯, ⟮ECMAScript⟯ → {⟮Javascript⟯, ⟮TypeScript⟯}, ⟮Java⟯, ⟮Perl⟯, ⟮Rust⟯, SCSS (but not Sass). 
Most ⟮curly-brace/bracket languages⟯ ⟮are thus because they are strongly influenced by⟯ ⟮C⟯. 
In some programming languages (JS, Lua, ...?) blocks can stand alone, merely creating a scope. In other programming languages, blocks must follow a certain statement.
In lua, blocks end with `end` (outside of repeat...until). They are begun by `do` when standing alone, or when after a loop, by `then` after an if condition, and by nothing after a function signature
In bash, blocks for if are delimited by then ... (possible else etc.) fi, for for and while by do ... done, for case by in ... esac
In ruby, blocks end with `end`. begin begins a dedicated block statement (and is the keyword for the error handling statement), but no other blocks
In python, pretty much anything (control structure, function, etc) that precedes a block ends with `:`. In Ruby by contrast (which otherwise may look pretty similar), nothing ends with `:`
In some languages, notably Ruby and Rust, block expression return the value of the last statement

liquid|{% keyword %} ... {% endkeyword %}
python|Sass|indentation

### bash

In bash, compound commands includes all control structures and block statements (which bash calls command grouping).
(ba)sh is not generally a curly-brace language, but it still allows creating block statements via {} (but also via `()`)
bash calls its block statements command grouping.
bash block statements/command grouping is what is used by bash functions.
The difference between bash block statements using () and using {} is that () spawns a subshell and thus a new scope, while {} executes the commands in the current shell.

## control structures

The default control flow is linear from top to bottom, this is called sequencing.
A thing that modifies control flow is a control structure. 

A control structure takes the normally linear flow of code and makes it somehow nonlinear.

Programming languages that use control structures outside of GOTO are structured programming languages.
Programming languages that do not use control structures or only use GOTO are non-structured programming languages, which are today quite rare.

Control structures are typically statements, however in Ruby and Rust, they are expressions.
In javascript or JS, most control structures take one statement after it, which can either be a normal statement or a block statement. A statement that does nothing is an empty statement
If control structures have conditions, they are delimited by...

()|C|JS|Java|C#|Perl
nothing|Python|Ruby|Rust|Lua
is complicated|shell

Conditions for control structures in ba(sh) are actually (a) command(s)
If the command(s) that make up the condition for a control structure return a zero exit code, they will be treated as true, and false otherwise.
Ergo, one can use the `test` command in the condition of a (ba)sh control structure, but one can also use any other command and rely on its exit status.
test is also available under the name `[` but requires a closing `]` in this case.
(ba)sh requires all operators and the [] themselves to be separated by spaces, since [ is actually just a symlink for test, and thus all of these are actually arguments for a command.

### choice/selection control structures

choice/selection control structures allows choosing between several alternatives based one or more conditons.
choice/selection control structures constructs are also just called conditionals.
In conditionals, any of the possible paths is called a branch.

#### if

The most common conditional is if/then/else. 
  
the if/then/(else) conditional is typically a statement (in rust, it's an expression).
An if/then(else) conditional is started by `if` in nearly all programming languages
the else arm of an if/then(else) conditional is started by `else` in nearly all programming languages

else if|C#|Java|JS|SCSS/Sass
elseif|lua
elsif|liquid|perl|ruby
elif|Python|(ba)sh
  
Anki has a if-like conditional to show something only if a field has content, indicated like: 
```
lang=text;
⟮{​{⟯⟮#FieldName⟯⟮}​⟯}
	Lorem Ipsum
⟮{​{⟯⟮/FieldName⟯⟮}​⟯}
```

#### conditional operator

The ternary operator is a conditional which is typically an expression. 
The ternary operator is more properly called conditional operator. 
The conditional operator typically has the syntax ‹condition› ? ‹iftrue› : ‹iffalse›. 
The conditional operator comes from C (more properly an early ancestor of C), thus most programming languages that are inspired by C have it. 
Example in JS:
`let attack = enemy.isFireType() ? this.attacks.thundershock : this.attacks.inferno;`
Languages that I can write that ⁑don't⁑ have a ternary/conditional operator with the typical syntax are Bash (more precisely, only exists for arithmetic expressions), Lua, Python, and Rust.

#### others

An if statement/expression, but reversed in its truth value, is an unless statement/expression.
unless statements/expressions use the keyword unless.
unless statements exist in liquid, perl, ruby


Some languages (Perl, Ruby), allow a one-line conditional, where the syntax is ‹expression› ‹conditional› (we might term this a postfix notation)
for the postfix conditionals in perl, ruby


in rust, `if let` instead of `if` allows for an if with pattern matching

#### switch

switch is a type of conditional.
the switch conditional is generally a statement.
the switch conditional generally has one condition, and then n branches for possible values.
Besides the branches for possible values of the conditional, the switch conditional generally also allows for a default case.
The default for switch statements is optional in JS
In many languages switch conditionals feature fallthrough, which is where it will continue even after the case ends, until it hits a break/return statement.
switch conditioals are generally started by the `case` keyword.
Different cases for a switch conditional are started by `switch` in Java, JS and by `when` in liquid, ruby.
In liquid, ruby, multiple cases are separated by commas.
The default case for a switch conditional is `default`  in Java, JS, and `else` in liquid, ruby.
Bash has a fucked-up syntax: case ‹expression› in {‹case›) ‹command› ;;} esac
In C-family languages, switch cases are generally syntactically equivalent to labels, and thus don't themselves create a new scope by default.

JS Syntax examples:

```
switch (expression) {
  ⟮case⟯ ⟮c2;⟯value1⟮c2;⟯⟮:⟯
   //Statements;
   ⟮default:⟯
}
```

#### guards

guardss are additional boolean expressions specified on branches of conditionals that must also evaluate to true if the program is to continue.
Of the languages I know, Rust has guards, introduced by `if`.

### iteration/loop control structure 

Control flow that repeats the code a number of times is called iteration/looping


#### count-controlled loops

Count-controlled loops are loops that repeat a piece of code a certain number of times.
Count-controlled loops are often started with the keyword for.
Count-controlled loops are often called for-loops.
The typical syntax for count-controlled loops inheriting from C (e.g. C#, Java, JS, Perl) is 
for ‹delimiter›[‹counter-initialization›];[‹counter-end-condition›];[‹counter-change-per-loop›]‹delimiter›‹block›
for (;;) ends up just being an infinite loop
SCSS/Sass instead has the syntax @for ‹variable› from ‹lowerbound› to (excl)/through (incl) ‹upperbound›


#### condition-controlled loops


A condition-controlled loop is aloop that repeats until a condition changes.
condition-controlled loops can begin or end with their condtion, in which case they will run at least 0 or at least 1 time.
condition-controlled loops that test at the beginning of the loop are often started with the keyword `while` and are often called while-loops. 
condition-controlled loops that test at the end of the loop are often started with the keyword do, then a block, then end with the keyword while followed by the condition and are often called do-while-loops.
Most programming languages I know have while and do-while loops, in fact I don't think I know a programming language that doesn't have a while loop.
Perl and bash have an until loop: a while loop with an inverted condition (analogous to unless).
Lua also has a while loop with an inverted condition that tests at the end of the loop with the syntax repeat ... until
in rust, `while let` instead of `while` allows for a while with pattern matching


#### collection-controlled loops 


A collection-controlled loop is a loop that loops over all elements of a thing.
Collection-controlled loops are commonly called foreach loops.
Collection-controlled loops most commonly start with the keyword `for`, but then feature a different syntax than count-controlled loops. In perl, they instead start `foreach`.
Collection-controlled loops generally work on iterators, or by transforming the thing into an iterator implicitly.
Lua: for ‹expression› do
bash, Liquid, Python, Ruby, Rust: for ‹expression› in ‹iterable› ...
Java: for (‹type› ‹element› : ‹iterable›) ...
JS: for (‹variable› in ‹object›) ... (only used to iterate over all key-value pairs of an assoc array)
In a JS forin loop, the thing assigned to the variable is the key, not the value.
for (‹variable› of ‹iterable›) ...
SCSS: @each ‹variable› in  ‹iterable›
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
In Rust, you can pass an argument to the break thing (break ‹something›) to have that be the return value of the block expression


Sometimes, loops have an else clause. In python, this runs at the end if we never break out of the loop. In liquid, this runs if the loop is empty

(loops with reversed condition do not count as separate kinds of loops)
lang|count-cont|cond-cont|col-cont|infinite
lua|1|2|1|0
liquid|0|0|1|0
Python|0|1|1|0
JS|1|1|2|0
SCSS|1|1|1|0
Rust|0|1|1|1

## labels

A label in a programming language is a sequence of characters that identifies a location within source code. In most languages labels take the form of an identifier, often followed by a punctuation character (e.g., a colon). 
JS and C have labels.
JS label syntax: ‹name›:
Labels can be used to break out of a loop that is not the enclosing one.

## other statements

### empty statements

Empty statements are useful if a statement is required syntactically, but there is nothing to do, e.g. when writing outlines

;|JS|C#
pass|Python
:|(ba)sh

: is actually more complicated. It is kinda similar to true, and is therefore used as a condition for an infinite while loop.