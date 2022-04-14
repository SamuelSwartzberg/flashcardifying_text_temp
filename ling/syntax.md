
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

<pre><code data-codetype="text">*the lady’s a book</code></pre> <span class="divider">-&gt;</span> {{c1::That possessive s is a determiner}}
<pre><code data-codetype="text">Ann’s car</code></pre><pre><code data-codetype="text">She's car</code></pre> <span class="divider">-&gt;</span> {{c1::Possessor DPs cannot be replaced by pronouns}}
<pre><code data-codetype="text">Ann’s car</code></pre><pre><code data-codetype="text">She's car</code></pre> <span class="divider">-&gt;</span> {{c1::Replace the posessor DP with a pronoun}}
<pre><code data-codetype="text">The book's the bookmark.</code></pre> <span class="divider">-&gt;</span> {{c1::Possessive s is followed by NPs, not by DPs}}
<pre><code data-codetype="text">[the owner of the car]'s mother</code></pre> <span class="divider">-&gt;</span> {{c1::DP}}
<pre><code data-codetype="text">[the owner of the car]'s mother</code></pre> <span class="divider">-&gt;</span> {{c1::It attaches to DPs}}
<pre><code data-codetype="text">the city’s destruction</code></pre> <span class="divider">-&gt;</span> {{c1::general ascription}}
<pre><code data-codetype="text">the man’s hat</code></pre> <span class="divider">-&gt;</span> {{c1::posession&nbsp;}}
<pre><code data-codetype="text">the owner of the car's mother</code></pre> <span class="divider">-&gt;</span> {{c1::<pre><code data-codetype="text"><mark>the owner of the car</mark>'s mother</code></pre>}}
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


#### clauses

A clause links a predicand (expressed or not) with a predicate.

<div class="c1-f">
Under the more wide definition, what is the predicate here?
</div>
<div class="c1-f">
Under the more narrow definition, what is the predicate here?
</div>
<div class="c1-f">
How are these often called in short?
</div><br><pre><code data-codetype="text">Bill heard Fred</code></pre> <span class="divider">-&gt;</span> {{c1::heard Fread.}}
<pre><code data-codetype="text">Bill heard Fred</code></pre> <span class="divider">-&gt;</span> {{c1::heard}}
In grammar, a predicate either connects the subject to an idea ('what the subject is like'), or is...? <span class="divider">-&gt;</span> {{c1::something that says something about a subject}}
In grammar, a predicate is either the thing that says something about the subject, or the thing that connects what to what? <span class="divider">-&gt;</span> {{c1::the subject to an idea ('what the subject is like')}}
In grammar, a predicate is either the thing that says something about the subject, or what, in relation to the the subject and an idea ('what the subject is like')? <span class="divider">-&gt;</span> {{c1::It connects the subject to an idea ('what the subject is like')}}
In grammar, either (a) something that says something about a subject or (b) something that links something a subject and what that subject is like is called... <span class="divider">-&gt;</span> {{c1::a predicate}}
In grammar, what is the problem with the term predicate? <span class="divider">-&gt;</span> {{c1::It has two competing definitions}}


A clause is a type of constituent.

In linguistic typology, a null-subject language is a language whose grammar permits an independent clause to lack an explicit subject; such a clause is then said to have a null subject.
An independent clause always features a subjecti or has a null subject.
Languages I speak that are null-subject languages are spanish and japanese.

Subordinate clause = dependent clause
A subordinate/dependent clause cannot stand alone as a sentence.
Independent clause = main clause ≈ root clause ≈ matrix clause
A independent clause can stand alone as a sentence.

##### subordinate clauses

An embedded question is a question that is a subordinate clause.
As CPs generally are, embedded questions are adjuncts of the VP or complements of the verb (in japanese too)

###### relative clause

A relative clause is a subordinate clause that describes a DP/NP
A ⟮relative clause⟯ is a ⟮subordinate clause⟯ which generally ⟮describes the referent of its head⟯.
I met a furry who was passionate.
In indo-european languages, a relative clause is generally introduced by a relative pronoun.

##### interrogative

In syntax, an interrogative clause has a particular type of syntax and/or prosoody, which is typically used to ask question (attach the illocutionary act/force of asking a question).
Languages may have diffrent types of interrogative clauses (i.e. different syntaxes used to ask different types of questions).
A question iteself is an illocutionary act/force seeking to obtain an answer.
In many languages, besides syntax/prosody, written exchanges often indicate interrogatives by special punctuation.

If syntax is used to indicate an interrogative, it may be in the form of conjugating the verb, changing the word order, adding interrogative words, particles, or other constituents, or often a combination of these.

###### conjugation

###### word order

####### I-to-C movement

In english, wh-questions and yes/no questions alike are marked by I-to-C movement.
In english interrogatives that are not subject questions, the sentence becomes a CP.
In english interrogatives, the newly formed C position is filled by I moving to C.
In english interrogatives, if there is no I to move to C, I is made pronounced via do-support.

####### wh-movement

A wh-question is a interrogative sentence using a wh-word.
Wh-questions typically feature wh-movement.
wh-movement is a form of head movement.
The wh-constituent moves from and therefore its trace is to be found in where it would be in an answer to the question, unless it is in situ.
A wh in situ question is a wh-question where the wh-prhase does not move.
She was reading what? They went where? She spoke to who(m)?
A subject question in english is where the wh-phrase is the subject of the sentence.
Of the wh-questions, subject questions are the only ones that don't feature I to C movement, and thus also no do-support.
the syntax of a subject question has the same syntax as a statement.

Places out of which constituents for wh-questions are impossible to extract   islands
There are a bunch of islands:
- No extraction of one of the conjuncts of a coordinated phrase.
- No extraction out of a CP inside a DP
- No extraction out of a subject (for most English speakers)
- No extraction out of adjuncts
Besides out of islands, wh-movement will be ungrammatical if it does not comply with the shortest move / minimal link condition: The move must be the shortest possible = there must not be a wh-element that would have to move less far.

###### adding constituents

####### tag questsions

A tag question is an interrogative clause which is formed from a declarative clause plus a question tag.
A question tag is an interrogative fragment.
Most languages have an (or multiple) simple question tag(s) allowing for tag question formation.
question tags come in two basic flavors, asking one to confirm or asking one to deny.
Examples of question tags:
en|right?|no?, or no?
de|stimmts?, gell?, wa?, ne?|nicht wahr?, oder nicht?
es|verdad?|no?
English as well as some other languages allow  to the end of a declarative clause to turn it into an interrogative clause.
English as welll as a few other languages have specific grammar for forming more complex tag question fragments, in english: aux + pronoun

####### interrogative words ＆ particles

In english, interrogative words start with wh- and are thus known as wh-words.


##### ordination

Coordination/subordination may imply different semantic relationships between the conjuncts.
illative|presents a consequence
cumulative|adds more
adversative|introduces a contrast
disjunctive|selfexpl.

causal|presents a reason
purposive|
conditional|
concessional|
comparative|
temporal|

In english, coordination/subordination is most often performed by conjunctions.

###### coordination

Coordination is the process of linking two things of the same type.
The two things linked via coordination are called conjuncts.
The totality of coordinator(s) and conjuncts forming an instance of coordination is called a coordinate structure.

###### subordination

Subordination is linking two things (maincly clauses), where one depends on the other.
A complement clause is an argument of a predicate.
A complementizer turns a clause into 
A complementizer turns a clause into the subject or object of a sentence.
In english, the complementizer 'that' sometimes is unpronounced
Akane thought that Lilly was a いい子. ⇒ Akane thought Lilly was a いい子. 

##### sentences

A sentence consists of one or more clausees.
A simple sentence consists of one (main/independent) clause.
A complex sentence consists of at least one main/independent clause and at least one dependent clause.
A sentence is a constituent cannot be further joined into larger constituents.
A major sentence we might consider a 'normal sentence' following the usual syntactic rules etc.
A minor sentence is a sentence without the usual subject-predicate/constituent structure.
Minor sentences generally do not allow substitution of items of the same word class: Merry Christmas!; *Merry Birthday!
A sentence word (also called a one-word sentence) is a single word that forms a full sentence.

A cleft sentence splits a simple sentence up into a complex sentence. 
Cleft seentence typically put the constituent now in the independent clause into focus.
Syntax of cleft sentences in english: it + conjugated form of to be + X + subordinate clause


## Expletives

An ⟮expletive⟯ is a ⟮meaningless⟯ element put in some position to ⟮fulfil a grammatical requirement⟯. (Can also mean profanity, of course)
Often words used as expletives also have other functions with more semantic content, however this semantic content is discarded when used as an expletive.
E.g. ⁑There⁑ is someone helping us here. ⁑It⁑ was raining, wasn't ⁑it⁑?

## Grammatical relations

