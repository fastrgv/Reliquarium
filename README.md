![screenshot](https://github.com/fastrgv/Reliquarium/blob/master/t6a.png)

![screenshot](https://github.com/fastrgv/Reliquarium/blob/master/relic.gif)

# Reliquarium
Reliquarium is a very unique set of four 3D slider puzzles, all with a Crystal Skull theme.

Click on the large 7z file under releases for all source & binaries, or try this link:

https://github.com/fastrgv/Reliquarium/releases/download/v1.8.9/re21oct21.7z


Type "7z x filename" to extract the archive.

#### Note to github downloaders: Please ignore the "Source code" zip & tar.gz files. (They are auto-generated by GitHub). Click on the large 7z file under releases to download all source & binaries (Windows,Mac & Linux). Then, type "7z x filename" to extract the archive. 





# Reliquarium with OpenAL sound

**ver 1.9.0 -- 15nov2021**

* Updated glext64.lib.
* Cleaned up libs; prepped rpath for GNAT.
* Improved scripting supports both AdaCore & GNAT EXEs on Linux.
* Updated all GLFW libs to newer [static] version, & scripts.
* Elliminated OpenGL-mipmap error on nvidia nouveau drivers.
* Derestricted the directory of execution.

**ver 1.8.9 -- 21oct2021**
* Updated libraries.
* Increased separation of puzzle pieces.
* Updated tomb2 display to match others.
* Besides Win64, I now provide a Win32 build, to support older platforms.

**ver 1.8.8 -- 10oct2021**
* Enabled normal window exit.
* Added option to toggle numerals off, to increase challenge.
* Added slight offset to separate distinct puzzle pieces.
* Fixed GL error message in Linux.


**ver 1.8.7 -- 20feb21**

* Upgraded to OpenAL sound.

## See older revision history at end of file



## Reliquarium Game Description
Reliquarium is a very unique set of four 3D slider puzzles, all with a Crystal Skull theme.  Works on Macs running OSX and PCs running Windows or GNU/Linux.

A reckless raider from Indiana has been plundering tombs and displacing ancient relics.  The objective is to carefully return each relic to its rightful place at the center of its cubical box by rearranging the numbered blocks back into their proper order.  Colors and numerals help determine the proper order.

Dragging the cursor with the LEFT mouse button rotates the cube for a better view angle.  The keys n/a (Nearer/Away) or the mouse wheel zooms.  Typing a number selects a block to move.  Then use the keys {u,d,l,r,f,b} to move the selected block (Up,Down,Left,Right,Forward,Backward).

Alternatively, you can select a block by RIGHT-clicking the cursor on it, prior to the move.

To make the puzzles much more challenging, you can toggle the numerals with the n-key. Of course that means you will need to use the right mouse button to select the piece you want to move.

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

*	forward/backward : moves selected block in Z direction
*	right/left       : moves selected block in X-direction
*	up/down          : moves selected block in Y-direction

This terminology for key-assignments assumes X+ is rightward, Y+ is upward, and Z+ is outward...the standard "view" for geometrical discussions in mathematics and physics.  Note that the X, Y, & Z Axes are displayed by default.

Obviously this might get confusing if you rotate the figure to get a better look. That is part of the challenge!

Other keys active:

* (esc)-key => Exit puzzle
* (q)-key => Exit selection screen
* (mouseWheel) => Zoom
* (i)/(o)-keys => Zoom In/Out
* (spc)-key => Restart
* (c)-key => nextSkinColor
* (n)-key => toggle Numerals
* (h)-key => Help toggle
* 0-9 => select numbered block
* (s)-key => select Skull
* (m)-key => select Medusa head
* (v)-key => toggle move-sounds

------------------------------------------------------------


## Required for running:

* graphics card & updated driver that supports OpenGL version 3.3 or later;
* Windows, GNU/Linux or OSX>=10.13(sep2017);


## Setup and Running Reliquarium:

Windows users should read "windows-setup.txt".
Mac users see "osx-setup.txt".

Unzip the archive.  On Windows, 7z [www.7-zip.org] works well for this.  On OSX, you can use Keka.

Open a command line terminal, then cd to the install directory.

--------------------------------------------------------------------
Windows users type "winreliq.bat" for Win64, or "w32reliq.bat" for Win32.

--------------------------------------------------------------------
Linux users type "gnureliq.sh" to start the game.
In Linux, you may also double click the icon for reliquarium in the file manager.

The distributed linux executables require glibc v2.14 or newer.  That means if your distribution is older, it might not run, and you will need to recompile. Another option, however is that linux users can probably run the Windows executables under "wine". Here are two examples that work on my linux machine:

		wine bin/win/reliquarium.exe

		wine bin/win/tomb6.exe

Thusly, each executable can be called directly, skipping the selection screen. Without wine that would be:

		bin/gnu/tomb6

On the other hand, I suggest that Windows users DO NOT try running the linux executables under WSL [Windows Subsystem for Linux]; that mode is not supported. Simply use the windows version.


--------------------------------------------------------------------
The Mac command line version is initiated by opening a terminal, navigating to the install_directory, and typing "macreliq.sh" on the command line.

Also, for Mac users, there is a Mac bundle (named "reliquarium.app") that acts like a typical Mac app.  You can put it into your personal Applications directory with the command "cp -r reliquarium.app ~/Applications".  You can navigate to the installation directory in Finder and click the reliquarium.app icon named "Reliquarium".


Select which of the four tombs to open by clicking on it.  Hit the (esc)-key at any time to return to the selector app;  hit (q)-key to quit completely.

Hint: if the move sound goes silent, you probably hit the "v" key by mistake.

--------------------------------------------------------------------------

Feel free to send comments, suggestions or questions to:  <fastrgv@gmail.com>

--------------------------------------------------------------------------

## Open Source libraries included for rebuilding:
* systems:  Windows, OSX or GNU/Linux
* a recent GNAT or AdaCore Ada compiler
* the ./adabindings/ directory contains Ada interfaces for:
	* AdaPngLib
	* gl
	* glfw
	* FreeType
	* OpenAL (Windows)



## Build instructions:

Four [pre-compiled] binary executables are provided, two for Windows, one for gnu/linux and one for OSX.

Build scripts for the free AdaCore Ada compiler are provided;  a Windows or linux build machine need not have a C++ compiler installed.  GNAT from the GNU Compiler Collection will also work with slight changes to the scripts.

-------------------------------------------------------
msWin32 => w32buildAll.bat

msWin64 => wbuildAll.bat
Note that the 64-bit AdaCore gnat compiler needs to be on your path to use this script.

-------------------------------------------------------
MacOSX => obuildAll.sh:

build script for generating a portable executable that will run on most OSX platforms whether or not they have non-standard libraries installed.  Any Mac with a recent but standard configuration of OSX should be able to rebuild using this script.  Here, all nonstandard libraries are included under the ./libs/ directory and are statically linked.

------------------------------------------------------
GNU/Linux => lbuildAll.sh

utilizes the uncommon relocatable libraries (mainly GLFW) that are delivered in this bundle under ./libs/.  This is used to build a dynamically linked [gnu/linux] executable, which should run in the presence of ./libs, whether or not your system has those libraries installed.
Please, see also the file "gnatUserNote.txt".


### Link Problems during linux build:

On a linux build machine, you might have minor link errors, depending on its configuration.  For example, if you are missing "libz", you can copy "libz.so" from the AdaCore ~/lib/ directory into /usr/local/lib/.  If "libGL" cannot be found, this literally means "libGL.so" was absent.  But you might have "libGL.so.1" present.  In this case, simply create a softlink by changing to the libGL directory, then type the line:

sudo ln -s libGL.so.1 libGL.so  (and enter the admin password)

whence the linker should now be able to find what it wants.  But if there is more than one file libGL present on your system, make sure you use the best one;  i.e. the one that uses your accelerated-graphic-driver.



## What is special about this project?
It uses the Ada programming language and modern OpenGL methods, with textures, shaders and uniforms.  Compiles and runs on Windows, GNU/Linux and Mac OSX systems.

Focusing on portability, transparency, and open source freedom, this project relies exclusively on F.O.S.S. tools:  a thin GLFW3 binding, a thin OpenGL binding, a PNG reader by Stephen Sanguine & Dimitry Anisimkov, OpenAL-Audio with a homebrew binding, and a GNAT compiler.

Written in C++ style, the code neglects many safety features available to Ada, but it does serve as a working example for learning OpenGL.  The Ada bindings used are thin, so the relationship to C++ methodology is transparent.  Developers should note that these Ada bindings are usable as a standalone library for most any OpenGL project that uses Ada.

Thus, for the C++ programmer the code should be easy to comprehend; and for the experienced Ada programmer there are many potential improvements to be made.  Suggestions or improvements from Ada developers are welcomed.


--------------------------
## License:


Reliquarium is covered by the GNU GPL v3 as indicated in the sources:


 Copyright (C) 2021  <fastrgv@gmail.com>

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
**ver 1.8.6 -- 28oct20**
* Updated all glfw libs to v3.3.2.
* Elliminated SFML-audio entirely.
* Greatly simplified build process.


**ver 1.8.5 -- 18apr20**

* OpenGL v3.3 is now sufficient to run this app...allows older hardware.
* Improved coding style to read WAV file while "protected";
* Added a move-sound mute-toggle using v-key (Volume);


**ver 1.8.4 -- 3apr20**

* Created new linux sound system with no latency:  a WAV-player using an Ada binding to the ALSA sound library.
* Sliding sounds have been reenabled; other sounds equilibrated.


**ver 1.8.3 -- 10mar20**

* Fixed bad sound file. Sliding sounds disabled on Linux due to significant latency.


**ver 1.8.2 -- 18jan20**

* Alternate sound system greatly improves linux portability.


**ver 1.8.1 -- 5jan20**

* Added FreeTypeAda (w/TTF);
* Corrected & improved help screens;


**ver 1.8.0 -- 28dec19**

* Converted to GLFW;
* Improved & simplified code structure & layout;


**ver 1.7.0 -- 20dec19**

* Fixed path problem that disallowed running from "relic" directory.


**ver 1.6.9 -- 26nov19**

* Repaired a library problem with GNU/Linux build that limited portability.
* No problems with Mac/OSX or M.S. Windows builds.


**ver 1.6.8 -- 26jun19**

* Changed axis labels to High Contrast Font;
* Darkened background;
* Executables can now be run from either of 2 directories.

...

**ver 1.0 -- 21jan16**

* initial release



