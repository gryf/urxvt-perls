Deprecated perl extensions for the rxvt-unicode terminal emulator.

See the file README.md in the parent directory for installation instructions,
in case you still want to use them.


clipboard
---------

**DEPRECATED**

Since version 9.20 rxvt-unicode natively supports copying to and pasting from
the CLIPBOARD buffer with the `Ctrl-Meta-c` and `Ctrl-Meta-v` key bindings. The
`clipboard.autocopy` setting is provided by the `selection-to-clipboard`
extension shipped with rxvt-unicode.

Use keyboard shortcuts to copy the selection to the clipboard and to paste the
clipboard contents (optionally escaping all special characters).

After installing, put the following lines in your .Xdefaults/.Xresources:

    URxvt.perl-ext-common: ...,clipboard
    URxvt.keysym.M-c:   perl:clipboard:copy
    URxvt.keysym.M-v:   perl:clipboard:paste
    URxvt.keysym.M-C-v: perl:clipboard:paste_escaped

Options:

    URxvt.clipboard.autocopy: if set to true, the clipboard is automatically
                              updated whenever the PRIMARY selection changes

You can also overwrite the system commands to use for copying/pasting.
The default ones are:

    URxvt.clipboard.copycmd:  xsel -ib
    URxvt.clipboard.pastecmd: xsel -ob

If you prefer xclip, then put these lines in your .Xdefaults/.Xresources:

    URxvt.clipboard.copycmd:  xclip -i -selection clipboard
    URxvt.clipboard.pastecmd: xclip -o -selection clipboard

On Mac OS X, put these lines in your .Xdefaults/.Xresources:

    URxvt.clipboard.copycmd:  pbcopy
    URxvt.clipboard.pastecmd: pbpaste

The use of the functions should be self-explanatory!
