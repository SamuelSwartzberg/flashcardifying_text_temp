# grammar

Most broadly, grammar is the sets of rules governing a languoid.
A reference work on the grammar of a language may also be known as a grammar, more precisely as a reference grammar.
If a string conforms to the grammar of a lect, it is called grammatical.
A grammaticality judgement is a judgement on the gramatticality of a string by a certain speaker.
grammaticality judgements are often used as linguistic evidence, generative grammar also aims to predict them.
* marks a thing that is ungrammatical.
In linguistics, an empty category is an element in the study of syntax that does not have any phonological content and is therefore unpronounced.
An empty category = something unpronounced is often indicated by ø or ＊e＊
In linguistics, a string is a sequence of words/sounds that we don't want to put any deeper analytical category on just yet.

## syntax

Syntax is the study of how words and morphemes form larger units such as phrases and sentences.
Morphosyntax is where morphology and syntax interset.

### Information structure

Information structure is the subfield of linguistics describing how information is organized within a sentence.
Information structure mainly consists of the three oppoositions of focus/background, topic/comment, and givenness/new

### Expletives

An ⟮expletive⟯ is a ⟮meaningless⟯ element put in some position to ⟮fulfil a grammatical requirement⟯. (Can also mean profanity, of course)
Often words used as expletives also have other functions with more semantic content, however this semantic content is discarded when used as an expletive.
E.g. ⁑There⁑ is someone helping us here. ⁑It⁑ was raining, wasn't ⁑it⁑?

### Grammatical relations

Grammatical relations are subjects and objects, and perhaps others depending on your theory.
Grammatical relations are different things to different theorists.
The generative grammar/chomskyan approach is to see an object as the DP complement of a verb.

### labelled bracket

