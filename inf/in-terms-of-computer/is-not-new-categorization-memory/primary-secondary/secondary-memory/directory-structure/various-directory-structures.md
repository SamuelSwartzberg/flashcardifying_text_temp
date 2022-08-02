# various directory structures

## home dir

Generally one home directory per user.
On *nix, the home directory of a user generally contains all the stuff pertaining ot a user.
FHS: Home directories live in /home/
$XDG_CONFIG_HOME/autostart contains .desktop files to run on system start
$XDG_DATA_HOME/fonts contains fonts for a specific user

## XDG Base Directory Specification

XDG Base DIrectory Specification is the spec governing the organization of files in your home directory   

XDG Base Dir Var|default|global equivalent
$XDG_DATA_HOME|$HOME/.local/share|/usr(local/)share
|$HOME/.local|/usr/local
|$HOME/.local/lib|/usr/local/lib
|$HOME/.local/bin|/usr/local/bin
$XDG_CONFIG_HOME|$HOME/.config|/etc
$XDG_CACHE_HOME|$HOME/.cache|/var/cache

## FHS

FHS  Filesystem Hierarchy Standard
FHS (Filesystem Hierarchy Standard) is the Linux spec for ⟮directory structure⟯
source code should be in src for reference only

### /sys

/sys provides a window to the kernel.
/sys/class|contains (a view of) different types of devices
/sys/class/power_supply|contains (a view of) the power supplies
/sys/class/power_supply/BAT‹n›|information about the nth battery
/sys/class/backlight|contains (a view of) the screen backlights.

### /boot

/boot contains things necessary for booting, most importantly the kernel.

### /proc

/proc contains information for each process and a lot of runtime system info.

### /var

/var contains data likely to change often.
the structure of /var is provided by the OS

/var/mail/ and/or /var/spool/mail contain MBOXes for each user 
Of /var/mail/ and /var/spool/mail, the semantics are the same, and thus one is most often a symlink to the other.
/var/spool/   data awaiting processing
/var/cache/|cache data
/var/backup/|backups of key system file
/var/crash/ contains crash dumps of the system
/var/log|global log data
/var/lock|global lock files (for mutexes)
/var/lib data to maintain program state that doesn't have  a better directory to be in. 
/var/lib state information is valid even after reboot.

### /opt

/opt   software packages (complete and kind of foreign)
programs in /opt are usually more self-contained and system-fremd.

### /srv

/srv is a directory for data served by the system
/srv is often organized into subfolders by protocol (though this is not a requirement.)
/srv is not used particularly commonly

### /mnt and /media

/media is where the system mounts things automatically (e.g. removable media), and /mnt is where you mount things manually (with generic semantics)
You are not forced to mount things in /mnt, you can mount them wherever you want.

### /opt

/opt contains fairly self-contained programs
/var/opt contains variable data of programs installed in /opt
today, usage of /opt is fairly rare

### /run and /var/run

today, /var/run is deprecated in favor of and a symlink to /run
/run or /var/run contains runtime variable data that programs rely on that is cleaned or tirimmed at reboot

### /usr

/usr is called usr because it contains userland and not kernel land data
Data within /usr should be usable on any FHS-compliant host, ergo data specific to host or time should not go in /usr.
Data within /usr should be read-only
/usr is for programs installed by the OS/package manager, while /usr/local is for programs installed by the root user
the structure of /usr/local mirrors the structure of /usr
/usr(/local)/include is for C include files
stuff in a share directory is data sharable sharable across all architectures of a given OS
/usr(/local)/src contains source code of installed programs for reference only.
typically, /usr and /usr/local include at least bin, lib, include and share

### bins

whatever/bin is generally for executables
Originally and still in some unixes, /bin would have contained system-essential binaries, while /usr/bin and /usr/local/bin would have contained non-system essential bins (and analogously for lib)
today, /bin often just is a symlink to /usr/bin (and analogously for lib)
whatever/lib generally conains libraries for whatever/bin
whatever/lib32 and 64 are libraries for the architecture specifically, most commonly when two versions of the same library for different arches are installed.
instead of whatever/bin, games may also go in whatever/games
/sbin is for binaries needing superuser priviledges/for system administration
sbin = superuser binary

