
# syntax

Syntax is the study of how words and morphemes form larger units such as phrases and sentences and thus give rise to meaning.
To me, syntax is one way of indicating grammemes.
Syntax indicates sememes and pragmemes via the branching structure it forms.
fronting something is movving it to the front of the sentence
Morphosyntax is where morphology and syntax intersect.

## constituents

### constituents

A constituent is a word or group of words that functions together as a single unit and has hierarchical structure.
The assembly of constitutents into larger constituents allows the generation the infinite variety of possible sentences that language is famous for.
Phrases are constituents, but not all constituents are phrases.
Constituents are identified by using constituent tests.
There are many constituent tests in english, among which are: proform substitution
proform test: Substitute the relevant proform, perform a grammaticality judgement
```lang=text;
The lady running the group handed in her resignation at noon.
The lady running the group did so at noon.
```
cleft test: Move the string into the main clause of a cleft sentence (It was/is x that...)
```lang=text;
The guests from overseas visited the best parts of the city on Monday
It was the best parts of the city that the guests from overseas visited on Monday.
```
question test: Ask for the string in question with a wh-question.
```lang=text;
The lady running the group handed in her resignation at noon.
What did the lady running the group hand in at noon?
Her resignation.
```
Movement test: move string to different position in sentence.
```lang=text;
Gertrude wasn't interested in art.
Interested in art, Gertrude wasn't.
```

### branching

For something to be left/right-branching is for their parse trees to grow to the left/right.
Things that are left-branching are also head-final.
Things that are right-branching are also head-initial.

### annotation

#### labelled bracket

