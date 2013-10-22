---
layout: project
permalink: /software/patternpaint/index.html
category: software
img: patternpaint
title: PatternPaint
technologies: [Processing, Arduino, BlinkyTape]
sourcecode: [
	[PatternPaint, "https://github.com/blinkiverse/BlinkyTape/tree/master/examples/PatternPaint"]
]
type:
when:
collaborators:
task: 
desc:
images:
context: 
---

PatternPaint is companion software for the [BlinkyTape](/blinkytape).  It allows you to create animations for your BlinkyTape in real-time, and save your designs to the BlinkyTape for playback on-the-go.

![NyanCat in PatternPaint](/images/{{page.img}}/PatternPaint-nyan.png)

![NyanCat painted in light](/images/{{page.img}}/nyan-painted.jpg)

## Uses

* Create light paintings with long-exposure photography.
* Design blinky patterns for wearable lights.
* Set static patterns for ambient light installations.
* And more!

## Features

* **Simple Paint Tools** - Create vivid animated patterns with just a few clicks.
* **Live Preview** - Connect your BlinkyTape to your computer to preview your patterns in real time.
* **PNG Import and Export** - Create or edit your patterns in your favorite paint program.
* **Save to BlinkyTape** - When you're done, you can save your patterns directly to the BlinkyTape for playback away from your computer.

{% include software/patternpaint-download.md %}

# Starting PatternPaint

1. Connect your BlinkyTape to your computer via USB
2. Open the PatternPaint sketch in Processing
    * Find it at `BlinkyTape/examples/PatternPaint/PatternPaint.pde`
3. Click the Run button.

# Using PatternPaint

PatternPaint provides some simple tools for drawing your own patterns.

Alternatively, PatternPaint also lets you save and load PNG files, for use in
your favorite graphics program.

Here's a breakdown of the PatternPaint UI:

![PatternPaint Components](/images/{{page.img}}/PatternPaint-screenshot.png)

## Drawing Controls

* Click in the color selector to change the current color.
* Click in the pattern area to place points in the current color.
    * Click and drag to draw straight lines.
* Click and drag in the "ToolSize" slider to draw larger or smaller points and lines.

## Importing and Exporting Images

* Click the "Load PNG Image" button to load a PNG image file.  The pattern area will resize to fit the new image.
    * A BlinkyTape has 60 LEDs, so use images that are 60px tall to fill the whole display!
* Click the "Save PNG Image" button to save your current pattern as a PNG image.

## Live Preview Controls

* The preview frame indicator highlights the frame that is currently displayed on your BlinkyTape.
* Click the "Pause" button to pause or resume the live animation.
* Click and drag in the "Speed" slider to make the animation preview move faster or slower.
* When paused, use the Left and Right arrow keys to manually change which frame is displayed on your BlinkyTape.

# Saving Your Pattern to the BlinkyTape

**UPDATE 10/21/13:** This should now work on OS X!  Just make sure that you grab a fresh copy of the [BlinkyTape software package](/blinkytape/BlinkyTape.zip) (or follow the instructions [here](/blinkytape/docs/processing/) for the very freshest version) and that you also install something called the [AVR Crosspack, version 2013-02-12](http://www.obdev.at/products/crosspack/download.html/), which lets your Mac talk to the BlinkyTape controller board.

Patterns are way more fun when they're saved on your BlinkyTape!  For the Mac types, the process shouldn't be too difficult.

1. Fire up PatternPaint in Processing, as above. 
1. Draw the pattern you want to save.
1. Ignore the **Save to BlinkyTape** button, and just press `CMD-l` instead. (That's a lower-case L, just in case you're wondering...)
1. That's it!  Your tape should pause for a moment as it's uploading the new program, containing your custom pattern.

If you're not on OS X, this process is a bit more manual, but it's still possible.  You'll just need a few files, including this [PatternTemplate Arduino file](/blinkytape/PatternTemplate.zip) which requires the [NeoPixel Library](https://github.com/adafruit/Adafruit_NeoPixel)

1. Fire up PatternPaint in Processing, as above. 
1. Draw the pattern you want to save.
1. Click **Save to BlinkyTape**.
1. Quit PatternPaint so it will release control of your BlinkyTape.
1. Press `CMD-k` (OS X) or `CTRL-k` (Windows and Linux) to open the PatternPaint sketch folder.
1. Open the `PatternTemplate.ino` sketch in Arduino.
1. Choose **File** | **Save As**.
1. Give a name to your new Arduino sketch.  For example,"MyAwesomeAnimation".
1. Drag and drop the `pov.h` file from your file browser into Arduino.
1. Confirm that you want to overwrite `pov.h`.
1. Check the **Tools** menu options in Arduino.
    * Set **Board** to **Arduino Leonardo**.
    * **Serial Port** should match the serial port for your BlinkyTape.
	    * For Linux and OS X, this will be something like `/dev/tty.usbserialXXXXXX`.
		* For Windows, this will be something like `COM6`.
		* Your BlinkyTape must be connected to your computer for this step! :)
1. Click the Upload button in Arduino.
1. Once the upload is complete, you will see your pattern play back on the BlinkyTape!

For more information on using your BlinkyTape with Arduino, as well as information about *how to return to the factory pattern*, [click here.](/blinkytape/docs/arduino/)

# Advanced Usage

For folks who are comfortable making things in Arduino, here's a little more
in-depth technical information about how the BlinkyTape works with PatternPaint.

You can use this information to save multiple animations to your BlinkyTape,
create interactive programs that use animations, and more!

## How the BlinkyTape Plays Back Animations

* Call `pov()` in `loop()` to draw next frame
* `anim_delay_ms` to speed up/slow down animation
* Fastest framerate? 120fps?
* `animation.h`/`animation.cpp` contains the logic.

## Chaining Multiple Animations

We've created an example using multiple animations on the BlinkyTape.
The BlinkyTape draws a rainbow until the button is pressed, at which point
it finishes the painting by drawing NyanCat.

![Long NyanCat is Nyaaaaaaaaaaaan](/images/{{page.img}}/nyan-paint-long.jpg)

You can find the code in the [NyanPaint](https://github.com/blinkiverse/BlinkyTape/tree/master/examples/light_painting_examples/NyanPaint) example.
