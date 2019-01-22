RobotFindsKitten for NES 0.10.122 (robotfindskitten.nes)
by  Damian Yerrick
20 Oct 2018

https://github.com/pinobatch/rfk-nes
robotfindskitten is a "Zen simulation" originally written by Leonard Richardson as an entry to a game jam in 1997. It won by default.

This program implements robotfindskitten on the Nintendo Entertainment System, mostly following the RFK RFC with a few minor willful deviations to fit NES constraints.
Build

Install ca65, GNU Make, Python 3, and Pillow per instructions at https://github.com/pinobatch/nrom-template/
Play

In this game, you are robot (#). Your job is to find a kitten hiding from Sirhan. This task is complicated by the existence of various things which are not kitten. Robot must touch items to determine if they are kitten or not. The game ends when robotfindskitten.

Use the Control Pad on controller 1 or controller 2 to move robot. Bump into an object to see if it is kitten. If it is, you win! If not, the description of a non-kitten item (NKI) will appear on your side of the status.
Customize

The files src/*.nki define non-kitten items. The makefile defines which files are used. Each nonblank line in these files that does not start with a # (robot) defines one NKI and MUST NOT exceed 72 characters nor use code points outside Basic Latin (ASCII).
Deviations

There are two instances of robot, one for each controller port. Each moves independently and has its own half of the Status. As robot is not kitten, finding robot displays a special NKI.

Because of the reduced width available for NKI text in a two-robot simulation, the Status is four lines instead of three, with the NKI occupying the second through fourth lines. The underscores separating the Status from the Field overlap the fourth line.

The Field consists of 48 by 24 cells, each occupying 5 by 7 pixels. NKI count cannot be configured, nor is diagonal movement possible. Because items in the Field are drawn as sprites, there is a limit on how many items can occupy one row of the Field.

To quit the simulation, turn off the power, or if the simulation has been exit patched, press the Reset button on the Control Deck. (Examples of exit patched simulations include the one included in Action 53.)

NKI descriptions are hardcoded because the NES has no file system. Because this port of robotfindskitten was developed for Action 53, more included NKIs allude to the first two volumes of Action 53 than one might expect otherwise. As described in "Customize", one can edit the NKI files and reassemble the program for a larger pool, but this pool cannot exceed 28 KiB once compressed with digram tree encoding (DTE), also called byte pair encoding (BPE).
Legal

Copyright 2014 Damian Yerrick

The zlib License
================

Copyright (c) 2017 Damian Yerrick

This software is provided 'as-is', without any express or implied warranty. In
no event will the authors be held liable for any damages arising from the use of
this software.

Permission is granted to anyone to use this software for any purpose, including
commercial applications, and to alter it and redistribute it freely, subject to
the following restrictions:

1.  The origin of this software must not be misrepresented; you must not claim
    that you wrote the original software. If you use this software in a product,
    an acknowledgment in the product documentation would be appreciated but is
    not required.

2.  Altered source versions must be plainly marked as such, and must not be
    misrepresented as being the original software.

3. This notice may not be removed or altered from any source distribution.

https://github.com/pinobatch/rfk-nes