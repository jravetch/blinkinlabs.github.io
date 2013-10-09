---
layout: project
permalink: /blinkytape/index.html 
category: hardware
type: "Interactive Lighting Controller" 
img: blinkytape
title: BlinkyTape
technologies: [C/C++, Arduino, Processing]
desc:
images:
sourcecode: [
	[BlinkyTape, "https://github.com/blinkiverse/BlinkyTape"]
]
---

## Sign Up to be Notified when the BlinkyTape is Available for Purchase

We're busily manufacturing the first BlinkyTapes for our Kickstarter Backers.
Afterwards, we plan to make the BlinkyTape available for purchase via
distributors online.

**Subscribe here to be notified when the BlinkyTape becomes available!**

<!-- Begin MailChimp Signup Form -->
<div id="mc_embed_signup">
<form action="http://blinkiverse.us7.list-manage1.com/subscribe/post?u=dc573c24e7e76c16c7e391838&amp;id=e44ba946d9" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
	<input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
	<input type="hidden" value="btweb-avail-2013-07" name="SIGNUPSRC" id="SIGNUPSRC"/>
	<input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button">
</form>
</div>

<!--End mc_embed_signup-->

<div class="videoWrapper">
	<iframe class="project_full_video" src="http://player.vimeo.com/video/66034735?byline=0&amp;portrait=0&amp;color=ffffff" width="100%" height="394px" frameborder="0" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>
</div>

We've had a lot of fun [working](/domestar) with [LEDs](/daftpunk), but we've often been frustrated by how difficult they can be to program, power, mount, and enclose.

That's why we invented the BlinkyTape!

![Meet BlinkyTape](/images/{{page.img}}/big/bt.jpg)

BlinkyTape is a one meter long, full-color light tape with 60 independent RGB LEDs controlled by our custom light processor. Power and communications are provided by a built-in micro-USB connector. An on-board button allows for simple interactions such as choosing between effects.

BlinkyTape is flexible, so you can easily integrate it into any shape your project needs. BlinkyTape also comes enclosed in weatherproof silicone, so it's suitable for outdoor use!

# Portable Power

![Portable Power](/images/{{page.img}}/big/power.png)

Patterns can be stored directly on the BlinkyTape, so there's no need for a dedicated computer. Taking designs on the go is as simple as plugging the BlinkyTape into a USB battery pack!

# Software

The BinkyTape comes with bright, colorful built-in patterns, but of course you will want to make your own!

## Pattern Editor

![PatternPaint](/images/{{page.img}}/big/pattern.png)

The BlinkyTape comes with a rich set of companion software that run cross-platform on Mac OS X, Windows, and Linux. Creating custom animations is as easy as plugging the BlinkyTape into your computer and starting [PatternPaint](/software/patternpaint/). Patterns can be edited in real-time, or saved to the strip for playback away from the computer.

## Music Reactive Mode

Need some sweet lighting for your next party? No problem, hook a couple of BlinkyTapes up to your USB port, fire up [DiscoParty](/software/discoparty/), and you'll have flashing colors and bright lights in no time.

## Hacking

![Processing](/images/{{page.img}}/big/processing.png)

Our favorite thing about the BlinkyTape is how easy it is to program to meet your own needs.

The BlinkyTape understands a simple serial protocol over USB, and we have plenty of example code for controlling the BlinkyTape using free programming environments such as Processing and Python.

![Arduino](/images/{{page.img}}/big/arduino.png)

Of course, it's possible to go even lower level. The BlinkyTape uses the same ATMEGA32u4 processor that you will find in the Arduino Leonardo, and can be programmed using the same easy-to-learn Arduino programming environment. We provide plenty of examples to get your project started!

# We &lt;3 Open Source Hardware

![We &lt; Open Source](/images/{{page.img}}/big/opensource.jpg)

We strongly believe in open source, and the BlinkyTape is no exception. All of the design files, PCB layouts, and source code are available now on Github.

Got a cool extension or some neat patterns? Please share them! Operators are standing by to review your pull requests.

# Speed Projects