Labeled bracketing notation can generate an arbitrary tree, but is mostly used to generate syntax trees.
Labeled bracketing notation: tree ::= \[‹nodename {‹tree›|‹leaf›}
leaf ::= #somestring

### frameworks

Syntax is a field where there are a bunch of frameworks or theories of how it works, but not much agreement.
Generative semantics was a response to generative grammar developed in the 1960s.
The conflict between propoonents of generative grammar and generative semantics was known as the linguistics wars.
The proponents of generative semantics in the linguistics wars called themselves ⟮the four horsemen of the apocalypse⟯, amongst which was george lakoff
Generative semantics held that syntactic structures from meanings, rather than the other way around

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

### phrasees

a phrase is a constituent which acts a certain way related to other constituents and has a certain internal structure relative to its type.
The head of a phrase is the thing everything else in the phrase is about.
In a phrase, everything that isn't the head is a dependent.
In head-inital/head-final languages, the head comes at the beginning/end of the phrase, respectively
head-initial|English (partially)

#### X-bar framework-based


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

##### IPs

under the IP theory, the sentence is an IP headed by an I.
The argument for I as the head of the sentence goes something like: It makes sense for a sentence to be a type of phrase and has a head, inflectional information is core to a sentence, so it makes sense for that to be the head.
in the IP theory, I stands for inflection.
under the IP theory, the subject is the thing that is in the specifier of the IP.
under the IP theory, the complement of I is the VP.

class=blank-canvas;span=3;class=inner;⟮IP⟯
class=inner;⟮NP⟯|span=2;class=inner;⟮I'⟯
class=inner;|class=inner;⟮I⟯|class=inner;⟮VP⟯
class=leaf;somethin|class=leaf;somethin|class=leaf;somethin



##### VP-internal subject hypothesis

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

##### DP hypothesis: 

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


###### posessive s

class=blank-canvas;span=3;class=inner;⟮DP⟯
class=inner;⟮DP⟯|span=2;class=inner;⟮D'⟯
|class=inner;⟮D⟯|class=inner;⟮NP⟯
class=leaf;[Possessor]|class=leaf;'s|class=leaf;[Possessed entity]


class=blank-canvas;span=3;class=inner;⟮DP⟯
class=inner;⟮DP⟯|span=2;class=inner;⟮D'⟯
span=1,2;|class=inner;⟮D⟯|span=2;class=inner;⟮NP⟯
|class=inner;⟮N⟯|class=inner;⟮PP⟯
class=leaf;that woman|class=leaf;'s|class=leaf;books|class=leaf;on physics


##### NP hypothesis

class=blank-canvas;span=2;class=inner;⟮NP⟯
class=inner;⟮D⟯|span=2;class=inner;⟮N'⟯
|class=inner;⟮AP⟯|span=2;class=inner;⟮N'⟯
||class=inner;⟮N⟯|class=inner;⟮PP⟯
class=leaf;the|class=leaf;best|class=leaf;student|class=leaf;of physics


##### IP hypothesis

Auxiliaries actually start out as V, and then the top one (in the tree) moves to I.
Multiple auxiliaries are adjoined as Vs to the VP.
Assuming multiple auxiliaries as part of one I head does not work, as we can insert things such as adverbs between them.

##### early modern english

Lexical verbs could move to I, and thus to C, following the HMC.
In current english, wh-questions need do-support since something needs to fill the C position, and the verb can't, since it can't move to I.
In early modern english, wh-questions did not need do-support since the V could move to I and thus to C.
"What heards't thou?"

##### german sentences

The german main clause V2, subordinate clause V-final constituent order is explained as follows:
In german, VP and IP are head-filnal
All german clauses are CPs with pronouced Cs.
Subordinate german clauses have their C positions filled by a complementizer as usual.
If C is not filled by a complementizer (mostly main clauses), then V moves to I and then to C.
In german subordinate clauses, the V can't move to C, because that is typically already filled by a real complementizer.
If in german the V position is occupied by a compound verb, if the V moves (via I to C), what moves is the root, leaving the affix behind.
Main clauses in german have the specifier of C filled by an arbitrary constituent moving there.

#### types of phrases

The type of phrase a phrase is (AdvP, VP, NP...) is called phrasal category.
An XP is a phrase with X as its head.

### clauses

A clause links a predicand (expressed or not) with a predicate.
A clause is a type of constituent.

In linguistic typology, a null-subject language is a language whose grammar permits an independent clause to lack an explicit subject; such a clause is then said to have a null subject.
An independent clause always features a subjecti or has a null subject.
Languages I speak that are null-subject languages are spanish and japanese.

Subordinate clause = dependent clause
A subordinate/dependent clause cannot stand alone as a sentence.
Independent clause = main clause ≈ root clause ≈ matrix clause
A independent clause can stand alone as a sentence.

#### subordinate clauses

An embedded question is a question that is a subordinate clause.
As CPs generally are, embedded questions are adjuncts of the VP or complements of the verb (in japanese too)

##### relative clause

A relative clause is a subordinate clause that describes a DP/NP
A ⟮relative clause⟯ is a ⟮subordinate clause⟯ which generally ⟮describes the referent of its head⟯.
I met a furry who was passionate.
In indo-european languages, a relative clause is generally introduced by a relative pronoun.

#### interrogative

In syntax, an interrogative clause has a particular type of syntax and/or prosoody, which is typically used to ask question (attach the illocutionary act/force of asking a question).
Languages may have diffrent types of interrogative clauses (i.e. different syntaxes used to ask different types of questions).
A question iteself is an illocutionary act/force seeking to obtain an answer.
In many languages, besides syntax/prosody, written exchanges often indicate interrogatives by special punctuation.

If syntax is used to indicate an interrogative, it may be in the form of conjugating the verb, changing the word order, adding interrogative words, particles, or other constituents, or often a combination of these.

##### conjugation

##### word order

###### I-to-C movement

In english, wh-questions and yes/no questions alike are marked by I-to-C movement.
In english interrogatives that are not subject questions, the sentence becomes a CP.
In english interrogatives, the newly formed C position is filled by I moving to C.
In english interrogatives, if there is no I to move to C, I is made pronounced via do-support.

###### wh-movement

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

##### adding constituents

###### tag questsions

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

###### interrogative words ＆ particles

In english, interrogative words start with wh- and are thus known as wh-words.

### sentences

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

### movement

discontinuity is the phenomenon where a constituent is split into two parts ⟮due to the insertion of an element which is not part of it⟯
Syntactic movement is the means by which some theories of syntax address discontinuities.
Two types of movement often distinguished are phrasal and head movement.
In phrasal movement, an entire phrase moves.
In head movement is when only a head of a phrase moves, leaving its dependents behind.

In chomskyian theories, movement leaves behind an empty category called a trace.
Traces are indicated by t and subscripted with a letter or  number indicating what moved, this is known as coindexing.
Some of the evidence of traces is that we can't contract over them.

In syntax, something is "in situ" if it doesn't move, although it normally would.

#### head movement 

The Head Movement Constraint (HMC) is the rule that a head H can only move to a position occupied by the head which selects HP as its complement.
Due to the HMC, the only way a constiutent can move to a position that isn't selecting HP as its complement is via stepwise movement.
The head movement contraint only applies to head movement, obv.

##### prepositions

When the object of a transitive preposition moves, what may happen to the prepostion is either preposition stranding or pied piping.
An entire expression moves, instead of leaving something behind   Pied Piping
A head moves and leaves behind a preposition   Preposition stranding

## grammatical feature

A grammatical feature is more rarely called grammatical category.
A grammatical feature is a property of items within the grammar of a language. 
Within each grammatical feature there are two or more possible values (sometimes called grammemes), which are normally mutually exclusive.

### phi-features (noun-related)

phi-features is a group of grammatical features related to nouns.
Phi-features include person, number, gender and case

#### noun class

Grammatical gender is a form of noun-class system.

#### number

Grammatical number is a grammatical feature distinguising amounts.
Grammatical number is most often marked on things present in the DP/NP (Determiners, Nouns, Adjectives) and via verbal agreement.
As regars grammatical number, most languages have a singular/plural distinction.
In languages with a singular/plural distinction, the singular refers to one entity, and the plural refers to more than one entity.
In languages with a singular/plural distinction, most often the singular is the unmarked form, and the plural is marked.
Some languages have a singulative/collective distinction.
In languages with a singulative/collective distinction, the collective refers to the item with no distinction into individual entities, and the singulative refers to a specific entity.
In languages with a singulative/collective distinction, the collective form is generally the unmarked one, while the singulative form is marked.
English, German and Spanish have grammatical number that distinguishes Singular and Plural, Japanese does not have grammatical number.

Other grammatical numbers:
Dual|two
Trial|three
Paucal|a few

#### case

Grammatical case is a grammatical feature marking thematic relation or grammatical relation/morphosyntactic alignment.
Grammatical case is mostly marked on things within the DP/NP.

Accusative   object of a verb
Nominative   Subject of a verb

Dative case is sometimes said to mark the indirect object, but the indirect object is just an english construct for describing a certain kind of object of a verb. in this sense, many cases mark something that is an object or at least argument of a verb, not just dative.
Dative indicates recipient or benificiary of an action.
Lative case indicates a movement to a location.
Ablative case indicates a movement away from a location.
Locative case indicates a location.
benefactive case indicates that something is done for the benefit someone/is intended for someone.
Benefactive case is often included in the dative case.
Terminative/terminalis case specifies a limit in space/time and/or the goal/target of an action.
Genitive   posess⁑or⁑
Instrumental   A means or tool used or companion present in/while performing an action	
Abessive/caritive/privative absence of the thing.
Comitative accompaniment
Ornative endowed with, supplied with
In english, the word with performs the function of both comitative and instrumental cases, this case is sometimes called the instrumental-comitative case..
Prolative/vialis/prosecutive/traversal/mediative by way of, via
Inessive within
Illative into
Elative out of
In elative "from inside"
Superessive on top of, on the surface of.
subessive below
perlative through, across, along
Vocative   adressee
Exessive away from a state
Egressive beginning of a movement from a location or time ('starting from')
Identical something is identical to another
Equative something is the same value as another
Comparative something is like something (e.g. cold as ice)
Translative case becoming X, changing to X
Pertingent case touching x
Intrative case "amidst"

### honorific

A honorific is a grammatical feature that encodes social relationships.
Honorifics may encode formality, social distance, politeness, humillity, deference, or respect, depending on the language.
Honorifics may be encoded via a variety of linguistic devices.

#### T-V

The T-V distinction is a honorific distinction encoded in pronouns.
The T-V distinction is sometimes understood more narrowly as a honorific distinction encoded in two different second-person pronouns.
The T-V distinction is common in many Indo-European languages, but not english.
The name T-V distinction comes from latin tu/vos.

### polarity

Polarity is a grammatical feature that encodes the difference between validity/truth/confirmation (positive polarity) and falsity/denial (negative polarity).
Positive polarity = affirmation
Negative polarity = negation

### others



### mainly related to verbs

#### grammatical person

⟮Grammatical person⟯ is personal deixis encoded in language.
It is frequently realized in ⟮personal pronouns⟯ and ⟮verbs⟯ (but sometimes also in other places).
Most languages distinguish three forms of grammatical person.

First person|The speaker
Second person|The addressee
Third person|neither speaker nor addressee

#### grammatical voice

Voice is a grammatical feature, mainly of verbs/VPs, that maps semantic roles over grammatical relations.
Subject is agent   active voice
Subject is patient/theme (= not agent)   passive voice
In english, when an active sentence is transformed to a passive sentence, the former object becomes the subject.
In english, the AGENT of a passive sentence is realized in a by-pp or left out entirely.
In english, by-PPs realizing the agent are adjoined to the right of the VP.
In english, the verb that is used to form passives is be, there is also a odd type of passive formed with get.

#### transitivity

Valency is the number of argument controlled by a thing, mainly by a verb.
Transitivity is a property of varbs that relates to whether a verb can take objects, and how many.
Valency is different from transitivity in that it counts arguments, and thus also the subject.
In general, the valency of a verb or similar is one higher than its transitivity.

0|impersonal/avalent
1|monovalnet
2|divalent
...

intransitive|doesn't take an object
transitive|takes an object
ditransitive|takes two objects
tritransitive|takes three objects
ambitransitive|may take an object or not

Ditransitive verbs take two objects, which in english may be termed the direct and indirect object.
In languages which mark grammatical case, it is common to differentiate the objects of a ditransitive verb using, for example, the accusative case for the direct object, and the dative case for the indirect object. In languages without morphological case (such as English for the most part) the objects are distinguished by word order and/or context. However, there exist differences in morphosyntactic alignment.

#### causative

A causative indicates that someone/thing causes someone/thing else to do/be something.
A causative increases the valency of the verb involved.

#### ergativity

an unergative verb is an intransitive verb whose argument is an agent.
an unaccusative verb is an intransitive verb whose argument is not an agent.

In linguistics, morphosyntactic alignment is the grammatical relationship between arguments.
Morphosyntactic alignment is more specifically used for the relationship between the two arguments (in English, subject and object) of transitive verbs like the dog chased the cat, and the single argument of intransitive verbs like the cat ran away.
The most common types of morphosyntactic alignment are nominative-accusative and ergative-absolutive, though there are others.
All languages I speak are nominative-accusative languages.
In a nominative-accusative (or just accusative) language, the specifier of an intransitive verb is treated like the specifier of a transitive verb grammatically, while the complement of a transitive verb is treated differently.
In a ergative-absolutive (or just ergative) language, the specifier of an intransitive argument is treated like the complement of a transitive verb grammatically, while the specifier of a transitive verb acts differently,

#### evidentiality

Evidentiality is the grammatical feature encoding what kind of evidence there is for a given statement.
A feature that encodes evidentiality is known as an evidential or verificational/validational

Following the typology of Alexandra Aikhenvald (2004, 2006), there are two broad types of evidential marking:

indirectivity marking ("type I")
evidential marking ("type II")

The first type (indirectivity) indicates whether evidence exists for a given statement, but does not specify what kind of evidence. The second type (evidentiality proper) specifies the kind of evidence (such as whether the evidence is visual, reported, or inferred).

type II evidentiality contains a bunch of distinctions, which may blend together:

witness/nonwitness: whether the source is direct eyewitnessing or obtained otherwise (secondhand, inferral, logical deduction, etc.)
firsthand/secondhand/thirdhand: may be orthogonal to witness/nonwitness since information may be firsthand but nonwitness (e.g. own inferral)
sensory: Which senses does the information stem from
inferential: Evidence was not personally experienced but inferred from indirect evidence.
Reportative evidentials indicate that the information was reported to the speaker by another person. A few languages distinguish between hearsay evidentials and quotative evidentials. Hearsay indicates reported information that may or may not be accurate. A quotative indicates the information is accurate and not open to interpretation, i.e., is a direct quotation.

Often languages form evidentiality systems based on a combination of some of the possible evidentials, e.g. {visual sensory, nonvisual sensory, inferential, reportative}

#### others


Clusivity is the grammatical feature encoding the difference between inclusive and exclusive first-person plural reference.
Inclusive first-person plural reference includes the adressee, exclusive first-person plural reference excludes the adressee.

#### tense-aspect-mmod

tense, aspect and modality are three grammatical features that are often strongly entangled in a given language and thus hard to separate.
for something to be a tense, aspect or modality it must be marked on the verb/vp.
Modality marked on a verb/VP is known as mood, however some authors also treat them as synonyms.
The marking of tense, aspect and modality is sometimes known as tense-aspect-mood
tense-aspect-mood is most often marked on verbs or via auxiliary verbs.

##### aspect

Aspect is tells you how time flows within the process/event itself.
Aspect may be divided into grammatical aspect, which is aspect indicated through inflection, and lexical aspect, which is inherent in a certain lexeme.
Aspect encodes different distinctions:
Eventive: Perfective/Imperfective
Inchoative/Cessative/ø
Prospective/Retrospective/ø
Gnomic/anything else

table:span=3;Eventive
span=1;⟮c+;s1:4;Perfective⟯|span=4;⟮c+;s1:4;Imperfective⟯
|span=2;⟮c+;s1:2;Habitual⟯|span=2;⟮c+;s1:2;Continuous⟯
|||⟮c+;s3:5;Progressive⟯|⟮c+;s3:5;Stative⟯


Perfective and imperfective aspect together make up the eventive aspect

perfective|event viewed in its entirety ( = without internal complexity)
Imperfective|event viewed with some sort of internal complexity 
Continuous|ongoing situation without interruption
Habitual|habitual, usual, customary action (imperfective but not continuous)
Progressive|continuous: ongoing and evolving 
Stative|continuous: ongoing but not evolving

There are other imperfective aspects:

Iterative aspect "signals that an action is repeated on a single occasion and differs from frequentative aspect, which both signal the repetition occurred on different occasions" (p. 160). 

Habitual be is a feature of AAVE indicating habitual aspect.
Spanish distinguishes imperfective and perfective verbs in the preterite tense.
In german, 'imperfekt' and 'perfekt' indicate tense, not aspect, despite their names!

The inchoative/cessative aspect indicates how the state is changing during the specified time.
Inchoative aspect is aspect indicating that something is beginning (however not that something is about to begin).
Cessative aspect is aspect indicating that something is ending.

The prospective/retrospective aspect indicates when an event takes place relative to the reference time.
Prospective aspect is aspect indicating that an event occurs subsequent to a reference time.
Retrospective aspect (commonly but confusingly also called perfect aspect, not to be confused with perfective aspect) is aspect indicating that an event occurs before a reference time.

Telicity (telic/atelic) is the grammatical feature of whether something has a specific endpoint.
Telicity is most often considered an aspect.

Gnomic aspect is an apsect indicating general truths.
The opposite of gnomic aspect is episodic aspect, truths that are temporally bounded.

##### modality

modality is a grammatical feature used to discuss possible situations. 
Different forms of modality are sometimes called flavors.
Modalities are primarily distingished along two axes: deontic/epistemic and realis/irreals
Deontic modality is modality that is concerned with how the world ought to be.
Epistemic modality is modality that is concerned with knowledge, belief or credence.
Realis moods/modalities are a set moods/modalities that indicate that something is the case.
Irrealisa= moods/modalities are a set moods/modalities that indicate that something is somehow not the case.
Most languages have a single realis mood/modality called the indicative mood/modality, although some languages have additional realis moods, for example to express different levels of certainty.
Distinction between different types of modality may not always be clear-cut, since different languages use different analyses.

Non-indicative realis moods are 
energetic: emphasis or strong belief
gnomic: general truths or aphorisms

Types of epistemic irrealis modalities
Subjunctive modality is a type of epistemic irrealis modality indicating that something is unlikely, this is generally used in subordinate clauses.
Potential modality is a type of epistemic irrealis modality indicating that something is likely. This may also be called tentative when talking about japanese, as potential means something else.
Dubitative modality is a type of epistemic irrealis modality indicating that something is dubious/doubtful or uncertain.
Speculative modality is a type of epistemic irrealis modality indicating that something is mere speculation.
Hypothetical modality is a type of epistemic irrealis modality indicating that while something did not happen, it could have happened.
Assumptive modality is a type of epistemic irrealis modality indicating that something is true because it is usually true in similar circumstances.

Types of deontic irrealis modalities

Deontic modality may be roughly dividend into commissive, directive and volitive:
commmissive|commital to something
directive|commands, requests, etc.
volitive|wishes, desires etc.

Permissive modality is a type of directive modality indicating that something is permitted
Imperative modality is a type of directive modality indicating a command.
Hortative modality is a type of directive modality indicating one is trying to encourage or discourage an action.
Prohibitive/vetative modality is a type of directive modality indicating that something is prohibited.
Propositive modality is a type of directive modality indicating a proposal or suggestion.
Propositive modality is a type of directive modality indicating that something should be brought about.

Desiderative modality is a type of volitive deontic modality indicating that one wants something.
Optative modality is a type of volitive deontic modality indicating Event is hoped/wished

Types of irrealis modalities not clearly epistemic/deontic
Conditional|Event depends on another condition

mirativity is an epistemic modality of which it is not clear if it is realis or irrealis.
Mirative|surprise/unpreparedness in relation to a given thing

## morphology

⟮Morphemes⟯ are the ⟮smallest⟯ ⟮unit of language⟯ that ⟮has some sort of meaning⟯. 
⟮Morphemes⟯ are studied in the field of ⟮morphology⟯. 
⟮Morphology⟯ generally deals with the ⟮phonology⟯ and not ⟮orthography⟯ of morphs/morphemes, as s⟮peech is more basic to language than writing⟯. 
A ⟮morpheme⟯, bearing ⟮a unit of meaning⟯, is made up of ⟮allomorphs⟯, which are ⟮the different phonetic realizations of that morpheme⟯. 
The word ⟮unbreakable⟯ consists of the morpheme ⟮un, break, able.⟯ 
⟮Morphs⟯ and ⟮morphemes⟯ are generally written in ⟮curly braces {⟯}. 
{{c17::{/ s /}, {/ z /}, and {/ iz /}}} are all ⟮allomorphs⟯ of {{c19::the morpheme {s} (plural s)}} 

Alternation is a morpheme exhibiting variation in its phonological realization based on its phonological/morophological and/or syntactic environment. Variants are called alternants. TODO: is this equivalent to allomorphs?
Alternation (a synchronic morphological phenomenon) needs to be distinguished from sound change (a diachronic phenomenon).
A null/zero morpheme is a morpheme that has no phonetic form/realization.

### Word formation

Word formation is broadly the creation of new words.
Word formation may either be the creation of variant forms of a lexeme via inflection (e.g. fly-flew), or the creation of new lexemes.
Word formation as the creation of new lexemes is known as derivation.
Derivation may be morphological or nonmorphological.
Morphological derivation is derviation by adding or removing morphemes.
Nonmorphological derivation is derivation that is not directly related to the morphemes in the base.

A portmanteu is where parts of multiple words are combined into a new word/morph.
A blend/blend word word/lexical blend is a portmanteu where at least one of the parts combined is not a morph.
Sometimes, portmanteus and blends are considered synonyms, i.e. the restriction that a blend is a thing where one thing is not a morph is dropped.
In linguistics, a portmanteu or portmanteu morph may also be the merger of multiple morphs into one morph.
Examples of blend words are smog (smoke + fog) or brunch (breakfast + lunch)

For example, -t in spanish might be a portmanteu morph of the morph for 3rd person and for singular, took may be considered a portmanteu morph of take + ed.

#### morphological

In linguistics, clipping, also called truncation or shortening, is word formation by removing some segments of an existing word to create a synonym.
Clipping: Coronavirus → rona, refridgerator → fridge, influenza → flu
Clipping is also different from back-formation, which proceeds by (pseudo-)morpheme rather than segment, and where the new word may differ in sense and word class from its source.

A hybrid word is a morphological derivation that derives from at least two different languages. 
The most common ⟮hybrid words⟯ in ⟮english⟯ consist of ⟮one latin-derived and one greek-derived part⟯
⟮asexual (greek a- and latin sexus), democide (greek demos and latin -cida), automobile (greek autos and latin mobilis)⟯ are examples for ⟮hybrid words⟯

#### nonmorphological

##### abbreviation

An abbreviation is a nonmorphological derivation by shortening a word.

While rareish, there are some abbreviations that use a slash, generally separating two characters representing two morphemes, but not in an 'or' rleationship (e.g. w/o, b/w, w/e, n/a)

###### acronym

An acronym is a type of abbreviation formed from the first letters of other words.
Sometimes initialism or alphabetism is sometimes used to refer to an acronym which is pronounced as individual letters.
Sometimes initialism is a synonym for acronym.
Examples of acronyms include ATM for automated teller machine and SIA for singapore international airlines
A backronym is a word that originally was not an acronym but is turned into one.
Examples of backgronyms: SAD ("seasonal affective disorder"), SOS ("Save Our Souls")
More recent examples include the brand name Adidas, named after company founder Adolf "Adi" Dassler but falsely believed to be an acronym for "All Day I Dream About Sport";[15] Wiki, said to stand for "What I Know Is",[16] but in fact derived from the Hawaiian phrase wiki-wiki meaning "fast";[17] or Yahoo!, sometimes claimed to mean "Yet Another Hierarchical Officious Oracle", but in fact chosen because Yahoo's founders liked the word's meaning of "rude, unsophisticated, uncouth" (taken from Jonathan Swift's book Gulliver's Travels).

###### numeronym

A numeronym at its most common is a word based on/using numbers.
Most commonly, a numeronym (a number based on/using numbers) is an abbreviation.
Numeronyms as abbreviations frequently either count the amount of letters in a word, have the numbers stand for words thus forming a weird abbreviation, or use the number metonymically.
Examples for numeronums: 9/11 (date metonym), i18n (letter count), 4649 (weird syllablecronym)
a11y  accessibility
g11n  globalization
p13n   personalization
i18n   internationalization

#### Productivity

productivity is the degree to which native speakers of a language use a particular grammatical process, especially in word formation.
The polar ends of productivity are productive and unproductive.
Word formation processses that are applied very infrequently are likely unproductive.
If a word formation process can be applied to create new words, it is productive.
In english, using ablauts to create preterite verbs is unproductive, while using -ed to create preterite verbs is productive.

### Inflection

Inflection is modifying a lexeme to reflect one or more gramattical features, thus creating a new word.
Inflection is commonly done via affixation or apophony, but there are also other possible modifications.
An invariable/invariant word is a word that cannot be inflected.
Inflection can be subdivided into ⟮Declension and conjugation⟯
Name|Inflection of|
⟮Conjugation⟯|⟮Verbs⟯
⟮Declension⟯|⟮Nouns or Adjectives⟯


#### Agreement

Agreement is inflection caused by other words (or similar) in the sentence.

#### Inflectional paradigm

An »inflectional paradigm« is the complete set of forms that a class of words can assume ⟮when inflecting⟯
An inflectional category is a class of inflection pattern that have a common grammatical category/feature. (i.e. its any realization of a grammatical category/feature as inflection)
A lexeme that lacks some of the forms of its inflectional paradigm is defective.
beware is a verb that is defective, as we can see by the fact that we can't say she bewares (of) the dog.

A verb that follows a pattern of a typical inflectional category is called regular, else irregular.
Inflectional categories of verb conjugations are called verb clasess.

### stem, base, root

The root is the irreducable morphological core of a word, with the core lexical meaning.
The stem is the root plus any derivational changes (see derivation (word formation))
The stem is the morpheme that is commonly used as a starting point for inflections.
A base is any morphological unit to which affixes can be attached.

#### japanese stems

The stem that we most commonly call 'stem' in english is the 
stem of ru-verb is verb - る
Stem of u-verb is ‹consonant›u → ‹consonant›i

### free and bound forms

A free form is one that can stand on its own as a word.
'cat', 'fire'
A bound form is a morpheme that onlly appears as part of a larger word.
'-ment'
A bound/free morpheme is a bound/free form that is a morpheme.

#### affixes

Affixes are bound morphemes attached to the stem for word formation.
prefix|before the word|a- (e.g. atheist)
suffix|after the word|-s (plural suffix)
circumfix (more rarely confix or ambifix)|a affix that has a part that goes before and a part that goes after the word|o- ... -ni naru
duplfix|synonym of reduplication
infix|affix inserted into a word stem

Reduplication is the process in which a morpheme is repeated within a single word

A ⟮libfix⟯ is a ⟮productive⟯ ⟮bound morpheme affix⟯ created by ⟮back-formation⟯, which still ⟮contains some of the original meaning of the word⟯.
⟮-gate, -cation, -tard, -verse⟯ are examples of ⟮libfixes⟯

#### clitics

Clitics are bound morphemes that acts like a word in certain syntactic properties, and like an affix in that it can't stand on its own, though the boudnaries are somewhat fuzzy.
The thing that a clitic attaches to is its host.
When something is being attached as a clitic, it is ⟮cliticising⟯
```lang=text;
It☞'s☜ a boy!
I☞'m☜ terribly sorry.
The queen☞'s☜ balls.
I haven☞'t☜ the faintest.
Senatus Populus☞que☜ Romanus
``` 
Enclitic   A clitic that appears after its host
Mesoclitic   A clitic that appears between the stem of the host and other affixes
Proclitic   A clitic that appears before its host

### compounds

In linguistics, a compound is a lexeme that consists of more than one stem.
The head of a compound is the stem that is the thing that is being modified by the other stem(s) in the compound.
name|description|formalization, assuming head-final
endocentric compound|the basic type of thing is indicated by the head, and the other stems describe that|A+B denotes a kind of b|smalltalk
exocentric compound|s a hyponym of some unexpressed semantic category (such as a person, plant, or animal)|A+B denote a special kind of unexpressed thing|white-collar, scarecrow
copulative compound|the word is what any of the stems is|A+B indicate the sum of A and B|bittersweet, sleepwalk
appositional compound|all stems are equal attributes of a certain referent|A+B indicates something that is both A and B|hunter-gatherer
A dvandva is another name for an appositional compound.
If the english word for siblings was a dvandva/appositional compound and we believed in the gender binary, it would be brothersister.
Japanese forms appositional compounds, which will generally not display 連濁.
e.g. 　山（やま・さん）　川（かわ・せん） for mountains and rivers = scenery and 　左（さ）　右（ゆう） for left and right = control.
Japanese endocentric compounds will generally display 連濁 if phonotactically possible.

#### english

In english, ⟮compounds⟯ can be ⟮open⟯ = ⟮containing a space⟯, e.g. ⟮real estate⟯, ⟮closed⟯ = ⟮not containing a space⟯, e.g. ⟮waistcoat, bookstore⟯, or ⟮hyphenated⟯ = ⟮containing a hyphen⟯, e.g. ⟮long-term⟯ 
In english, ⟮compounds⟯ generally ⟮progress from open to closed⟯, sometimes ⟮with a hyphenated form as an interim phase.⟯ 

An example of ⟮the typical progression of english compounds⟯ is "T⟮c+;o day" → "to-day" → "today"⟯

### errors

A surface analysis is any valid analysis of a words morphology, no matter if etymologically true.

reanalysis is a form of surface analysis, specifically an analysis of a lexeme into a different morphology than it originally had.
juncture loss is the form of reananalysis where an article and a noun fuse.
Juncture loss: al + chemy (from arabic) → alchemy

Rebracketing is also sometimes known as resegmentation or metanalysis
rebracketing is the form of reanalysis that involves analyizing a lexeme/lexical unit into a different set of morphemes 
rebracketing: hamburger as ham + burger instead of hamburg + er

#### etymological

a folk etymology (or similar) is an etymology that is based on an common-sense/obvious (but false) interpretation, it may also be in a different sense be used as a synonym to reanalysis
Synonyms: folk etymology, fake etymology, false etymology, pseudoetymology

## linguistic error

Speech (production) error = mistake
Mistakes and errors are both unintentional deviation from the grammar of a languoid.
An error is a deviation from the grammar of a languoid that is caused by lack of knowledge about the grammar of the languoid.
A mistake is a deviation from the grammar of a languoid that is merely an error in performance, and would ordinarily not have happened.
Typically, only L2 speakers make errors, while anyone can make mistakes.
Errors may also lead to language change.

# types of words

## numerals

A numeral is a word or phrase that describes a numerical quantity.
Numerals may be seen as their own part, or as an abstract concept that may be instantiated by different parts of speech.
Across languages, numerals seem to be able to act as nouns, pronouns or adverbs.
Numerals are generally based on one or more counting systems.
In linguistics, measure words are words (or morphemes) that are used in combination with a numeral to indicate a semantically qualified amount.
There are different kind of numerals (whether realized as words or phrases): 
ordinal numerals|position in sequence
cardinal numerals|amount/quantity
multipliers|
distributive numerals|
collective numerals|
Numerals are typically constructed via a counting system.
Counting systems across languages may have different bases, and stop counting every power of 10 at different numbers: most commonly at 1000 or at 10 000 (myriad)
due to the practice of wrapping at 10 000, 10 000 is used in many sinosphere languages to mean a lot, and most commonly 10k years = a long life.

### japanese

In japanese grammar, measure words are typically called counters.
In japanese grammar, measure words are required for any numeral and when asking for quantities.
In japanese grammar, numerals, measure words and optional indicators for cardinality form a phrase (which I will call Counter Phrase).
Japanese 'counter phrases' can function in various syntactic ways: They can become no-adjectives, be used adverbially or postpositionally.

The japanese counting system:
rational-number ::= [マイナス]‹positive-rational-number›
positive-rational-number ::- ‹integer›[　点（てん）‹digit›{‹digit›}]
integer ::= {‹myriad-unit›}[‹place›][‹place›][‹place›]‹place-when-base-1›
myriad-unit ::= [‹place›][‹place›][‹place›]‹place-when-base-multiple-of-four›
place ::= ‹digit›‹base-word›
place-when-base-1 ::= ‹digit›
place-when-base-multiple-of-four ::= ‹digit›‹base-multiple-of-four-word›

Japanese digits:

0|零・丸・ゼロ


1|一|いち|ひと
2|二||ふた
3|三||みっ
4|四||よ(ん・っ)
5|五||いつ
6|六||むっ
7|七||なな
8|八||やっ
9|九||ここの

Japanese bases up to 1000

10|十|じゅう|とお
100|百|ひゃく|もも
1000|千|せん|ち

Japanese base when multiple of four words:

10^4|万|まん|よろず
10^8|億|おく|none
10^12|兆|ちょう|none

Counters

日|か|days|訓 (exception 一日：ついたち)

## interrogative word

An interrogative word or particle is a word used to create a kind of interrogative sentence.
Interrogative words are generally not their own part of speech, but instead fall into the category of other parts of speech.
An interrogative particle is a type of inerrogative word that converts a statement into a yes-no question.

## demonstratives

demonstrative determiners usually map onto the spatial/discourse deixis distinction
Demonstratives usually come in two flavors, demonstrative determiners and demonstrative pronouns, which may or may not be derminers depending on your theory.

proximal|this
medial/distal|that
distal (rare)|yon(der)

proximal|este, estos|esta, estas|esto
medial|ese, esos|esa, esas|eso
distal|aquel, aquellos|aquella, aquellas|aquello

Neuter forms do not change for number.

### Japanese

In japanese, the deictical distinction comes in form of morphemes, which form a large set of demonstratives with other morphemes.
The japanese deictical morphemes collectively are known as こそあど.

proximal|こ
medial|そ
distal|あ
question|ど

demonstrative determiner|~の
demonstrative pronoun (things)|~れ

the demonstrative determiners この、その… are originally abbreviations of これの、それの….

## posessive

A posessive is a word or form indicating poession,
Many languages (of those I speak: en, de, es) indicate a posessive via a set of possessive determiners and pronouns.
Many languages also have a posessive verb, e.g. en/de have/haben, es tener.
In japanese, the job of the posessive verb is done by extential verbs/clausees.

# ordination

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

## coordination

Coordination is the process of linking two things of the same type.
The two things linked via coordination are called conjuncts.
The totality of coordinator(s) and conjuncts forming an instance of coordination is called a coordinate structure.

## subordination

Subordination is linking two things (maincly clauses), where one depends on the other.
A complement clause is an argument of a predicate.
A complementizer turns a clause into 
A complementizer turns a clause into the subject or object of a sentence.
In english, the complementizer 'that' sometimes is unpronounced
Akane thought that Lilly was a いい子. ⇒ Akane thought Lilly was a いい子. 

# parts of speech

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

## particle

A particle is a function word (member of a functional category) which cannot be inflected.
A particle occurring at the end of the sentence is a sentence-final particle.
Particles do not refer.
Sentence-final particles in particular generally indicate modality, register or other pragmatic effects.

## Interjections

An interjection is a lexical item that indicates a reaction. 
Interjections are pretty separated from the rest of the syntax of the sentence.
Interjections are a syntactic category, while discourse marker is a pragmatic category.

## adjective

An adjective (phrase) describes a thing or restricts its referent.
Adjective phrases in english can exist syyntactically in three ways: an attributive adjective, a predicative adjective and a nominalized adjective.
An attributive adjective phrase is adjoined to an NP.
A predicative adjective phrase has the adjective phrase as the complement of the verb.
A nominalized adjective works as the head of an NP.

## adverb

In english at least, adverb(ial) phrases (and thus adverbs) act as a modifier/adjunct for any number of phrases, but not NPs (which is instead handled by APs).
Adverbial phrases describes the thing its modifying.
Adverbs/adverbial phrases are at least able to modify other AdvPs, APs, DPs, PPs, VPs, and IPs.

## noun

Nouns are heads of NPs.
NPs (no DP theory) matter because they are the things that can be subjects or objects of verbs or prepositions.
If we believe in the DP theory, NPs matter because they are the complements of Ds, and DPs are the things that can be subjects or objects of verbs or prepositions.

### attribution

In grammar, something attributive is a phrase within a NP/DP that modifies the head noun. 
Adnnominal seems to be a synonym for attributive
In english, relative clauses and attributive adjectives are the main things that act attributively.
A verb that can be used attributively is known as an attributive verb.

## det

A determiner is a word/affix that occurs that occurs together with a NP and expresses something about the reference of the noun phrase.
Often, for any given pronoun, there is a similar or identical determiner
Types of determiners: Articles, Demonstrative determiners, Quantifiers, distributive determiners, interrogative determiners

### Quantifier

Quantifiers are a type of determiner/pronoun (which may depending on your analysis may be a quantifier too).
quantifiers are adjoined to the DP/NP to form a larger DP/NP.
table:span=2;⟮DP⟯
⟮Q/D⟯|⟮DP⟯
all|the students

Floating quantifier is a quantifier that is not immediately near the NP/DP it quantifies.
According to the VP-int-subj-hyp, floating quantifiers happen because of the two DPs that could move to the subject position in the specifier position of the IP, the smaller DP moves, leaving the quantifier behind.
The existence of floating quantifiers provides evidence for the VP-internal subject hypothesis by explainin why the quantifier is in this position.

### Articles

Examples of Articles in EN: the, an, a

### posessive determiners

my, your, his, her, its, our, their

## adpositions

An adposition may either be a preposition, circumposition or a postposition.
semantically, adpositions may be temporal adpositions, spatial adpositions, or adpositions that mark a different semantic/thematic role.
Adpositions may be transitive or intransitive.
Intransitive adpositions are often called adverbs, though that's probably an inferior analysis.
Intransitive adposition examples: here/everywhere/downstairs/ahead/outside/...
Transitive adpositions may take other adpositions as complements.

## conj

Conjunctions either perform coordination or subordination.

## proforms

Proforms are function words that stand in for another constituent.
DP/NP|Pronouns
NP/N'|one
Verb|do (so)
Temporal adposition|then
Spatial adposition|there
other adposition|none exists

### pronouns

Pronouns are proforms that stand for NPs, or DPs if we believe in them, not for nouns themselves.

A pro-drop language is a language where certain classes of pronouns may be omitted when they are pragmatically or grammatically inferable. 
Japanese and Spanish are pro-drop, German and English are, with rare exceptions, not.

#### personal

Personal pronouns are pronouns that are associated primarily with a particular grammatical person.


## copula (and existential verbs)

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

## verbs

### dynstat

Dynamic and static verbs are often contrasted.
A dynamic verb is a verb that describes an action.
A stative (unclear relation to stative aspect) verb is a verb that descirbes a state.
setzen is a dynamic verb while sitzen is a dynamic verb.

### aux

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

## changing parts of speech

### nominalization

Nominalization is the process of treating / transforming something which is not a noun as / into a noun / head of an NP.
A nominalizer is a thing, usually a bound morpheme, that nominalizes a thing.
# phon

## phonology

Phonology is a branch of linguistics that studies the sound systems of lects = how lects organize their sounds.

### morphophonolgy

Morphophonology studies the interaction between morphology and phonology/phonetics.

#### sandhi

Sandhi is a cover term for sound changes that happen at morpheme/word boundaries
Sandhi is a part of morphophonology.
Japanese exhibits two forms of sandhi, 連濁 and 連声.
連声 is the phenomenon that when a morpheme ending in ん and a morpheme beginning with a vowel collide, the second morpheme will instead begin /n‹vowel›/
てんおう → てんのう is an example of 連声

### segmental phonology

Segmental phonology is concerned with the analysis of speech into phonemes.

#### phonemic contrast

two phones (/etic units)...
appear in the same phonetic (/emic) environment|don't appear in the same phonetic (/emic) environment
free variation|contrastive distribution|complementary distribution
changing between two phones (/etic units) doesn't change the meaning|changes the meaning|is impossible
allophones (/alloetic units)|not allophones (/not alloetic units)|possibly allophones (/possibly alloetic units)

Two phones (/etic units) in contrastive distriibution have phonemic (emic) contrast = the difference between phones (/etic units) markes the phones (/etic units) as belonging to different phonemes (/emic units).
Two phones  (/etic units) in contrastive distribution = with phonemic  (/whateveremic) contrast are said to be contrastive or phonemic (/whateveremic).

A minimal pair is two or more words that only differ in only one distinctive feature, yet are not homophones  (/homoetic units).
In a minimal pair, the set of phones (/etic units) that has the difference in one distinctive feature is in contrastive distribution (thus marking them as belonging to different phonemes (/emic units))

Two phones wihtout phonemic  (/whateveremic) contrast = never appearing in contrastive distribution = not having a minimal pair may still be part of different phonemes (/emic units) if they are very dissimilar phonetically (/whateveremicaly).

If two phones (/etic units) which normally are contrastive/phonemic occur in a phonemic (/whateveremic) environment where they no longer are contrastive/phonemic(/whateveremic), the phonemic (/whateveremic) contrast is said to have been neutralized.

Free variation is free in the sense that it does not mark a difference in semantics/grammar, but not free in the sense that variants in free variation may have social significance, making them variants in a sociolinguistic variable.

#### the syllable

##### structure


table:headerrows=0;style=min-width: 15em;!span=3;⟮σ/syllable⟯
!⟮c+;s4:5;Onset⟯|span=2;⟮c+;s4:5;Rhyme⟯
!|⟮c+;s2:3;Nucleus⟯|⟮c+;s2:3;Coda⟯

The syllable is typically represented by σ.
Syllables must at least have a nucleus.
The nuleus of a sullable is almost always a vowel, except in the case of syllabic consonants.
When writing syllables, vowels are typically indicated V and consonants C.
A semivowel is a vowel that forms a syllable boundary and thus not the nucleus.
A semivowel is indicated by the IPA as ［◌̯］, sadly.
A semivowel may be called a glide since they often act similar to a dipthong, but this term is ambiguous between any transitional sound.
A consonant that forms the nucleus of a syllable is known as a syllabic consonant.
Only consonants are explicitly marked as syllabic with the IPA symbol when necessary, as it is presumed that vowels are also syllable nuclei.
syllabic consonants are marked by ［◌̩］ or ［◌̍］}} in the IPA
An open syllable is a syllable without a coda. (CV, V, ...) 
A closed syllable is a syllable with a coda. (CVC, VC, ...) 
In japanese most syllables are open syllables, either CV or V.

