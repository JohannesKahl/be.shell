Description
======

This repository contains my configs and relative themes for [BE::Shell](http://sourceforge.net/p/be-shell/code/ci/master/tree/).

**Reference**

- [BE::Shell official wiki](https://sourceforge.net/p/be-shell/wiki/browse_pages/)
- [Qt Stylesheet documentation](http://qt-project.org/doc/qt-4.8/stylesheet-reference.html)

**Important notes** 

- Due to the absolute positioning in BE::Shell themes may need adjustments within the css or the config file
- Some configurations use external scripts as info providers [e.g. skutter], which need to be installed and configured separately in most of the cases
- In the instructions below scripts and menus are installed under ~/.local, instead of using the default configuration directory for be.shell. This decision has been made to prevent issues with different kde4 configuration paths
- In all of my themes i used the [DSP](http://sourceforge.net/p/styleproject/code/ci/master/tree/) Qt style and KWin decoration. Usually a dsp preset is included within the subdir "extra" of the specific theme

**Issues**

- GlobalMenu:
 - Since many asked, in case the applications menubar is not exported in the globalmenu follow the instructions
 [here](https://github.com/Hombremaledicto/be.shell/wiki/Menubar-exportation)
 - In case not even the default entries are shown but the applications *do not* have the menubar visible(after starting BE::Shell), it is most probably due to some value within the theme css (font, padding or margin) than can be easily fixed. Rightclick on the desktop → Themes → Edit Current. Check the values for GMenu.
- Buttons/TaskBar:
 - Blank icons in taskbar: This is due to the fact that sticky buttons are set for applications you most likely do not have installed. Simply edit the config (rightclick on the desktop → Config → Edit current) and remove their entry in the Buttons list under Type=TaskBar. Then save and reload the config.


Installation
======

Before to proceed, install BE::Shell if you haven't done it yet (instructions on its [wiki](http://sourceforge.net/p/be-shell/wiki/Installation/). As for KDE Plasma5, i also suggest to read [this](https://github.com/Hombremaledicto/be.shell/wiki/BE::Shell-on-KF5) page), then clone this repository:

    git clone --recursive https://github.com/Hombremaledicto/be.shell.git

And enter into the source folder:    

    cd be.shell
    
You can either install presets using the provided script or copying the files manually.
   
**By script**

**NOTE:** _The script shipped with this repository assumes you're on a KDE4 or Plasma5 session and makes use of some KDE tools already preinstalled on most distributions (kreadconfig & kwriteconfig are mandatory).
Optionally, in case kde4 python bindings are installed, it will copy & apply on the fly a kde4 colorscheme, if the preset provides one._

To start the script in interactive mode, simply type:

    ./be.installer -p
    
Or, alternatively, you can skip the list of available presets and specify directly the one you want, passing its name after the -p argument - e.g. for be.shell.Vertex :

    ./be.installer -p Vertex
    
**NOTE:** By default the script will ask if you want to backup your current config and theme, this functionality can also be invoked with:

    ./be.installer -b
    
To get a list of all the commands:

    ./be.installer -h
    
 **Manually**
 
If this is the first time you install BE::Shell, you need to create its configuration and themes folders:

    mkdir -p `kde4-config --localprefix`/share/apps/be.shell/Themes
 
Copy the Theme directory: 

    cp -r Themes `kde4-config --localprefix`/share/apps/be.shell/

Copy one of the included config file (in this example Vertex.conf) as be.shell:

    cp Config/Vertex.conf `kde4-config --localprefix`/share/config/be.shell
    
Install the provided scripts:

    mkdir -p ~/.local/share/be.shell
    cp -r Scripts ~/.local/share/be.shell && chmod -R 777 ~/.local/share/be.shell/Scripts/*
    
Install the menus:

     cp -r Menu ~/.local/share/be.shell
    
Copy the MainMenu.xml under your be.shell config dir:

    cp MainMenu.xml `kde4-config --localprefix/share/apps/be.shell
   
Finally, (re)load be.shell. If you're using Plasma on KDE SC4, kill its process and start BE::Shell:

    kquitapp plasma-desktop; sleep 2; be.shell
    
While if you're on Plasma5, the command is:

    kquitapp plasmashell; sleep2; be.shell
    
If you're already on BE::Shell, restart it in order to apply the new theme & config:

    be.shell --restart


Vertex
======

Unity-Like dark theme using [BE--Tray icons](http://be-desk.deviantart.com/art/Be-Tray-Icons-16px-364645083) by LaGaDesk and [Moka Minimal](http://cbowman57.deviantart.com/art/Moka-Minimal-and-Faba-Minimal-Icon-Sets-482927307) by cbowman57.
The suite is inspired by [Vertex GTK](http://horst3180.deviantart.com/art/Vertex-Theme-470663601).


![Vertex preview](https://lh5.googleusercontent.com/-h83zA_HCRVQ/VGYMxGGvQOI/AAAAAAAAC7I/eNZRGMB8qW4/w1058-h595-no/schermata662.png "Vertex")

Dynamo
======

A light theme miming the official Breeze artworks for KDE Plasma5. You can find the offial Breeze icon theme [here](https://github.com/NitruxSA/plasma-next-icons).
Dynamo makes use of BE::Shell labels, either by polling a script, either as FiFos. Some of these scripts are included in this repository (check the Scripts folder for rss2html and be.kdeconnect), others are from [magpie240](https://github.com/magpie240) and require to be installed & configured from the relative repositories:

- [shellfeed](https://github.com/magpie240/shellfeed)
- [shelloid_mpris](https://github.com/magpie240/shelloid_mpris)

![Dynamo preview](https://raw.githubusercontent.com/Hombremaledicto/be.shell/master/Pictures/Dynamo.png "Dynamo")

Pandora
======

Mac alike preset directly derived from Dynamo. Using a mix of Paper and Breeze icon themes. 
Some of the applets within the SideBar requires to install & configure [skutter](https://github.com/Bedevil/skutter).
Recommended fonts: Helvetica Neue, Arimo, Nimbus Sans.

*NOTICE!* This is still in beta: the CSS & config are still *extremely* dirty, and there are still a lot of details which need to be refined.    


![Pandora preview](https://raw.githubusercontent.com/Hombremaledicto/be.shell/master/Pictures/Pandora.png "Pandora")