### /tmp

/tmp is for temporary files.
/tmp is sometimes emptied on process exit or on boot.
/var/tmp is like /tmp, but meant to last longer and thus autocleaned less or not at all
Organization within /tmp is pretty hodgepodge.

### /etc

/etc contains global config files for all the programs that run on your Linux/Unix system
/etc/hosts
/etc/motd|contains the message of the day
/etc/machine-info contains machine metadata such as type of computer, deployment, location and pretty-printed hostname
/etc/hostname contains the usesrs static hostname.
hostnamectl administers the stuff in /etc/hostname and /etc/machine-info, i.e. all the hostnames and the machine metadata.
hostname - show or set the system's host name
Instead of /etc, some programs stored in /usr/local store their config in /usr/local/etc

### /dev

/dev contains device files.
It makes sense to treat devices as just another file, as the operations they support (reading, writing or both) are the same as a file.
device files are files that are interfaces to device drivers (or more rarely other things).
udev is a system managing the /dev directory and userspace hardware events.

#### drivers

on *nix, any device is identified by its major and minor number.
on *nix, drivers generally should provide a mechanism but not a policy.

|identifies
major number|driver
minor number|device of driver
if two device files have the same major number, they are managed by the same driver
if two device files have the same major and minor number, they are the same device

#### not real devices

/dev/random and /dev/urandom are CSPRNGs of nix* systems
the difference between /dev/random and /dev/urandom is that the former blocks to wait for more entropy if necessary, the latter does not.
the man suggests one use /dev/random for long-lived GPG/SSL/SSH keys, and /dev/urandom for anything else.
/dev/full is  always full
/dev/zero returns as many 0x00 as you like.
anything written to /dev/null discards the data, whence its nicknames bit-bucket/black hole
/dev/video‹n› represents attached cameras.

#### block device files

The beginning of the device file name specifies the kernel's used driver subsystem to operate the block device.
Originally, the /dev/sd‹char› was only used for block devices using SCSI.
Because ATA/SATA/PATA devices suppoort a subset of the commands of SCSI, linux decided to also handle them by the kernel's SCSI driver subsystem, therefore their device files also use the  /dev/sd‹char› naming scheme. 
/dev/nvme‹n›n‹n› represents devices attached via NVMe
for /dev/nvme‹n›n‹n›, the first ‹n› represents the index of the controller, the second ‹n› represents the device on the controller.
/dev/vd‹char› represents devices attached to a virtio block device interface, which is an interface for virtual devices.
/dev/mmcblk‹n› represents devices handled by the kernels mmc driver, such as SD cards.
/dev/fd/‹n› are device files representing the file descriptors of the current process, however /dev/fd‹n› (notice the difference!) indicates the nth floppy disk connected.
/dev/hd‹n› are device files representing entire, raw hard disks (not commonly used today)
/dev/input contains device files for

‹char› and ‹n› as indices are genrally assigned based on which was discovered first
to represent a partition, add ‹index› to the relevant device file if the name ends in a character, and p‹index› if it ends in a number.
e.g. /dev/sda1 or /dev/loop0p2

A loop device is a normal file mounted as a block device, which you then can use as part of a filesystem.
.iso files might be good candidates for mounting as a loop device.
loop devices are mounted at /dev/loop on linux

#### character device files

/dev/stdin and /dev/stdout are symlinks to /dev/fd/0 and /dev/fd/1
piping to `source /dev/stdin` executes the text as a command

## Mac

flex-container:✫sm_Screenshot%202020-07-09%20at%2014.36.21.jpg✫
⟮macOs⟯'s ⟮/private⟯ folder contains ⟮a few directories that would have been found in / on FHS-compliant devices⟯, namely ⟮s1:3;⟮etc⟯, ⟮tmp⟯, and ⟮var⟯⟯