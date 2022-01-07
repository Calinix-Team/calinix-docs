# Adding new fonts in CalinixOS

CalinixOS pre-installs several basic fonts by default. This page explains how to add new fonts to a CalinixOS installation.

## Packaged fonts

Did you know CalinixOS packages several freely-licensed fonts? There are several supplementary fonts to preview and try out that are not installed by default. Like all fonts on CalinixOS, these fonts are not encumbered with licenses or restrictions.

An added benefit of packaged fonts is they give you control over the font package in the future. You will receive future updates and can easily uninstall it later if you decide it is not the font for you.

If you prefer working in a C.L.I., you can install fonts with `yay`.

List all available font packages from enabled repositories

```
yay font
```

Install the font package you need by selecting them.

## Unpackaged fonts

In many cases, you may want to use a specific font that is not available in CalinixOS or is not made available under [Free Culture](https://freedomdefined.org/Definition) licenses.

Unpackaged fonts are not managed by a package manager. You will not automatically receive updates or optimizations. If a font is provided by a distribution package, you should always use a packaged version of a font.

### System fonts

System fonts are installed for all users. Anyone with an account on the machine will be able to use these fonts.

Create a new directory `/usr/share/fonts/<font-family-name>/` for the new font family

`sudo mkdir /usr/share/fonts/robofont`

Copy font files (e.g. `.ttf` files) to the new directory

`sudo cp ~/Downloads/robofont.ttf /usr/share/fonts/robofont`

Update the font cache

`sudo fc-cache -v`

### User fonts

User fonts are installed for an individual user. Only the user who installs the fonts on the machine will be able to use these fonts. This is also convenient if you do not have superuser (i.e. `root`) access on the machine.

If you prefer a command line interface, you can install user fonts manually. Follow these steps in a terminal window to install a font locally:

Create a new directory `~/.local/share/fonts/<font-family-name>/` for the new font family

`mkdir -p ~/.local/share/fonts/robofont`

Copy font files (e.g. `.ttf` files) to the new directory

`cp ~/Downloads/robofont.ttf ~/.local/share/fonts/robofont`

Update the font cache

`fc-cache -v`