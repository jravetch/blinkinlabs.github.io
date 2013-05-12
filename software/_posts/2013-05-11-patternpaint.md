---
layout: project
permalink: /patternpaint/index.html 
category: software
img: patternpaint
title: PatternPaint
technologies: [Processing, Arduino, BlinkyTape]
sourcecode: [
	[PatternPaint, https://github.com/blinkiverse/blinkyboard/examples/PatternPaint]	
]
type:
when:
collaborators:
task: 
desc:
images:
context: 
---

![Image of PatternPaint (Nyan) side-by-side w/ light painting]()

[PatternPaint](https://github.com/blinkiverse/blinkyboard/examples/PatternPaint) is companion software for the [BlinkyTape](/blinkytape).  It allows you to create animations for your BlinkyTape in real-time, and save your designs to the BlinkyTape for playback on-the-go.

## Features

* **Simple Paint Tools** - Create vivid animated patterns with just a few clicks.
* **Live Preview** - Connect your BlinkyTape to your computer to preview your patterns in real time.
* **PNG Import and Export** - Create or edit your patterns in your favorite paint program.
* **Save to BlinkyTape** - When you're done, you can save your patterns directly to the BlinkyTape for playback away from your computer.

## Uses

* Load images for light painting with long-exposure photography
* Create flashy patterns for wearable lights
* Design static patterns for ambient light installations
* And more!

# Installing PatternPaint

## Prerequisites

PatternPaint is written in [Processing](http://processing.org/).

To use PatternPaint, you'll need to download and install:

* [Processing 1.5.1](http://processing.org/download/) - Use the latest stable.  PatternPaint is untested in Processing 2.0.
* [ControlP5 1.5.2](https://code.google.com/p/controlp5/downloads/list) - Provides the UI widgets for PatternPaint.
	* Installation instructions can be found [here](http://www.sojamo.de/libraries/controlP5/)

### Saving Patterns

Saving patterns to the BlinkyTape currently requires [Arduino](http://arduino.cc/) to program the BlinkyTape.

You'll need to download and install [Arduino 1.0.4](http://arduino.cc/en/Main/Software)

## Downloading PatternPaint

PatternPaint comes in the `examples` folder of the [blinkyboard source repository](https://github.com/blinkiverse/blinkyboard/) on Github.

If you have Git installed, you can grab the `blinkyboard` repository with:

	$ git clone git://github.com/blinkiverse/blinkyboard.git

If you don't have Git installed, you can download the [blinkyboard respository as a zip file](https://github.com/blinkiverse/blinkyboard/archive/master.zip).

# Starting PatternPaint

1. Connect your BlinkyTape to your computer via USB
2. Open the PatternPaint sketch in Processing
    * Find it at `blinkyboard/examples/PatternPaint/PatternPaint.pde` 
3. Click the Run button.

# Using PatternPaint

![PatternPaint Components](/images/{{page.img}}/PatternPaint-screenshot.png)

## Drawing Conrols

* Click in the color selector to change the current color.
* Click in the pattern area to place points in the current color.
    * Click and drag to draw straight lines.
* Click and drag in the "ToolSize" slider to draw larger or smaller points and lines.

## Live Preview Controls

* The preview frame indicator highlights the frame that is currently displayed on your BlinkyTape.
* Click the "Pause" button to pause or resume the live animation.
* Click and drag in the "Speed" slider to make the animation preview move faster or slower.
* When paused, use the Left and Right arrow keys to manually change which frame is displayed on your BlinkyTape.

## Importing and Exporting Images

* Click the "Load PNG Image" button to load a PNG image file.  The pattern area will resize to fit the new image.
    * A BlinkyTape has 60 LEDs, so use images that are 60px tall to fill the whole display!
* Click the "Save PNG Image" button to save your current pattern as a PNG image.

# Saving Your Pattern to the BlinkyTape

Patterns are way more fun when they're saved on your BlinkyTape!

Unfortunately, this process is a bit manual at the moment.  We hope to automate many of these steps in the near future!

1. Click **Save to BlinkyTape**
1. Quit PatternPaint so it will release control of your BlinkyTape
1. Press `CMD-k` (OS X) or `CTRL-k` (Windows and Linux) to open the PatternPaint sketch folder
1. Open the `PatternTemplate.ino` sketch in Arduino
    * Find it at `blinkyboard/examples/PatternTemplate/PatternTemplate.ino`
1. Choose **File** | **Save As**
1. Give a name for your new Arduino sketch, like "MyAwesomeAnimation"
1. Drag and drop the `pov.h` file from your file browser into Arduino
1. Confirm that you want to overwrite `pov.h`
1. Check the **Board** menu options in Arduino
    * Board should be **Arduino Leonardo**
    * Serial Port should match the serial port for your BlinkyTape.
	    * For Linux and OS X, this will be something like `/dev/tty.usbserialXXXXXX`
		* For Windows, this will be something like `COM6`
		* Your BlinkyTape must be connected to your computer for this step! :)
1. Click the Upload button in Arduino.
1. Once the upload is complete, you will see your pattern play back on the BlinkyTape!

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
The BlinkyTape's button is used to make it interactive!

The end result? Light painted NyanCat!

![NyanCat!!!!]()

### How it Works

* When powered on, the BlinkyTape begins playing a rainbow animation.
* When the button is pressed, the BlinkyTape changes to show NyanCat, then stops
  animating.
* Pressing the button again will return to the rainbow animation.

You can find the code in the [NyanPaint](https://github.com/blinkiverse/blinkyboard/tree/master/examples/light_painting_examples/NyanPaint) example.