monosyllable|Word that consists of a single syllable
dibisyllable|Word that consists of two syllables
trisyllable|Word that consists of three syllables
polysyllable|Word that consists of either more than one or more than three syllables

Syllable breaks are explicitly marked in teh IPA by `.` or when that would be too confusing by $
The stress and secondary stress marks also imply a syllable break.
Using spaces in the IPA implies a syllable break, if you want to prevent this, use the ‿ symbol.

The part of the syllable called the rhyme is called that because it's the part that's often used for rhymes.

#### morae

A mora is a unit of equal timing.

### suprasegmental phonology

suprasegmentals/prosodic features are properties of syllables and larger units of speech.
suprasegmental = prosodic feature
suprasegmental phonology/prosody is the branch of phonology concerned with suprasegmentals/prosodic features.
Suprasegmental phonology is also called prosody.
prosody is also sometimes used in a more narrow sense as a synonym to metre in poetry.



####  types of prosodic features

The main prosodic features are intonation, tone, stress, tempo.
Many phenomena of prosody have to do with syllables.

##### stress

In linguistics, and particularly phonology, stress or accent is the relative emphasis or prominence given to a certain syllable in a word or to a certain word in a phrase or sentence.
The IPA distinguishes between primary and secondary stress, the symbol follows polish notation in both casees.
primary stress|ˈ (ˈa; sɐˈbiɐ)
secondary stress|ˌ (ˌa; [ˈfotəˌɡɹæf])

##### tone & intonation

Tone is the use of pitch in language to distinguish lexical or grammatical meaning.
In linguistics, intonation is variation in spoken pitch when used, not for distinguishing words as sememes (a concept known as tone), but, rather, for a range of other functions.


phenomenon|symbol
⟮extra high/top tone (not intonation) (suprasegmental)⟯|⟮［ŋ̋ e̋］ or［e˥］⟯
⟮high tone (not intonation) (suprasegmental)⟯|⟮[ŋ́ é] or [e˦]⟯
⟮mid tone (not intonation) (suprasegmental)⟯|⟮［ŋ̄ ē］ or ［e˧］⟯
⟮low tone (not intonation) (suprasegmental)⟯|⟮[ŋ̀ è] or [e˨]⟯
⟮extra low/bottom tone (not intonation) (suprasegmental)⟯|⟮[ŋ̏ ȅ] or [e˩]⟯
⟮global rise (intonation, not tone) (suprasegmental)⟯|⟮↗︎◌⟯
⟮global fall (intonation, not tone) (suprasegmental)⟯|⟮↘︎◌⟯
⟮Generic rising tone (not intonation) (suprasegmental)⟯|⟮ŋ̌ ě⟯
⟮Generic falling tone (not intonation) (suprasegmental)⟯|⟮ŋ̂ ê⟯
⟮Upstep (not intonation) (suprasegmental)⟯|⟮ꜛ◌ or ꜞ◌⟯
⟮Downstep (not intonation) (suprasegmental)⟯|⟮ꜜ◌ or ꜝ◌⟯

Why does it make sense to have a downstep at the end of a word?  ⟮Because any attached morphemes will inherit the downstep⟯
What does the downstep arrow apply to?  ⟮Everything after it⟯

##### speech tempo

##### rythym

###### isochrony

Isochrony is question of which linguistics units occupy equal time.
There are three broad ways languages can be isochronically.
The three isochronic types are: syllable-timed, mora-timed, and stress-timed.
The three isochronic types don't seem to exist as extremes, rather a language makes use of all three types to greater or lesser degrees depending on the language.
Isochrony is one of the main ways language's prosody is categorized in linguistic typology.

####### isochronic types

table:unit which occupies equal time|name
syllable|syllable-timed
mora|mora-timed
interval between two stressed syllables|stress-timed

###### feet

