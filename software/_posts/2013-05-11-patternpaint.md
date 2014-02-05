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
2. Open the PatternPaint program
3. Click the *Connect* button.

The frame indicator bar should start moving across the preview area, and the patterns you draw will be displayed on your tape.

# Using PatternPaint

PatternPaint provides some simple tools for drawing your own patterns.

Alternatively, PatternPaint also lets you save and load PNG files, for use in your favorite graphics program.

Here's a breakdown of the PatternPaint UI:

![PatternPaint Components](/images/blinkytape/big/PatternPaintQT.png)

## Drawing Controls

* Click in the color selector to change the current color.
* Click in the pattern area to place points in the current color.
* Click and drag in the "ToolSize" slider to draw larger or smaller points and lines.

## Importing and Exporting Images

* Click the "Load" button to load a PNG image file.  The pattern area will resize to fit the new image.
    * A BlinkyTape has 60 LEDs, so use images that are 60px tall to fill the whole display!
* Click the "Save" button to save your current pattern as a PNG image.
    * This is a great way to save your favorite patterns for later.

## Live Preview Controls

* The preview frame indicator highlights the frame that is currently displayed on your BlinkyTape.
* Click the "Pause" button to pause or resume the live animation.
* Click and drag in the "Speed" slider to make the animation preview move faster or slower.
<!-- * When paused, use the Left and Right arrow keys to manually change which frame is displayed on your BlinkyTape. -->

# Saving Your Pattern to the BlinkyTape
One of the best features in PatternPaint is the ability to save patterns to your BlinkyTape for later. When you do this, the tape will play this pattern back whenever it's plugged in to a power source.  

When you've fine-tuned your pattern, just click the "Upload" button to save it to tape! You'll see a progress bar, and the tape will stop for a moment -- now your tape will remember its pattern after you've disconnected it from the computer!  Or just connect again to fine-tune.

# Advanced Usage

For folks who are comfortable making things in Arduino or Processing, here's a little more in-depth technical information about how the BlinkyTape works with PatternPaint.  If this perks up your ears, we'd recommend checking out the information for using BlinkyTape with [Arduino](/blinkytape/docs/arduino/) and [Processing.](/blinkytape/docs/processing/)

You'll find another version of PatternPaint in the Processing blinkytape package. This one is great for hacking, but if it's not your cup of tea, you can find the source for the standalone QT-based version [right here](https://github.com/Blinkinlabs/PatternPaint/)

You can use this stuff to save multiple animations to your BlinkyTape, create interactive programs that use animations, and more!

## How the BlinkyTape Plays Back Animations

* Call `pov()` in `loop()` to draw next frame
* `anim_delay_ms` to speed up/slow down animation
* Fastest framerate? 120fps?
* `animation.h`/`animation.cpp` contains the logic.

## Chaining Multiple Animations

We've created an example of multiple animations on the BlinkyTape. With this program, the BlinkyTape draws a rainbow until the button is pressed, at which point it finishes the painting by drawing NyanCat.  

![Long NyanCat is Nyaaaaaaaaaaaan](/images/{{page.img}}/nyan-paint-long.jpg)

You can find the code in the [NyanPaint](https://github.com/Blinkinlabs/BlinkyTape_Arduino/tree/master/examples/KickstarterVideo/NyanPaint) example.
