# inodes

## inodes themselves

In linux exty file systems, a file is identified by an inode.
An inode stores things such as types, permissions, ownership, and most importantly a pointer to the file's contents.
Things such as chmod edit the inode.
It's unclear what inode exactly is short for, but probably something like index node.
Oddly, the inode does not contain the file name, which is instead stored by the directory.
If linux finds an inode without a filename (that is referenced in no directory), it puts it in lost+found

## inode numbers

An inode is uniquely identified by an inode number.
Sometimes, inode is incorrectly used to refer to inode.

## inode table

The inode table is a property of the file system.
The inode table contains all possible inode numbers.
Thus, inode numbers are (only) unique to the file system.
The inode table is created at fs creation type.
The inode table takes up roughly 1% of a file system's storage space.
The fact that there is a limited number of inode numbers which are determined at fs creation time means that its possible to run out of inode numbers (and thus the ability to create no files)

## special inode numbers

table:inode number|refers to
2|/ (root)
1|Bad blocks indication thingy
0|NULL (no inode)