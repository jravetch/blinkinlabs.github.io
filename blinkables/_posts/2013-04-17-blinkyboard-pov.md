---
layout: project
permalink: /blinkables/blinkyboard-pov/index.html 
category: blinkable
type: "Blinkables" 
img: blinkables/blinkytube-pov
title: "Light Painting with BlinkyTube Persistence of Vision"
technologies: [Blinkyboard, Processing, Long Exposure Photography] 
when: 04/2013
collaborators: [Matt Mets, Marty McGuire]
task:
desc: Blinkyboard POV
images:
sourcecode: [[povmaker, https://github.com/blinkiverse/blinkyboard/tree/master/examples/povmaker]]
context:
---

![Blinkiverse! Long Exposure](/images/{{page.img}}/big/blinkiverse-pov-final.png)

There are some [cool](https://sites.google.com/site/mechatronicsguy/lightscythe)
[things](http://blog.makezine.com/2012/08/12/light-painting-with-raspberry-pi/)
being done with [light painting](http://www.flickr.com/groups/lightjunkies/#derp) out
there!

We were playing with the [Blinkyboard](https://github.com/blinkiverse/blinkyboard),
our tiny board that makes it dead simple to control LEDs over USB, and realized
that light painting would be a great hack that we could knock out quickly.

# Quick Overview

<iframe class="project_full_video" src="http://player.vimeo.com/video/64485701?byline=0&amp;portrait=0&amp;color=ffffff" width="700" height="393" frameborder="0" webkitAllowFullScreen="" mozallowfullscreen="" allowFullScreen=""> </iframe>

This video shows the basics of how the process works.

# Hardware

We found some great aluminum extrusion in the markets of Shenzhen that comes in
convenient 1 meter lengths, a perfect match for our 60-count RGB LED strips!

Some double-sided tape made it easy to attach the LED strip and Blinkyboard:

![Blinkyboard and LED strip affixed to aluminum extrusion](/images/{{page.img}}/big/hardware-1.jpg)

(Yes, the Blinkyboard is *that* small.)

LEDs look great, but they look *even better* with a bit of diffusion.  We added
a 1 meter length of diffusion tubing that fit perfectly over the aluminum
extrusion (because we bought it from the same vendor).

![With a nice diffuser attached](/images/{{page.img}}/big/hardware-2.png)

**Behold, the BlinkyTube&trade;!**

# Software

With the BlinkyTube&trade; ready to go, it's time to create the actual imagery
that we will paint.

The default Blinkyboard firmware speaks a very simple serial protocol that
allows a program on your computer to push pixel values to display.

With this in mind, we wrote a [Processing](http://processing.org/) called [povmaker](https://github.com/blinkiverse/blinkyboard/tree/master/examples/povmaker).

povmaker is pretty simple.  It uses Processing's drawing routines to create our
image data on a small canvas 60 pixels tall.  Each column in the image then
becomes one "frame" for it to send to the Blinkyboard.  This happens in a loop,
so the animation simply runs over and over until you kill the program.

You can grab the source for povmaker from the [Blinkiverse GitHub](https://github.com/blinkiverse/blinkyboard/tree/master/examples/povmaker) account.  You'll want to customize it by creating your own art, adjusting drawing speeds, etc.

# Capture

At this point, we have enough of a system that we can paint some light!

![Marty, ready to do some light painting](/images/{{page.img}}/big/ready-for-pov.jpg)

Light painting works best in the dark, so it's a good idea to do it at night or,
if you're indoors, just block out the windows and shut off the lights.

Set up a DSLR camera in long exposure mode on a table or tripod, aimed at the
target area.

To create your exposure, have a human volunteer carry the laptop +
BlinkyTube&trade; combo through the target area.  Start your exposure just
before the animation begins, and stop it just after the animation ends.

![Our imagery. Some text that reads "Blinkiverse!" and a couple of red bars to help time the shot](/images/{{page.img}}/big/povmaker.png)

To help coordinate our camera and walking work, we added a couple of full-height
red bars, separated by some black space to our image.  The practical effect of
these bars is that the BlinkyTube&trade; flashes red to indicate when it is time
to start the exposure and get moving.

It took us a few tries to get a decent capture, but failure is cheap with
a digital camera!

# Results

![Blinkiverse! Long Exposure](/images/{{page.img}}/big/blinkiverse-pov-final.png)

The BlinkyTube&trade; POV turned out to be a great [speed project](http://fffff.at/speed-project/).
We went from zero to passable images in less than an hour.

Even better, we now have a tool for making some lovely light-painted mischief.

Stay tuned for a future update where we will store the animation on the
Blinkyboard itself for battery-powered light-painting action!
