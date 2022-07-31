# windowing system

windowing system is

## X

the X window system is the whole thing with X servers, X clients, an X server, X11, ...
The core part of the X window system is the X server.
the Xorg X server is the main implementation of the X Server
by default, the X server handles displays and kb/mouse.
When something of interest happens, the X server sends events to its clients.
The X server handles the actual displaying to the display.
If one wants to display something using X, one sends an request to the X Server.
X11 is the communication protocol of the X window system.
X clients are things such as individual applications.
X clients may be anywhere, including on another computer.

X thingies installed by default live in /usr/share/X11
X local config changes live in /etc/X11
xorg is configured in X11/xorg.conf(.d)

### window manager

In Unix, a window manager handles window management.
to the X window system, the window manager is just another client.
A window manager does things such as resizing, minimizing, closing
wmctrl   Manage an X window manager
A desktop environment is a window manager plus a set of base applications and some other stuff such as a clipboard manager, toolbar, etc.
Well-known desktop environments are GNOME, KDE, XFCE, Unity...

### starting X

startx is a wrapper around to xinit.
xinit/startx source .xinitrc when run.
.xprofile and /etc/xprofile is run by X before your window manager is run.
.xsession is (at least in theory) only sourced when logging in from a display manager

### Login

A X display manager is a graphical login manager which starts a login session on an X server.
the GNOME X display manager is gnome's display manager.
GDM = GNOME display manager
LightDM is the most common alternative to GDM.

### DE

D-Bus is a protocol/interface/middleware for messaging between processes (IPC).
AccountsService is a D-BUs service for accessing the list of user accounts and information attached to those accounts.

What Desktop Environment you're using   XDG_CURRENT_DESKTOP
What Desktop Environment you selected from the display manager (might be limited to gnome display manager)   GDMSESSION

### CLI

xdotool allows automation of X windows
xdpyinfo gets info about an x server
xwininfo gets information about open windows
xev shows X events such as keyboard, resizing, clicking etc.

## misc

pango is a linux library for international text rednering.
