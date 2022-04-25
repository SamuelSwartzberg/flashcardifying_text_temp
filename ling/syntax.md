
# syntax

Syntax is the study of how words and morphemes form larger units such as phrases and sentences and thus give rise to meaning.

## basic structure

### constituents

A constituent is a word or group of words that functions together as a single unit and has hierarchical structure.
The assembly of constitutents into larger constituents allows the generation the infinite variety of possible sentences that language is famous for.

#### constituenty tests

Constituents are identified by using constituent tests.
There are many constituent tests in english, among which are: proform, cleft, question, and movement

##### proform

proform test: Substitute the relevant proform, perform a grammaticality judgement
```lang=text;
The lady running the group handed in her resignation at noon.
The lady running the group did so at noon.
```

##### cleft

cleft test: Move the string into the main clause of a cleft sentence (It was/is x that...)
```lang=text;
The guests from overseas visited the best parts of the city on Monday
It was the best parts of the city that the guests from overseas visited on Monday.
```

##### question

question test: Ask for the string in question with a wh-question.
```lang=text;
The lady running the group handed in her resignation at noon.
What did the lady running the group hand in at noon?
Her resignation.
```

##### movement

Movement test: move string to different position in sentence.
```lang=text;
Gertrude wasn't interested in art.
Interested in art, Gertrude wasn't.
```

#### phrases

a phrase is a constituent which has a head which defines its type and acts in a certain way based on its type.
The head of a phrase is the word everything else in the phrase is about.
In a phrase, everything that isn't the head is a dependent.
An XP is a phrase with X as its head.
A phrasal category is the type of XP a phrase is.
A word class gives rise to a relevant phrasal category.

### trees

#### direction

Something is head-inital/head-final if the head comes at the beginning/end, respectively.
Something is left/right-branching if their parse trees grow to the left/right.
Things that are left/right-branching are also head-inital/final.

#### annotation

##### labelled bracket

Labeled bracketing notation is a notation to generate an arbitrary tree.
Labeled bracketing notati is mostly used to generate syntax trees.
Labeled bracketing notation: tree ::= [‹nodename› ｛‹tree›|‹leaf›｝]
leaf ::= #somestring

## frameworks

Syntax is a field where there are a bunch of frameworks or theories of how it works, but not much agreement.

### generative semantics

Generative semantics was a response to generative grammar developed in the 1960s.
the linguistics wars was the conflict between propoonents of generative grammar and generative semantics.
The proponents of generative semantics in the linguistics wars called themselves ⟮the four horsemen of the apocalypse⟯, 
george lakoff was arguably the most famous horseman of the apocalypse.
Generative semantics held that syntactic structures from meanings, rather than the other way around

### chomskyan

#### dependents

Dependents may be arguments or modifiers.
Arguments/modifiers are necessary/optional for the phrase to be grammatical
Arguments may be complements or specifiers.
Complements appear closer (in the tree) to the head than the specifier.
modifier =syn= adjunct.
Adjoining adjuncts creates a phrase of the same type as it originally was.
Ergo adjoining something to a YP results in a larger YP.
Adjunction can be recursive.
The generative grammar/chomskyan approach is to see an object as the DP complement of a verb.

#### X-bar theory

flex-container:✫x-bar-schema-basic.jpg✫


The X-bar theory claims that all phrases follow the X-bar schema.

##### !In the X-bar schema...

each node is binary, i.e. has two children.
each phrase has a head.
arguments are necessary but may be empty.
arguments are necessary but may be empty.
The difference between complements and specifiers is that the complement is a sister node to X, while the specifier is a sister node to X'.

##### layout

flex-container:✫sm_Screenshot%202020-10-13%20at%2000.10.05.png✫


table:class=blank-canvas;style=table-layout: fixed;headerrows=0,,,span=4;class=inner;⟮XP⟯
class=inner;⟮ZP⟯||span=3;class=inner;⟮X'⟯
span=2;|class=inner;⟮X⟯||class=inner;⟮YP⟯

##### image example

flex-container:✫sm_Screenshot 2020-10-13 at 00.28.29.png✫


table:in image|is
X|the head
YP|the complement
ZP|the specifier

##### in terms of projections

In the X-bar schema, XP is theoretically X''.
In the X-bar schema, X' and X'' (XP) are projections of X.


table:symbol|projection description
X|the minimum projection of X
X'|neither the minimum nor the maximum projection of X
X''/XP|the maximum projection of X

##### drawing

###### heads that are both the minimal and maximal projection

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

#### certain phrases/hypotheses

##### CP

C = Complementizer
[CP [C] [IP]]

