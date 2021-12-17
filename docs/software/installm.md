# Finding and installing Linux applications

Many powerful software applications are available on the Linux operating system. You can find alternatives to most of the popular applications used on other systems.

You can use the CalinixOS package management system to install applications. Most essential applications are available from the repositories provided by chaotic-aur, arcolinux, arch linux and Calinix project. You can enable other repositories to get additional applications.

## Package management in CalinixOS

Like most modern Linux distributions, CalinixOS uses a *package management* system. Package management tools automate installation, upgrading, and removing of software applications and components.

Each application or component is defined as a *package*. When the package is installed, all code, configuration, and other files are deployed on the system.

A single package is not necessarily the same as an application. Some applications can be shipped as several packages. Moreover, shared code (libraries) in Linux is normally shipped as separate packages, while in other systems applications often ship their own versions of required libraries and install them if necessary.

### File placement

The package management tools track which files on your CalinixOS installation belong to each package; normally, every file that is installed in the `/usr` tree as well as most configuration files under `/etc` are installed by one of the packages. When installing a package, the package management system verifies its integrity; if any files are missing or corrupted, the package is not installed.

### Resolving dependencies

The package management system also tracks all *dependencies* between the packages. For example, if an application requires some libraries, the package for this application lists the libraries as dependencies. When you install the application package, the package management tools automatically install the library packages. If a dependency is not available, the tools do not install the package, so you can avoid a sudden malfunction.

When you want to remove a package, package management tools cleanly delete all code files for this package without affecting other packages. By default, configuration files are not removed, so you can install the package again and keep the configuration that you have set up earlier.

### Updating packages

Updating any package is entirely automatic with the package management system. The system replaces all the necessary code files and preserves existing configuration.

In fact, for most Linux distributions, including CalinixOS, all of the system installation except the earliest part is performed by installing various packages. Security updates and upgrades to a next release are performed entirely by package management tools.

### Repositories

To get packages, Pacman uses *repositories*. A repository is an organized collection of packages. Repositories can be kept on any data media; notably, the CalinixOS installation image contains a repository. However, most up-to-date repositories are normally maintained online.

Each CalinixOS release has an official *calinix* repository and few other repositories like the chaotic-aur repository (which contains pre-built packages from the Arch User Repository), ArcoLinux 3rd party and ArcoLinux X-Large repositories (which again contain a large number of software outside the official Arch Linux repositories and are maintained regularly). And ofcourse the Arch Linux Repositories which make Calinix very close to actual Arch Linux. In these repositories, you can find almost any Linux software. You can also install packages from other repositories, not maintained by the CalinixOS project and known as *third-party repositories*.

### Installing from source code

While many Linux applications can be built and installed from from source code, using such builds can make your system much harder to manage. For example, automatic updates to system packages (especially when updating to the next release) might impact an application that was installed from source. And, of course, no automatic security updates are available for the application.

### Other installation methods

Sometimes you might need to install software using other package management systems. Notably:

* [CPAN](https://www.cpan.org/) for libraries for the Perl language
* [PyPI](https://pypi.python.org/pypi) for libraries (and sometimes applications) for the Python language
* Commercial repositories for games

However, installing applications using the CalinixOS package management systems is the preferred option.

## Searching for Linux software alternatives on the Web

To complete your tasks on a Linux system, you need to find the software applications that fit your needs. If you are switching from another operating system, you might need to find replacements for the software that you used before.

Most applications available on Linux are open-source software. You can use open-source software without acquiring any licenses. Moreover, widespread open-source software is usually available in the official CalinixOS repository, so you can install it easily.

Procedure

Access the following websites to review Linux alternatives to popular software packages:

* https://linuxappfinder.com/alternatives
* https://www.linuxalt.com/
* https://opensource.com/alternatives
* https://www.osalt.com/
* https://alternativeto.net/

## Browsing and installing software on CalinixOS

You can use a graphical utility to browse the available software packages. When you find the software that you want, you can use the utility to install it on your CalinixOS system.

Before you start

To install any packages on your CalinixOS system, you need to have **root** privileges.

Procedure

1. On your GNOME desktop, select the **Activities** menu and then click the ![Software](https://docs.CalinixOSproject.org/en-US/quick-docs/_images/packages_icon_software.png) icon.
2. Find a software package in one of the following ways:

  * Click one of the suggested categories, for example, **Productivity**. Then review the suggested packages. To see more packages, select items in the menu in the left-hand part of the window. For example, for the Productivity category, you can select **Calendar**, **Database**, **Finance**, **Word Processor**.
  * Choose one of the **Editor’s Picks** or other recommended software in the window.
  * Click the ![Search](https://docs.CalinixOSproject.org/en-US/quick-docs/_images/packages_icon_search.png) icon, then enter a keyword or the name of the application. Review the suggested packages.

3. Click a package to read its description.
4. To install the package, click the **Install** button. When prompted, provide the root password.

## Installing software packages using the command line

You can install packages in CalinixOS using the DNF utility.

Before you begin

You must execute the command with **root** privileges. Use one of the following methods:

* Prefix the command with `sudo` and provide your user password. The `sudo` command must be enabled for your user.
* Use the `su` command and provide the root password to switch to a root prompt in a terminal window.
* Log in as `root` on a virtual console.

You must know the name of the package. Any dependencies will be installed automatically.

Procedure

1. Run the command:

# dnf install <packagename>

where `<packagename>` is the name of the package.

2. Answer `y` to any prompts, if necessary.

## Enabling third-party repositories

You can install software packages from repositories that are not supported by the CalinixOS project, known as third-party repositories.

### RPM Fusion

The most commonly used third-party repository is [RPM Fusion](https://rpmfusion.org/). It provides packages that can not be included in CalinixOS because of US software patents or other similar reasons. Among other things, RPM Fusion provides packages necessary for viewing media in many common formats. RPM Fusion packages are extensively tested, but they are not supported by the CalinixOS project.

### Copr

A set of repositories for CalinixOS is known as [Copr](https://copr.CalinixOSinfracloud.org/). Developers can provide packages in Copr repositories for software that is not at present included in CalinixOS. **These packages might be untested.**

### Application-specific repositories

Certain non-free applications for Linux, such as Google Chrome or Skype, provide their own repositories for CalinixOS.

To install software from a third-party repository, you must first *enable* that repository. Then the packages from the repository become available in the command line and graphical package management tools.

If you enable a third-party repository, packages that you did not explicitly select might also be installed from the repository. Do not enable repositories that you do not trust. The CalinixOS project does not support third-party repositories.

Procedure

To enable a third-party repository, follow the instructions provided by the repository. For example:

* For RPM Fusion, https://rpmfusion.org/Configuration
* For Copr repositories, https://docs.pagure.org/copr.copr/how_to_enable_repo.html