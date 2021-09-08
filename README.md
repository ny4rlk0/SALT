# SALT

First WTF is this? 

    $ +It's flasher tool for LG SmartPhones on Linux.

Cool how can i use it?

    $ Follow the instractions below.

Clone repostory with:

    $ git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY

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

    $ sudo apt install adb fastboot policykit-1 yad git xterm python3 python3-usb python3-crypto python3-pip
    $ pip3 install zstandard and sudo pip3 install cryptography
    
Add your device:

    $ dmesg | tail

Now, you can ge the idVendor and idProduct. It will be something like this:

    $ [24936.555273] usb 1-2: USB disconnect, device number 9
    $ [24939.022181] usb 1-2: new high-speed USB device number 10 using xhci_hcd
    $ [24939.187152] usb 1-2: New USB device found, idVendor=04e8, idProduct=6860
    $ [24939.187154] usb 1-2: New USB device strings: Mfr=1, Product=2, SerialNumber=3
    $ [24939.187156] usb 1-2: Product: SAMSUNG_Android
    $ [24939.187157] usb 1-2: Manufacturer: SAMSUNG
    $ [24939.187158] usb 1-2: SerialNumber: 5ae1b464
    $ [24939.188132] cdc_acm 1-2:1.1: ttyACM0: USB ACM device

add the following line to your /etc/udev/rules.d/51-android.rules (Beware, you need to change idVendor, idProduct and username to yours):

    $ sudo nano /etc/udev/rules.d/51-android.rules
    $ SUBSYSTEM=="usb", ATTR{idVendor}=="2a70", ATTR{idProduct}=="9011", MODE="0600", OWNER="username"
    $ sudo adb kill-server
    $ sudo adb start-server
    $ adb devices -l
    $ If still cannot see your phone with above command open your debug mode in android and change usb mode from mtp to p2p (or any other mode then set it back).
