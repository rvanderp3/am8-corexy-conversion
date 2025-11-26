# am8-corexy-conversion

WIP: I'm still wrapping up the build but wanted to start documenting it here.

## Overview

I got into 3d printing almost 2 years ago and to be honest, I didn't expect to enjoy the hobby as much as I do.  My friends, i’m sure, are tired of hearing me talk about it.. not to mention my poor, wonderful wife, Chelsea. My first printer was a very second hand AM8 off Facebook marketplace.  Since then I picked up a new Anycubic Kobra 3 and another very used 3D printer, a Creality Ender 3 off of Facebook marketplace.  The hobby has allowed me to tie together the geek nexus of interests that I have: electronics, programming, physics, and mechanical engineering.  With the exception of programming, I am very much an amateur… though folks that review my code might argue I'm an amateur at that too.

Since getting started in the hobby I've made numerous mistakes.  As much as I wanted to, you can’t just start printing and hope to end up with anything even close to decent with ancient printers.  Sure, you can buy a Bambu or newer Amycubic and its fairly “turn key” but where is the fun in that?  Eventually, even with those awesome machines you'll run into trouble and will be forced to wait on replacement parts or fix them yourself.

In this project I'll be covering my most recent endeavor in converting my old AM8 into a core xy printer loosely based on the MP3DP v5.  If you've never heard of V1 engineering,  they are a company that produces designs of 3D printers, CNC machines, and sand tables that you can build yourself with parts largely obtained from the hardware store.  This is a follow on project to my build of the MPCNC also designed by V1 engineering.  

Goals for the project:
- Mill all aluminum brackets with the MPCNC.
- Use every component possible from the AM8.
- Model all my own plastic parts with the exception of what I'm able to directly reuse from the MP3DP design.
- Buy as little as possible from Amazon.
- Be as fast as my fastest bed slinger > 300mm/sec.
- No compromise in quality.
- Be a platform for learning and experimentation.
- I already have two other cartesian bed slingers and I want to try something new.
- Have fun!

Don't get me wrong, the AM8 can be a really useful printer.  However, there are some issues. It’s not fast. Seriously, it’s not fast. Quality of prints, at least in my case, we're passable but not great. Keeping the 300x300mm bed leveled is difficult at best and needs near constant recalibration. The motherboard is antiquated and arguably a fire hazard. With all that said ...

__Let's Get Started and Make Mistakes!__

## Needed Parts

From the AM8, I'm reusing:
- All aluminum extrusion 
- Linear rods and bearings
- Lead screws
- Heated bed
- Power supply
- Limit switches, though these are technically optional if you use sensorless homing.

The primary elements I'm resuing from the MP3DP: 
- Core xy kinematic design with modifications to support the linear rails belt layout
- The 3 z axis motor design, though I'm using lead screws rather than belts

From Amazon, I bought:
- Timing Belt
- Idler pullies
- Drive pullies
- Motherboard capable of running 6 or more steppers
- M3 and M5 screws
- Coffee for the 3D modeling
- CA glue with activator - hopefully you wont need this but is cuper helpful for prototyping your own customizations
- 2 500mm pieces of 2020 aluminum extrusion.  You can forego this, but your x axis will be less than 200 mm.  Not a deal breaker, but :shrug:.
- Bowden tube extruder.  You can reuse the anet a8 extruder, but I'm looking for a bit more capability in this build.
- An additional lead screw for the third z axis motor

From the hardware store:
- ¾” electrical conduit
- Blue glue to keep screws from backing out
- Slide on electrical connectors, but consider soldering if you're using limit switches

My current implementation results in the following dimensions:
- X: 280 mm
- Y: 280 mm
- Z: 195 mm

These dimensions are largely constrained by my own goals of hardware reuse.  The beauty of the MP3DP design in concert with the design elements introduced in this project is that you can largely determine or change your build volume with relatively simple, cheap upgrades.  Granted, the MP3DP project alone allows you to determine your own build volume.  By using linear rods, you get additional granularity in build volume you don't get with linear rails.  Not a huge advantage, but it does lend itself to “using what you have” which was the overarching goal for this printer.

### Printed Parts
- 3 Z axis linear rail mounts: 1 left, right, and center and associated backing plates
- 3 Z axis motor mounts and backing plates
- 4 Linear rod mounts for the y axis
- 3 60 degree brace brackets and associated backing plates
- 3 bed mounts: 1 left, right, and center
- 1 bed spacer

Optional: don't want to or cant Mill parts? Now obviously… there are down sides here, especially for rigidity.  That said, it works. Time will tell if this is a bad idea.  Just be aware of temperature limitations of the filament you're using. If you're printing in PLA, for example, the chamber temp can’t exceed 60C.  The same applies to the stepper motor mounts.

- 2 corner power brackets and stepper motor mounts
- 4 tensioner brackets
- 2 X axis mounting brackets
- 1 x carriage printed in ASA or ABS. As long as the heat break fan is on when the hot end is running, ABS and ASA seem to hold up fine.

### Milled Parts

# Assembly

## Disassemble the AM8

__Note: It is highly recommended that you have a second 3D printer for printing replacement parts. Otherwise, make sure you print everything before you disassemble your AM8 .. obviously :)__

1. Break down all parts of the AM8 except for the base. It is already square(hopefully) and the rest of the build will take place on or around the base.
2. Clean everything. If it is anything like mine, it's covered in years of grime.  Especially the linear rod. To ensure smooth motion with the linear rods, be sure to clean them.
3. Store everything away

Print the parts.  Supports are recommended. Use 40% infill.

## tuning
Tuning bowden extruder often requires a slightly different set of starting values than a direct drive.  Then length of the tube results in a lesser impact of retraction on the backpressure at the nozzle tip. Tube itself stores energy that can continue to apply pressure to the filament and cause oozing, blabbing, etc...
- retraction, 5 - 10% length of bowden tube
- pressure advance, 1s, .12s



