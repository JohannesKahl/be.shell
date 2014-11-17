Installation
======

Install [BE::Shell](http://sourceforge.net/p/be-shell/code/ci/master/tree/) or upgrade to the latest commit.
Themes are made with [QSS](http://qt-project.org/doc/qt-4.8/stylesheet-reference.html) - Qt Style Sheets, while the menu files for the globalmenu applet follow a simple [xml syntax](http://sourceforge.net/p/be-shell/wiki/Menu%20reference/).

Notice that due to the absolute positioning in BE::Shell themes usually require some adjustments within the css or the config file.

**Theme and Config**

Clone this repository:

   git clone https://github.com/Hombremaledicto/be.shell.git
   
Copy the Theme directory to: 

   cp -r Themes ~/.kde4/share/apps/be.shell/

Copy the included be.shell.Vertex file to:

   cp be.shell.Vertex ~/.kde4/share/config/be.shell
   
Reload BE::Shell:

   kquitapp be.shell; sleep 2; be.shell
   
   
**Globalmenu** 

Copy the folders `Menu`, `Script` and the MainMenu.xml file to:

  ~/.kde4/share/apps/be.shell
  
Make the scripts executable:

   chmod -R 777 ~/.kde4/share/apps/be.shell/Scripts/*

*n.b. The places script requires xmlstarlet*
  

Vertex
======

![Vertex preview](https://lh5.googleusercontent.com/-h83zA_HCRVQ/VGYMxGGvQOI/AAAAAAAAC7I/eNZRGMB8qW4/w1058-h595-no/schermata662.png "Vertex")


