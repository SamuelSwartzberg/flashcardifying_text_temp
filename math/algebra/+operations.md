# operations

»⟮c1;an operation⟯« is the same thing as ⟮＿a function＿⟯, but one which ⟮gets its own ＿operator＿⟯.
»⟮c4;Operands⟯« are ⟮the input values⟯ of ⟮＿operations＿⟯.
»⟮c7;An operator⟯« is ⟮the symbol signifing⟯ ⟮＿the operation＿⟯.
We might want to consider a mathematical constant to be an operation of arity 0.

## types

### binary

#### exponentiation

»⟮c10;Exponentiation⟯« is ⟮＿a binary operation＿⟯ involving the two operands ⟮＿base＿⟯ and ⟮c_;＿exponent＿⟯.
⟮c13;＿Exponentiation＿⟯ is often written as `⟮b⎴n⎴⟯`, where ⟮b⟯ is ⟮＿the base＿⟯ and ⟮c-;n⟯ is ⟮＿the exponent＿⟯.
⟮c17;＿Exponentiation＿⟯ `⟮b⎴n⎴⟯` means `⟮Π⟯⟮⎵i=1⎵⎴n⎴b⟯` .
⟮c21;base⟯ =syn= ⟮radix⟯
⟮c23;＿Exponentiation＿⟯ is ⟮＿nonassociative＿⟯ and ⟮＿noncommutative＿⟯.
The order of operations for multiple ⟮c26;＿exponentiation＿⟯ is typically ⟮top-down⟯.

##### root

»⟮c28;The root⟯« is ⟮ambiguous between⟯ ⟮any ＿nth root＿⟯.
»⟮c31;The nth root⟯« of »⟮a radicand⟯« x is ⟮a number⟯ r such that ⟮r^n = x⟯ (n ∈ N).
»⟮c35;The degree⟯« of a root is ⟮the n of ＿the nth root＿⟯.
»⟮c37;A square/cube root⟯« is ⟮＿a root＿⟯ with ⟮＿a degree＿ of 2/3⟯.
»⟮c40;A surd⟯« is ⟮an unresolved ＿root＿⟯.
»⟮c42;Root extraction⟯« is ⟮the computation of ＿a root＿⟯.

###### real roots

»⟮c44;A real root⟯« is ⟮＿a root＿⟯ which is ⟮＿a real number＿⟯.
⟮c47;Any number⟯ may have ⟮0 - 2⟯ ⟮＿real roots＿⟯.
There are ⟮c50;2⟯ ⟮＿nth real roots＿⟯ if ⟮＿the degree＿⟯ of the root is ⟮even⟯.

####### special cases

⟮c54;＿the real root＿⟯ of ⟮0⟯ is ⟮0⟯ no matter ⟮the ＿degree＿⟯.
⟮c58;A negative number⟯ has ⟮no⟯ ⟮＿real roots＿⟯.

####### properties

!For ⟮c61;non-negative⟯ ⟮real⟯ ⟮＿radicands＿⟯ a, b:
```
⟮c64;nthrt(n, a⎴m⎴)⟯ = ⟮(a⎴m⎴)⎴1/n⎴⟯ = ⟮a⎴m/n⎴⟯
⟮c67;nthrt(n, ab)⟯ = ⟮nthrt(n, a)⟯⟮c_;*⟯⟮c_;nthrt(n, b)⟯
⟮c69;nthrt(n, a/b)⟯ = ⟮nthrt(n, a)⟯⟮c_;/⟯⟮c_;nthrt(n, b)⟯
```

###### imaginary unit

»⟮c71;The imaginary unit⟯« is a ⟮non-real⟯ number satisfying ⟮x⎴2⎴+1=0⟯.
⟮c74;imaginary unit⟯ =symb=&gt; ⟮i⟯

###### notation

»⟮c76;The radical symbol⟯« is the symbol ⟮√⟯.
»⟮c78;Radical notation⟯« is using⟮＿ the radical symbol＿⟯ with ⟮a line continuing on top⟯ to ⟮indicate ＿a root＿⟯.
⟮c82;＿The degree＿ of ＿a root＿⟯ is ⟮placed on the top left⟯ of ⟮＿the radical symbol＿⟯.
⟮c85;＿The radical symbol＿⟯ ⟮without an explicit ＿degree＿⟯ generally refers to ⟮＿the square root＿⟯.

###### in terms of exponentiation

⟮c88;nthrt(degree, radicand)⟯ = ⟮radicand⎴1/degree⎴⟯

##### logarithm

»⟮c90;The logarithm⟯« is ⟮＿the inverse function＿⟯ to ⟮＿exponentiation＿⟯.
»⟮c93;The logarithm⟯« of a number x yields ⟮the exponent n⟯ that ⟮applied to a given base b⟯ ⟮would yield x⟯.
⟮c97;If no base is given⟯ for a logarithm, it is ⟮obvious⟯ or ⟮c_;doesn't matter⟯.
⟮c99;The logarithm of x for a base b⟯ is denoted as `⟮log⎵b⎵(x)⟯` or `⟮c_;log⎵b⎵x⟯`
`⟮c101;log⎵b⎵⟯⟮(b⎴n⎴)⟯ = ⟮n⟯`

