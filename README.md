# SALT

First WTF is this? 
+It's flasher tool for LG SmartPhones on Linux.

Cool how can i use it?
+Follow the instractions below.

SALT - [S]teadfasterX [A]ll-in-one [L]G [T]ool

08/09/2021
Fixed/Tested on Ubuntu 18.04 LTS.

Install

On Arch: 
          
    $ sudo pacman -Sy polkit git xterm python-pyusb python-crypto python-pip
    $ trizen -Sy yad python-zstandard (hint: you may need to install trizen first) - 
		you need to manually do this until it has been fixed upstream: workaround
    $ pip3 install cryptography
Manjaro:

    $ sudo pacman -Sy polkit yad git xterm python-pyusb python-crypto trizen python-pip python-zstandard
    $ pip3 install cryptography
Ubuntu, Debian, Mint etc:

    $ sudo apt install policykit-1 yad git xterm python3 python3-usb python3-crypto python3-pip
    $ pip3 install zstandard and sudo pip3 install cryptography