Labeled bracketing notation can generate an arbitrary tree, but is mostly used to generate syntax trees.
Labeled bracketing notation: tree ::= \[‹nodename {‹tree›|‹leaf›}
leaf ::= #somestring

### types of constiutents

#### phrasees

a phrase is a constituent which acts a certain way related to other constituents and has a certain internal structure relative to its type.
The head of a phrase is the thing everything else in the phrase is about.
In a phrase, everything that isn't the head is a dependent.
In head-inital/head-final languages, the head comes at the beginning/end of the phrase, respectively
head-initial|English (partially)

##### unsorted

Posessive s is a determiner
Posessor DP cannot be replaced by pronoun
Posessive s is followed by NPs not DPs
Posessive s attaches to DPs
How does English possessive s differ from German genitive -s, in where it attaches? <span class="divider">-&gt;</span> {{c1::German genitive -s attaches to nouns, english possessive s to DPs (or NPs, depending on your theory)}}
Prove that possessive s is a determiner by inserting other determiners! <span class="divider">-&gt;</span> {{c1::*the lady’s a book}}
What can't posessor DPs do, but most other DPs can? <span class="divider">-&gt;</span> {{c1::Be replaced by a normal pronoun}}
What does posessive s attach to? <span class="divider">-&gt;</span> {{c1::DPs}}
What syntactic category does possessive s belong to? <span class="divider">-&gt;</span> {{c1::Determiner}}
What type of constitutent is the thing after a posessive s? <span class="divider">-&gt;</span> {{c1::A NP (dp theory)}}
What type of constitutent is the thing before a posessive s? <span class="divider">-&gt;</span> {{c1::A DP}}
the children’s toys <span class="divider">-&gt;</span> {{c1::the toys of the children}}

##### X-bar framework-based


The X-bar theory asserts that all phrases have the structure ✫https://upload.wikimedia.org/wikipedia/commons/thumb/3/38/X-bar_schema_%28basic%29.png/300px-X-bar_schema_%28basic%29.png✫, which is called the X-bar schema.
In the X-bar theory, each node is binary, i.e. has two children.
In the X-bar theory, each phrase has a head.
in the X-bar schema, there are four types of components in each schema.
In the X-bar schema, arguments are necessary but may be empty.
In the X-bar schema, the two types of arguments are complements and specifiers
The difference between complements and specifiers is that the complement is a sister node to X, while the specifier is a sister node to X'.
In the X-bar schema, anything that is not a head or an argument is an adjunct.
Adjuncts may also be called modifiers.
Adjuncts are optional, and adjoining them creates a phrase of the same type as it originally was.
Ergo adjoining something to a YP results in a larger YP.
Adjunction can be recursive.
An adjunct can be any type of phrase.

flex-container:✫sm_Screenshot%202020-10-13%20at%2000.10.05.png✫

table:class=blank-canvas;style=table-layout: fixed;
span=4;class=inner;⟮XP⟯
class=inner;⟮ZP⟯||span=3;class=inner;⟮X'⟯span=2;|class=inner;⟮X⟯||class=inner;⟮YP⟯



flex-container:✫sm_Screenshot 2020-10-13 at 00.28.29.png✫
X|the head
YP|the complement
ZP|the specifier

X|the minimum projection of X
X'|neither the minimum nor the maximum projection of X
X''/XP|the maximum projection of X

In the X-bar schema, XP is theoretically X''.
In the X-bar schema, X' and X'' (XP) are projections of X.

In the X-bar schema, to indicate that foo is both a head and a complete phrase (both the minimal and the maximal projection), you can

X/XP
foo

X(P)
foo

XP
|
X'
|
X
foo

XP
|
X
foo

In the X-bar framework, a phrase consists

CP

[CP [C] [IP]]
CP may either be complement or adjunct to verb/VP
to test whether a CP is an adjunct or a complement, use a proform test on the Verb/VP without the CP.

The object is the thing that is the complement of the VP.

###### IPs

under the IP theory, the sentence is an IP headed by an I.
The argument for I as the head of the sentence goes something like: It makes sense for a sentence to be a type of phrase and has a head, inflectional information is core to a sentence, so it makes sense for that to be the head.
in the IP theory, I stands for inflection.
under the IP theory, the subject is the thing that is in the specifier of the IP.
under the IP theory, the complement of I is the VP.

class=blank-canvas;span=3;class=inner;⟮IP⟯
class=inner;⟮NP⟯|span=2;class=inner;⟮I'⟯
class=inner;|class=inner;⟮I⟯|class=inner;⟮VP⟯
class=leaf;somethin|class=leaf;somethin|class=leaf;somethin



###### VP-internal subject hypothesis

According to the VP-internal subject hypothesis, the subject DP starts out in the VP, and them moves to the specifier of the IP later.
According to the VP-internal subject hypothesis, the subject DP will not move from the specifier of the VP to the specifier of the IP if the specifier of the IP is already filled by an expletive subject.
The VP-internal subject hypothesis is desirable because it makes the VP consistent with the X-bar schema.
The VP-internal subject hypothesis is desirable because it makes the subject which is semantically an argument of the V also grammatically an argument of the V.
The VP-internal subject hypothesis is desirable because it lets us address some discontinuities, especially in relation to adverbs.
Evidence: The subject is an argument of the V, but it appears outside of the VP, closer to I than to V.

flex-container:✫sm_Screenshot%202020-10-20%20at%2010.44.18.png✫


table;class=blank-canvas;class=inner;span=3;⟮IP⟯
class=inner;⟮DP⟯|span=3;class=inner;⟮I′⟯
class=inner;|class=inner;⟮I⟯|span=3;class=inner;⟮VP⟯
class=inner;span=2;|class=inner;⟮DP⟯|span=3;class=inner;⟮V′⟯
class=inner;span=3;|class=inner;⟮V⟯|class=inner;|class=inner;⟮DP⟯
someone⎵＊i＊⎵|is|t⎵＊i＊⎵|following|us

###### DP hypothesis: 

The DP hypothesis claims that what are commonly assumed to be NPs are actuall DPs headed by a D.
The DP hypothesis argues that D can be seen as the head of a DP since the D picks out the referent, and everything, including the noun, then merely describes the D.
Intuitively, the head of "the best student of physics" seems to be "student", but the DP hypothesis claims its "the".
Part of the motivation for the DP hypothesis is that pronouns seem to be NPs without an actual N head.
The DP hypothesis is still a controversial hypothesis
The DP hypothesis often correlates with the idea that pronouns are determiners.
In the DP hypothesis, a determinerless noun has a silent/unpronounced D.

class=blank-canvas;span=2;class=inner;⟮DP⟯
class=inner;⟮AP⟯|span=2;class=inner;⟮NP⟯
|class=inner;⟮AP⟯|span=2;class=inner;⟮NP⟯
||class=inner;⟮N⟯|class=inner;⟮PP⟯


class=blank-canvas;span=2;class=inner;⟮DP⟯
class=inner;⟮D⟯|span=2;class=inner;⟮NP⟯
|class=inner;⟮AP⟯|span=2;class=inner;⟮NP⟯
||class=inner;⟮N⟯|class=inner;⟮PP⟯
class=leaf;the|class=leaf;best|class=leaf;student|class=leaf;of physics


####### posessive s

class=blank-canvas;span=3;class=inner;⟮DP⟯
class=inner;⟮DP⟯|span=2;class=inner;⟮D'⟯
|class=inner;⟮D⟯|class=inner;⟮NP⟯
class=leaf;[Possessor]|class=leaf;'s|class=leaf;[Possessed entity]


class=blank-canvas;span=3;class=inner;⟮DP⟯
class=inner;⟮DP⟯|span=2;class=inner;⟮D'⟯
span=1,2;|class=inner;⟮D⟯|span=2;class=inner;⟮NP⟯
|class=inner;⟮N⟯|class=inner;⟮PP⟯
class=leaf;that woman|class=leaf;'s|class=leaf;books|class=leaf;on physics


###### NP hypothesis

class=blank-canvas;span=2;class=inner;⟮NP⟯
class=inner;⟮D⟯|span=2;class=inner;⟮N'⟯
|class=inner;⟮AP⟯|span=2;class=inner;⟮N'⟯
||class=inner;⟮N⟯|class=inner;⟮PP⟯
class=leaf;the|class=leaf;best|class=leaf;student|class=leaf;of physics


###### IP hypothesis

Auxiliaries actually start out as V, and then the top one (in the tree) moves to I.
Multiple auxiliaries are adjoined as Vs to the VP.
Assuming multiple auxiliaries as part of one I head does not work, as we can insert things such as adverbs between them.

###### early modern english

Lexical verbs could move to I, and thus to C, following the HMC.
In current english, wh-questions need do-support since something needs to fill the C position, and the verb can't, since it can't move to I.
In early modern english, wh-questions did not need do-support since the V could move to I and thus to C.
"What heards't thou?"

###### german sentences

The german main clause V2, subordinate clause V-final constituent order is explained as follows:
In german, VP and IP are head-filnal
All german clauses are CPs with pronouced Cs.
Subordinate german clauses have their C positions filled by a complementizer as usual.
If C is not filled by a complementizer (mostly main clauses), then V moves to I and then to C.
In german subordinate clauses, the V can't move to C, because that is typically already filled by a real complementizer.
If in german the V position is occupied by a compound verb, if the V moves (via I to C), what moves is the root, leaving the affix behind.
Main clauses in german have the specifier of C filled by an arbitrary constituent moving there.

##### types of phrases

The type of phrase a phrase is (AdvP, VP, NP...) is called phrasal category.
An XP is a phrase with X as its head.




## Expletives

An ⟮expletive⟯ is a ⟮meaningless⟯ element put in some position to ⟮fulfil a grammatical requirement⟯. (Can also mean profanity, of course)
Often words used as expletives also have other functions with more semantic content, however this semantic content is discarded when used as an expletive.
E.g. ⁑There⁑ is someone helping us here. ⁑It⁑ was raining, wasn't ⁑it⁑?

## frameworks

Syntax is a field where there are a bunch of frameworks or theories of how it works, but not much agreement.
Generative semantics was a response to generative grammar developed in the 1960s.
The conflict between propoonents of generative grammar and generative semantics was known as the linguistics wars.
The proponents of generative semantics in the linguistics wars called themselves ⟮the four horsemen of the apocalypse⟯, amongst which was george lakoff
Generative semantics held that syntactic structures from meanings, rather than the other way around

## movement

discontinuity is the phenomenon where a constituent is split into two parts ⟮due to the insertion of an element which is not part of it⟯
Syntactic movement is the means by which some theories of syntax address discontinuities.
Two types of movement often distinguished are phrasal and head movement.
In phrasal movement, an entire phrase moves.
In head movement is when only a head of a phrase moves, leaving its dependents behind.

In chomskyian theories, movement leaves behind an empty category called a trace.
Traces are indicated by t and subscripted with a letter or  number indicating what moved, this is known as coindexing.
Some of the evidence of traces is that we can't contract over them.

In syntax, something is "in situ" if it doesn't move, although it normally would.

### head movement 

The Head Movement Constraint (HMC) is the rule that a head H can only move to a position occupied by the head which selects HP as its complement.
Due to the HMC, the only way a constiutent can move to a position that isn't selecting HP as its complement is via stepwise movement.
The head movement contraint only applies to head movement, obv.
According to the HMC, I can only move to a position that sellects IP as its complement.
If english lexical verbs wanted to move to C in y/n questions, it would have to move to I first.

#### prepositions

When the object of a transitive preposition moves, what may happen to the prepostion is either preposition stranding or pied piping.
An entire expression moves, instead of leaving something behind   Pied Piping
A head moves and leaves behind a preposition   Preposition stranding


