---
title: My Fedora Linux Setup
---
Im Currently running the Fedora 37 i3-spin on my T480 Thinkpad. I landed on Fedora after trying multiple different distros. I have tried many of the popular distros, Ubuntu, Debian, Manjaro, Acrh, Void. I used Debian the longest because the thing I value the most is that the distro just works. Then I started to have problems with Debian and moved to [Fedora i3 spin](https://spins.fedoraproject.org/fi/i3/).

> Inspired by David Haras's Gitlab [repo](https://gitlab.com/daveharas/fedora-i3-config).

## Installation guide for Fedora.
 The official intructions can be found [here](https://docs.fedoraproject.org/en-US/fedora/f36/install-guide/)

## Things to do after the installation.

### Configuring [DNF](https://dnf.readthedocs.io/en/latest/conf_ref.html):

At */etc/dnf/dnf.conf* you find the configuration file for DNF where we want to add the following lines.

+ *fastestmirror=True*
	+ During the next update it will seek for the fastest mirror. 

+ *max_parallel_donwloads=10*, I chose 5 packages
	+ Defaults to 3. Maximum of 20.
	+ Maximum number of simultaneous package downloads. 
	+ Depends on your network speed. 10 fits well with gigabit speed. If your have slower try 5.

+ *defaultyes=True*
	+ Download confirmation will be yes by default.
	

+ *keepcache=True*
	+ Caches downloaded packages.
	+ Future references will be faster.
	+ If cache size is a concern. Use *sudo dnf clean all* to clean the cache.

**Now update the system for changes to take place**

### Enabling [RPM Fusion](https://rpmfusion.org/Configuration)

RPM Fusion will add more packages to DNF that are free as well as nonfree. Such as proprietary drivers or media codecs.

To download RPM Fusion: *sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm*

Additionally if you will be using a graphical package manager. Install appstream-data with *sudo dnf groupupdate core*

## Congratulations now you have a **well** functioning Fedora system!
Below is a list of stuff that use the most on my computer.

### Stuff I Use

+ Ranger, terminal filemanager
+ Feh, Image viever
+ Zathura, pdf viewer
+ Neovim, text editor
+ Tlp, laptop battery saver
+ Lxappearance, appearance manager
+ Pcmanfm, filemanager
+ Kitty, terminal emulator
+ Xarchiver, archiving tool
+ Speedchrunch, calculator
+ Transmission, torrent client
+ Firefox, browser
+ i3-gaps, i3 wm with gaps
+ arandr, display manager
+ arc-theme, nice looking dark GTK3 theme
+ pandoc, file converter
+ Latex, typesetting system
+ Github, online code repository with git
+ Git, version control 
+ Rofi, app launcher

Installing all of this

*sudo dnf install ranger feh zathura zathura-pdf-mupdf neovim tlp lxappearance pcmanfam kitty xarchiver speedchrunch transmission-gtk firefox-esr i3-gaps arandr arc-theme pandoc texlive-scheme-basic gh git rofi*
