
Download all source code & resources in the following 7-zip file:

https://github.com/fastrgv/RetroArcade/releases/download/v2.6.0/ret15nov22.7z



# RetroArcade

	* SpaceInvaders 
	* Frogger
	* Pacman


## What's new:


**ver 2.6.0 -- 15nov2022**

* Initial spinoff of RetroArcade (from coterminalapps).




===============================================================
## Introduction

RetroArcade is a highly portable collection of ASCII arcade games with sound that run in a commandline terminal on Windows, OS-X and Gnu/Linux. Includes SpaceInvaders, Pacman & Frogger. Includes full source code.

-----------------------------------------------------------
Featuring

	* no installation
	* no dependencies (Ncurses not needed)
	* simply unzip in your Downloads directory, or any other writeable directory, and run;
	* or unzip onto a USB flash drive [w/same file format] and run.
-----------------------------------------------------------

The 7zip command to extract the archive and maintain the directory structure is "7z x filename".

* Windows versions use runtime-priority control for arcade-level response.

Rebuildable using the free GNU Ada compiler, even on OSX.

Includes 3 retro arcade games: SpaceInvaders, Pacman, Frogger.


Usable keys for all:

* arrow-keys for movement; (see ~/docs/KeyboardMoves.txt)
* you can also use wasd or ijkl for moves.
* (q)=quit
* (?)=help toggle

Can be called directly from the command line; e.g.

* bin\win\cpac.exe	(from base dir)
* cpac.exe				(from ~\bin\win\ dir)

but it is more convenient to use the selector app, thusly:

* winArcade.bat		(Win64)
* macArcade.sh			(Mac/OSX)
* gnuArcade.sh			(linux)

Use the keyboard arrow keys to highlight the desired game, then press the (enter)-key.

* Windows users note: Using linux executables under WSL [Windows Subsystem for Linux] is not supported. Instead, you should use the windows versions because extraordinary measures have been taken to achieve arcade-level response.

* Similarly, linux users cannot use wine to run Windows executables, with this particular App.


### For Maximal Enjoyment...
Keyboard setup can be very important for playability.  You should have a very short key-delay and fast repeat rate setting when running the arcade games.

Screen setup is important, too. Terminal sizes required:
* pacman:	60x40
* frogger:	56x21
* Invaders:	80x30

It is recommended to resize your terminal window, per the above table; then enlarge the font until the window just barely fits your computer screen.

===========================================================================

### Space-Invaders (cinv.adb)
This is my translation of nInvaders.c into Ada, but with SOUND !!!

You need only the (space)-key to fire your laser gun and the left/right arrow keys [or a-key/d-key] to move out of the way of the alien missiles. The terminal window must be at least 80-chars wide x 30-lines. There are no command-line options, but difficulty increases with level.


### Pacman (cpac)
Pacman, is a kid friendly ascii character version of Pacman that plays in a commandline terminal.  Pure minimalism with classic sounds and 9 predefined levels.  

Now with runtime-priority control to prevent terminal freezes on Windows, plus commandline control of gamespeed & ghostspeed.

Runs on Windows, OSX & Linux.

Keyboard setup is important.  You should have a short key-delay and fast repeat setting.  

The arrow keys, or wasd-keys, or ijkl-keys control movement.  The (x),(q) keys quit;  (p) pauses game.

Includes executables and source code.  Note that this game does NOT require an ncurses library in your environment.

When run directly, cpac can be given 2 optional command line parameters:

	* game speed 0..9; 0=slow, 5=default=medium, 9=fast;
	* ghost speed 0..9; 0=stopped, 2=default=easy, 9=fast.

If you want to try non-default values for these params, you need to run directly from the directory of the executable. To do this: "cd bin/gnu" or "cd bin/osx" or "cd bin\win", first.

Before running cpac, it is recommended to resize your terminal to 60 chars. wide by 40 lines tall; then, perhaps, enlarge the font.



### Frogger (cfrog)
Terminal frogger is a kid friendly ascii character version of Frogger that plays in a commandline terminal.  Pure minimalism with classic sounds and three levels.

* @@@@ is a raft of lillypads, 
* QQQQ is a team of turtles, 
* ==== is a log, 
* TTT is a truck, 
* ccc is a car.

Runs on Windows, OSX & Linux.

Keyboard setup is important.  You should have a short key-delay and fast repeat setting.

The arrow keys, or wasd-keys, or ijkl-keys control movement.  The (x),(q) keys quit.

Before running cfrog, it is recommended to resize your terminal to 56 chars. wide by 21 lines tall; then, perhaps, enlarge the font.






===============================================================
## Setup & Running:

RetroArcade is a stand-alone application.
Ncurses is NOT needed; there are no prerequisites.

