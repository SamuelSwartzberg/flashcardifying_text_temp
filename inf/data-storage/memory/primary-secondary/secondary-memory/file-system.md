# file system

The file system is the method/system/whatever that controls/specifies how ⟮data is organized within a partition⟯
A flat file system is a file system with no ⟮subdirectories⟯
Most *nix file systems are case-sensitive, but the apple ones (AFS/HFS+) are not; furthermore, windows is not case-sensitive.
Even non-case-sensitive file systems are almost always case-preserving.
fsck checks/repairs a linux filesystem.
FUSE = Filesystem in userspace
FUSE  is system that allows users to create their own filesystems without editing kernel code
FUSE was originally developed for linux, but has been ported to other OSs such as win or mac
fuse is configured in /etc/fuse.conf

## mounting

mouting is associating a device with a location in the directory tree.
/etc/fstab allows specifying default moun points for certain devices/partitions.
/etc/fstab ensures that the same device will always be mounted inn the same way.
mount and unmount are the commands to mount/unmount things in linux using sudo.
mount may take both a device and a mountpoint.
mount may take just a device or mountpoint, in which case it will try to mount this in the way specified in /etc/fstab.
in contrast to mount, pmount allows one to mount a device without being root, but only if one conforms to a certain set of rules (its policy)

## file info

stat|info about file
file|get file type and related info
