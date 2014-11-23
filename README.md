Installation
======

Install [BE::Shell](http://sourceforge.net/p/be-shell/code/ci/master/tree/) or upgrade to the latest commit.
Themes are made with [QSS](http://qt-project.org/doc/qt-4.8/stylesheet-reference.html) - Qt Style Sheets, while the menu files for the globalmenu applet follow a simple [xml syntax](http://sourceforge.net/p/be-shell/wiki/Menu%20reference/).
Some of the menus, *Recent* and *Places*, are generated by the relative scripts located under the Scripts folder.

**Notes** 

- Due to the absolute positioning in BE::Shell themes may need adjustments within the css or the config file.
- The places script requires xmlstarlet

**Theme and Config**

Clone this repository:

    git clone https://github.com/Hombremaledicto/be.shell.git
   
Copy the Theme directory: 

    cp -r Themes `kde4-config --localprefix`/share/apps/be.shell/

Copy the included be.shell.Vertex file:

    cp be.shell.Vertex `kde4-config --localprefix`/share/config/be.shell
   
Reload BE::Shell:

    kquitapp be.shell; sleep 2; be.shell
   
   
**Globalmenu** 

Copy the folders Menu, Scripts and the MainMenu.xml file:

    cp -R Menu Scripts MainMenu.xml `kde4-config --localprefix`/share/apps/be.shell
  
Make the scripts executable:

    chmod -R 777 `kde4-config --localprefix`/share/apps/be.shell/Scripts/*


Vertex
======

Unity-Like dark theme using [BE--Tray icons](http://be-desk.deviantart.com/art/Be-Tray-Icons-16px-364645083) by LaGaDesk and [Moka Minimal](http://cbowman57.deviantart.com/art/Moka-Minimal-and-Faba-Minimal-Icon-Sets-482927307) by cbowman57.
The suite is inspired by [Vertex GTK](http://horst3180.deviantart.com/art/Vertex-Theme-470663601).

By default panels are locked and browsing through workspaces with the mouse wheel disabled (yes, unity-like). 
To unlock panels simply change the two lines *Frozen=true* to false. 
To revert the mouse wheel behaviour, change *WheelOnLMB=true* to false, under [BE::Desk]. 

Always from the config file, there are preconfigured WmCtrl applets(close, minimize, maximize) you can add to the array list of top panel, e.g. *Applets=close,min,max,Globalmenu,etc...*
Then, you could also want maximized windows without borders, which takes a small modification to kwinrc:

    kwriteconfig --file kwinrc --group Windows --key BorderlessMaximizedWindows true
    
Reload the WM with the new config:

    qdbus org.kde.kwin /KWin reconfigure

![Vertex preview](https://lh5.googleusercontent.com/-h83zA_HCRVQ/VGYMxGGvQOI/AAAAAAAAC7I/eNZRGMB8qW4/w1058-h595-no/schermata662.png "Vertex")


