# latam-dvorak
### A Latin American Spanish Dvorak keyboard layout.

This this the new Latin American Spanish Dvorak layout:

![](im/new-latam-dvorak.png)

Improvements:

* It's based on Latin American QWERTY keyboard
* There  are some  keyboards  with  additional symbols  and  now  it's easier  change  physical
  keys. Usually Q (@) and Ñ (~)
* Detailed lvl3 symbols.

## Installation on X.Org
I suggest to back up the `/usr/share/X11/xkb/symbols/latam` file. For example, in Ubuntu:

    sudo cp /usr/share/X11/xkb/symbols/latam /usr/share/X11/xkb/symbols/latam.bak

Copy the `latam` file to the  `/usr/share/X11/xkb/symbols` directory, or alternatively apply the
patch `01-dvorak-latam.patch`to the `/usr/share/X11/xkb/symbols/latam` file.

## Installation on console (now available in some distros by default)
Copy `dvorak-la.map.gz` on the dvorak keymaps directory (Usually `/usr/share/keymaps/i386/dvorak/`):

     sudo cp dvorak-la.map.gz /usr/share/keymaps/i386/dvorak/

Some distros use /etc/conf.d/keymaps to handle keyboard configuration. Edit it to configure your
keyboard.

     keymap="dvorak-la"

Or it is possible to set the keymap just for current session:

     loadkeys dvorak-la

## Installation on GRUB
Copy `latam-dvorak.gkb` on the layouts directory (Usually `/boot/grub/layouts/`):

    sudo cp latam-dvorak.gkb /boot/grub/layouts/
	
Add the options to the GRUB config, `/etc/grub.d/40_custom` is recommended:

    terminal_input at_keyboard
    keymap latam-dvorak

Optionally, you can generate your own gkb file with the files lacated on `ckbdcomp` directory on
this repository  and the  command `grub-mklayout`.  That files are  just the  `ckbdcomp` command
output.
