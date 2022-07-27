
# git 

Git is a VCS, but really isn't.
Git is fundamentally a content-addressable filesystem with a VCS user interface written on top of it.
Git is a content-addressable filesystem in that it fundamentally indexes files by hash keys.

## objects

Objects are the various things git has.
Objects in git are stored in .git/objects
files in .git/objects are further sorted into subdirectories with the first 2 characters of their hash, with the contained file names having the leftover 38 characters.
Git objects are text files.
git objects have their hashes as their names, allowing them to easily be referenced.
git objects are commits, trees, blobs and annotated tags.

### inspecting

the `git cat-file` command is the swiss army knife for inspecting git objects.

-p|Pretty-print the contents of ‹object› based on its type. (can be used to retrieve the file from the store)
-t|Instead of the content, show the object type identified by ‹object›.

### hashes

hashes can be abbreviated to their first n characters, as long as those are unique.
the command `git hash-object` takes some data and returns the hash git would hash it with.
If you use the flag -w, `git hash-object` actually writes the file to .git/objects and returns the hash.
The type of hash git uses is a 40-character SHA-1 hash

### commits

At its most simple, a repository contains a series of commits.
A commit is an object consisting of a few metadata.
Across different VCSs, a commit may be associated a snapshot (a copy of the file) or a diff, though git chooses a snapshot (contrary to what I thought)
The commit object has its hash as its name.
A commit consists of a hash of the tree, a hash of the parent commit, author, committer, date, and message.
Running `git commit` adds a new commit with the files in the staging area.

### trees

A tree is a git object representing the directory structure of the project at time of commit as an ordered list.
The file representing the tree has 'entry' (not a real term) per line.
A tree 'entry' consists of file permissions, object type, object hash, and filename.
The object type of a tree 'entry' is usually "blob" for files or "tree" for a subdirectory.
tree git objects are confusingly named, as they are ordered lists and only become trees by their ability to refer to other trees.

### blobs

A blob is a git object representing the contents of a file.

### annotated tags

A tag git object contains the hash of the tagged object, the type of tagged object (usually a commit), the tag name, author, date and message.

## heads

the HEAD is a pointer to the currently checked out commit/branch head.
You are in detatched HEAD state is when your HEAD is pointing directly to a commit.
checking out a commit/branch moving the HEAD to that commit/branch head.
the command to check out a commit/branch head is `git checkout`.
the newer porcelain command to check out a branch head is `git switch`.
the HEAD is implemeted by storing the hash of the commit or the file for the branch header (i.e. refs/head/whatever) we're pointing to in .git/HEAD 
HEAD may also often be used as a keyword for git commands.

## repository

The working directory contains the repository directory as well as the current versions of all the files in the repository.
The repository directoy contains all git internals, and is called .git.
Whenever you stage a file, it is added to the staging area and its blob is added to .git/objects.
The staging area is a directory listing containing the hashes of all staged files.
The staging area is implemented by a single file, .git/index.
`git add` stages a file.
git status tells us about our working directory and staging area.
The staging area is not emptied by committing! But after commiting, there is no difference between the staging area and the working directory
If you changed a file, it's unchanged version will be living in the staging area, while its `modified` version will be living in the working directory. To make it part of the staging area, you need to `git add`.

### tracked and untracked files

At the beginning of a git repository, all files are untracked.
All files that have been `git add`ed at some point become tracked files.

### .gitignore

there is also a per-clone version of the gitignore in form of the .git/info/exclude file.
Patterns which a user wants Git to ignore in all situations (e.g., backup or temporary files generated by the user’s editor of choice) generally go into a file specified by core.excludesFile in the user’s ~/.gitconfig. Its default value is $XDG_CONFIG_HOME/git/ignore. If $XDG_CONFIG_HOME is either not set or empty, $HOME/.config/git/ignore is used instead.

By default, any line in a gitignore contains one pattern to ignore.
If a line is prefixed by !, a line in a gitignore instead contains a pattern to reinclude. 

Github hosts a nice list of gitignores for most common languages/frameworks/build tools.

### creating a new repository

`git init` creates a new repository by creating the repository directory.



## commit history

git log shows a set of commits of the commit history.
`git reset` can be used to reset your HEAD to the specified past commit.
git reset moves the HEAD/branch heads to the specified commit, as well as the staging area, but does not modify the working area.

### retrieval

`git checkout ‹commit› ‹filename›` retrieves the file ‹filename› as of commit ‹commmit›

## branches

branches split the linear relationship of the commit history.
In git, a branch merely consists of a branch head.
A branch head is a pointer to the commit at the tip of the branch.
git stores branch heads as files in .git/refs/head
Each file in .git/refs/head, i.e. each branch head contains the hash of a commit.
A branch can be kept track of by only a branch head since every commit has the hash of the previous commit.
When we create a new branch, git creates a new branch head pointing to the specified commit.
`git branch` without arguments lists the current branch heads.
A newly created repository contains one branch head, master/main.

### creating branches

`git branch` with two arguments A, B creates a new branch A with the commit to start at specified by B.
`git checkout -b` works the same as git branch with two arguments, but also checks out the new commit.

### unifying

to include changes from another branch into the current branch, one has two choices: rebase and merge
Compared to merging, rebasing results in a more 'pretty' commit history

#### merging