»⟮c104;the natural logarithm⟯« is ⟮log⎵e⎵⟯.
⟮c106;＿the natural logarithm log⎵e⎵＿⟯ is usually just written ⟮ln⟯.

##### axioms, properties and identities

```
b⎴⟮c108;1⟯⎴ = ⟮b⟯
b⎴⟮c110;0⟯⎴ = ⟮1⟯
b⎴⟮c112;-n⟯⎴ = ⟮1/b⎴n⎴⟯
```

##### exponent rules

»⟮c114;The exponent rules⟯« are ⟮a set of ＿identities＿⟯ that hold for ⟮all rational exponents⟯ 
```
⟮c117;b⎴n⎴b⎴m⎴⟯ = ⟮b⎴n+m⎴⟯
⟮c119;(b⎴n⎴)⎴m⎴⟯ = ⟮b⎴nm⎴⟯
⟮c121;(bc)⎴n⎴⟯ = ⟮b⎴n⎴c⎴n⎴⟯
```

## properties

### identity element

»⟮c123;The right/left-identity element e⟯« of a binary operation ⋅ on a set S is ⟮e ∈ S⟯ such that (⟮∀ a ∈ S⟯)(⟮a ⋅ e = a / e ⋅ a = a⟯).
»⟮c127;The identity element⟯« is an element that is ⟮＿a right-identity element＿ ∧ ＿a left-identity element＿⟯.
⟮c129;The identity element⟯ may simply be called ⟮an identity⟯.
⟮c131;＿The identity element＿⟯ ⟮of a certain operation⟯ is often called ⟮‹operation› identity (e.g. multiplicative identity)⟯.
⟮c134;＿The identity element＿⟯ of ⟮＿multiplication/addition＿⟯ performed on real numbers is ⟮1/0⟯.
⟮c137;＿The right-identity element＿⟯ of ⟮＿division/subtraction＿⟯ performed on real numbers is ⟮1/0⟯.

#### inverse

given a binary operation ⋅ and ⟮c140;＿an identity element e＿⟯, if ⟮x*y = e⟯, ⟮x⟯ is »⟮the left-inverse⟯« of ⟮c-;y⟯ and ⟮c_;y⟯ is »⟮the right-inverse⟯« of ⟮c_-;x⟯.
An element is »⟮c144;the inverse element⟯« of another element if it can be both its right- and left inverse
⟮c145;＿The inverse＿⟯ ⟮of a certain operation⟯ is often called ⟮‹operation› inverse (e.g. multiplicative inverse)⟯.

##### nomenclature

⟮c148;＿the inverse＿⟯ of a number x is denoted by ⟮x⎴-1⎴⟯.
⟮c150;additive inverse⟯ =syn= ⟮opposite⟯
⟮c152;multiplicative inverse⟯ =syn= ⟮reciprocal⟯

#### certain cases

⟮c154;＿the reciprocal＿⟯ of a fraction ⟮a/b⟯ is ⟮b/a⟯.

### idempotentitcity

A function/operation/etc. is »⟮c157;idempotent⟯« if ⟮it can be applied mulitple times⟯ without ⟮changing the result⟯ ⟮beyond the initial application⟯. 
Examples for ⟮c161;＿idempotent functions＿⟯ include ⟮abs(x), floor(x), ceil(x) etc.⟯ 

### comeassdir

»⟮c163;Comeassdir⟯« is the three properties ⟮＿commutativity＿⟯, ⟮＿associativity＿⟯, and ⟮＿distributivity＿⟯.

#### commutative

»⟮c167;Commutatitivity⟯« is ⟮if changing the order of operands⟯ ⟮does not change the result⟯.
Of the elementary arithmetic operations, ⟮c170;addition and multiplication⟯ are ⟮commutative：order ops⟯, ⟮c-;subtraction and division⟯ are ⟮noncommutative⟯.

#### associative

»⟮c172;Associativity⟯« is ⟮if rearranging parentheses⟯ ⟮does not change the result⟯.
Of the elementary arithmetic operations, ⟮c175;addition and multiplication (if not mixed)⟯ are ⟮associative：parentheses⟯, ⟮c-;subtraction and division⟯ are ⟮nonassociative⟯.

#### distributive

something is »⟮c177;distributive⟯« if it is ⟮both ＿left-＿ and ＿right-distributive＿⟯


table:distributivity|rule
»⟮c179;left-distributive⟯«|⟮ζ * (x+y)⟯ = ⟮(ζ * x) + (ζ * y)⟯
»⟮c182;right-distributive⟯«|⟮(x+y) * ζ⟯ = ⟮(x * ζ) + (y * ζ)⟯

## arguments

### arity

The »⟮c185;arity⟯« of something is ⟮how many⟯ ⟮＿operands＿ or ＿arguments＿⟯ are involved. 
⟮c188;＿Arity＿⟯ is a property of ⟮＿operations＿/＿functions＿/＿relations＿⟯.
⟮c190;arity⟯ and ⟮adicity⟯ are rough synonyms
⟮c192;＿arity＿⟯ is specified in ⟮latinate⟯ numbers
⟮c194;＿adicity＿⟯ is specified in ⟮greek-derived⟯ numbers.
something »⟮c196;variadic⟯« has ⟮an indefinite ＿arity＿⟯


