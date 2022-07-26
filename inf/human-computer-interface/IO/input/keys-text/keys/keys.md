# keys

## QWERTYlike

A QWERTYlike keyboard is a keyboard that functions like a QWERTY keyboard.

### language variants

#### basics

A QWERTYlike language variant is a QWERTYlike keyboard with some QWERTYlike language variant differences based on the QWERTYlike language variant region.
A QWERTYlike language variant difference is the difference of a QWERTYlike language variant region to QWERTY.
A QWERTYlike language variant identifier is an identifier for a QWERTYlike language variant, and is typically the first few keys of the top row.
The QWERTYlike language variant region is the region where a QWERTYlike language variant is typically used.

#### table

table:QWERTYlike language variant identifier|QWERTYlike language variant region
QUERTY|en
QWERTZ|de
AZERTY|fr

#### QWERTYlike language variant differences

##### QWERTZ

Between english and german keyboards, the only difference in letter keys in that z and y are flipped.

### types of keys

A visible character/non-visible character key is a key that produces a visible character/some other effect.
A mode/non-mode key (my term) is a key that creates a mode⎵wide⎵.

#### mode keys

A mode key may be a lock key or a modifier key.
A lock/modifier key is a key that enters&exits a mode/maintains a quasimode.

##### alternate-character generating key

An alternate-character-generating key is a mode key that produces an alternate character while in its mode⎵wide⎵.
An alternate character (my term) is a character produced by a non-mode key while in a mode⎵wide⎵ produced by a mode key.
The shift/altgr alternate character is the character produced by shift/altgr

##### lock keys

toggle key =syn= lock key
Typical lock keys are {caps lock, shift lock, num lock, insert}.

###### insert

The insert key is a lock key that switches between insert and overtype mode.
in the 2020s, insert mode is common, overtype is barely used.
In overtype mode, typing replaces characters to the right
In insert mode, typing moves the characters in the right further to the right.

When in overtype/insert mode, the cursor is reasonably wide/narrow

###### caps & shift lock

Caps lock/shift lock is a lock key which is an alternate-character-generating key producing shift alternate characters only for letter keys/for all keys.
The left lock key is the lock key on the left of QUERTYlike keyboards that typically behaves as caps lockor shift lock.

On windows/mac the left lock key behaves as caps lock or shift lock depending on the QWERTYlike language variant/always as caps lock.
Many operating systems but not mac allow pressing shift to temporarily ignore caps/shift lock.

##### modifier keys

The modern modifier keys are shift, ctrl, altlike key(s), os key(s).
The small formfactor modifier keys are the modern modifier keys + fn.

###### primary modifier keys

The primary modifier key is the modifier key that is most often used as a key combination modifier ingredient in a given OS.
Windows & linux/mac treat(s) ctrl/cmd as their primary modifier key.

###### os key

The os key is the modifier key unique to a given os.
The os key for windows/mac/linux is win/cmd/the linux os key.

###### super, meta, hyper

Originally, super, meta and hyper keys were all dedicated modifier keys present on some keyboards.
The linux os key is variantly super or meta depending on the distribution.
win/cmd/linux equivalent.
The simulated hyper key is a fictional modifier key created by simulating an insane number of modifier keys at the same time by pressing a different non-modifier key (often the left lock key).

###### altlike

####### basics

An altlike key is either alt, alt gr, or option.
The alt key is a modifier key that only acts as a key combination modifier ingredient.
The alt gr key is a modifier key that only generates altgr alternate characters.
The option key is a modifier key that acts either as a key combination modifier ingredient.

####### distribution & history

alt gr =short for=> alt graph
alt gr was originally for producing box drawing characters.
US/european&international/mac keyboards typically have two alt/one alt and one alt gr/two option keys.
Due to historical reasons, emacs used to use the meta key as a modifier, but later switched to alt. However, it kept the label 'M' for this modifier key.

###### fn

fn =short for=> function key
fn is a modifier key or more rarely a lock key to allow access to function keys both for shortcuts and for various os/media functions.
On mac, fn + backspace simulates delete.
On laptops, fn + left/right arrow simulates home/end.
On laptops, fn + up/down arrow simulates pg up/pg down.

#### non-mode keys

##### visible character keys

###### letter keys

A letter key is a visible character key that produces a letter

##### delete/backspace

The delete/backspace key deletes characters forwards (to the right)/backwards (to the left).

##### navigation keys 

navigation keys are keys that move the content within the viewport andor the cursor.
A viewport/cursor/viewport&cursor navigation key is a navigation key that can move the content within the viewport/the cursor/both.
a real/simulated navigation key is a real navigation key on the keyboard (or at least on some keyboards)/the functionality of navigation keys simulated by a keyboard shortuct.

###### pgupdown home end

The ⟮end, home and pgup/pgdown⟯ keys ⟮move the cursor⟯ when ⟮text-editing⟯, ⟮and the view⟯ when ⟮not⟯.
  span=2;Text-editing context
Key|Action
⟮Home key⟯|⟮Move the cursor to beginning of line⟯
⟮End key⟯|⟮Move the cursor to end of line⟯
⟮Pg Up / Pg down⟯|⟮Go up/down a page⟯

  span=2;Non-text-editing context
Key|Action
⟮Home key⟯|⟮Go to beginning of document⟯
⟮End key⟯|⟮Go to end of document⟯
⟮Pg Up / Pg down⟯|⟮Go up/down a page⟯




on ⟮macOS⟯ ⟮home, end, pgup, pgdown⟯ only ever ⟮move the view.⟯‹/p›

mac, instead of home, end, pgup, pgdown
Key|does
⟮cmd + left/right⟯|⟮moves the cursor to the beginning/end of the line⟯
⟮cmd + up/down⟯|⟮oves the cursor to the beginning/end of the document⟯


###### navigation key combinations

Platform specific
Key|does
⟮alt + left/right⟯|⟮go to beginning/end of word (mac⟯)
⟮ctrl + up/down⟯|⟮go to beginning/end of word (win/linux⟯)
⟮alt + backspace/delete⟯|⟮delete to beginning/end of word (mac⟯)
⟮ctrl + backspace/delete⟯|⟮delete to beginning/end of word (win/linux⟯)
⟮cmd + backspace⟯|⟮delete to beginning of line (mac⟯)

##### dead keys



## cursor

A cursor is an indicator what thing an interaction will affect.
Cursor is ambiguous between pointing cursor and text cursor.
A pointing/key cursor is a cursor for a pointing device/keyboard.
pointer =syndef= pointing cursor 
caret =syndef= text cursor 

Some editors feature multi-cursors, which is where you can create multiple text cursors, which will perfom the edito at all places where there is a cursor.
add text cursor above/below|⟦⇧⟧ ⟦⌥⟧ ⟦↑/↓⟧
add/remove text cursor at mouse cursor location|⟦⌥⟧ ⟦click⟧
add text cursors to all occurences of current selection|⟦⌘⟧ ⟦⇧⟧ ⟦l⟧
add text cursor to nex occurrence of selection|⟦⌘⟧ ⟦d⟧

If in VSCode you have ⟮as many text cursors⟯ as ⟮the thing you want to paste has lines⟯, it will auto paste it there.