The basic rythmic unit of indo-european poetry is a foot.

####### number of feet

Meter|Number of feet
⟮Trimeter⟯|⟮3⟯
⟮Tetrameter⟯|⟮4⟯
⟮Pentameter⟯|⟮5⟯

####### type of feet

Foot|Pattern|Mnemonic
⟮Iamb⟯|⟮daDA⟯
⟮Trochee⟯|⟮DAda⟯|⟮c:∞;⁑Tro⁑chees; ⁑tro⁑phies¶
⁑Dou⁑ble, ⁑dou⁑ble, ⁑toil⁑ and ⁑trou⁑ble;⁑Fi⁑re ⁑burn⁑ and ⁑cauld⁑ron ⁑bubb⁑le.⟯
⟮Anapest⟯|⟮dadaDA⟯|⟮c:∞;Jeder dritte stirbt durch die pest.¶
 Die pest gewann den dritten platz auf der rangliste "Größte tragödien der Menschheitsgeschichte". Ana⁑pest⁑¶
 Twas the ⁑night⁑ before ⁑Christ⁑mas and ⁑all⁑ through the ⁑house⁑⟯
⟮Dactyl⟯|⟮DAdada⟯|⟮c:∞;⁑Just⁑ for a ⁑hand⁑ful of ⁑sil⁑ver he ⁑left⁑ us ¶
⁑Just⁑ for a ⁑rib⁑and to ⁑stick⁑ in his ⁑coat⁑⟯
⟮Choriamb⟯|⟮DAdadaDA⟯|⟮c:∞;A choriamb is an iamb that has been held up a mirror.¶
⁑Who⁑ hath not ⁑seen⁑ thee oft amid thy store? ⁑Some⁑times who⁑ev⁑er seeks abroad may find⟯
⟮Molossus⟯|⟮DA DA DA⟯|
⟮Amphibrach⟯|⟮da DA da⟯|⟮c:∞;If amphibrach was an amphibrach, it would have a stressed 21st greek letter (phi)¶
「There ⁑once⁑ was / a ⁑girl⁑ from / Nan⁑tuc⁑ket.」⟯

##### pause

In the IPA, | and ‖ both mark prosodic breaks.
In the IPA, | is used to mark a longer break than ‖, but how long each of them is depends on the context.
In a similar sense to how the IPA uses it, the vertical bar | is used to mark feet in poetry.
In poetry, often the slash is used to mark line breaks.

##### chunking


#### changes in sounds

Changes in sounds may be for sound changes (diachronic changes in a sound system), alternation between allomorphs by a speaker, or apophony.
Apophony is sound change within a word to indicate a grammatical feature ≈ sound change within a word due to inflection.
Types of changes in sounds (whether for sound change, alternation, or apophony) may amongst others be elision, epenthesis, metasthesis, lenition/fortition, transphonologization or assimilation/dissimilation.

##### Elision

In linguistics, an elision or deletion is broadly defined as the omission of one or more sounds (such as a vowel, a consonant, or a whole syllable) in a word or phrase. However, it is also used to refer more narrowly to cases where two words are run together by the omission of a final sound.
Syncope, apocope and apheresis are most commonly of unstressed vowels.

Syncope is a form of elision which is the loss of a sound from the interior of a word
Apocope is a form of elision which is the loss of a sound from the end of a word
Apheresis is a form of elision which is the loss of a sound from the beginning of a word
Haplology is a form of elision where an entire syllable is lost, where that syllable was similar to an adjacent syllable

##### Epenthesis

Epenthesis is the addition of a sound to the word.
prothesis is epenthesis at the beginning of the word.
paragoge is epenthesis at the end of the word.

##### Metathesis

Metathesis is the transposition/switcharoo of sounds or syllables in a word or sentence:

fo☞li☜age → **fo☞il☜age
ane☞mone☜ → ane☞nome☜
Methathesis of non-adjcancent sounds is sometimes known as hyperthesis/long-distance metathesis
pa☞r☜abo☞l☜a (latin) → pa☞l☜ab☞r☜a

##### Lenition/Fortition

Lenition moves sounds up the sonority hierarchy (more sonorous)
Lenition moves sounds down the sonority hierarchy (less sonorous)

##### Transphonologization

Transphonologization is the change of a phonemic contrast so that the contrast is preserved, but the distinctive feature it is based on changes.

For example, a language contrasting two words */sat/ vs. */san/ may evolve historically so that final consonants are dropped, yet the modern language preserves the contrast through the nature of the vowel, as in a pair /sa/ vs. /sã/. Such a situation would be described by saying that a former contrast between oral and nasal consonants has been transphonologized into a contrast between oral vs. nasal vowels. 

##### Assimilation/Dissimilation

Assimilation is a sound change in which some sounds change to become more similar to other nearby sounds. 
Dissimilation is a sound change in which some sounds change to become less similar to other nearby sounds. 
Example of assimilation: English "handbag" (canonically /ˈhændbæɡ/) is often pronounced /ˈhæmbæɡ/ in rapid speech 


#### phonotactics

Phonotactics is a branch of phonology that deals with the permissible combinations of phonemes.


## phonetics

Phonetics is a branch of linguistics that studies the properties, production and perception of speech sounds, or in the case of sign languages, the equivalent aspects of sign.
Phonetics is traditionally divided into articulatory, acoustic and auditory phonetics.
articulatory phonetics|production of speech sounds
auditory phonetics|perception of speech sounds
acoustic phonetics|acoustic effects on speech sounds

Unit of interest: phones


### distinctive feature

distinctive features are features that describe binary phonetic values.
Distinctive features are *relevant* for phonemic contrast in phonetics.
In phonology, a natural class is a set of phonemes in a language that share certain distinctive features.
When a phone has multiple feature specifications that we are interested in talking about, we produce a feature matrix. [g] could be [+voiced, +dorsal, +high]. 
Distinctive features are typically grouped into major class features, manner features, place features, and laryngeal features.
Major class features are a group of four features that share little in common phonetically, but describe the overall type of a phone.
The four major class features are [+/- syllabic], [+/- approximant], [+/- consonantal or eqivalently +/- vocalic], [+/- sonorant]

#### IPA



### anatomy

The laryx containes the vocal cords/folds, the gap between which is called the glottis.
The vocal tract is all the anatomy above the laryx used for speech production.
The vocal tract consists of the buccal, oral, nasal and pharyngeal cavities, and the articulators contained within.
Soft palate = velum
The pharynx is the posterior part of the vocal tract, consisting of a tube of muscles sitting above the larynx.
The pharynx = pharyngeal cavity.
the pharynx can be narrowed or closed by the epiglottis, a flap that is usually used to prevent food from entering the larynx.
https://upload.wikimedia.org/wikipedia/commons/d/d4/Illu01_head_neck.jpg
The buccal cavity is the space between the teeth and the cheeks.
The oral cavity aka the mouth is the space between the pharynx and the lips.

### consonants

The difference between consonants and vowels is that for vowels, the vocal tract is less narrowed than for consonants.
Whether something is a consonant is described by the major class feature [+/- consonantal]
There exist voiceless nasals, but no extra IPA symbols for them (they must be diacriticized)
Whether voiceless approximants exist is controversial
Consonants are traditionally categorized by their manner and place of articulation as well as their voicing.

#### signeltons and geminates

Singleton and geminate are two types of consonates distinguished by consonant length.
A geminate consonant is articulated for longer than a singleton.
A geminate consonant is also just called geminate.
The process of a singleton becoming a geminate is called gemination.
In many alphabets, geminates are written with doubled letters.
gemination is phonemic/contrastive in japanese but not in english, german or spanish.
For gemination, lengthened fricatives, nasals, laterals, approximants and trills are simply prolonged. In lengthened stops, the obstruction of the airway is prolonged, which delays release, and the "hold" is lengthened. 
In japanese, gemination is marked by っ.
In japanese, non-phonemic gemination implies emphasis (not in all varieties though).
すごい → すっごい
In japanese, gemination typically only happens to unvoiced consonants (and vowels), voiced consonants only geminate if part of 外来語.
If gemination of voiced consonants happens as part of 外来語, they are often devoiced.

#### Coarticulation

Co-articulated consonants are consonants produced with two or more simultaneous places of articulation.

co-articulated consonants
doubly articulated consonants|consonants with secondary articulation

secondary articulation is the articulation that happens when a consonant has two or more places of articulation whose manners are different and at least one of which has the manner of approximant.
Secondary articulation is indicated in the IPA by superscripting the approximant version of the letter, where the place indicated by the superscript is the place which is articulated with the manner of approximant.
Therefore:
labialization (AKA rounding) (secondary articulation)|［◌ʷ］
pharyngealization (secondary articulation)|［◌ˤ］
velarization (secondary articulation)|［◌ˠ］
There is one special symbol for secondary articulation which indicates velarization OR pharyngalization, and is not a superscripted approximant symbol: ［◌̴ ］, as in ［ɫ］
labialization (secondary articulation)|［◌ʷ］
It's important to realize that although the superscripting of a letter for secondary articulation seems to imply that it is simlar to the release diacritics which also use superscripts, in fact secondary articulation is simultaneous to the primary articulation.
In phonetics, vowel roundedness refers to the amount of rounding in the lips during the articulation of a vowel.
Vowel roundedness is labialization of a vowel.
Labialization is a form of secondary articulation involving the lips.
There are two forms of labialization/rounding, protruded rounding anc compressed rounding.
In protruded rounding, the lips push out of the face to produce the rounding.
In compressed rounding, the lip push onto each other and do not push out to produce rounding.
There are no dedicated IPA diacritics to represent the distinction, but the superscript IPA letter ⟨◌ᵝ⟩ or ⟨◌ᶹ⟩ can be used for compression[8] and ⟨◌ʷ⟩ for protrusion. 
flex-container:✫sm_paste-9d57b921c2367caed7728b4ecc2e08a61fccaafe.jpg✫✫sm_paste-5da6ee49b0be29e64772806d15b710f95be11ec5.jpg✫
(lips that are) less rounded/labialized (than usual for that sound)   ◌̜
(lips that are) more rounded/labialized (than usual for that sound)   ［◌̹］

Doubly articulated consonants are consonants with two simultaneous primary places of articulation of the same manner.

#### IPA mnemonics

Progression of voiceless stops (palatal, velar, uvular)?  ckq]

### mechanics

Speech production is the process by which thoughts are translated into speech.
Speech production is not the same as language production since language can also be produced manually by signs. 
The phonetic part of speech production is divided into three parts, which are sequentially initiation, phonation and articulation.

#### initiation

Initation is the production of the airstream that will constitute the produced sound.
The organ generating the airstream in initation is called the initiatior.
There are three initiators commonly used in human language, the diaphragm+ribs+lungs. the glottis, and the tongue.
Besides the three initators used in human speech, the cheeks may also be used, though no natural language does this, and the esophagus may be used in case of a laryngectomy.
diaphragm+ribs+lungs|pulmonic mechanism
glottis|glottalic mechanism
tongue|lingual/velaric mechanism
cheeks|buccal mechanism
esophagus|esophageal mechanism

There is also a category of consonants produced without any airstream mechanism, these are known as percussive consonants.

Any initiator may in theory act by increasing or decreasing pressure to generate an airstream.
In general, if an initiator increases the air pressure, the airflow will be outward, if an initiator decreases the air pressure, the airflow will be inward. 
An initiator increasing the pressure is termed egressive, an initiator decreasing the pressure is termed ingressive.
Outside of pulmonic consonants, to create an airflow, there needs to be two closures, one of which is released, producing sounds that are always obstruents.

The combination of the three common initiators plus egressive/ingressive produces six possible combinations. However, lingual/velaric egressive and pulmonic ingressive are not commonly used.

##### pulmonic

Pulmonic egressive initiation is the most common form of initiation, and 75% of languages, including indo-european languages, only feature speech sounds with pulmonic egressive initiation.

##### glottalic

In glottalic initiation, the glottis is moved, a closure is produced at the desired place of articulation, the glottis is moved again to create pressure, and then the closure is released.
For egressive glottalic initiation, the glottis is lowered, the closure is produced at the desired place of articulation, then the glottis is raised, building up pressure, and then the closure is released.
For ingressive glottalic initiation, the glottis is raised, the closure is produced at the desired place of articulation, then the glottis is lowered, building up suction (low pressure), and then the closure is released.
sounds produced by egressive glottalic initiation are called ejectives
sounds produced by ingressive glottalic initiation are called implosives
implosives are marked by the IPA via a right-facing hook on top, e.g. ［ɓ］ or ［ɗ］
implosives are marked by the IPA via ［ʼ］, e.g. ［qʼ］

Implosives are most often voiced oral stops, occasionally voiceless oral stops. 

##### velaric

In velaric/lingual (ingressive, egressive does not exist) initiation, a closure is produced at the velum, and then a second one at the desired place of articulation. the tongue's body is lowered, and thus suction is created. the frontmost closure is then released.
lingual aka velaric ingressive initiation produces sounds known as clicks.

⟮ʘ⟯|⟮Bilabial⟯
⟮ǀ⟯|⟮Dental⟯
⟮ǃ⟯|⟮(Post)alveolar⟯
⟮ǂ⟯|⟮Palatoalveolar⟯
⟮ǁ⟯|⟮Alveolar lateral⟯

Mnemonics/Rules

The alveolar click is the only one that uses a punctiation mark as an IPA symbol.


#### phonation

The laryngeal features are features that describe how the larynx is involved in speech production.
The three laryngeal distinctive features are [+/- voiced], [+/- aspirated AKA spread glottis], [+/- glottalized AKA constricted glottis]

Phonation is any state of the larynx that modifies the airstream.
Phonation may sometimes more narrowly refer to voicing.
Voicing is the part of phonation where the vocal cords/folds vibrate (or not).
Something voiced has the distinctive feature [+voice]
Something unvoiced or voiceless has the distinctive feature [-voice]
Something voiced becoming voiceless is known as devoicing.
Somehthing voiceless becoming voiced is known as voicing.
voicing|［◌̬］
devoicing|［◌̥］

Aspiration is a laryngeal phenomenon where the vocal folds remain open aka spread after a sound is produced.
For voicelessness, the glottis need to remain open, therefore the feature [+/- spread glottis] is sometimes used for aspirated consonants (and h) as well as voiceless things. Sometimes the distinctive feature of [+/- aspiration] is used instead, and narrowly for aspiration.
Aspiration is indicated in the ipa via ［◌ʰ］
Aspiration seems like a little burst of air to the speaker.
The burst of air for aspiration can be felt by putting ones hand in front of one's mouth while saying an aspirated thing.

Glottalization is the partial or complete closure or constriction of the glottis.
Glottalization as partial constriction results in creaky voice
Glottalization as total constriction produces the glottal stop, or a glottalic consonant if together with a different closure, in this case, it is acting as an initiator.
Glottalization as a laryngeal distinctive feature may be specified as [+/- glottalization or +/- constricted glottis]
glottal consonants have the glottis as their articulatior, in a sense.
There are two manners assoicated with glottal consonants, 'oral' stops and fricatives.
the glottal stop has [+glottalization] [-voice]
the voiceless glottal fricative has [-glottalization] [-voice]
And then there's the breathy-voiced glottal fricative

Creaky voice has [+constricted glottis].
Creaky voice is indicated in the IPA as ［◌̰］

Breathy voice is also called murmured voice.
During breathy voice the vocal folds vibrate, but allow more air to escape.
Breathy voice has [+spread glottis] [+voiced]
Breathy voice is indicated in the IPA as ［◌̤］.

#### articulation

Articulation is the shaping of airflow to get a sound.
An articulator is a feature within the vocal tract that is used for articulation.
An active articulator moves to create a speech sound, a passive articulator stays put.
Most often it is the combination of an active and a passive articulatior that performs articulation.

##### Liquids

rhotic consonants are r-like consonants.
Liquid consonants are a grouping of rhotic consonants and voice lateral appoximants.
Liquid consonants are grouped because they often behave similar phonotactically.

Which phoneme the japanese liquid is is completely unclear:
Most commonly it is sait to be a  apico-alveolar tap [ɾ] or an alveolar lateral approximant [l], less commonly various combinations of alveolar, postalveolar or retroflex lateral or non-lateral approximant, tap or stop.

##### Place of articulation

