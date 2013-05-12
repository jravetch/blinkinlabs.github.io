---
layout: project
permalink: /patternpaint/index.html 
category: software
img: patternpaint
title: PatternPaint
technologies: [Processing, Arduino]
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

# PatternPaint

![Image of PatternPaint w/ something cool in it]()

[PatternPaint](https://github.com/blinkiverse/blinkyboard/examples/PatternPaint) is companion software for the [BlinkyTape](/blinkytape).

It allows you to create animations for your BlinkyTape.  Plug in your BlinkyTape to preview your patterns in real time.  When you're done, 

Uses:

* Light painting
* Flashy wearable lights
* Ambient light patterns
* And more!

## Installing PatternPaint

### Prerequisites

PatternPaint is written in [Processing](http://processing.org/).

To use PatternPaint, you'll need to download and install:

* [Processing 1.5.1](http://processing.org/download/) - Use the latest stable.  PatternPaint is untested in Processing 2.0.
* [ControlP5 1.5.2](https://code.google.com/p/controlp5/downloads/list)
  * Installation instructions can be found [here](http://www.sojamo.de/libraries/controlP5/)

Saving patterns to the BlinkyTape currently requires [Arduino](http://arduino.cc/) to program the BlinkyTape.

To save patterns directly to your BlinkyTape, you'll need to download and install:

* [Arduino 1.??](http://arduino.cc/download)

### Downloading PatternPaint

## Starting PatternPaint

1. Connect your BlinkyTape to your computer via USB
2. Open `PatternPaint.pde` in Processing
3. Click the ![run icon]() Run icon

## Using the Paint Tool

## Importing Images

## Saving Your Pattern to the BlinkyTape

### Using Arduino

* Click **Save to BlinkyTape**
* Quit PatternPaint so it will release control of your BlinkyTape
* Press `CMD-k` (OS X) or `CTRL-k` (Windows and Linux) to open the PatternPaint sketch folder
* Open the `??????.ino` sketch in Arduino
* Choose **File** | **Save As**
* Give a name for your new Arduino sketch, like "MyAwesomeAnimation"
* Drag and drop the `pov.h` file from your file browser into Arduino
* Confirm that you want to overwrite `pov.h`
* Check the **Board** menu options in Arduino
** Board should be **Arduino Leonardo**
** Serial Port should be the blah blah blah.  What is a concise way to explain this?  Unplug, check menu, plug in, check menu for the new serial port?
* Click the ![upload icon]() Upload icon in Arduino
* See your pattern!

## Advanced Usage

### How the BlinkyTape Plays Back Animations

* Call `pov()` in `loop()` to draw next frame
* `anim_delay_ms` to speed up/slow down animation
* Fastest framerate? 120fps?

### Chaining Multiple Animations

[NyanPaint](https://github.com/blinkiverse/blinkyboard/tree/master/examples/light_painting_examples/NyanPaint)
