# Package Management System

## Introduction

CalinixOS is a distribution that uses a package management system. This system is based on [the Arch Linux Package Management System](https://wiki.archlinux.org/title/Arch_Build_System) , with the [pacman](https://wiki.archlinux.org/title/Pacman) Package Manager and with several higher level tools built on top of it, most notably [Pamac](https://wiki.manjaro.org/index.php/Pamac) (default gui). CalinixOS comes with [yay](https://github.com/Jguer/yay) preinstalled which is an [AUR Helper](https://wiki.archlinux.org/title/AUR_helpers). Know more about the [AUR/Arch User Repository](https://wiki.archlinux.org/title/Arch_User_Repository)

## Advantages of package management systems

Package management systems have many advantages:

* It’s easy to query what version of a package is installed or available.
* It’s easy to remove a package entirely, making sure all its files are gone.
* It’s easy to verify the integrity of the packages files, so you can see if it’s been corrupted or tampered with.
* It’s easy to upgrade a package by installing the new version and removing all the old versions files. This will make sure not to leave any lingering files from the old package around to confuse or break things.
* It’s easy to see what packages require or provide things that other packages provide or require, so you can be sure to have the needed items for the package to function correctly.
* It’s easy to install or remove groups of packages.
* In many cases it’s possible to downgrade back to a previous version of a package, for example when a new version has a bug.

## Disadvantages of package management systems

* You are restricted to either using the versions of the package that are available or having to make your own package if you need a different version.

## Preferred search order for a software

If some software is missing in your installation then you should try the following steps to get the packaged version:

1. Search in Calinix ( 'yay foo' or search for 'foo' in the Pamac gui )
2. Try searching up the [AUR](https://aur.archlinux.org/) repositories and install them through [yay](https://github.com/Jguer/yay)
3. [Build your own package](https://wiki.archlinux.org/title/creating_packages)

## Package Management tools

- [pacman](https://wiki.archlinux.org/title/Pacman) - The pacman package manager is one of the major distinguishing features of Arch Linux. It combines a simple binary package format with an easy-to-use build system.

- [yay](https://github.com/Jguer/yay) - Yet Another Yoghurt, a fast and simple AUR Helper

- [pamac](https://wiki.manjaro.org/index.php/Pamac) - pamac gui tool ('add/remove software' in your menu)

See a typo, something missing or out of date, or anything else which can be improved? Edit this document at [Github](https://github.com/Calinix-Team/Calinix-docs).