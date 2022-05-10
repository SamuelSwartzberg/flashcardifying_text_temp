# operations

»⟮an operation⟯« is the same thing as ⟮＿a function＿⟯, but one which ⟮gets its own ＿operator＿⟯.
»⟮Operands⟯« are ⟮the input values⟯ of ⟮＿operations＿⟯.
»⟮An operator⟯« is ⟮the symbol signifing⟯ ⟮＿the operation＿⟯.
We might want to consider a mathematical constant to be an operation of arity 0.

## types

### binary

#### exponentiation

»⟮Exponentiation⟯« is ⟮＿a binary operation＿⟯ involving the two operands ⟮＿base＿⟯ and ⟮c_;＿exponent＿⟯.
⟮＿Exponentiation＿⟯ is often written as `⟮b⎴n⎴⟯`, where ⟮b⟯ is ⟮＿the base＿⟯ and ⟮c-;n⟯ is ⟮＿the exponent＿⟯.
⟮＿Exponentiation＿⟯ `⟮b⎴n⎴⟯` means `⟮Π⟯⟮⎵i=1⎵⎴n⎴b⟯` .
⟮base⟯ =syn= ⟮radix⟯
⟮＿Exponentiation＿⟯ is ⟮＿nonassociative＿⟯ and ⟮＿noncommutative＿⟯.
The order of operations for multiple ⟮＿exponentiation＿⟯ is typically ⟮top-down⟯.

##### root

»⟮The root⟯« is ⟮ambiguous between⟯ ⟮any ＿nth root＿⟯.
»⟮The nth root⟯« of »⟮a radicand⟯« x is ⟮a number⟯ r such that ⟮r^n = x⟯ (n ∈ N).
»⟮The degree⟯« of a root is ⟮the n of ＿the nth root＿⟯.
»⟮A square/cube root⟯« is ⟮＿a root＿⟯ with ⟮＿a degree＿ of 2/3⟯.
»⟮A surd⟯« is ⟮an unresolved ＿root＿⟯.
»⟮Root extraction⟯« is ⟮the computation of ＿a root＿⟯.

###### real roots

»⟮A real root⟯« is ⟮＿a root＿⟯ which is ⟮＿a real number＿⟯.
⟮Any number⟯ may have ⟮0 - 2⟯ ⟮＿real roots＿⟯.
There are ⟮2⟯ ⟮＿nth real roots＿⟯ if ⟮＿the degree＿⟯ of the root is ⟮even⟯.

####### special cases

⟮＿the real root＿⟯ of ⟮0⟯ is ⟮0⟯ no matter ⟮the ＿degree＿⟯.
⟮A negative number⟯ has ⟮no⟯ ⟮＿real roots＿⟯.

####### properties

!For ⟮non-negative⟯ ⟮real⟯ ⟮＿radicands＿⟯ a, b:
```
⟮nthrt(n, a⎴m⎴)⟯ = ⟮(a⎴m⎴)⎴1/n⎴⟯ = ⟮a⎴m/n⎴⟯
⟮nthrt(n, ab)⟯ = ⟮nthrt(n, a)⟯⟮c_;*⟯⟮c_;nthrt(n, b)⟯
⟮nthrt(n, a/b)⟯ = ⟮nthrt(n, a)⟯⟮c_;/⟯⟮c_;nthrt(n, b)⟯
```

###### imaginary unit

»⟮The imaginary unit⟯« is a ⟮non-real⟯ number satisfying ⟮x⎴2⎴+1=0⟯.
⟮imaginary unit⟯ =symb=&gt; ⟮i⟯

###### notation

»⟮The radical symbol⟯« is the symbol ⟮√⟯.
»⟮Radical notation⟯« is using⟮＿ the radical symbol＿⟯ with ⟮a line continuing on top⟯ to ⟮indicate ＿a root＿⟯.
⟮＿The degree＿ of ＿a root＿⟯ is ⟮placed on the top left⟯ of ⟮＿the radical symbol＿⟯.
⟮＿The radical symbol＿⟯ ⟮without an explicit ＿degree＿⟯ generally refers to ⟮＿the square root＿⟯.

###### in terms of exponentiation

⟮nthrt(degree, radicand)⟯ = ⟮radicand⎴1/degree⎴⟯

##### logarithm

»⟮The logarithm⟯« is ⟮＿the inverse function＿⟯ to ⟮＿exponentiation＿⟯.
»⟮The logarithm⟯« of a number x yields ⟮the exponent n⟯ that ⟮applied to a given base b⟯ ⟮would yield x⟯.
⟮If no base is given⟯ for a logarithm, it is ⟮obvious⟯ or ⟮c_;doesn't matter⟯.
⟮The logarithm of x for a base b⟯ is denoted as `⟮log⎵b⎵(x)⟯` or `⟮c_;log⎵b⎵x⟯`
`⟮log⎵b⎵⟯⟮(b⎴n⎴)⟯ = ⟮n⟯`

»⟮the natural logarithm⟯« is ⟮log⎵e⎵⟯.
⟮＿the natural logarithm log⎵e⎵＿⟯ is usually just written ⟮ln⟯.

##### axioms, properties and identities

```
b⎴⟮1⟯⎴ = ⟮b⟯
b⎴⟮0⟯⎴ = ⟮1⟯
b⎴⟮-n⟯⎴ = ⟮1/b⎴n⎴⟯
```

##### exponent rules

