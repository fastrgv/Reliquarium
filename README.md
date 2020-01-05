![screenshot](https://github.com/fastrgv/Reliquarium/blob/master/t6a.png)

# Reliquarium
Reliquarium is a very unique set of four 3D slider puzzles, all with a Crystal Skull theme.

There are now two versions with differing internals...
Click on the large 7z file under releases for all source & binaries, or try this link:

https://github.com/fastrgv/Reliquarium/releases/download/v1.8.1/re5jan20.7z



# Reliquarium



**ver 1.8.1 -- 5jan20**

* Added FreeTypeAda (w/TTF);
* Corrected & improved help screens;


**ver 1.8.0 -- 28dec19**

* Converted to GLFW;
* Improved & simplified code structure & layout;


## See older revision history at end of file


## Reliquarium Game Description
Reliquarium is a very unique set of four 3D slider puzzles, all with a Crystal Skull theme.  Works on Macs running OSX and PCs running Windows or GNU/Linux.

A reckless raider from Indiana has plundered tombs and displaced ancient relics.  The objective is to carefully return each relic to its rightful place at the center of its cubical box by rearranging the numbered blocks back into their proper order.  Colors and numerals help determine the proper order.

Dragging the cursor rotates the cube for a better view angle.  The keys n/a [Nearer/Away] or the mouse wheel zooms.  Typing a number selects a block to move.  Then use the keys {u,d,l,r,f,b} to move the selected block (Up,Down,Left,Right,Forward,Backward).

Alternatively, you can select a block by clicking the cursor on it, prior to the move.

As indicated on screen, (h) will toggle a help screen.

These puzzles are easy enough for children but will likely help anyone improve their 3D visualization, geometry, problem solving and computer skills.

There are 4 variations numbered 2, 4, 5, and 6.  Puzzles # 4, 5, & 6 are my own creations, where the numeral represents the vertical size;  while #2 is a well-known [2D] Grabarchuk puzzle.  Generally, the puzzles with a smaller number are somewhat more difficult.  Puzzle #4 is the most compact & difficult.


## General Strategy
Temporarily combine complementary pieces to maximize contiguous empty swap space.


## Game Features
* Works on PCs or laptops running Windows, OSX or GNU/Linux.  And if GNAT is installed you can build it yourself!  But first try the delivered, prebuilt binaries.

* Windows, GNU/Linux and OSX binaries provided, as well as full source.

* Laptop friendly controls;  supports Mac Retina displays.



## Mouse/touchpad/keyboard controls

Look direction is controlled by a touch pad swipe or mouse drag;

Movement is controlled by the keys:  
	u d l r f b  (Up Down Left Right Forward Backward)

In other words...

* forward/backward : moves selected block in Z direction
* right/left       : moves selected block in X-direction
* up/down          : moves selected block in Y-direction

This terminology for key-assignments assumes X+ is rightward, Y+ is upward, and Z+ is outward...the standard "view" for geometrical discussions in mathematics and physics.  Note that the X, Y, & Z Axes are displayed by default.

Other keys active:

* (esc)-key => Exit puzzle
* (q)-key => Exit selection screen
* (mouseWheel) => Zoom
* (i)/(o)-keys => Zoom In/Out
* (spc)-key => Restart
* (c)-key => nextSkinColor
* (h)-key => Help toggle
* 0-9 => select numbered block
* (s)-key => select Skull
* (m)-key => select Medusa head


------------------------------------------------------------


## Required for running:

* graphics card & updated driver that supports OpenGL version 3.3 or later;
* Windows, GNU/Linux or OSX;


## Setup and Running Reliquarium:

Windows users should read "windows-setup.txt".
Mac users see "osx-setup.txt".

Unzip the archive.  On Windows, 7z [www.7-zip.org] works well for this.  On OSX, you can use Keka.

Open a command line terminal, then cd to the install directory.

Windows users type "winreliq.bat".

Linux users type "gnureliq.sh" to start the game.
In Linux, you may also double click the icon for reliquarium in the file manager.

The Mac command line version is initiated by opening a terminal, navigating to the install_directory, and typing "macreliq.sh" on the command line.

Also, for Mac users, there is a Mac bundle (named "reliquarium.app") that acts like a typical Mac app.  You can put it into your personal Applications directory with the command "cp -r reliquarium.app ~/Applications".  You can navigate to the installation directory in Finder and click the reliquarium.app icon named "Reliquarium".


Select which of the four tombs to open by clicking on it.  Hit the (esc)-key at any time to return to the selector app;  hit (q)-key to quit completely.

--------------------------------------------------------------------------

Feel free to send comments, suggestions or questions to:  <fastrgv@gmail.com>

--------------------------------------------------------------------------

## Open Source libraries included for rebuilding:
* systems:  Windows, OSX or GNU/Linux
* Xcode g++ compiler, if using OSX
* a recent gnat compiler
* the included "libs" directory contains Ada interfaces:
	* AdaPngLib
	* gl
	* glfwada
	* FreeTypeAda



## Build instructions:

Three [pre-compiled] binary executables are provided, one for Windows, one for gnu/linux and one for OSX.  The linux version, reliquarium, is intended to run in the presence of the directory "libs", which contains some dynamically loaded libraries that can be, but need not be present on a target system:
GLFW2, SFML, FLAC, ogg, vorbis, & openal.

Build scripts for GNAT2016 are provided;  and due to a recent script change, a Windows or linux build machine need not have a C++ compiler installed.  Only GNAT is required.

-------------------------------------------------------
msWin32 => wbuildAll.bat

build script that requires [static] libraries included in ./libs/win/.


-------------------------------------------------------
MacOSX => obuildAll.sh:

build script for generating a portable executable that will run on most OSX platforms whether or not they have non-standard libraries GLFW or SFML installed.  Any Mac with a recent but standard configuration of OSX should be able to rebuild using this script.  Here, all nonstandard libraries are included under the ./libs/ directory and are statically linked.

------------------------------------------------------
GNU/Linux => lbuildAll.sh

utilizes the uncommon relocatable libraries (mainly GLFW, SFML) that are delivered in this bundle under ./libs/.  This is used to build a dynamically linked [gnu/linux] executable, which should run in the presence of ./libs, whether or not your system has those libraries installed.

If it doesnt run on your linux distro, you will have to try to build the executable yourself.  In that case, it is hoped that this script will work for you.  The intent was to provide all the needed interface/include files under ./libs/.

The current build is compiled on OpenSUSE v13.2, and uses GLIBC 2.14 [dating from june 2011].  This generally means that if your linux distro uses glibc v2.14 or newer, then the prebuilt binary should probably run on your system (and be rebuildable).

If the delivered linux binary does not run...

* Manually install GNAT GPL from libre.adacore.com/download/.
* Rerun the linux compile script lbuildAll.sh


### Link Problems during linux build:

On a linux build machine, you might have minor link errors, depending on its configuration.  For example, if you are missing "libz", you can copy "libz.so" from GNAT.../lib/gps/ into /usr/local/lib/.  If "libGL" cannot be found, this literally means "libGL.so" was absent.  But you might have "libGL.so.1" present.  In this case, simply create a softlink by changing to the libGL directory, then type the line:

sudo ln -s libGL.so.1 libGL.so  (and enter the admin password)

whence the linker should now be able to find what it wants.  But if there is more than one file libGL present on your system, make sure you use the best one;  i.e. the one that uses your accelerated-graphic-driver.



## What is special about this project?
It uses the Ada programming language and modern OpenGL methods, with textures, shaders and uniforms.  Compiles and runs on Windows, GNU/Linux and Mac OSX systems.

Focusing on portability, transparency, and open source freedom, this project relies exclusively on F.O.S.S. tools:  a thin GLFW3 binding, a thin OpenGL binding, a PNG reader by Stephen Sanguine & Dimitry Anisimkov, SFML-Audio with a homebrew binding, and a GNAT compiler.

Written in C++ style, the code neglects many safety features available to Ada, but it does serve as a working example for learning OpenGL.  The Ada bindings used are thin, so the relationship to C++ methodology is transparent.  Developers should note that these Ada bindings are usable as a standalone library for most any OpenGL project that uses Ada.

Thus, for the C++ programmer the code should be easy to comprehend; and for the experienced Ada programmer there are many potential improvements to be made.  Suggestions or improvements from Ada developers are welcomed.


--------------------------
## Legal Issues:


Reliquarium is covered by the GNU GPL v3 as indicated in the sources:


 Copyright (C) 2020  <fastrgv@gmail.com>

 This program is free software: you can redistribute it and/or modify
 it under the terms of the GNU General Public License as published by
 the Free Software Foundation, either version 3 of the License, or
 (at your option) any later version.

 This program is distributed in the hope that it will be useful,
 but WITHOUT ANY WARRANTY; without even the implied warranty of
 MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
 GNU General Public License for more details.

 You may read the full text of the GNU General Public License
 at <http://www.gnu.org/licenses/>.


## Media Files for Reliquarium:

### SoundFiles [x.wav]
Some sounds are from freesound.org and are covered by the Creative Commons Attribution noncommercial license documented in the accompanying file creativeCommons.txt.  Others [eg. shriek] are from http://www.freesfx.co.uk.

### ImageFiles 
Images for textures were from pixabay.com have a CC0 license.  Files for text-textures were created using gimp and are also covered by the GNU GPL v3 license.

## Thanks:
... to Serhiy and Peter Grabarchuk for their Hole in One puzzle [tomb2], one of my inspirations for the other 3 puzzles in Reliquarium.

----------------------------------------------------------------
## Best Download Site for all my games:
https://github.com/fastrgv?tab=repositories



## Revision History:

**ver 1.7.0 -- 20dec19**

* Fixed path problem that disallowed running from "relic" directory.
* Updated SDL2 to v2.0.10, including binding, libs, & scripts.


**ver 1.6.9 -- 26nov19**

* Repaired a library problem with GNU/Linux build that limited portability.
* No problems with Mac/OSX or M.S. Windows builds.


**ver 1.6.8 -- 26jun19**

* Updated SDL2 to version 2.0.9
* Updated Ada binding to SDL2;
* Changed axis labels to High Contrast Font;
* Darkened background;
* Executables can now be run from either of 2 directories.

...

**ver 1.0 -- 21jan16**

* initial release