Grammatical relations are subjects and objects, and perhaps others depending on your theory.
Grammatical relations are different things to different theorists.
The generative grammar/chomskyan approach is to see an object as the DP complement of a verb.



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


## parts of speech

A part of speech/word class is a category of words with similar grammatical properties.
Part of speech is synonymous with word class.
Part of speech may be synonymous with lexcial category if we don't acknowledge functional categories.
a closed word class is one that rarely or never accepts new members
an open word class is one that can be extended without limit/readily accepts new members
Clear distingction of word classes are difficult across languages.
Often the things we think of a ertain word class doing is actually what a phrase headed by that thing does.

A|Adjective
P|Adposition
Adv|Adverb
Comp|coordinating conjunction
D|Determiner
N|Noun
V|Verb

esp. in generative grammar, functional and lexical categories are often distinguished.
functional category|purely grammatical meaning|Det, Conj, Aux...
lexical category|some sort of semanting content|V, N, A, Adv...

A word that is a member of a functional category is called a function word.
A word that is a member of a lexical category is called a content word.

### particle

A particle is a function word (member of a functional category) which cannot be inflected.
A particle occurring at the end of the sentence is a sentence-final particle.
Particles do not refer.
Sentence-final particles in particular generally indicate modality, register or other pragmatic effects.

### Interjections

An interjection is a lexical item that indicates a reaction. 
Interjections are pretty separated from the rest of the syntax of the sentence.
Interjections are a syntactic category, while discourse marker is a pragmatic category.

### adjective

An adjective (phrase) describes a thing or restricts its referent.
Adjective phrases in english can exist syyntactically in three ways: an attributive adjective, a predicative adjective and a nominalized adjective.
An attributive adjective phrase is adjoined to an NP.
A predicative adjective phrase has the adjective phrase as the complement of the verb.
A nominalized adjective works as the head of an NP.

### adverb

In english at least, adverb(ial) phrases (and thus adverbs) act as a modifier/adjunct for any number of phrases, but not NPs (which is instead handled by APs).
Adverbial phrases describes the thing its modifying.
Adverbs/adverbial phrases are at least able to modify other AdvPs, APs, DPs, PPs, VPs, and IPs.

### noun

Nouns are heads of NPs.
NPs (no DP theory) matter because they are the things that can be subjects or objects of verbs or prepositions.
If we believe in the DP theory, NPs matter because they are the complements of Ds, and DPs are the things that can be subjects or objects of verbs or prepositions.

#### attribution

In grammar, something attributive is a phrase within a NP/DP that modifies the head noun. 
Adnnominal seems to be a synonym for attributive
In english, relative clauses and attributive adjectives are the main things that act attributively.
A verb that can be used attributively is known as an attributive verb.

### det

A determiner is a word/affix that occurs that occurs together with a NP and expresses something about the reference of the noun phrase.
Often, for any given pronoun, there is a similar or identical determiner
Types of determiners: Articles, Demonstrative determiners, Quantifiers, distributive determiners, interrogative determiners

#### Quantifier

Quantifiers are a type of determiner/pronoun (which may depending on your analysis may be a quantifier too).
quantifiers are adjoined to the DP/NP to form a larger DP/NP.
table:span=2;⟮DP⟯
⟮Q/D⟯|⟮DP⟯
all|the students

Floating quantifier is a quantifier that is not immediately near the NP/DP it quantifies.
According to the VP-int-subj-hyp, floating quantifiers happen because of the two DPs that could move to the subject position in the specifier position of the IP, the smaller DP moves, leaving the quantifier behind.
The existence of floating quantifiers provides evidence for the VP-internal subject hypothesis by explainin why the quantifier is in this position.

#### Articles

Examples of Articles in EN: the, an, a

#### posessive determiners

my, your, his, her, its, our, their

### adpositions

An adposition may either be a preposition, circumposition or a postposition.
semantically, adpositions may be temporal adpositions, spatial adpositions, or adpositions that mark a different semantic/thematic role.
Adpositions may be transitive or intransitive.
Intransitive adpositions are often called adverbs, though that's probably an inferior analysis.
Intransitive adposition examples: here/everywhere/downstairs/ahead/outside/...
Transitive adpositions may take other adpositions as complements.

### conj

Conjunctions either perform coordination or subordination.

### proforms

Proforms are function words that stand in for another constituent.
DP/NP|Pronouns
NP/N'|one
Verb|do (so)
Temporal adposition|then
Spatial adposition|there
other adposition|none exists

#### pronouns

