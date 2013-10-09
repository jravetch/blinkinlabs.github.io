# Downloading PatternPaint

## Prerequisites

To use PatternPaint, you'll need to download and install:

* [Processing](http://processing.org/download/) - Use the latest stable.  PatternPaint is known to work with Processing 2.0.2.
* [Arduino](http://arduino.cc/en/Main/Software) - Allows patterns to be saved to the BlinkyTape, so not needed if you're only going to use your BlinkyTape while it's connected to a computer.

## Install the BlinkyTape Processing Libraries & Software

Now that you have downloaded Processing, let's get the BlinkyTape examples. This stuff lets us make our programs a bit more simply than if we had to do everything from scratch, as you'll see later on. There's also some helper code in here if you start programming for yourself a little down the line.

### Get it. 
Here is the link to [the package we want](/blinkytape/BlinkyTape.zip). This includes PatternPaint as a software example for Processing.<!--- we'll have to update this when there's a different download link --->

### Install it
Unzip this folder in your Processing libraries folder - this is located at Documents/Processing/libraries on Mac or My Documents\Processing\libraries on Windows.

## Install the ControlP5 library
The last step before firing up PatternPaint is to install a Processing library
called "ControlP5." This helps us draw interface elements. 

Luckily, Processing 2 has a way to easily install ControlP5 without
downloading it separately. In Processing, open the **Sketch** menu, followed by
**Import Library**, then **Add Library**.  A new **Library Manager** window will
appear. In the "*Filter your search...*" box, type in 'controlp5' and click the
ControlP5 item that appears to install it.

If you have any trouble, [here's some more info about libraries for
Processing](http://processing.org/reference/libraries/) including [instructions
for manually installing libraries](http://wiki.processing.org/w/How_to_Install_a_Contributed_Library).
If you need to install it manually, you can download ControlP5 from [the
ControlP5 home page](http://www.sojamo.de/libraries/controlP5/).

## Restart Processing

Be sure to close Processing and start it up again so it can find the new libraries.

You should now see the BlinkyTape examples if you look in the menu under
**File | Examples**. This will open a chooser-type window so you can scroll
through all of your installed examples for Processing.  You'll find ours in
**Contributed Libraries | BlinkyTape**. 
