# email

Fundamentallly, all emails in an email account (generally associated with a single email address, but not necessarily) are stored in an an (email) mailbox
Message/mail delivery agents are programs that deliver emails to a mailbox.

## mbox ＆ imf

In the mbox format, an entire mail directory is held in a single file.
The mbox format consists of individual IMF messages.
The fileformat for emails is generally IMF.
The mbox format has problems with concurrency (safety and performance).
To prevent corruption, mbox files generally need to use file locking to prevent problems arising from concurrency.
mbox ::= ‹mbox-email›{‹mbox-email›}
mbox-email ::= ‹from-line›‹IMF-message›‹LF›
from-line ::= From ‹sender-email› ‹utc-datetime›‹LF›
IMF-message ::= ‹headers›‹body›‹LF›
headers ::= {‹key›: ‹value›‹LF›}
body ::= ‹LF›‹body-contents›

The IMF uses CRLF, however when stored in mbox, they use LF instead.

## maildir

The maildir format is a format to store mailboxes and mail directories.
The maildir format has three subdirectories (at least) for any directory.
The three mandatory directories for any subdirectory in maildir are cur, new, and tmp.
Using maildir, an arriving message will be sorted into tmp until it is processed completely, then it is inserted into new.
Using maildir, once a mail in new has been read, it si sorted into cur.