
## local variants

Keyboards are often identified based on ⟮their first few keys on the top letter row⟯
QUERTY|en
QWERTZ|de
AZERTY|fr

Between english and german keyboards, the only difference in actual letters in that z and y are flipped.

strg   ctrl

## modes

Lock keys are keys that enter/exit a mode.
Lock keys: {caps lock, shift lock, num lock, insert}
The insert key is a lock key that switches between insert and overtype mode.
in the 2020s, insert mode is common, overtype is barely used.
In overtype mode, typing replaces characters to the right
In insert mode, typing moves the characters in the right further to the right.

The cursor is reasonably wide   overtype mode
The cursor is reasonably narrow   insert mode (the kind of thing that the ins key changes)

caps lock|makes all latin characters generate uppercase characters but not alternate characters
shift lock|acts as shift was continuously pressed, that is, generates both uppercase and alternate characters respectively

On ⟮windows⟯ under ⟮certain keyboard layouts⟯, ⟮h14;e.g. ⟮AZERTY and QWERTZ⟯,⟯ the ⟮caps lock key⟯ ⟮acts as shift lock⟯, ⟮hb;however not on ⟮mac⟯, and ⟮there is no setting to make it so⟯, making ⟮any solution requiring scripting via Hammerspoon or Karabiner⟯.⟯ 
Many operating systems support ⟮typing 'normal' characters⟯ by ⟮pressing shift⟯ when in ⟮capslock / shiftlock mode⟯⟮hb;, however, not ⟮mac⟯⟯. 

## types of keys

### modifier keys

modifier keys are keys that maintain a quasimode.
modifier keys that are found on any hardware keyboard as of 2020 are shift, ctrl, alt/option/altgr, win/cmd/linux equivalent.
On small layout keyboards, the additional modifier key function is often present.
the function key is often abbreviated fn.
Windows and linux treat ctrl as their primary modifier key, while mac treats cmd as the primary modifier keys.
Originally, super, meta and hyper keys were all dedicated modifier keys present on some keyboards.
today, different linux distros treat meta or super as their equivalent to cmd/windows.
today, since hyper keys are not really present anywhere, hyper key refers to a fictional modifier key created by simulating an insane number of modifier keys at the same time by pressing a different non-modifier key (often e.g. capslock)f

#### alt/option

alt gr = alt graph
alt gr was originally for producing box drawing characters.
Despite having similar names, alt and alt gr generally share no functionality.
alt gr produces a quasimode for alternative characters similar to shift. 
US keyboards typically have two normal alt keys.
European/international keyboards typcially have one alt and one alt gr key.
The mac option key has functionality of both the alt and alt gr keys: it can be used as a key in key command like alt, but can also produce additional characters like alt gr.
Due to historical reasons, emacs used to use the meta key as a modifier, but later switched to alt. However, it kept the label 'M' for this modifier key.

### delete/backspace

Delete key|Delete characters forwards (to the right)
Backspace key|Delete characters backwards (to the left)

### navigation keys 

navigation keys are keys that move the viewport or the cursor.

#### pgupdown home end

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


The ⟮function key⟯ is used to ⟮simulate home/end/pgup/pgdown⟯ via ⟮the arrow keys⟯ on ⟮smaller formfactors⟯. 

  span=2;Laptops and other small form factors
Is simulated by|Key combination
⟮Home key/End key⟯|⟮fn left/right arrow⟯
⟮Pg Up / Pg down⟯|⟮fn + up/down arrow⟯


on ⟮macOS⟯ ⟮home, end, pgup, pgdown⟯ only ever ⟮move the view.⟯‹/p›

mac, instead of home, end, pgup, pgdown
Key|does
⟮cmd + left/right⟯|⟮moves the cursor to the beginning/end of the line⟯
⟮cmd + up/down⟯|⟮oves the cursor to the beginning/end of the document⟯


#### navigation key combinations

Platform specific
Key|does
⟮alt + left/right⟯|⟮go to beginning/end of word (mac⟯)
⟮ctrl + up/down⟯|⟮go to beginning/end of word (win/linux⟯)
⟮alt + backspace/delete⟯|⟮delete to beginning/end of word (mac⟯)
⟮ctrl + backspace/delete⟯|⟮delete to beginning/end of word (win/linux⟯)
⟮cmd + backspace⟯|⟮delete to beginning of line (mac⟯)

## caret

cursor can be text or mouse
mouse cursor = pointer
text cursor = caret

Some editors feature multi-cursors, which is where you can create multiple text cursors, which will perfom the edito at all places where there is a cursor.
add text cursor above/below|⟦⇧⟧ ⟦⌥⟧ ⟦↑/↓⟧
add/remove text cursor at mouse cursor location|⟦⌥⟧ ⟦click⟧
add text cursors to all occurences of current selection|⟦⌘⟧ ⟦⇧⟧ ⟦l⟧
add text cursor to nex occurrence of selection|⟦⌘⟧ ⟦d⟧

If in VSCode you have ⟮as many text cursors⟯ as ⟮the thing you want to paste has lines⟯, it will auto paste it there.