»⟮The exponent rules⟯« are ⟮a set of ＿identities＿⟯ that hold for ⟮all rational exponents⟯ 
```
⟮b⎴n⎴b⎴m⎴⟯ = ⟮b⎴n+m⎴⟯
⟮(b⎴n⎴)⎴m⎴⟯ = ⟮b⎴nm⎴⟯
⟮(bc)⎴n⎴⟯ = ⟮b⎴n⎴c⎴n⎴⟯
```

## properties

### identity element

»⟮The right/left-identity element e⟯« of a binary operation ⋅ on a set S is ⟮e ∈ S⟯ such that (⟮∀ a ∈ S⟯)(⟮a ⋅ e = a / e ⋅ a = a⟯).
»⟮The identity element⟯« is an element that is ⟮＿a right-identity element＿ ∧ ＿a left-identity element＿⟯.
⟮The identity element⟯ may simply be called ⟮an identity⟯.
⟮＿The identity element＿⟯ ⟮of a certain operation⟯ is often called ⟮‹operation› identity (e.g. multiplicative identity)⟯.
⟮＿The identity element＿⟯ of ⟮＿multiplication/addition＿⟯ performed on real numbers is ⟮1/0⟯.
⟮＿The right-identity element＿⟯ of ⟮＿division/subtraction＿⟯ performed on real numbers is ⟮1/0⟯.

#### inverse

given a binary operation ⋅ and ⟮＿an identity element e＿⟯, if ⟮x*y = e⟯, ⟮x⟯ is »⟮the left-inverse⟯« of ⟮c-;y⟯ and ⟮c_;y⟯ is »⟮the right-inverse⟯« of ⟮c_-;x⟯.
An element is »⟮the inverse element⟯« of another element if it can be both its right- and left inverse
⟮＿The inverse＿⟯ ⟮of a certain operation⟯ is often called ⟮‹operation› inverse (e.g. multiplicative inverse)⟯.

##### nomenclature

⟮＿the inverse＿⟯ of a number x is denoted by ⟮x⎴-1⎴⟯.
⟮additive inverse⟯ =syn= ⟮opposite⟯
⟮multiplicative inverse⟯ =syn= ⟮reciprocal⟯

#### certain cases

⟮＿the reciprocal＿⟯ of a fraction ⟮a/b⟯ is ⟮b/a⟯.

### idempotentitcity

A function/operation/etc. is »⟮idempotent⟯« if ⟮it can be applied mulitple times⟯ without ⟮changing the result⟯ ⟮beyond the initial application⟯. 
Examples for ⟮＿idempotent functions＿⟯ include ⟮abs(x), floor(x), ceil(x) etc.⟯ 

### comeassdir

»⟮Comeassdir⟯« is the three properties ⟮＿commutativity＿⟯, ⟮＿associativity＿⟯, and ⟮＿distributivity＿⟯.

#### commutative

»⟮Commutatitivity⟯« is ⟮if changing the order of operands⟯ ⟮does not change the result⟯.
Of the elementary arithmetic operations, ⟮addition and multiplication⟯ are ⟮commutative：order ops⟯, ⟮c-;subtraction and division⟯ are ⟮noncommutative⟯.

#### associative

»⟮Associativity⟯« is ⟮if rearranging parentheses⟯ ⟮does not change the result⟯.
Of the elementary arithmetic operations, ⟮addition and multiplication (if not mixed)⟯ are ⟮associative：parentheses⟯, ⟮c-;subtraction and division⟯ are ⟮nonassociative⟯.

#### distributive

something is »⟮distributive⟯« if it is ⟮both ＿left-＿ and ＿right-distributive＿⟯


table:distributivity|rule
»⟮left-distributive⟯«|⟮ζ * (x+y)⟯ = ⟮(ζ * x) + (ζ * y)⟯
»⟮right-distributive⟯«|⟮(x+y) * ζ⟯ = ⟮(x * ζ) + (y * ζ)⟯

## arguments

### arity

The »⟮arity⟯« of something is ⟮how many⟯ ⟮＿operands＿ or ＿arguments＿⟯ are involved. 
⟮＿Arity＿⟯ is a property of ⟮＿operations＿/＿functions＿/＿relations＿⟯.
⟮arity⟯ and ⟮adicity⟯ are rough synonyms
⟮＿arity＿⟯ is specified in ⟮latinate⟯ numbers
⟮＿adicity＿⟯ is specified in ⟮greek-derived⟯ numbers.
something »⟮variadic⟯« has ⟮an indefinite ＿arity＿⟯


table:Arity of...|Name
⟮0⟯|»⟮nullary⟯«
⟮1⟯|»⟮unary⟯«
⟮2⟯|»⟮binary⟯«
⟮3⟯|»⟮ternary⟯«
⟮n⟯|»⟮n-ary⟯«


### order

⟮＿Operations＿⟯ can be written in ⟮＿prefix＿⟯, ⟮c_;＿postfix＿⟯ or ⟮c_;＿infix＿⟯ notation.


table:notation|description|alias
»⟮prefix notation⟯«|⟮operator before operands⟯|⟮c+;s∞;polish notation⟯
»⟮postfix notation⟯«|⟮operator after operands⟯|⟮c+;s∞;reverse polish notation⟯
»⟮infix notation⟯«|⟮operator between operands⟯


Trivia: The description "Polish" refers to the nationality of logician Jan Łukasiewicz, who invented Polish notation in 1924