Pronouns are proforms that stand for NPs, or DPs if we believe in them, not for nouns themselves.

A pro-drop language is a language where certain classes of pronouns may be omitted when they are pragmatically or grammatically inferable. 
Japanese and Spanish are pro-drop, German and English are, with rare exceptions, not.

##### personal

Personal pronouns are pronouns that are associated primarily with a particular grammatical person.


### copula (and existential verbs)

A copula is a word or phrase that links the subject of a sentence to its complement/predicate.
The tree ☞is☜ blue.
Depending on the language, a copula may or may not be a verb.
An existential verb indicates the existence of something.
In some languages the copula and the main existential verb are the same, of those I speak, only english: to be (The chair is green, there is a god)
In some languages the copula and the main existential verb are different:
es|ser/estar|haber
de|sein|geben
ja|だ|ある・いる

Some languages distinguish different existential verbs for different semantic categories.
Japanese distinguishes its existential verbs ある・いる along a inanimate/animate distinction.

### verbs

#### dynstat

Dynamic and static verbs are often contrasted.
A dynamic verb is a verb that describes an action.
A stative (unclear relation to stative aspect) verb is a verb that descirbes a state.
setzen is a dynamic verb while sitzen is a dynamic verb.

#### aux

Non auxiliary verbs are called lexical verbs.
auxiliary verb is frequenly abbreviated auxiliary.
In English, sentences without auxiliars cannot have negation.
In English, auxiliaries cannot take an object (complement of the VP), while lexical verbs can.
Auxiliary verbs are members of the functional category, while lexical verbs are members of the lexical category.
In English, auxiliaries go before the subject DP/NP in question inversion.
have and do may or may not be auxiliary verbs.
dummy do is do used as an auxiliary verb.
using dummy do is called do-support
do-support is used when an axuliary verb is syntactically required but none is present.


In english, what are the non-lexical verbs that don't take objects? <span class="divider">-&gt;</span> {{c1::auxiliary verbs}}
In english, what types of verbs are required to use negation? <span class="divider">-&gt;</span> {{c1::auxiliary verbs}}
In english, what types of verbs go before the subject DP in question inversion? <span class="divider">-&gt;</span> {{c1::auxiliary verbs}}
Why does auxiliary being equivalent to auxiliary verb not cause confusion? <span class="divider">-&gt;</span> {{c1::Because there are no other kinds of auxiliary words}}
auxiliary verbs <span class="divider">-&gt;</span> {{c1::auxiliaries}}
In the circumstances where do and have aren't auxiliaries (and also aren't lexical), what are they? <span class="divider">-&gt;</span> {{c1::light verbs}}
Light verbs are different from auxiliary verbs how? <span class="divider">-&gt;</span> {{c1::Can't do the syntactical stuff auxes can}}
Light verbs are different from lexical verbs how? <span class="divider">-&gt;</span> {{c1::Little semantic content}}
Verbs that have little semantic content but are not auxiliaries due to syntactic concerns are called what? <span class="divider">-&gt;</span> {{c1::light verbs}}
Relationship between auxiliaries and modals in set notation? <span class="divider">-&gt;</span> {{c1::modals ⊊ auxiliaries}}
What property do modal verbs express? <span class="divider">-&gt;</span> {{c1::Modality}}<br><div class="sub">
<div class="sub c1-f c2-b">
competing definitions
</div>
<div class="sub c1-b c2-f">
Question inversion, negation etc.
</div>
<div class="sub c1-b c2-f">
auxiliaries ⊋ modals
</div>
</div>

### changing parts of speech

#### nominalization

Nominalization is the process of treating / transforming something which is not a noun as / into a noun / head of an NP.
A nominalizer is a thing, usually a bound morpheme, that nominalizes a thing.

## word order

Word order is how a language orders the syntacic constituents of a language.
Word order may be a distinguishing characteristic in linguistic typology.
Even languages which typically allow large amounts of flexibility in word order (e.g. by marking case) generally have a typical word order, where having a different order is considered marked. (see: Japanese)

### constituent order

the constituent order of a clause, namely the relative order of subject, object, and verb, is one way to distinguish word order.
German has verb-second constituent order in main clauses and verb-final constituent order in subordinate clauses.
SOV, SVO, etc

Verb-final language place the verb at the end of a clause.
Completely verb-final: japanese

V2 word order is that the verb comes in the second syntactically relevant place of the sentence, and the first can be filled by a variety of different constituents.
In V2 word order, the first constituent functions as the topic.
