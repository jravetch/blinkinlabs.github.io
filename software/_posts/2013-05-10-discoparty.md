---
layout: project
permalink: /software/discoparty/index.html
category: software
img: discoparty
title: DiscoParty - Music Reactive Lighting
technologies: [Processing, BlinkyTape]
sourcecode: [
	[DiscoParty, https://github.com/blinkiverse/blinkyboard/tree/master/examples/DiscoParty]	
]
type:
when:
collaborators:
task: 
desc:
images:
context: 
---

[DiscoParty](https://github.com/blinkiverse/blinkyboard/examples/DiscoParty) is companion software for the [BlinkyTape](/blinkytape).  It allows you to turn one or more BlinkyTapes into colorful music-reactive lighting.

![DiscoParty DJ Photo Thing]()

## Uses

* Light up your DJ booth.
* Add mood lighting to your next party.
* Create installations that react to music, voice, or other sounds.
* And more!

## Features

* Uses your computer's audio input.
* Written in [Processing](http://processing.org/), so customization is easy!

# Downloading DiscoParty

## Prerequisites

To use DiscoParty, you'll need to download and install:

* [Processing 1.5.1](http://processing.org/download/) - Use the latest stable.  DiscoParty is untested in Processing 2.0.

DiscoParty comes in the `examples` folder of the [blinkyboard source repository](https://github.com/blinkiverse/blinkyboard/) on Github.

If you have Git installed, you can grab the `blinkyboard` repository with:

	$ git clone git://github.com/blinkiverse/blinkyboard.git

If you don't have Git installed, you can download the [blinkyboard respository as a zip file](https://github.com/blinkiverse/blinkyboard/archive/master.zip).

# Using DiscoParty

1. Connect your BlinkyTape to your computer via USB.
2. Open the DiscoParty sketch in Processing
    * Find it at `blinkyboard/examples/DiscoParty/DiscoParty.pde`.
3. Click the Run button.

Out of the box, DiscoParty uses your computer's built-in sound input (ie -
microphone input) for it's sound source.  This is a great way to get started
quickly, but means that your lights will react to *all* ambient sound in the
room, not just your music.

## "Clean" Audio Input with SoundFlower (OS X Only)

For users of Mac OS X, SoundFlower is a great way to capture your system's audio
in a "clean" way.

To use DiscoParty with SoundFlower:

1. Install [Soundflower](http://cycling74.com/soundflower-landing-page/) (requires reboot!)
2. Run `Soundflowerbed`
3. Configure system audio to pipe through Soundflower:
    1. Option-click on the Volume control in the OS X taskbar
    2. Change **Output Device** to **Soundflower (2ch)**
    3. Repeat 1 and 2 to set **Input Device** to **Soundflower (2ch)**
4. Run DiscoParty as usual.

# Advanced Usage

For folks who are comfortable making things in Processing, here's a little more
in-depth technical information about how the DiscoParty works with BlinkyTapes.

You can use this information to customize the colors that are displayed, the
sound frequencies that your lights respond to, any more!

## How DiscoParty Detects Interesting Sounds

...

## How DiscoParty Displays Lights on a BlinkyTape

...