Every one of the projects in our Kickstarter video is what we like to call a Speed Project.  Speed Projects are typically done in one sitting and we think that these really show off how powerful the BlinkyTape can be!

## Blinky Hat - 30 minutes

![Blinky Hat](/images/{{page.img}}/big/hat.png)

The Blinky Hat started its life as a $7 hat found on the streets of Shenzhen, China.  With the help of some double-sided tape, we wrapped a BlinkyTape around the hat brim and plugged it into our computer.

We used the live preview feature of PatternPaint to map out which LEDs were part of the front-left, front-right, and rear parts of the hat.  From there it was a simple matter of making some sweet animations and saving them to the BlinkyTape.  The last step was to simply unplug from the computer and plug into a portable USB charger!

**More Information**

* Learn more about [PatternPaint](/software/patternpaint) and how you can make your own patterns!
* Check out the [BlinkyHat source](https://github.com/blinkiverse/BlinkyTape/tree/master/examples/FLEDora)

## Movie FX - 1 Hour

![Movie SFX](/images/{{page.img}}/big/sfx.jpg)

Inspired by the computer-screens-projected-on-faces effects in a popular sci-fi film, this project required only a BlinkyTape, some double-sided sticky tape, and a 4-sided box.

With the BlinkyTape attached to the front of the box we loaded up PatternPaint to make some cool looking animations that would light up our victi-, er, actor's face.  After saving the pattern to the BlinkyTape, we just needed to find a dark, quiet place to film!

**More Information**

* Learn more about [PatternPaint](/software/patternpaint) and how you can make your own patterns!
* Check out the source:
    * ["Dave" animations](https://github.com/blinkiverse/BlinkyTape/tree/master/examples/Dave)
	* ["Hal" pattern](https://github.com/blinkiverse/BlinkyTape/tree/master/examples/Hal9000)

## DJ Booth - 10 Minutes

![DJ Booth](/images/{{page.img}}/big/dj.jpg)

Armed with 3 BlinkyTapes mounted in our aluminum diffuser tubes, a USB hub for power, and a MacBook Pro for the tunes, this project was a breeze to set up.

Using the awesome SoundFlower from Cycling '74, we looped the laptop's outgoing audio back in to the system input.  This gives a clean audio signal to our DiscoParty app, which runs in Processing and makes use of the built-in beat detection analysis that Processing provides.

Warning: This project is super quick to set up, but we had so much fun tweaking the various visual effects that we spent hours playing with it afterwards.

**More Information**

* Learn more about the [DiscoParty](/software/discoparty) app and how you can run it yourself.

## Light Painting - 10 Minutes

![Nyan](/images/{{page.img}}/big/nyan.jpg)

This project used a BlinkyTape mounted in an aluminum diffuser tube, a camera with a long exposure setting, and a dark place to shoot pictures.

PatternPaint makes light painting super simple with its image import functionality.  Since the BlinkyTape has 60 RGB LEDs, we can load in almost any image that is 60 pixels tall.  By saving the pattern to the BlinkyTape and powering it with a portable USB charger, we can make ridiculously awesome light paintings anywhere and everywhere (that it is dark enough to do so).

**More Information**

* Learn more about [PatternPaint](/software/patternpaint) and how you can make your own patterns!
* Check out the [NyanPaint](https://github.com/blinkiverse/BlinkyTape/tree/master/examples/light_painting_examples/NyanPaint) source.
* Our initial [experiment on light painting](/light-painting/) shows off the hardware setup.

# OK, awesome! How do I lean how to use it?

We are so glad you asked. We have been working on a sweet [Getting Started Guide](/blinkytape/docs/getting-started/) which should help you learn about basic usage, including how to make your own programs and new firmware.

# Tech Specs

The BlinkyTape is a one meter strip of flexible PCB material containing 60 RGB LEDs.  At one end is our custom light processor, the BlinkyBoard.  The BlinkyTape comes enclosed in a weatherproof silicone tubing.

## BlinkyBoard Specs

* 8-bit ATMEGA32u4 operating at 16MHz
* 32KB Flash memory
* 2.5KB RAM
* 1KB EEPROM
* Micro USB connector for power and data
* On-board micro switch for interactive applications
