Super Tilt Bro (Super_Tilt_Bro_(E).nes)
by Sylvain Gadrat (sgadrat)
2018/10/27

NES homebrew inspired by Super Smash Bros.

Nintendo's consoles before the N64 do not have their Super Smash Bros game. Let's fix it! Super Tilt Bro is a 
NES hombrew project aiming at porting the "versus platformer fighting" to this good old system that made our 
childhood.

Last tagged build is playable here --> https://sgadrat.itch.io/super-tilt-bro

Building
You will need the XA cross assembler for 6502. It may be found on Archlinux in the package "community/xa", on 
ubuntu in the package "xa65" and for others you may find information here.

From the source repository run
xa tilt.asm -C -o 'Super_Tilt_Bro_(E).nes'
tilt.asm uses xa's preprocessor to directly output a valid iNES ROM file. The "-C" option is not mandatory but 
make xa stop assembling when using opcodes too recent for the NES.


Super Tilt Bro is a demake of the Super Smash Bros. series compatible with the good old Nintendo Entertainment 
System from the 1980s.
You and a friend take control of a clone of Sinbad, the badass mascot of Ogre3D. Two fellows, one platform: 
you will have to fight to throw the other out.

You can follow the development on my 
 -Twitter @RogerBidon (https://twitter.com/RogerBidon), 
- on Smashboards (https://smashboards.com/threads/super-tilt-bro-for-nes.443395/) 
- or directly fork it on github --> https://github.com/sgadrat/super-tilt-bro


Playing
You will need a NES emulator with two controllers configured. Each controller controls a character and the goal 
is to send the other out of screen.

Controller mapping:

          Jump
            |
Move left   |      Unused   Unused
     |   +--+         |        |
+----|---|------------|--------|------------------------+
|    |   |            |        |                        |
|    | +-|-+          |        |                        |
|    | | o |          |        |                        |
|  +-|-+   +---+      |        |                        |
|  | o       o |      o        o        ---     ---     |
|  +---+   +-|-+   (select) (start)    ( B )   ( A )    |
|      | o | |                          -o-     -o-     |
|      +-|-+ |                           |       |      |
+--------|---|---------------------------|-------|------+
         |   +---+                       |       +---+
       Shield    |                 Special moves     |
                 |                                   |
            Move right                            Attacks

You can use different moves by holding a direction when pressing the attack or special move button.


================================================================================================================
CHANGE LOG:
Version 1.0 released!

Changelog:

    Sinbad moves
        Jab
            New animation
            More end-lag, but can be cut into a new jab
        Side special
            Improved animation for charging
        Shield
            Improved graphics
            Shield lag now occurs when leaving the shield
        Aerial down
            Accelerated animation
            Cancels fast-fall
    Gameplay
        Implemented air friction: while mid-air you slowly decelerate
        Kill move are now stronger, compensating air friction
        Tech is now easier to input
    Bug fixes
        It is no more possible to regenerate your shield by pressing select
        No more artifacts between menus (only visible on some hardware)
        No more visual glitch at the end of stage selection
    Thanks
        Bjorn Nah for dedicated play-testing
        BacteriaMage for proofreading

Previous release:

Beta 6:

    New stage: The hunt
        An orb periodically appears on the stage
        Be the first to break it, obtain an incredible strength!
    Improved menu graphics
        Completely revamped configuration screen
        Added borders to elements of all menus
        Parallax-scrolling between title and credits
        Added margin between credits and screen's border

================================================================================================================
LICENSE
================================================================================================================
DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
                    Version 2, December 2004

 Copyright (C) 2004 Sam Hocevar <sam@hocevar.net>

 Everyone is permitted to copy and distribute verbatim or modified
 copies of this license document, and changing it is allowed as long
 as the name is changed.

            DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
   TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION

  0. You just DO WHAT THE FUCK YOU WANT TO.
