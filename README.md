# PyRadio

Command line internet radio player.

![Pyradio](https://members.hellug.gr/sng/pyradio/pyradio.png)

## IMPORTANT

**PyRadio** may fail to install/update on some linux distros (mainly Ubuntu 23.04, Debian and derivatives, etc.) due to a change to the underlined python installation.

If you face this situation, please refer to [this page](docs/pip-error.md) to resolve the problem.

## Table of Contents
<!-- vim-markdown-toc Marked -->

* [Features](#features)
* [Requirements](#requirements)
* [Installation](#installation)
* [Basic usage](#basic-usage)
* [Update notification](#update-notification)
    * [Updating a pre 0.8.9 installation](#updating-a-pre-0.8.9-installation)
* [Reporting bugs](#reporting-bugs)
* [Packaging PyRadio](#packaging-pyradio)
* [TODO](#todo)
* [Acknowledgment](#acknowledgment)
* [Special thanks](#special-thanks)

<!-- vim-markdown-toc -->

* Please follow this link for the [Detailed documentation](docs/index.md)

## Features

**PyRadio** provides the following features:

 - vi like keys in addition to arrows and special keys
 - Station editor (add/edit) with [CJK characters support](#cjk-characters-support)
 - Configuration editor
 - Multiple playlist support
 - vi like station registers
 - Search function
 - Theming support
 - [RadioBrowser](docs/radio-browser.md) support
 - Remote Control
 - Easy installation / updating
 - Runs on Linux, macOS and Windows

and much more...

## Requirements
* python 2.7/3.5+
    - setuptools
    - wheel
    - requests
    - dnspython
    - psutil
    - rich
    - python-dateutil
    - netifaces (optional)
* MPV, MPlayer or VLC installed and in your path
* MKVToolNix (cli files) to insert tags, chapters and cover to recordings (optional)

<!-- Changelog -->

## Installation

The best way to install **PyRadio** is via a distribution package, if one exists (*Arch Linux* and derivatives can install [any of these packages](https://aur.archlinux.org/packages/?K=pyradio) from the AUR, *FreeBSD* users will find it in the [ports](https://www.freshports.org/audio/py-pyradio/), etc.).

In any other case, and since **PyRadio** is currently not available via pip, you will have to [build it from source](docs/build.md).

## Basic usage

After a successful installation, the command to execute is:

    pyradio

This will display the program's window with a list of predefined radio stations ready to be played.

 - Select one of the station (using the arrow keys) and press "**ENTER**" to start playback.

- Press "**+**" (or "**.**") and "**-**" (or "**,**") to adjust the volume, and "**v**" to save it.

- Pressing "**?**" will give you access to the help screens; "**\\h**" will give you access to the help pages.

- "**Esc**" or "**q**" will exit the program.

In case the list of predefined stations are not enough for you, you can press "**O**" (capital "**o**") to access **RadioBrowser** online directory; you will probably have to read [this page](docs/radio-browser.md) to learn how to navigate the interface.

Finally, when you are ready to dive into the program's numerous features, you can refer to the [detailed documentation](docs/index.md).

## Update notification

**PyRadio** will periodically (once every 10 days) check whether a new version has been released.

If so, a notification message will be displayed, informing the user about it and asking to proceed with updating the program (provided this is not a distribution package).

### Updating a pre 0.8.9 installation

First thing you do is get the installation script. Open a **terminal** and type:

    cd
    wget https://raw.githubusercontent.com/coderholic/pyradio/master/pyradio/install.py

or using curl:

    cd
    curl -L https://raw.githubusercontent.com/coderholic/pyradio/master/pyradio/install.py -o install.py

**Note**: If you have neither *wget* or *curl* installed, or you are on Windows, just right click on [this link](https://raw.githubusercontent.com/coderholic/pyradio/master/pyradio/install.py) and use your browser "**Save link as**" menu entry to save the file in your home folder.

Finally, execute the command:

    python install.py --force

## Reporting bugs

When a bug is found, please do report it by [opening an issue at github](https://github.com/coderholic/pyradio/issues), as already stated above.

In you report you should, at the very least, state your **pyradio version**, **python version** and **method** of installation (built from source, AUR, snap, whatever).

It would be really useful to include **~/pyradio.log** in your report.

To create it, enter the following commands in a terminal:

    $ rm ~/pyradio.log
    $ pyradio -d

Then try to reproduce the bug and exit **pyradio**.

Finally, include the file produced in your report.

## Packaging PyRadio

If you are a packager and would like to produce a package for your distribution please do follow [this mini guide](docs/packagers-info.md).

## TODO

- [ ] Any user request I find interesting :)
- [ ] Use some kind of a scheduler
- [x] Use Radio Browser service ([#80](https://github.com/coderholic/pyradio/issues/80) [#93](https://github.com/coderholic/pyradio/issues/93) [#112](https://github.com/coderholic/pyradio/issues/112)) - v 0.9.0
- [ ] Use some OPML service, [https://opml.radiotime.com](https://opml.radiotime.com) for example
- [x] Notify the user that the package's stations.csv has changed -v 0.8.9
- [x] Update / uninstall using command line options (-U / -R) - v. 0.8.9
- [x] Basic mouse support ([#119](https://github.com/coderholic/pyradio/issues/119)) - v. 0.8.8.3
- [x] Players extra parameters ([#118](https://github.com/coderholic/pyradio/issues/118)) - v. 0.8.8.3
- [x] New player selection configuration window ([#118](https://github.com/coderholic/pyradio/issues/118)) - v. 0.8.8.3

## Acknowledgment

**PyRadio** uses code from the following projects:

1. [CJKwrap](https://gitlab.com/fgallaire/cjkwrap) by Florent Gallaire - A library for wrapping and filling UTF-8 CJK text.

2. [ranger](https://ranger.github.io/) - A console file manager with VI key bindings.

3. [Vifm](https://vifm.info/) -  A file manager with curses interface, which provides a Vi[m]-like environment.

## Special thanks

1. [edunfelt](https://github.com/edunfelt), for her wonderful work on [base16 themes](https://github.com/edunfelt/base16-pyradio), and ideas regarding theming and such.
