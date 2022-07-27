
# 7 types of files

In unix, there are 7 types of files.
Types of files in linux: ⟮Regular file⟯ ⟮Directory⟯ ⟮Symlink⟯ ⟮FIFO/named pipe⟯ ⟮Socket⟯ ⟮Device file (block)⟯ ⟮Device file (character)⟯

The file type is one of the following characters:
identifying characters (e.g. ls)|
-|regular file
b|block device
c|character device
d|directory
l|symbolic link
p|FIFO (named pipe)
s|socket
?|some other file type

## named pipe

named pipe = FIFO
named pipes are functionally very similar to a temporary files.
the use-case for using named pipes instead of anonymous pipes is that you don't need to read/write at the same time, that it persists and thus communication can happen multiple times, that processes that can read/write that aren't child processes of each other.
mkfifo creates a new named pipe
named pipes must be deleted manually (via rm)

## links

ln creates hardlinks by default, and symlinks with -/--symbolic.
ln orders its arguments the same way cp would.
symlink is short for symbolic link.
A symbolic link is a file that is a reference to another file in form of a path.
If the file a symbolic link points to is moved, the symbolic link now points to nothing.
since links exist, the file system isn't actually a tree, but a directed graph.
most programs treat symlinks transparently, however rm/mv/... edit the symlink file itself.
if using rm or mv on a symlink to a directory, if you don't include the trailing slash, they will act on the symlik like normal, if you do include the trailing slash, they will try to remove the directory itself.
A hard link is a reference to an inode.
A hard link only exists as a directory entry, in fact, all directory entries are hard links.
To use a hard link, the file must be on the same filesystem.
If a file moves, a hard link will still be pointing to it.
readlink prints the value of a symbolic link.

## directories

In *nix, directories are nothing but a file, where the files 'contained' within are only associated with it via their directory entry.
dentry = directroy entry.
in the ext filesystem, a directory file is made up of a list of directory entries.
In the ext filesystem, a directory entry contains the inode number, file name and file name length.
the . and .. entries are maintained by the directory files themselves.
Within the ext filesystem, the first entry in any directory file is the . entry.
Within the ext filesystem, the second entry in any directory file is the .. entry.
.|current directory
..|parent directory
If there is an inode not referenced by any directory entry, it will be placed in lost+found.

## device files

two of the seven types of files are device files.
The two types of device files are block device files and character device files.
Block device files grant random access.
Character device files grant sequential access.

## sockets

Unix IPC sockets are distinct from network/internet sockets
A socket in unix is realized as a file descriptor
⟮Unix (domain) sockets⟯ are used for ⟮bidirectional⟯ ⟮IPC⟯
/dev/log = socket for logging