# basic structure

## constituents

»⟮A wstring⟯« (my term) is ⟮＿a string＿ of 1+ words⟯.
»⟮A constituent⟯« is ⟮＿a wstring＿⟯ that ⟮functions as a single unit⟯ and has ⟮tree structure⟯.
»⟮Constituent nesting⟯« is ⟮the joining of ＿constituents＿ into larger ＿constituents＿⟯.

### constituenty tests

»⟮A constituency test⟯« is ⟮a test⟯ that ⟮identifies ＿constituents＿⟯.
»⟮The constituency test scope⟯« is ⟮the set⟯/⟮c_;characterstics⟯ of ⟮＿languoids＿⟯ in which ⟮it works⟯.

### phrases

»⟮a phrase⟯« is ⟮＿a constituent＿⟯ which ⟮behaves in a certain way⟯ which is defined by ⟮＿its head＿⟯.
An ⟮XP⟯ is ⟮＿a phrase＿⟯ with ⟮X as ＿its head＿⟯.

#### heads & non-heads

»⟮The head⟯« of ⟮＿a phrase＿⟯ is ⟮＿the lexemic unit＿⟯ ⟮everything else in the phrase is about⟯.
»⟮A dependent⟯« is ⟮any element of ＿a phrase＿⟯ that ⟮isn't ＿the head＿⟯.

#### phrasal category

»⟮A phrasal category⟯« defines ⟮the way ＿a phrase＿ behaves⟯ and ⟮arises from⟯ ⟮＿the word class＿⟯ of ⟮＿the head＿⟯.

## trees

### direction

Something is »⟮head-inital/head-final⟯« if ⟮＿the head＿⟯ ⟮comes at the beginning/end, respectively⟯.
Something is »⟮left/right-branching⟯« if ⟮their parse trees⟯ ⟮grow to the left/right⟯.
Things that are ⟮＿left/right-branching＿⟯ ⟮are also⟯ ⟮＿head-inital/final＿⟯.

### annotation

#### labeled bracket

»⟮Labeled bracketing notation⟯« is ⟮a notation⟯ that ⟮generates⟯ ⟮a compscitree⟯.
⟮＿Labeled bracketing notation＿⟯ is ⟮mostly⟯ used to generate ⟮＿syntax trees＿⟯.
⟮＿Labeled bracketing notation＿⟯: ⟮tree⟯ ::= ⟮[‹nodename›⟯⟮｛ ‹tree›|‹leaf›｝⟯⟮]⟯
⟮leaf⟯ ::= ⟮#somestring⟯
