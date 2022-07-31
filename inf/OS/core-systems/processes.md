# processes

On unix systems, a process is an (instance of a) program that is ⟮running⟯
On unix, a process is the instance that has its own heap.

## process relationshps

IPC|inter-process communication.

PPID|Parent Process ID
PID|Process ID


## process management

ps|list of processes
pstree|processes as a tree

procs is a more fancy version of ps written in rust

## file descriptors

A file descriptor is a positive integer that uniquely identifies a file (or file-like) things.
Each process has its own file descriptors.
The file descriptiors of a single process are stored in their own file descriptor table.
The kernel maps the file descriptors the file descriptor table of a single process to the file table.
The file table is a system-wide table of all open files.
The file table contains reference to the relevant inodes.
Each process has three file descriptors allocated automatically, namely for the standard streams.
the standard streams consist of stdin, stdout and stderr
The standard streams different from other file descriptors is that they are always allocated automatically, and that many mechanisms will use them by default.
stdin   0
stdout   1
stderr   2

using `-` to refer to stdin or stdout is a common convention specified by posiz, but not a feature of the shell or anything else

When you open a file on unixy systems, the kernel creates a file descriptor for the file using (amongst other things) the relevant the inode

## daemons

A daemon is a process running in the background, not under the direct control of a user.
In *nix, a daemon is generally a process which is a child of the init process.
A daemon is usually created either by a process forking a child process and then immediately exiting, thus causing init to adopt the child process, or by the init process directly launching the daemon. 
The names of daemons generally end with d.

## exit codes

true|do nothing, sucessfully (exits 0)
false|do nothing, unsuccessfully (exit non-0)

## process management tools

top is a process viewer.
htop is a more fancy version of top with a better TUI and interactivity.