The place of articulation is where the obstruction between the articulators occurs.
While the glottis is often seen as a place of articulation, it is involved in phonation at the same time. 
The place of articulation is described by the place distinctive features.
The place of articulation is in theory described by two positions, the position of the passive and the active articulator, however, most active/passive combinations have their own names.

###### Passive place of articulation



The upper lip
The upper teeth, either on the edge of the teeth or inner surface 
The alveolar ridge, the gum line just behind the teeth
The back of the alveolar ridge
The hard palate on the roof of the mouth 
The soft palate further back on the roof of the mouth 
The uvula hanging down at the entrance to the throat
The throat itself, a.k.a. the pharynx
The epiglottis at the entrance to the windpipe, above the voice box
all uvular voiced sounds have small-caps IPA symbols
While pharyngeal and epiglottal sounds are sometimes distinguished, there seems to be no clear basis for distinction.
Sounds that have a h/H as an IPA symbol are either pharyngeal/epiglottal or glottal.

###### Active place of articulation

The active place of articulation is roughly divided into labial, coronal, dorsal, radical and laryngeal consonants.
Labial consonants are consonants articulated with the lower lip as the active articulator.
Coronal consonants are consonants articulated with the flexible front part of the tongue as the active articulator.
Coronal consonants are further sudivided into laminal, apical and subapical consonants
Laminal consonants are consonants articulated with the upper front surface of the tongue just behind the tip, called the blade of the tongue.
Apical consonants are consonants articulated with the absolute tip of the tongue.
Subapical consonants are consonants articulated with the underside of the tip of the tongue.
Dorsal consonants are consonants articulated with the body of the tongue as the active articulator.
Radical consonants are consonants articulated with the root/base of of the tongue as the active articulator.
A pharyngeal consonant is a consonant that is articulated primarily in the pharynx. Some phoneticians distinguish upper pharyngeal consonants, or "high" pharyngeals, pronounced by retracting the root of the tongue in the mid to upper pharynx, from (ary)epiglottal consonants, or "low" pharyngeals, which are articulated with the aryepiglottic folds against the epiglottis in the lower larynx, as well as from epiglotto-pharyngeal consonants, with both movements being combined.

marking a given sound as articulated with dental as its place of articulation   ［◌̪］
marking a given sound as laminal   ◌̻ (a square is lame)
marking a given sound as apical   ［◌̺］

##### mapping

While the term retroflex implies that the tongue is actually curled back so that it is subapical at the hard palate, in fact it is often merely apical postalveolar.
palato-alveolar also means the tongue is domed up
Dental or denti-alveolar consonants are often not distinguished from alveolar consonants, as the difference is often not contrastive/phonemic, and this larger group may also be called alveolar.
The larger grouping of alveolar including dental is what has unique IPA symbols - indicating a dental sound specifically must be diacriticised.

table:class=yesno;style=text-align:center;span=1,2;Active articulator →|span=1,3;Lower lip (Labial)|span=3;Coronal|span=1,3;Tongue body (Dorsal)|span=1,3;Tongue root (Radical)|span=1,3;Aryepiglottic folds.
span=1,2;Tongue blade (Laminal)|span=1,2;Tongue tip (Apical)|span=1,2;Underside of tongue (Subapical)
Passive articulator ↓
Upper lip|bilabial|span=2;linguolabial|class=no; |class=no;|class=no;|class=no;
Upper teeth|labiodental|class=no;|class=no;|class=no; |class=no;|class=no;|class=no;
Upper teeth|class="no";|span=2;dental|class=no; |class=no;|class=no;|class=no;
Upper teeth / alveolar ridge (prealveolar)|class="no";|denti-alveolar|class=no;|class=no; |class=no;|class=no;|class=no;
Alveolar ridge|class="no";|span=2;alveolar|class=no; |class=no;|class=no;|class=no;
Back of alveolar ridge (postalveolar)|class="no";|palato-alveolar|retroflex (more precisely: apical postalveolar)|class=no; |alveolo-palatal|class=no;|class=no;
Hard palate (front)|class="no";|class=no;|class=no;|retroflex (more precisely: true retroflex) |palatal|class=no;|class=no;
Soft palate / velum|class="no";|class=no;|class=no;|subapical velar |velar|class=no;|class=no;
Uvula|class="no";|class=no;|class=no;|class=no; |uvular|class=no;|class=no;
Pharynx|class="no";|class=no;|class=no;|class=no; |class=no;|pharyngeal|class=no;
Epiglottis|class="no";|class=no;|class=no;|class=no; |class=no;|class=no;|(ary-)epiglottal
Glottis|class="no";|class=no;|class=no;|class=no; |class=no;|class=no;|glottal

##### Manner of articulation

The manner of articulation is the configuration of articulators when producing a speech sound.
The manner of articulation is described by the manner distinctive features [+/- continuant], [+/- nasal], [+/- strident], [+/- lateral], [+/- delayed release], plus the major class distinctive features.

###### stops

While stop or occlusive may often refer to merely the oral variety, nore properly they refer to any consonant where the airflow is blocked in the vocal tract, but not necessarily in the nasal tract.
Oral occlusives/stops are occlusives/stops, but so are nasal stops, implosives, ejectives, click consonants and affricates to a certain extent.
In phonetics, liquids are a class of consonants consisting of voiced lateral approximants like /l/ together with rhotics like /r/
stops build up pressure, which needs to be released.
The opposite of a stop or occulusive is a continuant.
Whether something is a stop or continuant is indicated by the distinctive feature [+/- continuant]

###### lateral consonants

A lateral is a consonant in which the airstream proceeds along the sides of the tongue, but it is blocked by the tongue from going through the middle of the mouth. 
Whether something is lateral is described by the feature [+/- lateral]
Manners of consonants that can become lateral are fricatives/affricates, approximants, taps/flaps and clicks.

###### Nasals 

A nasal sound is one where velum is lowered to allow air to escape through the nose.
Whether a sound is nasal is indicated by the distinctive feature [+/-] nasal
To indicate a nasal sound for which there is no dedicated ipa letter, ［◌̃］ is used.
A nasal stop is a nasal sound where there is an oral occlusion as well.
Other nasal sounds are nasalized vowels as well as other non-stop nasal consonants.
A nasal is generally though misleadingly used as a term for a nasal stop/nasal occlusive.



While manner of articulation is typically only applied to consonants, the distinction between sonorants or obstruents also applies to vowels, which are sonorants.
Speech sounds are either sonorants or obstruents.
Whether something is a sonorant is indicated by the distinctive feature [+son(orant)]

###### Sonorants

A sonorant is a speech sound that is produced with continuous, non-turbulent airflow.
Sonorants that are not voiced are existant but rare.
Sonorants may be said to be made up of approximants in the wide sense and nasals.
Sonorants may be said to be made up of approximants in the narrow sense, vowels, and nasals.

###### Approximants

An approximant is a distinctive feature that encompasses all sonorants except nasals.
In a more narrow definition, approximants are speech sounds that involve the articulators approaching each other but not narrowly enough nor with enough articulatory precision to create turbulent airflow. 
Therefore, approximants fall between fricatives, which do produce a turbulent airstream, and vowels, which produce no turbulence.
Although "semivowel" and "approximant" are sometimes treated as synonymous, most authors use the term "semivowel" for a more restricted set; there is no universally agreed-upon definition, and the exact details may vary from author to author.
Not only are semivowels not syllabic, they are are also closer/a type of approximant.


##### vowels

Vowels are classified ⟮by the IPA⟯ by ⟮tongue height⟯, ⟮tongue backness⟯, and ⟮lip rounding⟯.
The IPA features *may* be encoded as the distinctive features [+/- high], [+/- back], [+/- round]/
The IPA chart for vowels supposedly shows the height and backness of (the highest point of) the tongue, but this is mostly not true, instead it really shows formant frequencies.
r-colored vowel = rhotic vowel = rhotacized vowel
On a physical level, rhotacization is the lowering of the frenquency of the third formant.
In american english, rs following vowels frequently only indicate the vowels rhotacization.
r-colored vowels are uncommon crosslinguistically, but common in two of the most widely-spoken languages: american english and mandarin chinese.
rhotatication is indicated ［◌˞］ or by a superscript turned r ［ʴ］
the vowel written ə is called schwa

###### monopthongs/dipthongs

Monopthong and dipthong are two kinds of vowels often distinguished.
A monopthong is a vowel sound that stays the same during its articulation = includes one vowel.
A dipthong is a vowel sound that changes between two vowels during articulation = includes two vowels.
A monopthong may be called a pure, a dipthong an impure vowels.
Since a dipthong changes from one vowel to another, it may also be called a glide.

###### IPA chart

table:|⟮c+;s1:10;Front⟯|⟮c+;s1:10;Central⟯|⟮c+;s1:10;Back⟯
type=th;⟮c+;s1:10;Close⟯| ⟮c+;s∞;us1:10;i⟯•⟮c+;s∞;us1:10;y⟯ |⟮c+;s∞;us1:10;ɨ⟯•⟮c+;s∞;us1:10;ʉ⟯ |⟮c+;s∞;us1:10;ɯ⟯•⟮c+;s∞;us1:10;u⟯
⟮c+;s1:10;Near-close⟯|⟮c+;s∞;us1:10;ɪ⟯•⟮c+;s∞;us1:10;ʏ⟯•⟮c+;s∞;us1:10;ʊ⟯
type=th;⟮c+;s1:10;Close-mid⟯|⟮c+;s∞;us1:10;e⟯•⟮c+;s∞;us1:10;ø⟯ |⟮c+;s∞;us1:10;ɘ⟯•⟮c+;s∞;us1:10;ɵ⟯ |⟮c+;s∞;us1:10;ɤ⟯•⟮c+;s∞;us1:10;o⟯
⟮c+;s1:10;Mid⟯| |⟮c+;s∞;us1:10;ə⟯
type=th;⟮c+;s1:10;Open-mid⟯|⟮c+;s∞;us1:10;ɛ⟯•⟮c+;s∞;us1:10;œ⟯|⟮c+;s∞;us1:10;ɜ⟯•⟮c+;s∞;us1:10;ɞ⟯|⟮c+;s∞;us1:10;ʌ⟯•⟮c+;s∞;us1:10;ɔ⟯
⟮c+;s1:10;Near-open⟯|⟮c+;s∞;us1:10;æ⟯•|⟮c+;s∞;us1:10;ɐ⟯
type=th;⟮c+;s1:10;Open⟯⟮c+;s∞;us1:10;a⟯•⟮c+;s∞;us1:10;ɶ⟯|⟮c+;s∞;us1:10;ä⟯•|⟮c+;s∞;us1:10;ɑ⟯•⟮c+;s∞;us1:10;ɒ⟯

Openness|Backness|Roundedness|IPA Symbol
⟮Close ⟯|⟮Back⟯|⟮Rounded⟯|⟮u⟯
⟮Close ⟯|⟮Back⟯|⟮Unrounded⟯|⟮ɯ⟯
⟮Close ⟯|⟮Central⟯|⟮Rounded⟯|⟮ʉ⟯
⟮Close ⟯|⟮Central⟯|⟮Unrounded⟯|⟮ɨ⟯
⟮Close ⟯|⟮Front⟯|⟮Rounded⟯|⟮y⟯
⟮Close-mid⟯|⟮Central⟯|⟮Unrounded⟯|⟮［ɘ］⟯
⟮Close-mid⟯|⟮Back⟯|⟮Rounded⟯|⟮o⟯
⟮Close-mid⟯|⟮Back⟯|⟮Unrounded⟯|⟮ɤ⟯
⟮Close-mid⟯|⟮Central⟯|⟮Rounded⟯|⟮ɵ⟯
⟮Close-mid⟯|⟮Front⟯|⟮Rounded⟯|⟮ø⟯
⟮Close-mid⟯|⟮Front⟯|⟮Unrounded⟯|⟮e⟯
⟮Close⟯|⟮Front⟯|⟮Unrounded⟯|⟮i⟯
⟮Open-mid⟯|⟮Back⟯|⟮Rounded⟯|⟮ɔ⟯
⟮Open-mid⟯|⟮Back⟯|⟮Unrounded⟯|⟮ʌ (not ^)⟯
⟮Open-mid⟯|⟮Central⟯|⟮Rounded⟯|⟮ɞ⟯
⟮Open-mid⟯|⟮Central⟯|⟮Unrounded⟯|⟮ɜ⟯
⟮Open-mid⟯|⟮Front⟯|⟮Rounded⟯|⟮œ⟯
⟮Open-mid⟯|⟮Front⟯|⟮Unrounded⟯|⟮ɛ⟯
⟮Open⟯|⟮Back⟯|⟮Rounded⟯|⟮ɒ⟯
⟮Open⟯|⟮Back⟯|⟮Unrounded⟯|⟮ɑ⟯
⟮Open⟯|⟮Front⟯|⟮Rounded⟯|⟮ɶ⟯
⟮Open⟯|⟮Front⟯|⟮Unrounded⟯|⟮a⟯
⟮Mid⟯|⟮central⟯|⟮both unrounded and rounded⟯|⟮ə (=Schwa)⟯
⟮Near-close⟯|⟮back (or near-back, debate exists)⟯|⟮rounded⟯|⟮ʊ⟯
⟮Near-close⟯|⟮front (or near-front, debate exists)⟯|⟮rounded ⟯|⟮ʏ⟯
⟮Near-close⟯|⟮front (or near-front, debate exists)⟯|⟮unrounded⟯|⟮ɪ (sm. cap. i, often w serifs)⟯
⟮Near-open⟯|⟮central⟯|⟮unrounded or rounded⟯|⟮ɐ⟯
⟮Near-open⟯|⟮front⟯|⟮unrounded (sometimes also rounded)⟯|⟮æ⟯


Near front near close vowel's IPA symbols are smallcaps versions of the front close ones.
For the IPA vowel chart, further down more open and further up more closed since it describes tngue height relative to the top of the mouth, at least in theory.
The unrounded version of the back closed vowel is double the u compared the rounded version of the back closed vowel.
the IPA vowels spelled wit oe/E ligatures are both front and both rounded.
ɶ is lower in the vowel chart than œ.
The rounded near-back near-close vowel looks like the ひ kana.

##### obstruents

An obstruent is a speech sound that is produced by obstructing airflow.
For obstruents, the vocal tract is either completely closed or closed enough to create turbulence.
All obstruents are consonants, but consonants may also be sonorants
Obstruents are either plosives,  fricatives or affricates.

###### oral occlusives

A plosive/oral occlusive/oral stop is an obstruent consonant in which an occlusion in the vocal tract is formed that stops all airflow.
Plosives are also called oral occlusives or oral stops.
While oral stop, plosive and oral occlusive are synonyms, the terms have different geneses: "Stop" refers to the airflow that is stopped. "Occlusive" refers to the articulation, which occludes (blocks) the vocal tract. "Plosive" refers to the release burst (plosion) of the consonant.
The term plosive may be seen as inappropriate for plosives without an audible release, these are soemtimes called appolosives.

Oral stops can be released in different ways:
no audible release|［◌̚］, e.g. ［p̚］
nasal release|superscript of the relevant nasal stop, e.g. ［◌ⁿ］
lateral release|［◌ˡ］
Oral stops/oral occlusives/plosives with no audible release release their occlusion with no audible burst.
Oral stops with nasal release release the stop into some sort of nasal stop
Oral stops with nasal release release the stop into some sort of lateral consonant



###### fricatives

A fricative are obstruent consonants produced by forcing air through a narrow channel made by placing two articulators close together.
The turulent airflow produced for the formation of fricatives is called frication.
Stridents are a subset of fricatives where additionally a stream of air is directed by the tongue towards the teeth, resulting in higher amplitude and pitch, sibilants are a further subset of these.
Stridency is encoded in the distinctive feature [+/- strident]

###### affricates

An affricate is an obstruent consonant that begins as a stop and releases as a fricative, generally with the same place of articulation.
Affricates in the IPA are indicated by two symbols united by a tie on top or more rarely at the bottom.
p͡f, t͡ɕ etc.
Affricates are distinguised from non-affricates in that they have the disinctive feature [+delayed release]

###### consonant IPA

