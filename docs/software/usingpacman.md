# Using the Pacman package manager

The [pacman](https://archlinux.org/pacman/) [package manager](https://en.wikipedia.org/wiki/Package_manager) is one of the major distinguishing features of CalinixOS. It combines a simple binary package format with an easy-to-use [build system](https://wiki.archlinux.org/title/Arch_Build_System). The goal of *pacman* is to make it possible to easily manage packages, whether they are from the [official repositories](https://wiki.archlinux.org/title/Official_repositories) or the user's own builds.

Pacman keeps the system up-to-date by synchronizing package lists with the master server. This server/client model also allows the user to download/install packages with a simple command, complete with all required dependencies.

## Usage

### Basic Package Operations

To search the repositories for a package type:

```
$ pacman -Ss <package-name>
```

Alternatively use the `pacsearch` utility

```
$ pacsearch -n <search-term>
```

To install the package:

```
$ pacman -S <package-name>
```

To remove a package:

```
$ pacman -R <package-name>
```

To remove a package with all it's dependencies:

```
$ pacman -Rnsc <package-name>
```

### Updating the System with Pacman

You can update your system with:

```
$  sudo pacman -Syy
```

This is the CalinixOS equivalent of `apt update` on Debian-based distributions.

To upgrade your system (basically update all of your softwae), type in:

```
$ sudo pacman -Syu
```

This is the CalinixOS equivalent of `apt upgrade` on Debian

### Listing All Installed Packages With Pacman

You can list all the packages installed on your system along with their versions by typing :

```
$ pacman -Q
```

You can also view additional information about a package by using :

```
$ pacman -Qi <package-name>
```

For example, to view the details of the package ***“firefox”***, you can type in :

```
$ pacman -Qi firefox

Name            : firefox
Version         : 86.0.1-1
Description     : Standalone web browser from mozilla.org
Architecture    : x86_64
URL             : https://www.mozilla.org/firefox/
Licenses        : MPL  GPL  LGPL
Groups          : None
Provides        : None
Depends On      : gtk3  libxt  mime-types  dbus-glib  ffmpeg  nss  ttf-font  libpulse
Optional Deps   : networkmanager: Location detection via available WiFi networks [installed]
                  libnotify: Notification integration [installed]
                  pulseaudio: Audio support [installed]
                  speech-dispatcher: Text-to-Speech
                  hunspell-en_US: Spell checking, American English
Required By     : dracnmap  eyewitness  findsploit  firefox-security-toolkit  sn1per
Optional For    : None
Conflicts With  : None
Replaces        : None
Installed Size  : 217.90 MiB
Packager        : Jan Alexander Steffens (heftig) <heftig@archlinux.org>
Build Date      : Thu 11 Mar 2021 04:15:06 PM IST
Install Date    : Tue 16 Mar 2021 01:49:16 AM IST
Install Reason  : Explicitly installed
Install Script  : No
Validated By    : Signature
```

As a bonus, you can also list all the orphaned dependencies which you have installed on your system with :

```
$ pacman -Qdt
```

### More about Installing Packages

Once you have located the package of you want to install, you can install it with :

```
$ sudo pacman -S <package-name>
```

Sometimes some packages might already be installed. In that case, this command shall reinstall them. You can however skip these packages with :

```
$ sudo pacman -S <package-name> --needed
```

You can also install packages from a `tar.zst` file using ***pacman*** with the help of the following syntax :

```
$ sudo pacman -U <package-file>
```

Other common pacman commands include:

* `pacman -R $(pacman -Qdtq)` - removes packages installed as dependencies that are no longer required by currently installed programs.
* `pacman -Syup` - checks for updates, and displays the urls of packages that need updating.
* `pacman -Sc` - clears package cache.

For more Pacman commands refer to the man pages by typing `man pacman` at the command-line, or [Pacman Read The Docs](https://wiki.archlinux.org/title/pacman)

## Excluding Packages From Transactions

Sometimes it is useful to ignore specific packages from transactions, such as updates. One such case, for example, could be when an update includes a regression or a bug. Pacman allows you to exclude a package from the transaction:

* using the command line

```
sudo pacman -Syu --ignore=<package-name>
```

* using its configuration files

You can add a line to `/etc/pacman.conf` to exclude packages:

```
IgnorePkg=<package-name>
```

If you use a GUI update application which does not allow you to specify packages to exclude when they run, this method can be used.
