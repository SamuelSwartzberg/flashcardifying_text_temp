## file operations regardless of contents

mv will silently overwrite if moving to something that already exists.
dd   copying (similar to cat/cp) with some low-level options
shred overwrites a file multiple times so it is difficult to recover, however this interacts badly with SSDs
touch|create emtpy file
mkdir|create empty directory
cp|coping stuff

rsync is an improved version of rcp and shares much the same general interface, which is still often used for incremental backups, even if local.

rnr   regex renaming utility that actually works well


### diff

⟮diff⟯ is a tool that ⟮shows the differences between files⟯. 
⟮diff⟯ is originally ⟮a cli program of the same name⟯. 
There are variants of ⟮the original cli program diff⟯ that change how it work somewhat, e.g. ⟮sdiff⟯ for ⟮side-by-die diffs⟯ and ⟮icdiff⟯ for ⟮both colored and side-by-side diffs⟯ 
⟮diff⟯ is now offered as ⟮a subcommand of⟯ ⟮many other tools⟯. 
⟮npm⟯ ⟮diff⟯ provides ⟮diffs between packages⟯, some of which must be ⟮published to the npm registry⟯ 
⟮git diff⟯ shows the difference between things ⟮in/related to a git repository⟯. 
⟮no argument⟯|⟮show diff between unstaged and staged/committed⟯
⟮--staged/--cached (synonyms⟯)|⟮show diff of staged changes with latest commit (or specified commit⟯)


further, ⟮diff-like output⟯ is now used in ⟮a wide variety of gui applications⟯ 