table:class=yesno;place (active) →|span=4;Labial|span=8;Coronal|span=2;Dorsal|span=2;Dorsal (rarely coronal)|span=2;Dorsal|span=2;Radical/​Ary­epiglottal|span=2;Ary­epiglottal
Place (active + passive) →|span=2,2;Bi­labial|span=2,2;Labio­dental|span=6,2;Dental / Alveolar / Post­alveolar|span=2,2;Retro­flex|span=2,2;Palatal|span=2,2;Velar|span=2,2;Uvular|span=2,2;Pharyn­geal/​epi­glottal|span=2,2;Glottal
Manner ↓

type=th;Plosive|⟮p⟯|⟮b⟯|||span=3;⟮t⟯|span=3;⟮d⟯|⟮ʈ⟯|⟮ɖ⟯|⟮c⟯|⟮ɟ⟯|⟮k⟯|⟮ɡ⟯|⟮q⟯|⟮ɢ⟯|⟮ʡ⟯|class=no;|⟮ʔ⟯|class=no;
type=th;Nasal||⟮m⟯||⟮ɱ⟯|span=3;|span=3;⟮n⟯||⟮ɳ⟯||⟮ɲ⟯||⟮ŋ⟯||⟮ɴ⟯|class=no;|class=no;|class=no;|class=no;
type=th;Trill||⟮ʙ⟯|||span=3;|span=3;⟮r⟯|||||class=no;|class=no;||⟮ʀ⟯|⟮ʜ⟯|⟮ʢ⟯|class=no;|class=no;
type=th;Tap/flap|||||span=3;|span=3;⟮ɾ⟯||⟮ɽ⟯|||class=no;|class=no;|||||class=no;|class=no;
type=th;Lateral approximant|class=no;|class=no;|class=no;|class=no;|span=3;|span=3;⟮l⟯||⟮ɭ⟯||⟮ʎ⟯||⟮ʟ⟯|||class=no;|class=no;|class=no;|class=no;
type=th;Lateral fricative|class=no;|class=no;|class=no;|class=no;|span=3;⟮ɬ⟯|span=3;⟮ɮ⟯|||||||||class=no;|class=no;|class=no;|class=no;
type=th;Approximant||||⟮ʋ⟯|span=3;|span=3;⟮ɹ⟯|⟮ɻ⟯||⟮j⟯||⟮ɰ⟯||||class=no;|class=no;|
span=5;class=no;||type=th;span=2;Dental|type=th;span=2;Alveolar|type=th;span=2;Post­alveolar
type=th;Fricative|⟮ɸ⟯|⟮β⟯|⟮f⟯|⟮v⟯|⟮θ⟯|⟮ð⟯|⟮s⟯|⟮z⟯|⟮ʃ⟯|⟮ʒ⟯|⟮ʂ⟯|⟮ʐ⟯|⟮ç⟯|⟮ʝ⟯|⟮x⟯|⟮ɣ⟯|⟮χ⟯|⟮ʁ⟯|⟮ħ⟯|⟮ʕ⟯|⟮h⟯|⟮ɦ⟯


⟮ʍ⟯|⟮voice​less⟯|⟮labio​velar⟯|⟮approxi​mant⟯
⟮w ⟯|⟮voiced⟯|⟮labiovelar (labialized velar⟯)|⟮approximant ⟯
⟮ɕ⟯|⟮voiceless⟯|⟮aveolo-palatal⟯|⟮fricative⟯
⟮ɥ ⟯|⟮voiced⟯|⟮labio-palatal (=labialized palatal⟯)|⟮approximant ⟯
⟮ɺ (the long one⟯)|⟮voiced⟯|⟮alveolar⟯|⟮lateral tap/flap ⟯
⟮ʑ⟯|⟮voiced⟯|⟮aveolo-palatal⟯|⟮fricative⟯



all retroflex phones feature a right-facing bottom hook in their IPA symbol
all phones written with variants of the small h in the IPA are either epiglottal/pharyngeal or glottal, and are fricatives.

Both the velar and uvular voiceleess fricative are based in their IPA spelling on the x.
Uvular trill and fricative both feature variants of the smallcaps R as their IPA symbols.
phones with a c in their IPA symbol all have a passive place of articulation of palatal, and are voiceless.
In general, phones with greek IPA symbols are similar to phones with the same letter as a latin letter.

##### relative articulation

In phonetics and phonology, relative articulation is description of the manner and place of articulation of a speech sound relative to some reference point. 
Dimensions of relative articulation: advanced/retracted, raised/lowered, centralized/mid-centralized and more rarely advanced/retracted tongue root

An advanced or fronted sound is one that is pronounced farther to the front of the vocal tract than some reference point. 
a retracted or backed sound is one that is pronounced farther to the back of the vocal tract.
A raised sound is articulated with the active articulator raised higher than some reference point
A lowered sound is articulated with the active articulator lowered lower than some reference point
A centralized vowel is a vowel that is more central (front-back) than some point of reference.
Mid-centralized vowels are closer to the midpoint of the vowel space than their referent vowels. 
A sound with advanced or retracted tongue root has the base/root of the tongue move forward/backward, expanding/shringking the pharyngeal cavity.
A sound with retracted tongue root may also be seen as pharyngealized.

advanced|◌̟ or ◌˖
retracted|◌̠ or ◌˗
raised|◌̝  or ◌˔
lowered|◌̞ or ◌˕
centered|［◌̈］
mid-centralized|［◌̽］
Advanced Tongue Root   ［◌̘］
Retracted Tongue Root   ［◌̙］

### IPA

If there is no 'room' beneath an IPA symbol, you place a diacritic that would normally go there above instead.
For vowels, ［◌ˑ］ indicates a half-length vowel, while ［◌̆］ indicates an extra-short vowel.
For vowels and consonants both, ［◌ː］ indicates something that is longer, for consonants specifically it indicates gemination
Since they got their own diacritic at the 1989 kiel convention, extra-short vowels are ⟮happy⟯ ［◌̆］

# Semantics

Semantics is the field of linguistics that studies sememes.

## lexemes holding sememes

### lexical semantics

Lexical semantics is concerned with the relationships between lexemes and sememes

### semantic relations

lexical relations = semantic relations.
Semantic relations is concerned with how the sememes expressed by different lexemes relate to eeach other.
The most common types of semantic relations are those relating to sub/superset, to whole and part, to multiple meanings or to opposite meanings

#### same/opposite meaning (and related concepts)

name|meaning|pronunciation/spelling
synonyms|same|different
antonym (wide)|opposite|?
antonym (narrow)|opposite|different
auto-antonym|opposite|same
polyseme|different but related|same
homonym|different|same

homograph and homophone are hyponyms of homonym, distinguishing spelling and pronunciation.
Both homograph and homophone themselves exhibit polysemy: either pronunciation/spelling may be different or not, or must be.
A homograph is a word that means something different but is spelled the same, it may or must (depending on source) be pronounced differently.
A homophone is a word that means something different but is pronounced the same, it may or must (depending on source) be spelled differently.

A sense of a lexeme is one of the sememes it is associated with.
Senses of lexemes are related.
If one encounters two senses of the same lexeme that are unrelated, there are actually two unrelated lexemes which are homonyms.
Polysemy is the property of a lexeme of having multiple senses.

#### sub/superset

A hyponym is a more specific term than its hypernym.
A hypernym ⊃ a hyponym 
[⟮hypernym⟯ [⟮c;hyponym⟯
“Musical instrument” is a ⟮hyper(o)nym⟯ of “guitar” because a guitar is a musical instrument.
A hyponym that is the same word as its hypernym is ⟮An autohyponym⟯
A hypernym meant to be a hypernym for a specific set of terms|a cover term
A hypernym may also be called an umbrella term or a blanket term.

#### part/whole

A holonym denotes a whole.
A meronym denotes a part.
seatbelt is a meronym of (e.g.) car which is its holonym.
A holonym can be explained by listing its meronyms unless it is a gestalt.

## kinds of sememes

### concepts

#### concept hole

A »concept hole« is an uncommon term for the need of certain concept, but there not being a word for it.

## associations between sememe-containers and sememes

In semantics, mathematical logic and related disciplines, the principle of compositionality is the principle that the meaning of a complex expression is determined by the meanings of its constituent expressions and the rules used to combine them.


### indirect

#### metonym

A metonym is when something is referred to by the name of something closely associated with that thing.
Synechdoche is a form of metonymy where a part refers to a whole of something or a whole to one of its parts.
Pars pro toto is synechdoche where a part refers to a whole.
Individual body parts are often used to refer to an entire body, constituting a pars pro toto: "skin" or "hide" ("save your skin" or "skin in the game" or "the teacher will have my hide"), "mouth" ("mouth to feed"), "head" ("head count")
Totum pro parte is synechdoche where a whole refers to its part.
An example for a totum pro parte is the word America for the United States.

## Reference

### Deixis

What is a word/phrase/inflection that depends on its context to be (fully) understood is called  ⟮deictic⟯

#### vs. indexicality

Deixis and indexiciality refer to the same phenomenon, unless a given author distinguishes them.
Deixis is generally more commonly used in linguistics, and indexicality in philosophy.

#### types of deixis

Deixis exixts mainly in three domains: personal deixis (people involved), spatial deixis (locations involved), temporal deixis (the time involved), discourse deixis (parts of the discourse).

Would ☞you☜ like to have dinner?|personal deixis
She was sitting over ☞there☜.|spatial deixis
It is raining ☞now☜.|temporal deixis
I enjoy living in ☞this☜ city.|spatial deixis
☞I☜ am going to the movies.|personal deixis

##### spatial deixis

Spatial deixis often as two or three distances, rdepending on the language.
A language with two values for spatial deixis has the values proximal and distal.
For a language with two values for spatial deixis, proximal is close(r) to the speaker and distal is far/further from the speaker.
A language with three values for spatial deixis has the values proximal, medial, and distal.
For a language with three values for spatial deixis, proximal is close(r) to the speaker, medial is close to the adressee, and distal is far from both
Languages I know that have a three-way distinction in spatial deixis are japanese and spanish primarily, and english and german only archaically.

#### *phora

*phora is about the reference of an expression.
*phora is a form of deixis.

##### types of *phora

onion-box:[*phora [exophora][endophora [anaphora] [cataphora]]]


table:phora|reference depends on
Exophora|reference of expression depends on outside of the text
Endophora|reference of expression deptends on something in the text
Anaphora|form of endophora where referent depends on something before it
Cataphora|form of endophora where referent depends on something after it

##### endophora

In anaphora/cataphora, the thing its referent depends on is called an antecedent/postcedent respectively.
Most often, *phora is created by proforms.
Anaphora is sometimes also used as a synonym to endophora.
"She's the nobel prize winner, y'know." - If I say that and gesture to somone, "She" is exaphora.

###### binding

In linguistics, binding is the phenomenon in which endophoric elements such as pronouns are grammatically associated with their *ecedents.

## semantic relationships between multiple parts

### restriction

In semantics, a modifier is said to be restrictive if it restricts the reference of its head.
Relative clauses generally are restrictive.

## semantics and syntax

### Thematic/Semantic role

Semantic role aka thematic role aka theta role.
In the grammar taught in school grammatical relations and semantic roles are often conflated, but in fact these are orthogonal to each other.

Agent, patient, theme, instrument ... 
AGENT|volitional initiator|RAM broke the window with a stone
INSTRUMENT|Means of action|Ram broke the window with A STONE
PATIENT|undergoes action, changes state|Ram broke THE WINDOW with a stone.
THEME|undergoes action, does not change state


# Pragmatics

»⟮Pragmatics⟯« is the branch of ⟮＿linguistics＿⟯ that studies ⟮meaning⟯ ⟮beyond the literal semantic meaning of lexical units/constituents⟯.

## speech acts

»⟮Speech act theory⟯« is the branch of ⟮＿pragmatics＿⟯ studying ⟮＿speech acts＿⟯.
The idea of ⟮＿speech acts＿⟯ was coined by ⟮JL Austin⟯ in 『⟮How to Do Things with Words⟯』 (⟮1962⟯).
»⟮A speech act⟯« consists of ⟮＿locutionary＿, ＿illocutionary＿ and ＿perlocutionary＿⟯ ⟮act⟯.
The »⟮locutionary act⟯« is ⟮comprised of the expressing of the utterance (with all its phonological, syntactic and semantic aspects)⟯
the »⟮illocutionary act⟯« is ⟮what one does⟯ ⟮in saying something⟯.
the »⟮perlocutionary act⟯« is ⟮what one has done⟯ ⟮due to the consequences of saying something⟯.
the ⟮＿perlocutionary act＿⟯ ⟮depends of the reaction of the hearers⟯, ⟮c-;＿the illocutionary act＿⟯ ⟮does not⟯.
⟮Frightening⟯ is a ⟮＿perlocutionary＿⟯, not ⟮c_;＿an illocutionary act＿⟯ because ⟮it depends on the hearer to be frightened⟯.
a ⟮＿locutionary, illocutionary or perlocutionary＿⟯ ⟮＿act＿⟯ has ⟮c-;＿a locutionary, illocutionary or perlocutionary＿⟯ »⟮force⟯« attached.

## pragmeme

A pragmeme is a pragmatic act.
A pract is the combination of a certain utterance and a context that give rise to the pragmatic act.
Allopracts are all practs that result in the same pragmatic act.
Pragmatic act theory studies pragmemes.
Pragmatic act theory was developed by Mey starting around 2000.
Pragmatic act theory has become the standard sucessor theory to speech act theory. 
In relation to speech acts, the pragmatic act subsumes both illocutionary and perlocutionary act.
^it seems to me the point is that there is no such thing as a properly illocutionary act, since no pract may exist without context

## categorization

Austin distinguished 5 different types of illocutionary acts.
Austin's distinction of 5 types of illocutionary has been largely adopted by pragmatic act theory.
The 5 types of illocutionary/pragmatic acts are verdictive, commissive, exercitive, expositive, behabitives.


table:name|does|examples
»⟮verdictive⟯«|give a judgement
»⟮commissive⟯«|comitting oneself to a course of action|promising, betting
»⟮exercitive⟯«|exercising power/influence|excommunicating, resigning
»⟮expositivies⟯«|manage the flow/structure of discourse|postulating, defining
»⟮behabitives⟯«|regulating social relationships|toasting, apologizing

## lexical items that give rise to certain speech acts

### phatic expression

»⟮A phatic expression⟯« is ⟮a lexical unit/constituent⟯ ⟮devoid of⟯ ⟮semantic content⟯, but ⟮c-;expressing⟯ ⟮a ＿behabitive＿ ＿pragmatic act＿.⟯

### Discourse markers

»⟮A discourse marker⟯« is a ⟮different⟯ ⟮＿lexical unit＿⟯ which ⟮gives up its usual function⟯ to ⟮convey an ＿expositive＿ ＿pragmatic act＿ (managing the flow/structure of discourse).⟯

### backchanneling

»⟮A backchannel⟯« is ⟮an interjected response⟯ ⟮while another person is speaking.⟯
⟮＿Backchannels＿⟯ are often ⟮＿phatic expressions＿⟯.
Examples of ⟮＿backchannels＿⟯ in English are e.g. ⟮"yeah", "uh-huh", "hmm", and "right"⟯. 

Japanese backchannels are called 　相（あい）　槌（づち）.
　相（あい）　槌（づち） are quite common in japan.

### Hedge

»⟮a hedge⟯« is a lexical item or grammatical feature used to express the verdictive pragmatic act of expressing uncertainty.

## specific theories 

### Austins original constative/performative distinction

The original distincition Austin made before he arrived at speech acts was between ⟮constative and performative utterances⟯ utterances.
constative utterances (=constatives)|have a truth value, state a fact
performative utterances (=performatives)|do something else besides state a fact
In austins original distinction, the hereby criterion was used to determine if something was a performative.
An utterance is performative according to the hereby-criterion, if inserting the word hereby into the sentence ⟮Basically preserves the meaning⟯
「I promise to pay you 50$ tomorrow.」 is performative? ⟮c+;「I hereby promise to pay you 50$ tomorrow.」 → works → performative⟯
「The cat is on the mat.」 is not performative?  「The cat is hereby on the mat.」 → has changed the meaning → not performative (constative)
Problematically for austins original distinction, a sentence can both performative and constative.
Later, austin moved to a distinction between locutionary, illocutionary and perlocutionary speech acts.


### gricean implicature

Implicature is a term introduced by Grice which is whatever a person implied/meant by saying something else.
in the linguistic field of pragmatics, an ⟮inference⟯ (generally an ⟮implicature⟯) is said to be ⟮defeasible⟯ or ⟮cancellable⟯ if ⟮it can be made to disappear (e.g. by saying something contradictory⟯.
According to grice, implicatures may be conventional or nonconventional.

#### conventional

conventional implicatures are what a sentence entails due ot the conventional meaning of the words involved in the sentence, some people have argued these are merely entailments.
Grice: the conventional implicature of "The die is green and heavy" is "The die is green" (as well as "The die is heavy")

#### nonconventional

A nonconventional implicature is an implicature which is not conventional.
the type of nonconventional implicatures that Grice elaborates on is conversational implicature.

##### conversational

CP = Cooperative Principle
Conversational implicatures are generated by the cooperative principle.
CP: "Make your conversational contribution such as is required, at the stage at which it occurs, by the accepted purpose or direction of the talk exchange in which you are engaged."

###### generation via the CP

Conversational implicatures are generated when the speaker is presumed to be observing the CP and its maxims, and yet they have said something that seems to be violating the CP.
The generation of implicatures may take 3 forms:
1. supposition of implicature makes statement actually consistent with the CP, even though it did not seem so at first.
2. If the CP wouldn't have been violated by violating the Maxim M1, the maxim M2 would have been. Ergo we may deduce IMPLICATURE and are consistent with the CP
3. the thing the person is saying could not possibly be consistent with the CP, ergo we can assume something completely different as an implicature and be consistent with the CP again (flouting)

Via grice's definition, violating the CP at the level of what was said is necessary to conversationally implicate.
However one can also violate the CP but not generate true conv. implicatures: either in a way that indicates one is opting out of the CP completely (= cancellability), or without indicating that one is doing violating it, and thus (since the person still goes through the working-out schema) probably mislead the listener.

###### grice's razor

grice's razor is the motivation for positing conversational implicatures rather than additional senses or different entities.
Grice's razor: ceteris paribus it is better to postulate conversational implicatures rather than senses (or different entities) because they can be derived from independently motivated psychosocial principles.

###### maxims

To make the conversational contribution such as is required [...], Grice suggests the four Maxims.
The four maxims (and component submaxims) that Grice presents as governing cooperativeness are the maxims of 
Quantity (Make your contribution as informative as required), 
Quality (Try to make your contribution one that is true); Submaxims: 
  1) Do not say what you believe to be false
  2) Do not say that for which you lack adequate evidence
Relation (Be relevant)
Manner (Be perspicous)
  1) Avoid obscurity
  2) Avoid ambiguity
  3) Be brief
  4) Be orderly