A complement clause is a CP that is a clause. (I think this is all CPs, but not sure)
Interrogative sentences are often seen as CPs.

###### role in sentence

CP may either be complement or adjunct to verb/VP
to test whether a CP is an adjunct or a complement, use a proform test on the Verb/VP without the CP.

##### IP theory

I as a head is short for inflection.
under the IP theory, the sentence is an IP headed by an I.
The argument for I as the head of the sentence goes something like: It makes sense for a sentence to be a type of phrase and has a head, inflectional information is core to a sentence, so it makes sense for that to be the head.
under the IP theory, the subject is the thing that is in the specifier of the IP.
under the IP theory, the complement of I is the VP.

###### illustration

class=blank-canvas;span=3;class=inner;⟮IP⟯
class=inner;⟮NP⟯|span=2;class=inner;⟮I'⟯
class=inner;|class=inner;⟮I⟯|class=inner;⟮VP⟯
class=leaf;somethin|class=leaf;somethin|class=leaf;somethin

###### auxiliaries

In the IP theory, generally auxiliaries (at least in english) are treated as if they live in the I position.
However, assuming multiple auxiliaries as part of one I head does not work, as we can insert things such as adverbs between them.
So, auxiliaries probably all start out as V heads.
The top auxiliary (in the tree) moves from V to I.
Multiple auxiliaries are adjoined as Vs to the VP.

##### VP-internal subject hypothesis

According to the VP-internal subject hypothesis, the subject DP starts out in the VP, and them moves to the specifier of the IP later.
According to the VP-internal subject hypothesis, the subject DP will not move from the specifier of the VP to the specifier of the IP if the specifier of the IP is already filled by an expletive subject.

###### motivation

The VP-internal subject hypothesis is desirable because it makes the VP consistent with the X-bar schema.
The VP-internal subject hypothesis is desirable because it makes the subject which is semantically an argument of the V also grammatically an argument of the V.
The VP-internal subject hypothesis is desirable because it lets us address some discontinuities, especially in relation to adverbs.
Evidence: The subject is an argument of the V, but it appears outside of the VP, closer to I than to V.

##### DP hypothesis: 

The DP hypothesis claims that what are commonly assumed to be NPs are actuall DPs headed by a D.
The DP hypothesis argues that D can be seen as the head of a DP since the D picks out the referent, and everything, including the noun, then merely describes the D.
Intuitively, the head of "the best student of physics" seems to be "student", but the DP hypothesis claims its "the".

###### motivation

Part of the motivation for the DP hypothesis is that pronouns seem to be NPs without an actual N head.
The DP hypothesis is still a controversial hypothesis.
The DP hypothesis often correlates with the idea that pronouns are determiners.
In the DP hypothesis, a determinerless noun has a silent/unpronounced D.

## phenomena

### expletives

An ⟮expletive⟯ is a ⟮meaningless⟯ element put in some position to ⟮fulfil a grammatical requirement⟯. 
Expletitives are generally lexemes with other usual functions which are drained of their semantic contents for the purpose of acting as an expletive.
^E.g. ⁑There⁑ is someone helping us here. ⁑It⁑ was raining, wasn't ⁑it⁑?

### movement

A discontinuity is when two parts of a constituent are separated by an element that is not part of the constituent.
Syntactic movement is the explanation of discontinuities via movement within the posited syntax tree.
Syntactic movement is only used by some grammatical theories, and remains controversial.
Something is "in situ" if it doesn't move, although it normally would.

#### fronting

Fronting something is moving it to the front of the sentence

#### traces

In chomskyian theories, movement leaves behind an empty category called a trace.
Traces are symbolized by `t`.
Co-indexing is marking the trace and the thing that moved with a subscript index/letter.
Amongst the evidence for the existence of traces is that we can't contract over them.

#### types of movement

Two types of movement often distinguished are phrasal and head movement.

##### phrasal movement

phrasal movement is syntactic movement of a phrase.

##### head movement

Head movement is the syntactic movement of a head.
Head movement will leave behind any dependents as-is.
Whatever-stranding is head movement that leaves behind a dependent whatever.
Pied-piping is phrasal movement instead of head movement to prevent a dependent being left behind.

###### head movement constraint

The Head Movement Constraint (HMC) is the rule that a head H can only move to a position occupied by the head which selects HP as its complement.
The HMC is a proposed rule in generative grammar.
Due to the HMC, the only way a constiutent can move to a position that isn't selecting HP as its complement is via stepwise movement.
The head movement contraint only applies to head movement, obv.
According to the HMC, I can only move to a position that selects IP as its complement.

