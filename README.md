### Code for the Aurora LED wall: an iPad-controlled and music-responsive matrix of LEDs

For a description see [here](thecolorofthin.gs/post/25415779978/the-aurora-led-wall-a-4-foot-by-8-foot).
For build details including an extensive description of the code, see [here](thecolorofthin.gs/post/25418889588/build-details-for-the-aurora-led-wall).

Here are what the main and utility sketches do:
* LEDwallProcessing (the main loop and the iPad communication over OSC)
* BeatDetect (the code to allow responsiveness to music)
* CircularArray (a utility class for circular arrays used by the beat detection)
* Console (a class to display console output in a window when running as a standalone executable)
* Drawer (a base class for providing common utilities to each visualization program including doing gamma correction, accessing the current color palette, the current beat information and settings from the iPad)
* PaletteManager (a class to create and manage color palettes making it easy to shape the color scheme)
* Pixels (class to draw to the screen and/or the LED wall if it’s connected)
* SerialPacketWriter (utility class for creating packets to send to the microcontroller)
 

The following visualizations have been checked in. These inherit from the base Drawer class so they have access to the different parameters controlled by the iPad including the color palette to use, animation speed, color cycling speed (how fast to cycle through the color palette), custom settings for each animation, brightness, and various audio settings to make them beat sensitive:
* AlienBlob: uses Perlin noise to create smooth blobs of color that bounce around; different settings (controllable from the iPad) allow zooming in and out to change the size of the blobs as well as increasing the harmonics of the Perlin noise to alter the complexity of the blobs.
* BouncingBalls2D: a customizable number of balls of different sizes bouncing around a box in 2-dimensions including gravity and using physics to calculate fully elastic collisions.
* Paint: use your finger(s) to paint color-changing pictures on the wall from the iPad or just create ribbons of color that slowly (or quickly) disappear
* Fire: a flickering fire covering the wall with standard fire colors or a custom palette giving unreal effects.
* Belousov–Zhabotinsky reaction: a 2-dimensional cellular automota implementation of the cycling chemical phenomenon called the BZ reaction (adapted from www.aac.bartlett.ucl.ac.uk/processing/samples/bzr.pdf); this program displays rippling arc-like patterns that form in a somewhat chaotic way and tend to settle into repeating patterns that can be disturbed with finger touches to the iPad and with gradients that can be “sharpened” to increase contrast