Mac users see "osx-setup.txt".
Windows users see "windows-setup.txt".

Unzip the archive.  On Windows, 7z [www.7-zip.org] works well for this.
The proper command to extract the archive and maintain the directory structure is "7z x filename".

Open a commandline terminal, and cd to the game directory.

Arcade games require your keyboard to have a short key-delay and fast repeat rate.

Minimize the size of your terminal window:

* pacman:	60x40
* frogger:	56x21
* Invaders:	80x30

Then enlarge the Font so that the window fills your monitor.

To launch the game selector App, depending on your system, type:

* winArcade.bat (win64)
* macArcade.sh (OSX)
* gnuArcade.sh (linux)

Note that any individual app may still be executed from the directory appropriate to your O.S.  For example, on Windows you can CD to bin\win\ and then type "cfrog" to run Frogger.



### OSX caveat
The prebuilt OSX executables require version 10.13 (sep2017) or newer.

===========================================================================
## Compiler Scripts
There are 3 scripts, winbuildall.bat for Windows, lbuildall.sh for Linux, and obuildall.sh for OS-X.  They differ in where the executables are put.  With so many different precompiled binaries for each OS, there would be too much clutter if they were all put into the same place, particularly since windows needs colocated DLLs.

These build scripts work for GNU Ada [with its own g++].
See ./alternateBuildScripts/ for more examples.

The latest scripts have elliminated the need to use the "gnatcoll" library simply by compiling from source 3 additional tiny files, a small subset of gnatcoll, that are actually used.

Final note:  the latest OSX script does not use Xcode, only GNU Ada & GNU g++.

==========================================================================
## Build Instructions:
Remember that prebuilt executables are already included. But, if you want or need to rebuild...


To get a recent Ada compiler;  eg. GNU-Ada...try this source:

https://github.com/alire-project/GNAT-FSF-builds/releases


Manually install GNU Ada.  If you don't like my key-mappings, edit the code as you like.

Next, edit the scripts wincmp.bat, lcmp.sh or ocmp.sh so that the path to gnatmake is correct.  These scripts streamline the build process by allowing auxilliary files to be neatly hidden in subdirectories.

Windows users please read gnuAdaOnWindows.txt.

Then type "[win/l/o]buildall" to create new command-line executables for your system. ( win for Windows, l for Linux, o for OSX). 

There are NO other 3rd party libraries or tools required to build.




---------------------------------------------------------------

## What is special about this project?...freedom...portability

* uses the Ada programming language and the freely-available GNU compiler.
* runs on Macs running OSX, or PCs running Windows or Linux;
* uses only free open source software [F.O.S.S] tools & libraries;
* portable, transparent code, easy to modify, rebuild;
* uses a cross-platform implementation of OpenAL-Audio, adaptable by any Ada application that needs sounds & music-loops with a simple interface.
* pure minimalism:  no graphics, just colored ASCII characters, keyboard, & sound;
* Ncurses is <u>not</u> required.

Open source Ada developers are welcome to help improve or extend this app.
Developer or not, send comments, suggestions or questions to:
fastrgv@gmail.com


---------------------------------------------------------------


## License:

RetroArcade is covered by the GNU GPL v3 as indicated in the sources:

 Copyright (C) 2022  <fastrgv@gmail.com>

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


----------------------------------------------
## Other Credits and Thanks:

Mike Billars [michael@gmail.com] for his C-version of Pacman for the console, after which this Ada version was modelled (gnu gpl).

Sebastian Gutsfeld [segoh@gmx.net]  & Alexander Hollinger [alexander.hollinger@gmx.net] for the C-version of nInvaders (v0.1.1), after which this Ada version was modelled (gnu gpl).



----------------------------------------------
### SoundFiles (wav)
Fanfare/Applause and UFO sounds are from freesound.org and are covered by the Creative Commons CC0 Public License documented in the accompanying file ./docs/creativeCommonsCC0.txt. A few have a CC-by-3.0 license and are accompanied by a text file with the attribution.

Others from 
* classicgaming.cc/classics/pac-man/sounds
* classicgaming.cc/classics/frogger/sounds
(also CreativeCommons cc0).
The remaining sounds are public domain.
See also: ./sounds/licenses-sound-data.txt.

It is my intention to use media with copyrights or licenses that are compatible with GPLv3. Please notify me if you believe there is an incompatibility, and it will be removed; eg a CC-by-NC license is NOT GPL compatible.




----------------------------------------------
## Download Sites for all my games:
* https://github.com/fastrgv?tab=repositories
* https://www.indiedb.com/members/fastrgv/games
* https://fastrgv.itch.io
* https://sourceforge.net/u/fastrgv/profile/
* https://gamejolt.com/@fastrgv/games



--------------------------------------------------
## Some Earlier Revision History:



