# latam-dvorak
### A Latin American Spanish Dvorak keyboard layout.

This is the original layout and It's based in Spanish Dvorak layout:

![](https://dl.dropbox.com/u/1116031/images/latam-dvorak.png)

This this the new Latin American Spanish Dvorak layout:

![](im/new-latam-dvorak.png)

Improvements:

* It's based on Latin American QWERTY keyboard
* There  are some  keyboards  with  aditional symbols  and  now  it's easier  change  physical
  keys. Usually Q (@) and Ñ (~)
* Detailed lvl3 symbols.

## Installation on X.Org
I suggest to back up the `/usr/share/X11/xkb/symbols/latam` file. For example, in Ubuntu:

    sudo cp /usr/share/X11/xkb/symbols/latam /usr/share/X11/xkb/symbols/latam.bak

Copy the `latam` file to the `/usr/share/X11/xkb/symbols` directory, or alternatively append the contents of `latam-dvorak` into the `/usr/share/X11/xkb/symbols/latam` file.

To make the layout available in Ubuntu, edit the `/usr/share/X11/xkb/rules/evdev.xml` file and add the variant within the `latam` layout. Look at the example below:

    <layout>
      <configItem>
        <name>latam</name>
        
        <shortDescription>es</shortDescription>
        ...
      </configItem>
      <variantList>
        <variant>
          <configItem>
            <name>dvorak</name>
            <description>Spanish (Latin American, Dvorak)</description>
          </configItem>
        </variant>
        ...
      </variantList>
    </layout>

In the `/usr/share/X11/xkb/rules/evdev.lst` file, add the following entry under the `! variant` list:

      dvorak          latam: Spanish (Latin American, Dvorak)

## Installation on console (now available in some distros by default)
Copy `dvorak-la.map.gz` on the dvorak keymaps directory (Usually `/usr/share/keymaps/i386/dvorak/`):

     sudo cp dvorak-la.map.gz /usr/share/keymaps/i386/dvorak/

Some distros use /etc/conf.d/keymaps to handle keyboard configuration. Edit it to configure your keyboard. 

     keymap="dvorak-la"

Or it is possible to set the keymap just for current session:

     loadkeys dvorak-la
