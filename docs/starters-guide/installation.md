# Installation Guide

## Booting the Live environment

Booting the Live environment, whether from CD/DVD or USB flash
drive, will give you an overview of the CalinixOS environment
and let you test how well it will run on your machine. This is very
useful to check before committing to install a new operating system!
For best results you should be connected to the Internet. If you
have a wired Ethernet connection, and plug in before booting the
Live environment, CalinixOS will automatically set up a connection.
If you have a wireless (Wi-Fi) connection you can set up the wireless
network once you have reached the CalinixOS desktop. Just click the arrow icon in the taskbar

![](../assets/tasright.png)

And click the Network Manager applet (which will probably show a `<->` sign if not connected). Connect to internet using the applet.

The method of selecting the boot device varies considerably across
machines. You may need to spam (tap continuosly) one key, for example Esc, Del,
or F10, to select the boot device. Or, you may need to set the option in your BIOS. If you’re not sure, your machine’s user guide will have detail of the method you need, alternatively a web search will
also quickly turn up the answer.

!!! Note
    On Macs, keep your finger pressed on the Alt or Option key after hearing the boot sound.

### BIOS vs UEFI

!!! Note
    UEFI is the commonly agreed on name for both the EFI & UEFI standards which merged. It does not include the old EFI v1, or Apple’s own
    non-standard version of EFI.

Some newer hardware do not use the well-known BIOS to manage
boot options. Instead, a new one named UEFI (Unified Extensible
Firmware Interface) is used. It still has BIOS-like menus and often
has a legacy mode, which uses BIOS. UEFI often goes hand in hand
with the infamous Secure Boot option that makes it more difficult
to boot operating systems outside of a select few. If your computer
came with **Microsoft Windows 8** or later installed, your computer
probably uses UEFI and has Secure Boot enabled by default. 

However, the Linux community reacted to this and developed means to
install and boot Linux on those systems as well. Some installers,
such as Calamares which is used by CalinixOS, can even automate the
process so it makes virtually no difference to the user whether their
machine uses UEFI or BIOS.

#### Booting in UEFI mode

The most important step is to ensure that **your machine does not
have Fast Boot enabled**. Only a very limited number of operating
systems will boot with this enabled. You must disable Fast Boot
in your UEFI/BIOS before proceeding; if you don’t know how to do
this please refer to your computer’s user manual, as it differs for all
computers.