# latam-dvorak
### A Latin American Spanish Dvorak keyboard layout for X.Org.

![](https://dl.dropbox.com/u/1116031/images/latam-dvorak.png)

## Installation
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