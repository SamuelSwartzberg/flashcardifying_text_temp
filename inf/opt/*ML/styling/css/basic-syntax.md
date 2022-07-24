# CSS

CSS = Cascading Style Sheet

S ::= {‹statement›}
statement ::= ‹ruleset›|‹at-rule›
ruleset ::= ‹selector-list›‹declaration-block›
rulesets are less properly but more commonly called rules
selector-group ::= ‹selector›{,‹selector›}
declaration-block ::= \{‹declaration-list›\}
declaration-list ::= {‹declaration›}
declaration :: ‹property›:‹value›; // Technically, the ; is not a part of the declaration, since it only separates and does not terminate declarations. Therefore you can leave out the final semicolon of a declaration block, though this is generally not advised. This would overcomplicate the ENBF, so here this note.

at-rule ::= @‹identifier› ‹prelude›[\{‹block›\}]
At rules that have the optional block are known as nested at-rules.
the block that an at-rule may take is explicitly specified by the spec not to be the same as the declaration block of a ruleset, and therefore not at all subject to the same syntax. Nested at-rules may however *choose to* follow the same syntax as a declaration block.
nested at-rules whose block is a declaration block: @counter-style, @font-face
nested at-rules whose block is a declaration block, but also supports other at-rules within: @page
nested at-rules whose block is not a declaration block: @keyframes, @media, @supports.
A nested statement is a statement that can be used inside a conditional group rule.
A conditional group rules is a CSS at-rule that associates a condition with a group of other CSS rules.
The commmon conditional group at rules are @media and @supports.


flex-container:✫sm_tmpyk7c4jes.png✫

style as a HTML attribute takes n declarations