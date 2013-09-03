========================================
Customize US keyboard layout for GNOME 3
========================================

Since Gnome 3 "Region and Language Settings" input sources list doesn't
support adding custom XKB maps, as far as I was able to find, and
xmodmap settings disappear as soon as you switch between sources, this
file replaces the symbols/pc file in (Arch Linux) /usr/share/X11/xkb/ to
rotate the Escape, Left Control, and Caps Lock keys. Just copy the `pc`
file in this directory over that file and enjoy.

Incidentally, I can't believe there's no option to do this already:
there's 'ctrl:swapcaps' and 'caps:swapescape' but no option to swap
Control and Escape even though LCTL is a *way* better location for
Escape than all the way up in the left corner.


Appendix
========

To find out which files are being included by the current XKB keymap,
use `setxkbmap -print`, like so::

    $ setxkbmap -print
    xkb_keymap {
            xkb_keycodes  { include "evdev+aliases(qwerty)" };
            xkb_types     { include "complete"      };
            xkb_compat    { include "complete"      };
            xkb_symbols   { include "pc+us+inet(evdev)"     };
            xkb_geometry  { include "pc(pc104)"     };
    };