Grice does admit that there might be other maxims (e.g. politeness) besides his four at work when talking, but says they are not relevant for generating implicatures to the same extent/in the same way
⊐⊐ is sometimes used as "is predicted as an implicature by the CP and its maxims"
⊐ is used e.g. by Davis as "implicates"

####### quantity

A ⟮quantity implicature⟯ is often seen as a synonym with ⟮scalar implicature⟯, but may more properly be ⟮a blanket/umbrella term⟯ for ⟮all implicatures generated using the maxim of quantity⟯, including ⟮clausal implicatures⟯.
A scalar implicature is where a less informative statement implicates the deinial of a more informative statement.
Scalar implicatuers are explained by grice via the violation of the maxim of quantity, and thus the supposion of the implicature is necessary to make it consistent with the CP.

######## implicational scale

In the context of ⟮pragmatics⟯, ⟮Implicational scale⟯ has a somewhat different meaning, referring to ⟮the scales⟯ from ⟮weaker to stronger⟯ statements that are used in ⟮quantity implicatures⟯
```lang=text;
{all, most, many, some}
{always, often, sometimes}
{succeed in, try to, want to}
{certain, probable, possible}
```


# linguistics and the mind

Cogntivie linguistics is a field that studies how the things we know about the brain/mind generally give rise to human language. 
Thus cognitive linguistis would reject the claim that language is a separate faculty of the brain.
Psycholinguistics is a field that studies how the brain allows us to do language-related tasks such as language aquisition, comprehension, production.

## Cognitive linguistics

### conceptual metaphor

The idea of conceptual metaphor was coined by Lakoff ＆ Johnson in their seminal book Metaphors We Live By (1980)

A conceptual metaphor is a metaphor where one thing is understood in terms of another.
A structural metaphor is a metaphor that structures one thing in terms of another.
Conceptual metaphors are structural metaphors.
A mapping is a single conceptual/structural metaphor.
A mapping consists of a source domain, a target domain, and a set of correspondences between the domains.
e.g. Love is the target domain, a journey is the source domain
The set of correspondences of a mapping represents the structure that structural metaphor is referring to.
A correspondence is a equivalence between one element of the target domain and one element of the source domain.
e.g. for LOVE IS A JOURNEY, the lovers are travelers, the relationship is the vehicle, the lovers common goals are destinations on the journey.
Within a mapping, new correspondences may be created ad hoc, e.g. for stylistic effect.
A mapping is conventionally indicated as TARGET IS SOURCE.
The target domain is only partially structured in terms of the source domain.
The target domain only being partially structured in terms of the source domain means that only some attributes of the source domain carry over to the target domain.
Since the target domain is only partially structured in terms of the source domain, any conceptual/structural metaphor also hides/obscures things.
To Lakoff ＆ Johnson, all our conceptual system is based on conceptual metaphor.

### linguistic relativity

»⟮Linguistic relativity⟯« is the idea that ⟮the structure of language⟯ ⟮affects⟯ ⟮the speakers cognition⟯.
⟮＿linguistic relativity＿⟯ exists in ⟮a strong⟯ and ⟮c_;a weak⟯ ⟮c_;version⟯.
The ⟮strong⟯ version of ⟮＿linguistic relativity＿⟯ says the relationship between language structure and thought is one of ⟮determination⟯.
The ⟮weak⟯ version of ⟮＿linguistic relativity＿⟯ says the relationship between language structure and thought is one of ⟮influence⟯.
⟮＿linguistic relativity＿⟯ is more ⟮commonly⟯ but ⟮c_;misleadingly⟯ called the ⟮「sapir-whorf hypothesis」⟯.
The ⟮「sapir-whorf hypothesis」⟯ is misleading because ⟮sapir⟯ ⟮did not endorse it much at all⟯, and ⟮c-;whorf⟯ ⟮was not the first to endorse it⟯
⟮the strong version of⟯ ⟮＿linguistic relativity＿⟯ is also called ⟮linguistic determinism⟯

# diachronic

A »diachronic« approach considers the history and evolution of a language.
Historical linguistics is mainly interested in language change.

## language geneaology

* marks a form that is reconstructed (i.e. not attested)
A Sprachbund is a set of geographically contiguous languages ⟮that are more similar to each other in their structure than would be expected on the basis on their degree of genealogical relatedness⟯
A sprachbund may also be called a linguistic area.
The languages in a sprachbund may or may not be related (but if they are related, the similarity must be stronger than the relatedness would predict)
SAE (Standard Average European) is a sprachbund of extensive common features in europe.
euroversal is a feature that exists in (almost) all SAE languages
Germanic, Romance, Baltic, Slavic, Finno-Ugric languages as well as albanian and greek are the languages normally classifed under which group?  SAE
An ⟮areal feature⟯ is an element that is shared by languages in ⟮a geographic area⟯ (but not explainable by ⟮a common ancestor language⟯)

### cognates

Cognates are 2 or more words that have a common etymological origin.
Cognates often but not always have a similar meaning and a similar pronunciation.
False friends are words in different languages that look/sound similar and thus give off the impression of being cognates, but are unrelated.
Cognates in the same language are called doublets.

### comparative linguistics

Comparative linguistics is a branch of historical linguistics that compares language to establish how they are related
Mutualll intelligibility is whether two speakers of different lects can understand each other ⟮Without prior familiarity / special effort⟯
The higher th elinguistic distance, the lower the mutual intelligibility.

### language families

#### IE

Indo-European languages descend from Proto-Indo-European (PIE)
⟮Indo-European languages⟯ can be most basically divided into ⟮centum languages⟯ and ⟮satem languages⟯.
The ⟮Germanic languages⟯ are subdivided into ⟮east germanic languages⟯, ⟮north germanic languages⟯, and ⟮west germanic languages⟯.

#### Altaic

Most linguists consider altaic to be a sprachbund, some consider it to be a language family.
The grouping of ⟮Altaic⟯ languages (whether as a sprachbund or a language family) usually includes at least ⟮Turkic⟯, ⟮Mongolic⟯, and ⟮Tongusic⟯ (this smaller grouping is sometimes called '⟮Micro⟯-⟮altaic⟯')
⟮Macro⟯-altaic as a ({c4::very fringe}}) hypothesis also includes ⟮japonic⟯ and ⟮koreanic⟯

## language change

### sound change

Sound change is the diachronic change of sounds over time.
Sound change may be to the distribution of phonemes (phonetic change) or to which speech sounds exist (phonological change).

Forms of sound change:


### semantic change