two possible merges: fast-forward, three-way-merge
In a fast-forward merge, the the HEAD is (pointing to) a direct ancestor of the commit we're merging in.
In a fast-forward merge, it is merely the pointers that differ, so the merge merely moves the pointer forward
Any merge that is not a fast-forward merge is a three-way merge
a three way involves two different states and thus must create a merge commit.
In a three-way merge, the merge is performed based on the diff with the common ancestor commit.
In a three way merge, if the same section of the ancestor commit has been changed, it creates create a merge conflict.
A merge conflict is indicated by special syntax within the file.
merge-conflict ::= ‹seven-left-angle-brackets› ‹branch-name›‹newline›‹code-version-1›‹newline›‹seven-equals-sign›‹newline›‹code-version-3›‹newline›‹seven-right-angle-brackets› ‹branch-name›‹newline›
After fixing a merge conflict, you need to commit again.

To abort a maerge during a merge conflict: git merge --abort

#### rebasing

Rebasing in git is taking the changes from somewhere (e.g. a branch) and applying them on another branch as if the changes had been made there originally

## rev-parse

the suffixes ~‹n› and ^‹n› are for moving back in the tree of commits.
~‹n› goes n commits back into the history
~0 = this commit, ~1 = parent commit, etc. 
~ is an alias for ~1
^‹n› selects the nth parent commit sibling if there are multiple.
^1 = ~1, ^2 is the second commit of a merge commit, etc.

## plumbing and porcelain

Git has two kinds of commands, plumbing and porcelain.
Git's plumbing commands are older and more low-level.
Git's porcelain commands are newer and more high-level.

## remotes

Remotes are ⁑links to⁑ other git repositories. (!)
Remotes may be on the same device, or other devices (e.g. online).
The default name for a remote is 'origin'.
`git remote` is used to administer remotes.
`git remote add foo bar` adds a new remote to the current repository, where foo is the name we will call this remote, and bar is its URL.
remotes are stored in .git/config
In .git/config, each remote has its own header

### pushing, fetching, pulling

things git push/fetch transfers are refs and objects.


#### pushing

git push transfers all the information a remote does not yet have but needs of a certain refspec to that remote.
`git push [‹repository› [‹refspec›]]`
If the repository is left out from git push, it will take it from the branch.*.remote (i.e. the configured remote for the branch) config, or origin if none is found.
When the command line does not specify what to push with ‹refspec›... arguments or --all, --mirror, --tags options, the command finds the default ‹refspec› by consulting remote.*.push (i.e. the push key for the specified remote) configuration, and if it is not found, honors push.default configuration to decide what to push

#### fetching

`git fetch [‹repository› [‹refspec›]]`
If the repository is left out from git push, it will take it from the branch.*.remote (i.e. the configured remote for the branch) config, or origin if none is found.


### remote tracking branches

A remote tracking branch someremote/foo is a local copy of the foo branch on the remote, possibly as distinct from the truly local foo branch.
to list remote tracking branches, use `git branch --remotes`
remote tracking branches are named `‹remote›/‹branch›`
A tracking branch is a local branch that is directly related to a remote tracking branch.
The remote tracking branch of a tracking branch is called the upstream branch.
Establishing a new tracking branch can be done by creating a new local branch for a remote tracking branch e.g. via `git checkout -b newLocalBranch ‹remote›/‹branch›`, for which the shorthand `git checkout --track ‹remote›/‹branch›` exists.

### refspec

A refspec tells git how to map references from a remote to the local repo.
refspec-format ::= [+]‹src›:‹dst›
‹src› in a refspec is the pattern for references on the remote side
‹dst› in a refspec is the pattern for references on the local side
If a plus is included in a refspec, it tells git should update even if it isn't a fast-forward 
Default refspecs for pushing and fetching for each remote are established in the remote entry in the config file.

### cloning

`git clone` creates a new directory containing a copy of a remote repository, setting up remote tracking branches for each branch of the remote repository.

## config

per-repository config for git is stored in the .git/config file.
Global git config is stored in the .gitconfig or the ~/.config/git/config file.
Git config files are ini-likes

## tags

tags are pointers to specific commits.


## hooks

git supports hooks in the form of git hooks.
git hooks are stored in .git/hooks
you can use any language for git hooks as long as you can specify it via a shebang
by default, none of the git hooks run because they are postpended by .sample - removing this will make them run at the relevant time.
git hooks are not synchronized between origins by default, to do that, you would have to store them in the repository themselves and symlink them or sth.
there are 6 local and 3 server hooks.

local hooks
name|does|arguments passed to script|exiting non-0 does
pre-commit|after git commit, but before prompting for message|none|aborts commit
prepare-commit-msg|prepopulates text editor with commit message|name of temporary file with message, type of commit, hash of commit|aborts commit
commit-msg|after commit message was entered (for validating commit message)|name of temporary file with message|aborts commit
post-commit|after commit-msg hook (e.g. for notifications)|none|nothing
post-checkout|after running git checkout|previous HEAD, new HEAD, branch or file checkout|nothing
pre-rebase|called before git rebase|2, but I don't want to deal with them right now|aborts the rebase

server hooks
pre-recieve|when recieving commits from git push|none, but recieves commit reference via stdin|rejects the push
update|
post-recieve|after push has succeeded|none|nothing

## github

Github is a hosting service for git repositories.

### Issues ＆ PRs

Github issues track desired changes such as features, bugs, etc.
A milestone is a set of github issues.
PR = Pull Request
A pull request is a request to merge the specified changes into the branch
If you refer to an issue with ⟮#number⟯ and a word such ⟮as closes, fixes etc.⟯ within a ⟮commit⟯, it will ⟮close the issue⟯ (or ⟮close it⟯ once ⟮merged into the default branch⟯)