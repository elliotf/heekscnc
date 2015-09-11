# Introduction #

For Ubuntu build see https://code.google.com/p/heekscnc/wiki/HeeksCncUnderUbuntu

# Details #

You need to build HeeksCAD ( see http://code.google.com/p/heekscad/wiki/CompilingHeeksCAD1_0forWindows ), because HeeksCNC is an add-in for HeeksCAD.

make a new folder somewhere. I made this folder "C:\Dev\HeeksCNC1.0" right click on the HeeksCNC1.0 folder and do "TortoiseSVN"->"SVN Checkout..." The "URL of repository": http://heekscnc.googlecode.com/svn//branches/v1_0/ The Checkout directory something like: C:\Dev\HeeksCNC1.0 Press OK. It should checkout all the HeeksCNC 1.0 source code

Set an environment variable called HEEKSCAD1PATH to be the path where HeeksCAD source code is. For me it is set to C:\Dev\HeeksCAD1.0 ( to set an environment variable go to Control Panel -> System and Security -> System -> Advanced system settings -> press "Environment Variables" button -> in "user variable" add new ). ( you must restart Visual Studio for it to know the new environment variable )

Open "HeeksCNC VC2008.sln" with Visual Studio 2008 ( Express version is OK too ).

Change configuration to "Unicode Release"

Press "Build Solution"

Install the latest verion of Python, ( HeeksCNC uses Python scripts extensively )

Run HeeksCAD.exe.
On the file menu, choose "Plugins".
Add a new plugin called "HeeksCNC", and use the button to fill the box with the path to your HeeksCNC.dll that was built to your "HeeksCNC" folder.
Close HeeksCAD.
Run HeeksCAD.exe.
It should load up HeeksCNC.dll and add the extra windows and menu items. You will have to go to the "View" menu and tick them to make them visible.

kurve.pyd should have been built and be in the same folder as HeeksCNC.dll
( You will need this for the profile operation )

You also need to go to the Google Code projects "opencamlib" and "libarea" and build "ocl.pyd" ( for 3D surface operation ), "area.pyd" ( for pocket operation ) if you want those operations to work.
Copy them to the same place as your HeeksCNC.dll