Semantic change is the diachronic chanage of meanings of a given lexical item over time.
there are ⟮many different types⟯ of ⟮Semantic⟯ ⟮change⟯/⟮shift⟯/⟮drift⟯ (= ⟮the change of the meanings of words over time⟯ (the exact amount of which depends on ⟮which classification scheme you follow⟯).
Common types of ⟮Semantic⟯ ⟮change⟯/⟮shift⟯/⟮drift⟯ are ⟮semantic narrowing⟯ (also called ⟮specialization⟯), ⟮semantic widening⟯ (also called ⟮generalization⟯), ⟮amelioration/elevation⟯, ⟮pejoration⟯

#### types

⟮pejoration⟯/⟮degeneration⟯ is a form of ⟮Semantic⟯ ⟮change⟯/⟮shift⟯/⟮drift⟯ (= ⟮the change of the meanings of words over time⟯) where ⟮a word becomes more negative in meaning⟯
⟮villain⟯ used to mean ⟮serf, peasant⟯ - this is an example of ⟮perjoration/degeneration⟯
⟮knave⟯ used to mean ⟮boy, child, servant⟯ - this is an example of ⟮perjoration/degeneration⟯

⟮amelioration⟯/⟮elevation⟯ is a form of ⟮Semantic⟯ ⟮change⟯/⟮shift⟯/⟮drift⟯ (= ⟮the change of the meanings of words over time⟯) where ⟮a word becomes more positive in meaning⟯
⟮pretty⟯ used to mean ⟮tricky, crafty, sly⟯ - this is an example of ⟮amelioration/elevation⟯
⟮Knight⟯ used to mean ⟮boy, servant⟯ (thus cognate with german ⟮knecht⟯)- this is an example of ⟮amelioration/elevation⟯

⟮Semantic widening⟯ aka ⟮generalization⟯ is a form of ⟮Semantic⟯ ⟮change⟯/⟮shift⟯/⟮drift⟯ (= ⟮the change of the meanings of words over time⟯) where ⟮a word becomes more general/less narrow in its meaning⟯ (often, ⟮it takes on a meaning of one of its hypernyms⟯)
⟮bird⟯ used to mean ⟮young bird, chick⟯ - this is an example of ⟮semantic widening / generalization⟯
⟮assassin⟯ used to mean ⟮a member of the assassins chilling in the holy land⟯ - this is an example of ⟮semantic widening / generalization⟯

⟮Semantic narrowing⟯ aka ⟮specialization⟯ is a form of ⟮Semantic⟯ ⟮change⟯/⟮shift⟯/⟮drift⟯ (= ⟮the change of the meanings of words over time⟯) where ⟮a word becomes less general/more narrow in its meaning⟯ (often, ⟮it takes on a meaning of one of its hyponyms⟯)
⟮to starve⟯ used to mean ⟮to die⟯ (and thus is cognate with german ⟮sterben⟯) - this is an example of ⟮semantic narrowing / specialization⟯
⟮Wife⟯ used to primarily mean ⟮woman (of any sort)⟯ - this is an example of ⟮semantic narrowing / specialization⟯
⟮Meat⟯ used to refer to ⟮any food⟯ - this is an example of ⟮semantic narrowing / specialization⟯
⟮Deer⟯ used to refer to ⟮all (esp. quadrupedal mammals) animals⟯ (and thus is cognate with german ⟮Tier⟯) - this is an example of ⟮semantic narrowing / specialization⟯



### language contact

Language contact is when two or more languages influence each other.
The field that studies language contact is contact linguistics.
Language convergence is a type of linguistic change in which languages come to structurally resemble one another ⟮due to prolonged language contact⟯
In a language shift, a speech community switches to a different language.

#### dialects

Dialect levelling is the process of overall reduction in the distinctive features of a dialect towards ⟮(more similarity with) the standard language⟯
Since the industrial revolution, dialect levelling has been ocurring to most languages.
an aphorism sometimes applied to indicate that the difference between language and "mere dialect" is the embrace by state power: A language is a dialect with an army and navy

#### borrowing

Borrowing is a process within contact linguistics = language contact.
AN element that seems to be a borrowing but isn't is called a pseudo-loan/pseudo-borrowing/false borrowing.
borrowing is the cover term for any kind of loan element.
narrative word|not a borrwoing
donor language|the language from which the word was borrowed
recipient language   the language into which the word was borrowed
⟮Categorization⟯ of the loan-related terminology is ⟮hard⟯, as ⟮seemingly everyone uses their own, only slightly different categorization system⟯
While I use ⟮borrowing⟯ to mean ⟮any sort of loaned thing⟯, the term is ⟮not always used in exactly this manner⟯
A foreign word|A word from another language used in the relevant language, but not integrated, that is, recognizably foregin|Gestalt, Pickelhaube, mutatis mutandis (in english)
A loanword is a word loaned from another language which is recognizably now part of the recipient language

While a ⟮loan translation⟯ / ⟮calque⟯ ⟮translates all the parts exactly⟯, a ⟮loan rendition/rendering⟯ ⟮only uses approximate translation⟯
「ça va sans dire」 → 「it goes without saying」 
⟮A calque (sometimes also loan translation)⟯ is a word or phrase borrowed from another language by literal word-for-word or root-for-root translation.
While weekend → ⟮Wochenende⟯ is a ⟮loan translation⟯, skyscraper → ⟮Wolkenkratzer⟯ is a ⟮loan rendition/rendering⟯

⟮Loan creation⟯ is a bit of a vague term, but basically means ⟮creation of a word⟯ using ⟮native means⟯, either to ⟮fill a lack in the language which another language does not have⟯ or to ⟮replace a borrowing⟯

⟮Loanblends⟯ can either be formed by ⟮word with some semantic content⟯ + ⟮some functional affix (of the recipient language)⟯ or ⟮fusion of multiple words with semantic content⟯. 
If loanblends are formed by  ⟮word with some semantic content⟯ + ⟮some functional affix (of the recipient language)⟯, they are seen to be ⟮closer to loan words⟯, if they are formed by ⟮fusion of multiple words with semantic content⟯ they are seen to be ⟮closer to loan translations/renditions (= loan formations)⟯

⟮loan formation⟯ is a term usually used to group ⟮any borrowing that uses foregin structure⟯ (i.e. ⟮loan translations⟯ and ⟮renditions⟯, and depending on how you see them ⟮loan creations⟯ as well), but ⟮by far not by every author⟯

A Semantic loan is when a word exists in two languages, but only has some senses in one language, and then aquires the senses that the other language has.
realize (make happen, become aware of) / realisieren (make happen) → realize (make happen, become aware of) / realisieren (make happen, become aware of)


onion-box:
Types of borrowings
  senses are added
    semantic loan
  words/morphemes are added
    words/morphemes are directly borrowed
      foregin words, loanwords, (loanblends)
    morphological transformation is done
      part of the morphemes are native
        (loanblends)
      all of the morphemes are native
        the structure is native|the structure is foreign
          loan creation
          loan translation, loan rendition


A learned borrowing is a planned, purposeful borrowing, esp. from a classical language.

### Language death

A language with at least one native speaker|living language
A language without any *native* speakers|dead language
A language without *any* speakers|extinct language
Speakers choosing to abandon a language and it thus dying|language/linguisitic suicide
Causing languages to die out|linguicide

## English

Old English starts with the anglo-saxon setters/invaders in the 5th century, and ends with the norman conquest 1066 and more seriously by 1150, when middle english begins. 
Middle english lasts until the begin of the tudor era in the late 15th century, when early modern english begiins.
Early modern english lasts until the late 17th century, until the end of the reign of Charles II.
Early modern english is the language of Shakespeare and the King's BIble.


William Caxton: 1422 - 1491
William Caxton introduced the printing press to england.

## etymology

# discourse analysis

⟮Discourse analysis⟯ is the study of ⟮real language use⟯, in units ⟮larger than the sentence⟯
⟮Critical discourse analysis⟯ may be thought of ⟮discourse analysis⟯ via / for use of ⟮critical theory (lowercase)⟯


# multilingualism

A language that a speaker speaks is either a L1, L2, or heritage language.

L1|first language = native language
L2|second language

A majority language is a language spoken by the majority of the population of an entity.
A minority language is a language spoken by a minority of the population of an entity.

A target language is a language being learnt or translated into.
A source language is a langugage from which one is translating.

## multilingualism within speakers

SLA

### bi/multilingualism

⟮Bilingualism⟯ is ⟮The ability to speak two languages (or the state of being in two langauges)⟯
⟮Multilingualism⟯ is ⟮The ability to speak multiple language (or the state of being in multiple langauges)⟯
Bi/multilingualism from birth   Simultaneous bi/multilingualism
Bi/multilingualism by learning a second language later   Sequential bi/multilingualism

### language transfer

Language transfer is the application of linguistic features from one language to another by ⟮a bilingual or multilingual speaker⟯, or to say it differently, two languages influencing each other within a speaker.
CLI (crosslinguistic influence) is roughly synonymous to language transfer.
negative language transfer is language transfer that results in errors
positive language transfer is language transfer that results in easier language learning.
While language transfer/cli is two languages influencing each other within a speaker, language contact is two languages themselves influencing each other.


### SLA



#### Heritage language

A heritage language is the former native language of a speaker that ends up being lost or underdeveloped due to another language, generally a majority language, being dominant.
People may have varying degrees of fluency in their heritage language.

#### Interlanguage

An interlanguage is an idiolect that has been developed by a learner of a second language (or L2) which preserves some features of their first language (or L1) and/or overgeneralizes/misuses some L2 writing and speaking rules. 
When an interlanguage ceases becoming similar to the L2, it has fossilized.

### Attrition

Language attrition is split up into first-language attrition and second-language attrition
The process of losing language skills in a language   Language attritionThe process of losing language skills in a ⁑second⁑ language  Second-language attrition
The process of losing language skills in a ⁑native⁑ language  First language attrition

## languages for multilingual situations

A koine is a standard language or lingua franca created by the contact of ⟮c+;Two or more mutually intelligible languages ⟯

### auxiliary languages

international auxiliary language and auxiliary language are synonyms.
IALs are languages meant for communication between people who do not share a first language.
Conlang IALs (which is all IALs unless we include lingua franca) are mainly used to avoide linguistic dominance.
IALs may also be called auxlangs.
IALs (international ausiliary languages) may include or exclude natural languages that are lingua franca.
Besides the case of natural languages that are lingua franca, IALs are constructed languages.
Interlingua is a naturalistic IAL that takes its grammar and vocab mainly from the romance languages.
interlingua aims to be comprehensible to romance language native speakers without having learned it.
Interlingua is enabled in part by the existence of SAE.

### lingua franca

A lingua franca is a  lect that is used to communicate by groups who don't share a native language.

## Language birth

A pidgin is a grammatically simplified means of communication that develops between two or more groups that do not have a language in common.
Pidgins often develop in trade situations.
Pidgins usually have a limited vocabulary and low presstige.
A pidgin is never spoken as a native language. 
The traditional view (has criticisms) is that a pidgin that is nativized becomes a creole.
A language gaining native speakers (from 0 to › 0) is known as nativization.
A mixed language is a language combining aspects of two or more languages but ⟮c+;not clearly deriving primarily from any single language ⟯

Relexification is the process of replacing (all or a large number of) the words of one language with the words from another language, while the grammar of the original language remains intact

### conlangs

Languages are either natural or constructed.
A conlang (constructed language) is one which was constructed by humans.
A natural language is one that has evolved naturally through human use.
To an overwhelming extent, the languages that are spoken in the 21st century are natural languages.

Naturalistic conlangs mimic existing real languages.

## multilingual linguistics

### translingualism

Translingual phenomena are features of language that are relevant in more than one language. 
The International scientific vocabulary is the set fo science-related words that is  ⟮used translingually⟯

## rendering between representations/languages

### translation

Translation is the rendering of the meaning of a source language text in a target language text.

### transcription

Transcription is the represention of spoken language in written form.

### glossing

## misc

A pillow dictionary is a romantic partner that teaches you a foreign langauge.

### sprachraum

»⟮A sprachraum⟯« is⟮ a geographical region⟯ ⟮where a common L1 is spoken⟯

# linguistic typology

Linguistic typology = language typology
Linguistic typology is a field of linguistics that studies and classifies languages according to their structural features. 

## morphological typology 

Linguistic typology according to a language's morphological structures and mainly how these languages create words from morphemes is known as morphological typology.
The main distinction within morphological typology is the spectrum between analytic languages and synthetic languages.
Analytic languages contain very little inflection, and thus have very few morphemes per word (often close to one morpheme per word)
Synthetic languages contain a lot of inflection and thus have many morphemes per word.
Synthetic languages can be subdivided into (among others) agglutinative and fusional languages.
fusional languages merge many different inflectional categories into the same morpheme.
analytic languages have different morphemes for different inflectional categories and glue those together.
highly analytic|chinese, vietnamese
highly synthetic|japanese, turkish

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

A linguistic universal is a pattern that occurs systematically across (most often all) natural languages.

# theoretical linguistics

Theoretical linguistics may just contrast with applied linguistics, or specifically be the area of linguistics that answers fundamental questions about the nature of language

# formal language

## chomsky hierarchy

The chomsky hierarch describes a hierarchy of formal grammars.


onion-box:
recursively enumerable
  context-sensitive
    context-free
      regular

## metalanguage

A »metalanguage« is a language used ⟮to describe another language⟯
The language being described by a metalanguage is an object language.
Metasyntax is the syntax governing a meta-language.
A placeholder/variable that is not part of a given language, but instead is used in a metalanguage way is known as a metasyntactic variable.
The most common metasyntactic variables are foo, bar, quuz...

### BNF

BNF = Backus-Naur-Form
BNF is a metasyntax for context-free grammars.

metacharacter/construct|BNF meaning
definition   ::=
alternation   |
terminal (in this case with the name something)   "something" or 'something'
non-terminal (in this case with the name something)   ‹something›
concatenation   ␣

#### EBNF

EBNF = Extended Backus-Naur-Form
EBNF is an extension (with some changes) to BNF, but there is no one EBNF, but a bunch of dialects.

Possible ENBF syntax conventions:

[]|optional
{}|0 or more repetions
bar|alternation
= or : or ::=|definition
; or ø|end of production rule
()|grouping
␣ or , or ø|concatenation
barbar|'at least one of'

In ENBF dialects, usually either the terminals are quoted and the nonterminals are written as is, the terminals are unquoted and the nonterminals are indicated as ‹something›, or both are explicitly indicated

#### ABNF

ABNF is standartized in an RFC, and often used for IETF documents.
in ABNF, rules MAY be surrounded by ‹›.
in ABNF, rules and terminals are are case-insensitve
abnf-terminal ::= "{‹characters›}"|‹abnf-terminal-range›|‹abnf-terminal-numeric›
abnf-terminal-range ::= ‹abnf-base-specifier›‹abnf-character-digits›-‹abnf-character-digits›
abnf-terminal-numeric ::= ‹abnf-base-specifier›‹abnf-character-digits›{.‹abnf-character-digits›}
abnf-character-digits ::= ‹digit›{‹digit›}
abnf-base-specifier ::= %‹base-char›
base-char ::= b|d|x

abnf-rule ::= rule = ‹definition› [; ‹comment›]‹CRLF›

‹n›*‹m›‹rule›|repetitions from n to m (where leaving out either is infinity)
‹n›‹rule›|repetitions of n times
()|group
/|alternation

=/|add alternatives to previous rule
whitespace|concatenation
; foo| a comment foo
[]|optional

for ABNF repetition, leaving out ‹n› or ‹m› implies 0 or infinity as per usual

predefined rules
LWSP = 	*(WSP / CRLF WSP)
WSP = SP / HTAB	
DIGIT = a digit 0 - 9
ALPHA|upper/lowercase ascii char
DIGIT|deximal digits
VCHAR|an ascii visible char

### RFC 2119

RFC 2119 = BCP 14
RFC 2119 / BCP 14 defines a set of terms to indicate requirement levels.

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in RFC 2119. indicates that RFC 2119 is being followed.
when using RFC 2119, the words such as must are often allcaps.

MUST = REQUIRED = SHALL
MUST/REQUIRED/SHALL = absolute requirement of the specification
MUST NOT = SHALL NOT
MUST NOT/SHALL NOT = absolute prohibition of the specification
SHOULD = RECOMMENDED
SHOULD/RECOMMENDED = may exist valid reasons to ignore the thing, but full implications should be considered and carefully weighed beforehand
SHOULD NOT = NOT RECOMMENDED
SHOULD NOT/NOT RECOMMENDED = may exist valid reasons where behavior is acceptable or even useful, but full implications should be considered and carefully weighed beforehand
MAY = OPTIONAL
MAY/OPTIONAL = truly optional. however, An implementation which does not include a particular option MUST be prepared to interoperate with another implementation which does include the option, though perhaps with reduced functionality. In the same vein an implementation which does include a particular option MUST be prepared to interoperate with another implementation which does not include the option (except, of course, for the feature the option provides.)

# fundamental concepts

## units

### emic/etic

»⟮An emic unit⟯« is ⟮an abstract unit⟯ of ⟮a number of⟯ ⟮variant forms⟯.
»⟮An etic unit⟯« is ⟮a variant form⟯ of ⟮＿an emic unit＿⟯.
⟮Various types of⟯ ⟮＿emic/etic units＿⟯ exists for ⟮different fields/concerns⟯.
⟮＿Emic units＿⟯ carry ⟮the name of ＿the etic unit＿⟯, ⟮suffixed with -eme⟯.
⟮＿Etic units＿⟯ of ⟮the same ＿emic units＿⟯ are ⟮allo-⟯.


table:emic unit|etic unit-
⟮phoneme⟯|⟮phone⟯
⟮morpheme⟯|⟮morph⟯
⟮grapheme⟯|⟮glyph⟯
⟮phraseme⟯|⟮phrase⟯
⟮sememe⟯|⟮seme⟯
⟮pragmeme⟯|⟮pract⟯
⟮lingueme⟯|⟮ling⟯
⟮grammeme⟯|⟮gram⟯
⟮lexical unit/lexeme⟯|⟮lex⟯

### things

»⟮A linguistic unit⟯« is ⟮a generic name⟯ for ⟮an element⟯ which ⟮forms a sequence with others of its kind⟯.
^A linguistic unit may be e.g. phoneme, morpheme, phraseme, grapheme, syllable...
»⟮A segment⟯« is ⟮＿a linguistic unit＿⟯ of which ⟮we're not sure which linguistic unit it is⟯, or ⟮for which it is irrelevant⟯.
»⟮A lingueme⟯« is ⟮any linguistic emic unit⟯ which can be independently learned and transmitted.
A linguistic item is any linguistic thing under analysis

### feature

A feature is a binary value.
A feature is indicated by [‹name›].
A feature's states are indicated by [+ ‹name›] and [- ‹name›]
Most commonly, an etic unit can be further analyzed into multiple features.

### sequences

A string is most commonly assumed to be a string of words, but may also be a synonym for sequence.
A sequence of linguistic units is a series of these linguistic units with no claim as to compositionality.

## ways things can exist

### markedness

According to Haspelmath (2005), markedness has 12 distinctive senses, which makes it pretty hard to use unambiguously.
Most but not all senses of markedness share a feeling of oddness, and the marked form is generally more rare.
In semantics, a marked term is generally also more specific.
In a morphosemantic sense, something coded through a zero morpheme is unmarked, something coded by a non-zero morpheme is marked.

### implicational scale

flex-container:✫mplicational-scale-of-basic-color-terms.png✫✫sm_2021-10-21--08-21-02-screenshot.jpg✫


⟮Implicational scale⟯ is a term that means if ⟮one feature is present⟯, ⟮all the features⟯ ⟮lower on the scale⟯ ⟮will be as well⟯
If a thing is on an ⟮implicational scale⟯, and we find that ⟮the e.g. 5th stage is present⟯, we would expect to also find ⟮all four lower stages to be present⟯.
⟮Most linguistic areas⟯ have things that can be on an implicational scale

## structuralism

### history

Course in General Linguistics is a book by de Sassure and was published in 1916
⟮De Sassure⟯ founded ⟮structuralism⟯ in the book Course in General Linguistics.
Structuralism lies at the base of emic units and thus of linguistics.
Outside of linguistics, structuralism had its heyday in ⟮the 1950s and 1960s⟯ in ⟮France⟯ (but is still influential) 

### signs

#### semiotics

semiosis is activity/process involving signs is called 
semiotics is the study of semiosis

### the sign

The sign consists of the connection between a signfier and a signified.
I will define sign component as a cover term for either sign, signifer and signified.
A sign component gains its meaning by contrast with all other of the same type of sign component.

So, the meaning of the signifier ⟮horse⟯ is ¬{x ∈ S⎵signifier⎵ | x ≠ horse}
In structuralism, the masses of possible signifiers and possible signifieds starts out as an amorphous masses.
In structuralism, the heretofore ⟮amourphous masses of possible signfiers and possible signifieds⟯ are carved up into a set of possible signifiers and possible signifieds. 
The ⟮sign⟯ is ⟮arbitrary⟯ because ⟮any signified⟯ ⟮could have been signified by a different signifier⟯. 
Since the ⟮sign⟯ consists of ⟮the two parts of signifier and signified⟯, the model is often called ⟮dyadic⟯. 

#### image

flex-container:✫sm_planes_of_sound__thought.gif✫✫https://miro.medium.com/max/520/1*YI30OcZeMkEqy_aguUZbug.png✫


What?|Where in the image?
⟮a sign⟯|⟮the are between any two dotted lines⟯
⟮the arbitrary dividing point of sings⟯|⟮the dotted lines⟯
⟮the wavy areas⟯|⟮the world of signifier and signifieds⟯


#### nesting

flex-container:✫sm_paste-4ec4611eb2c01f7a72ccea70f0ba84d090431577.jpg✫✫sm_paste-e61d7b203b885a6825eeb111737b0f16b1bcaf01.jpg✫


⟮Barthes⟯ took ⟮Sassures sign⟯ and ⟮nested it.⟯ 
⟮Derrida⟯ then took ⟮Barthes sign⟯ and realized that it ⟮could be nested infinitely⟯ in ⟮both directions⟯
The endless nesting of signs creates ⟮an endless deferrment of meaning⟯
⟮Différance⟯ is the endless deferrment of meaning due to the endless nesting of signs.

## perspective

### langue and parole

flex-container:✫sm_paste-7e1cabd1841b80a2ab4a4d8a0f6746c2d1c4c811.jpg✫✫sm_planes_of_sound__thought.gif✫


As regards languoids, ⟮De Sassure⟯ created the distinction between ⟮langue⟯ and ⟮parole⟯. 
⟮Langue⟯ is ⟮the structuralist system⟯ of a given languoid 
⟮Parole⟯ is ⟮any instance of the use of a languoid⟯ 
!Sassure claims that in the ⟮langue⟯ of ⟮spoken language⟯
- !the ⟮signified⟯ is ⟮the concept⟯
- !the ⟮signifier⟯ is ⟮(the psychological reality of) the phonological realization⟯. 

### synchronic/diachronic

As regards viewpoints, De Sassure created the distinction between synchronic and diachronic.
A »synchronic« viewpoint considers a languoid at a moment in time without taking its history into account. 
If we're being structuralist, a synchronic approach specifically consideres the structuralist system of a languoid.