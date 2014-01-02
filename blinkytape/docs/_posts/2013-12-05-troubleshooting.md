---
layout: doc
permalink: /blinkytape/docs/troubleshooting/index.html
title: Troubleshooting OR How to fix common issues with the BlinkyTape
---
Like anything, BlinkyTape doesn't always work perfectly. There are a few issues that you might run into while you're getting up and running, or while you're creating your BlinkyTape magnum opus.  Here are a few suggestions on how to get going again if you run into an issue.

## I'm having trouble getting started on Windows
While platforms like OS X and Linux don't need special drivers for the BlinkyTape, Windows does. The easiest way to do this is to grab the PatternPaint installer, here: [PatternPaint Releases](https://github.com/Blinkinlabs/PatternPaint/releases)

On Windows, you'll need this even if you plan to make your own custom software, while you can skip this on other platforms if you're jumping right to the coding.

## My BlinkyTape was just working, but now I'm getting a strange error message in Processing (or another program)
Most likely there's no reason to worry here. If you're seeing red text down in the bottom console box of Processing or Arduino when you try to run or upload a program, most likely the code that talks to your serial port is just confused.

Luckily there's a quick fix: stop your program (if it's not already) disconnect your BlinkyTape, then reconnect it and try again. 

## My Mac won't let me run PatternPaint
Oh, right...since OS X 10.7 / "Mountain Lion" Apple also has infrastructure for signing applications, and has shipped new systems with settings that require apps to be signed. That's great for people who want to get most of their software from the app store or big commercial developers, but we turned that off right away because we use a lot of open-source software which isn't signed because signing costs money.
 
We may get a certificate for PatternPaint, but right now, you'll need to allow your computer to run unsigned applications.  Click on the Apple logo on the top-right corner of your screen and go to `System Preferences`. Then click on `Security & Privacy` in the top row. On the next screen, you should see an option that says "Allow applications downloaded from:" -- this is the one you need to change. Set it to "Allow applications downloaded from: Anywhere." There may be a pop-up warning at this point - click the button that says "Allow from Anywhere" so PatternPaint can run.

## I'm running Windows, and Processing says something about an OpenGL framebuffer...and the program doesn't seem to work!
Sorry about that! Once again with the Windows drivers. Processing 2 and later can do advanced 3d-accelerated stuff based on OpenGL...unfortunately, there are some Windows graphics chips that can't handle it, especially when they are using older drivers.

However, all is not lost. It may be possible to fix this by installing a newer driver. Check with your graphics chip/card manufacturer and install their latest. For example, we were able to resolve this by updating the drivers for a computer with Intel HD 3000 graphics.

## I'm having some odd issues with my BlinkyTape on Ubuntu...
It seems that Ubuntu 13.10 runs a program called 'modem-manager' that identifies your BlinkyTape as a modem and tries to talk with it. In this ase, the tape will work for a moment, then stop updating, and first 10 or so LEDs on the strip will turn black.  

The easiest way to fix this is to remove the modem manager software completely:

	sudo aptitude remove modemmanager

If you do need to use a dial-up modem, you may be able to stop the service temporarily, but most users can just remove this program without any problems.

## I just made a custom Arduino program and uploaded it to my BlinkyTape! But...it doesn't seem to be doing anything.
Uh oh. It's possible to create Arduino sketches that will compile just fine, but will then crash when it tries to run on your BlinkyTape. There are a few reasons for this: using too much memory, asking for something from a memory location that's not defined, dividing by zero...that sort of thing. Some of these will put your Arduino in a state where it doesn't want to accept another sketch.

However, there is a way to force your BlinkyTape to reset, so you can reprogram it:

![BlinkyTape Reset points](/images/blinkytape/big/bt_reset.png)

We've found that it's easy to use two sewing needles to reset the tape without peeling back the protective cover. There are four small holes near the USB connector - place one needle in the one furthest from the connector, and then push one so it's touching the ground pad.  Touch the two needles together and the tape will be in reset mode. Once you've reset the tape, you'll have six seconds to start uploading a new sketch using the Arduino IDE or the 'Restore Rainbow Sketch' option in PatternPaint.

As for timing, we'd suggest clicking the Arduino upload button, then using this method to reset your tape so it can accept a new sketch. You might need to try a few times to get the timing down right, but it'll work.

It should also be noted that this won't have any lasting effect if you're not uploading a sketch - this won't reset the tape to factory by itself.

## I'm having intermittent issues, not always connecting, or strange behavior...
It's worth checking to see if your USB cable is bad.  Keep in mind that USB cables move around a lot and don't last forever, especially when you're relying on them for data transmission.  A cable that works fine for charging a phone might not work for your BlinkyTape.  Try swapping the one you're currently using for another microUSB cable, and if the one we shipped you isn't great, please let us know.

## Still no worky!!!
OK, challenges are interesting and we are eager to meet and overcome them!  Try heading to the [forum](/forums) or emailing us at `support@blinkinlabs.com`.
