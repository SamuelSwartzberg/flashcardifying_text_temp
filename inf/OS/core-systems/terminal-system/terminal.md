
# terminal

A terminal may be a physical/hardware terminal, a virtual terminal/console, or a terminal window.
/dev/tty represents the current terminal, regardless of what kind of terminal it is (hardware, virtual, etc.)
the tty command tells us which device file is implementing the current terminal

## terminal architecture


flex-container:✫file://~/Downloads/terminalsys.svg✫

A physical terminal is connected via cables to an UART driver.
screen, keyboard etc. are connected via drivers to a virtual terminal (not a window).
The UART driver or virtual terminal are connected to the line discipline.
The line discipline may be disabled, in which case the characters are sent directly and instantly to the process, the so called raw mode.
cooked/canonical mode is when the line discipline is enabled, which means that text is only sent to the application after a newline is sent.
cooked = canonical mode
The line discipline is typically disabled for TUI applications or similar and for the shell, which implements its own line discipline.
the line discipline is connected to the tty driver.
The tty driver is passive, while it has fields and methods, they need to be called from outside, e.g. via signals.
the tty driver seems to be the parent process of the session leader.
stty administers the options for the tty driver.
The tty driver is the thing that has all all the processes living in a terminal as descendants (?)

### physical terminals and terminal emulators

Terminal emulator is properly a synonym for virtual terminal/console, though sometimes terminal emulator is used in the wider sense of 'any thing that emulates a hardware terminal', though I would consider this incorrect usage. Nevertheless, I wil use virtual terminal for this to avoid ambiguity. 
virtual terminal = virtual console.
vt/vc is short for virtual terminal/console.
Virtual terminals are realized by a /dev/tty‹n› file.
/dev/tty‹n› files are provided by the kernel.
Hardware terminals are realized by /dev/ttyS‹n› files (I think)
tty may be a synonym for virtual terminal (since all virtual terminals are realized via /dev/tty‹n›), or as a synonym for any non-pseudo-terminal terminal.
Each physical terminal would have been its own separate thing, and so each virtual terminal is also its completely separate thing.
Virtual terminals occupy the whole screen, they decidedly don't live within a GUI.
/dev/tty0 represents the current controlling virtual terminal.
When in a GUI, /dev/tty0 may be the virtual terminal the window server is running in.
On linux, pressing ctrl + alt + f‹number› switches to tty‹number›
In linux, the window manager lives within a virtual terminal.
Linux typically starts with 6 virtual ternubaks, and then one additional one (tty7) to run the window manager in.
ttys (physical terminals and virtual terminals) are initialized by `getty`, which mainly calls `login`.

each /dev/tty‹n› has a corresponding /dev/vcs‹n› (including /dev/tty0, which means that /dev/vcs0 corresponds to the memory of the current virtual terminal)
the /dev/vcs‹n› contains what is visible on the screen of a /dev/tty‹n›

### pseudo terminals

A pseudo-terminal consists of two device files, a master file and a slave file.
In a pseudo-terminal, a terminal window such as xterm (or sth like ssh) replaces the virtual terminal. 
In a pseudo-terminal, instead of being connected directly to the line discipline, the thing replacing the virtual terminal is connected to the pseudo-terminal master device file. 
The kernel links the pseudo-terminal master device file (ggf. filtering through the line discipline) to the pseudo-terminal slave device.
The link between pseudo-terminal master and pseudo-terminal slave is full duplex.
The pseudo-terminal slave fulfilles the role that the tty driver would normally, e.g. holding on to processes.
If you input something e.g. to a terminal window, it is written to the pseudo-terminal master device, which is transferred to the pseuod-terminal slave, which redirects it to the relevant process. 
the file /dev/ptmx is the pseudo terminal master multiplexer, which spawns new pseudo terminals.
Opening /dev/ptmx gives you a file descriptor for the master device and spawns a slave device in /dev/pts.
/dev/pts/‹n› represents a pseudo terminal slave.
When sshing, the pseudo terminal master device is connected to your terminal/terminal window/virtual terminal, but the pseudo terminal slave is instead on the remote machine.
The thing that creates the pseudo terminal slave on the remote machine is sshd.

### system console

In the past, many hardware/physical terminals might have been connected to one computer.
In the past, the system console would have been its own hardware/physical terminal connected directly to the computer.
Today, the system console is merely the device file /dev/console.
In most modern systems /dev/console is merely a symlink to /dev/tty (however it may also point at something else)
In any case /dev/console and /dev/tty have different major numbers.

