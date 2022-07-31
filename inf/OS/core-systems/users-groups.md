# users and groups

GID|group id
UID|user id
groups/users on nix are uniquely identified by their user or group ID.
groupadd is the command for creating new groups.
gpasswd is the command for managing /etc/group and /etc/gshadow.
id is the command for printing things like UID, GID, etc.
the groups command lists the groups a user is in.
/etc/groups defines the groups on the system:
etc-groups ::= {‹group-name›:‹password-encrypted›:‹GID›:‹member_list›‹newline›}
passwd – modify a user's password

## commands

whoami|show current username
login|login as user
logout|logout of shell

## superuser

superuser = root = admin(istrator)
OS-independently, the superuser/root/administrator is a user with large to unlimited power over the system.
In unix, the superuser is the user with the UID 0.
In unix, the three groups that hasve superuser/sudo-related priviledges are wheel, sudo and admin.
sudo allows executing a single command with superuser priviledges.
To use sudo you need to enter your own password, to use su you need the password of the relevant user, in this case the superuser password.
Who can use sudo is managed in /etc/sudoers
visudo edits the sudoers file in a safe fashion with your configured VISUAL/EDITOR.
getpass is the C function that makes sure that password input is hidden (nothing is displayed) on the comamnd line
sudo usually caches the entered credentials for a short while.
The su utility requests appropriate user credentials and switches to that user ID (the default user is the superuser).  A shell is then executed.
su = substitute (in the past super) user
sudo = substitute (in the past super) user do

-E = --preserve-env

### polkit

polkit is a toolkit to allow finer-grained control than just running sudo.
Polkit defines ⟮actions⟯, ⟮who can use them (group/user)⟯, and ⟮under which circumstances⟯.
pkexec works like sudo, but instead opens a window for password entry (it also depends on polkit policies)