# SolidCam-Mach3-Post
## A SolidCam postprocessor for Mach3, supporting 4x and 5x operations

**This post is yet to produce code that has been run on a real machine ! Use at your own risk !**

Inspired by bogan
Special thanks to Bruno Silva, modelling and testing.

CNCZone discussion link: http://www.cnczone.com/forums/solidcam/255556-cnc.html


Setup: standard 3 axis mill. A axis rotary, along X or Y.

##Current status :
 - 3 axis - working
 - 4 axis - working / for both repositioning moves and 4x toolpaths
 - 5 axis - working
 - Drill cyclels - G81 (drill), G82 (drill+dwell), G83 (peck drilling), Cannes: G85, G86, G89 
 - Tapping seems to work
 
##TODO :
 - 4x indexial use may need some more work to avoid unnecessary retracts to clearance. As of now it's safe but can be made faster w/o retracts.
 - Tool offsets and compensation

##Installation and usage notes :
 - Put the .gpp and .vmid files in `C:\Users\Public\Documents\SolidCAM\SolidCAM2015\Gpptool`
 - Usage in SolidCam - Select `Mach3_4X` or `Mach3_4X` for CNC-Machine
 - Mach3 setup
  * Config > General Config - tick `A-axis is angular`, set `IJ mode` to incremental, uncheck all in `Rotational`, possibly also check `G04 dwell in ms`
  * Config > Toolpath - Check `X-axis` / `Y-axis` for axis of rotation and enable `A-rotations`. `3d compass` also helps.

**Usage : Do set your CoordSyses so that the CS origin is in the pivot point (axis of rotation) and X is the axis around which the part revolves**