## terminal window

A terminal window must be one level of emulation deeper than a virtual terminal, since it lives in a GUI which in linux at least itself lives within a virtual terminal.
A terminal emulated within a GUI is known as a terminal window
Alternative terminal window (mac)|iTerm2
xterm is the classic terminal window for the X window system.
most terminal windows are based of xterm
the default terminal window for gnome is gnome-terminal.
all the various terminal windows generally have a command of the same name to launch them/specify options
most terminal windows take the -e argument to execute the command in the newly opened terminal window.
Termux is a terminal window for android.

## process interaction with terminals

PGID|Process group ID
SID|Session ID
pgrp|process group

On unix, every process has a parent.
A process group is a collection of one or more processes.
A session is a collection of one or more process groups.
Processes may not migrate between sessions.

To the terminal, the shell is just one more process running within it.

ctty = controlling terminal (doesn't have to be a tty)
A session has one controling terminal.
all processes within a session inherit the controlling terminal via fork()
Signals can only be sent by/via the controlling terminal and only to its forground process group.
The relevant foreground process will have its in/output connected to the tty driver of the controlling terminal.
Any session has exactly one foreground process groups, all other process groups are in the background.
Each session is managed by a session leader.
the shell is the session leader, and is always the process group leader of its process group
The session leader updates the tty driver and does some other admin stuff, e.g. creating new porcess groups for pipelines.
for the process group leader, PGID == PID
for the session leader, SID == PGID == PID


## signals

signals allow the kernel to communicate asynchronously with a process (group).
The thing that is signalled when being singalled from a terminal is always an entire process group.
In the context of terminals, signals may be sent by/via TTY driver or some other part of the terminal subsystem.
signal names are all-caps and start SIG.
In a terminal, any input, including stuff such as ^Z gets sent to the tty driver (or maybe the line discipline - I'm not quite sure, and people seem to be disagreeing). 
For some key combinations, such as ^Z, the tty driver will not transmit the input, but instead turn this into a signal and send this to the foreground process group.
For some key combinations, such as ^D, the tty driver will not transmit the input, but instead turn this into a different character and transmit this instead.
Other key combinations, including some ^‹char› combinations may merely be passed on to the process.
Ergo some ^‹char› combinations may always send the same signal (but leave it up to the process how to respond to the signal), some ^‹char› combinations may send a different character (which will be treated by that process as that characer), and some ^‹char› combinations will just send ^‹char›, which the process may handle if it so chooses.
You can change which ^‹char› the terminal driver handles how via stty.
^C|SIGINT|tty  driver
^\|SIGQUIT|tty driver
^Z|SIGTSTP|tty driver
^D|EOT/EOF|tty driver
^L|FF|processs|often interpreted as 'clear the screen' (shells) or 'redraw the screen' (curses)

kill sends a signal to a process, given its PID
killall sends a signal to a n processes, given a string that their name contains
by defaut, kill and killall send SIGTERM

## appearance

Things such as color and cursor movement in the terminal are implemented via control characters.

## shell commands for terminal management

There are a number of shell commands that nevertheless still are concerned with terminals, and not with shells

### virtual terminal

fgconsole   get the number of the current tty
fgconsole --next-avaliable   get next unallocated vt
openvt|run a program on the next free vt.
deallocvt   remove unused virtual terminals
chvt N   change to ttyN
Couldn't get a file descriptor referring to the console is an error you encounter using commands meant for virtual terminals somewhere else

### any terminal 

the who utility displays all active terminal sessions and for each the users logged into them, datetime of login, and hostname if not local.
    sam$ who
    sam      console  Dec  4 01:44 
    sam      ttys002  Jan  9 12:34 
    sam      ttys007  Jan 24 23:26 
uptime -  prints general system stats: time of day, uptime, amount of users logged in, and and the average number of jobs in the run queue over the last 1, 5 and 15 minutes.
w is an extended version of who, which shows everthing who does, plus what is currently running in the terminal and the time since the user last typed anything. w also the stats that `uptime` shows.
    sam$ w
    9:10  up 52 days,  7:26, 3 users, load averages: 2.10 2.05 2.01
    USER     TTY      FROM              LOGIN@  IDLE WHAT
    sam      console  -                04Dec21 52days -
    sam      s002     -                09Jan22  3:34 -bas
    sam      s007     -                Mon23    9:41 -bas
