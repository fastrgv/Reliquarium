# Reliquarium
Reliquarium is a set of four 3D slider puzzles, all with a Crystal Skull theme.


# Reliquarium -- v 1.5

## Whats new:


**ver 1.5 -- 6mar16**

* The 4x4x4 Tomb now has its finalizing "improvement".  Two more 1x1x1 cubelets complete the symmetry, while adding to the difficulty.  Yes, it is still solvable!


**ver 1.4 -- 5mar16**

* The 4x4x4 Tomb [the upper right puzzle] has revised corner stones that make it far more difficult.  Good luck!
* The Space-Key will now Restart the puzzle.

**ver 1.3 -- 21feb16**

* Restructured four into a single application.
* Added Mac binary bundle that acts like a typical Mac App.  This app is delivered in the installation directory, but could be moved elsewhere, such as your personal Applications directory [and initiated with a click].  Note that there are some soft [symbolic] links in the bundle that are resolved automatically when copied with the command "cp -r reliquarium.app destination-directory".
* Generalized utex package;  client defines character set file.


**ver 1.2 -- 25jan16**

* added shriek to Medusa's final enclosure.
* added gradual block moves.
* fixed error in proximity-pick.
* found and fixed block move logic errors.

**ver 1.1 -- 23jan16**

* added a 4th puzzle called tomb2, that is a version of "hole in one", a puzzle invented by Serhiy and Peter Grabarchuk.
* added logic to automatically select the first possible candidate for a move if the specified candidate is not feasible.
* added capability to select a block with a cursor click, using either:
	* mouse right-click
	* 2-finger click on a MacBook trackpad

**ver 1.0 -- 21jan16**

* initial release



## What is special about this project?
Uses the Ada programming language and fully modern OpenGL methods with textures, shaders and uniforms.  Achieves version 3.3 core profile contexts, and compiles and runs on both GNU/Linux and Mac OS-X systems.

Focusing on portability and freedom, no coding effort or compromise has been made to accomodate proprietary operating systems.  It relies on a thin SDL2 binding from Dan Vazquez, a thin OpenGL binding from "Lumen", a PNG reader by Stephen Sanguine, and SFML-Audio (because of its elegant audio interface).

Written in C++ style, the code neglects many safety features available to Ada, but it does serve as a working example for learning OpenGL.  The Ada bindings used are thin, so the relationship to C++ methodology is transparent.  Developers should note that these Ada bindings are usable as a standalone library for most any OpenGL project that uses Ada.

Thus, for the C++ programmer the code should be easy to comprehend; and for the experienced Ada programmer there are many potential improvements to be made.  Suggestions or improvements from Ada developers are not only welcomed, but solicited.


## Reliquarium Game Description
Reliquarium is a set of four 3D slider puzzles, all with a Crystal Skull theme.

Reckless raiders have plundered a tomb and displaced an ancient relic.  The objective is to return the relic to the center of its cubical box by rearranging the numbered blocks back into their proper order, which usually represents an RGB coloring...Red in the X-direction, Green in the Y-direction, Blue in the Z-direction.

Dragging the cursor rotates the cube for a better view angle.  The mouse wheel zooms.  Typing a number 1..8 selects a block to move, 0 selects the relic itself.  Then use the keys {u,d,l,r,f,b} to move it.

Alternatively, you can select a block by clicking the cursor near your pick, prior to the move.

As indicated on screen, (h) will toggle a help screen.

These puzzles are easy enough for children and will likely help with learning 3D visualization, geometry, problem solving and computer skills.

Works on Macs running OS-X and PCs running GNU/Linux.




## Game Features
* Works on PCs or laptops running OS-X or GNU/Linux.  And if GNAT is installed you can build it yourself!  But first try the delivered binaries.

* Both GNU/Linux and OS-X binaries provided, as well as full source.

* Laptop friendly controls;  supports Mac Retina displays.



## Mouse/touchpad/keyboard controls

Look direction is controlled by a touch pad swipe or mouse drag;

Movement is controlled by the keys:  u d l r f b  (Up Down Left Right Forward Backward)

...which might get confusing unless you keep the X-axis rightward, the Y-axis upward, and the Z-axis outward...the standard view for geometrical discussions in mathematics and physics.

(esc)-key => exit;  

------------------------------------------------------------

There are 4 variations numbered 2, 4, 5, and 6, according to a dimension of each puzzle.  Note that the puzzles with a smaller number are somewhat more difficult.

One way to start the game is to open a [command-line] console, navigate to the installation directory, and at the command line type "reliquarium_gnu" or "reliquarium_osx".

In Linux, you may also double click the icon for reliquarium_gnu in the file manager.

For Mac users, there is now a Mac bundle (named "reliquarium.app") that acts like a real Mac app.  You can put it into your personal Applications directory with the command "cp -r reliquarium.app ~/Applications".  You can navigate to the installation directory in Finder and click the reliquarium.app icon named "Reliquarium".

------------------------------------------------------------


## Required for running:

* graphics card & driver that supports OpenGL version 3.3 or later;
* GNU/Linux or a Mac running OS-X (even Yosemite & ElCapitan);


## Open Source libraries included for rebuilding:
* systems:  OS-X or GNU/Linux
* a recent gnat compiler
* the included "libs" directory contains Ada interfaces:
	* AdaPngLib
	* gl
	* sdlada


## Running Reliquarium:
Unzip the archive and you will see a new directory appear with a name like "bundle_date", that you should rename to something like "install_directory".  

Linux users should cd to install_directory, then type "reliquarium_gnu" to start the game.

The Mac command line version is initiated by opening a terminal, navigating to the install_directory, and typing "reliquarium_osx" on the command line.


--------------------------------------------------------------------------

Feel free to send comments, suggestions or questions to:  <fastrgv@gmail.com>

--------------------------------------------------------------------------



## Build instructions:

Two [pre-compiled] binary executables are provided, one for gnu/linux and one for OS-X.  The linux version, reliquarium_gnu, are intended to run in the presence of the directory "libs", which contains some dynamically loaded libraries that can be, but need not be present on a target system:  SFML, SDL2

Build scripts for GNAT2015 are provided.  Suggestions for improving the build process are welcome.

-------------------------------------------------------
MacOSX:

ocmp.sh:  
build script for generating a portable executable that will run on most OS-X platforms whether or not they have non-standard libraries SDL2 or SFML installed.  Any Mac with a recent but standard configuration of OS-X should be able to rebuild using this script.  Here, all nonstandard libraries are included under the ./libs/ directory and are statically linked.

------------------------------------------------------
GNU/Linux:  

lcmp.sh:
utilizes the uncommon relocatable libraries (mainly SDL2, SFML) that are delivered in this bundle under ./libs/.  This is used to build a dynamically linked [gnu/linux] executable, which should run in the presence of ./libs, whether or not your system has those libraries installed.

If it doesnt run on your linux distro, you will have to try to build the executable yourself.  In that case, it is hoped that this script will work for you.  The intent was to provide all the needed interface/include files under ./libs/.



--------------------------
## Legal Issues:


Reliquarium is covered by the GNU GPL v3 as indicated in the sources:


 Copyright (C) 2016  <fastrgv@gmail.com>

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
... to Serhiy and Peter Grabarchuk for their Hole in One puzzle [tomb2], one of the inspirations for Reliquarium.

----------------------------------------------------------------

