# applications

## cli tools

### differences

Different *nixes have different versions of different command-line tools, on account of having descended in different ways from the original unix.
coreutils are the basic GNU file, shell and tex manipulation utilities.
the GNU versions of basic command-line tools is generally more featureful than other versions.
the GNU versions of basic command-line tools is generally the one that is assumed e.g. online.
You can install the GNU coreutils on non-GNU systems via homebrew.
If there is also a preexisting version of the command when the GNU coreutils are installed with homebrew, they are prefixed with g (e.g. gdir instead of dir).
If you need the normal names of the GNU coreutils when installed with homebrew (e.g. because they're being used in a preexisting script etc, add the directory they're in (/opt/homebrew/opt/coreutils/libexec/gnubin) to your $PATH