table:Arity of...|Name
⟮c198;0⟯|»⟮nullary⟯«
⟮c200;1⟯|»⟮unary⟯«
⟮c202;2⟯|»⟮binary⟯«
⟮c204;3⟯|»⟮ternary⟯«
⟮c206;n⟯|»⟮n-ary⟯«


### order

⟮c208;＿Operations＿⟯ can be written in ⟮＿prefix＿⟯, ⟮c_;＿postfix＿⟯ or ⟮c_;＿infix＿⟯ notation.


table:notation|description|alias
»⟮c210;prefix notation⟯«|⟮operator before operands⟯|⟮c+;s∞;polish notation⟯
»⟮c213;postfix notation⟯«|⟮operator after operands⟯|⟮c+;s∞;reverse polish notation⟯
»⟮c216;infix notation⟯«|⟮operator between operands⟯


Trivia: The description "Polish" refers to the nationality of logician Jan Łukasiewicz, who invented Polish notation in 1924

<span class='cloze-dump'>{{c1::}}{{c2::}}{{c3::}}{{c4::}}{{c5::}}{{c6::}}{{c7::}}{{c8::}}{{c9::}}{{c10::}}{{c11::}}{{c12::}}{{c13::}}{{c14::}}{{c15::}}{{c16::}}{{c17::}}{{c18::}}{{c19::}}{{c20::}}{{c21::}}{{c22::}}{{c23::}}{{c24::}}{{c25::}}{{c26::}}{{c27::}}{{c28::}}{{c29::}}{{c30::}}{{c31::}}{{c32::}}{{c33::}}{{c34::}}{{c35::}}{{c36::}}{{c37::}}{{c38::}}{{c39::}}{{c40::}}{{c41::}}{{c42::}}{{c43::}}{{c44::}}{{c45::}}{{c46::}}{{c47::}}{{c48::}}{{c49::}}{{c50::}}{{c51::}}{{c52::}}{{c53::}}{{c54::}}{{c55::}}{{c56::}}{{c57::}}{{c58::}}{{c59::}}{{c60::}}{{c61::}}{{c62::}}{{c63::}}{{c64::}}{{c65::}}{{c66::}}{{c67::}}{{c68::}}{{c69::}}{{c70::}}{{c71::}}{{c72::}}{{c73::}}{{c74::}}{{c75::}}{{c76::}}{{c77::}}{{c78::}}{{c79::}}{{c80::}}{{c81::}}{{c82::}}{{c83::}}{{c84::}}{{c85::}}{{c86::}}{{c87::}}{{c88::}}{{c89::}}{{c90::}}{{c91::}}{{c92::}}{{c93::}}{{c94::}}{{c95::}}{{c96::}}{{c97::}}{{c98::}}{{c99::}}{{c100::}}{{c101::}}{{c102::}}{{c103::}}{{c104::}}{{c105::}}{{c106::}}{{c107::}}{{c108::}}{{c109::}}{{c110::}}{{c111::}}{{c112::}}{{c113::}}{{c114::}}{{c115::}}{{c116::}}{{c117::}}{{c118::}}{{c119::}}{{c120::}}{{c121::}}{{c122::}}{{c123::}}{{c124::}}{{c125::}}{{c126::}}{{c127::}}{{c128::}}{{c129::}}{{c130::}}{{c131::}}{{c132::}}{{c133::}}{{c134::}}{{c135::}}{{c136::}}{{c137::}}{{c138::}}{{c139::}}{{c140::}}{{c141::}}{{c142::}}{{c143::}}{{c144::}}{{c145::}}{{c146::}}{{c147::}}{{c148::}}{{c149::}}{{c150::}}{{c151::}}{{c152::}}{{c153::}}{{c154::}}{{c155::}}{{c156::}}{{c157::}}{{c158::}}{{c159::}}{{c160::}}{{c161::}}{{c162::}}{{c163::}}{{c164::}}{{c165::}}{{c166::}}{{c167::}}{{c168::}}{{c169::}}{{c170::}}{{c171::}}{{c172::}}{{c173::}}{{c174::}}{{c175::}}{{c176::}}{{c177::}}{{c178::}}{{c179::}}{{c180::}}{{c181::}}{{c182::}}{{c183::}}{{c184::}}{{c185::}}{{c186::}}{{c187::}}{{c188::}}{{c189::}}{{c190::}}{{c191::}}{{c192::}}{{c193::}}{{c194::}}{{c195::}}{{c196::}}{{c197::}}{{c198::}}{{c199::}}{{c200::}}{{c201::}}{{c202::}}{{c203::}}{{c204::}}{{c205::}}{{c206::}}{{c207::}}{{c208::}}{{c209::}}{{c210::}}{{c211::}}{{c212::}}{{c213::}}{{c214::}}{{c215::}}{{c216::}}{{c217::}}</span>