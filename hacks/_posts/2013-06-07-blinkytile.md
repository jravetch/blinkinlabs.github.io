---
layout: project
permalink: /blinkytile/index.html
category: hacks
type:
img: blinkytile
title: "BlinkyTile - A square LED matrix made from BlinkyTape"
technologies: [BlinkyTape, Laser Cutter]
when: 06/2013
collaborators:
task:
desc: Re-assemble your BlinkyTape into a 2D grid display of roughly 8x8 pixels.
images:
sourcecode: [[BlinkyTile, "https://github.com/blinkiverse/BlinkyTape/tree/master/examples/BlinkyTile"]]
context:
---

<div class="videoWrapper">
	<iframe class="vine-embed" src="https://vine.co/v/bLhMhIjzqFW/embed/simple" width="480" height="480" frameborder="0"></iframe><script async src="//platform.vine.co/static/scripts/embed.js" charset="utf-8"></script>
</div>

The BlinkyTile is an advanced hardware project that you can do with your
[BlinkyTape](/blinkytape). It allows you to turn your BlinkyTape into a square
display of (almost) 8x8 pixels!

This project is pretty advanced, so be prepared to spend some time on it!

# What You'll Need

## Tools

* Wire cutters
* Soldering station
* Laser cutter
* Acrylic Glue with syringe applicator
* Clear tape

## Supplies

* 1 x BlinkyTape
* 22ga stranded wire, 3 colors
* 3 x M3 bolts, 8mm long, with washers and nuts
* Laser cutting materials for the frame:
	* Black (or otherwise opaque) 1/8" acrylic, 12"x12" sheet
	* Translucent 1/8" acrylic, 12"x12" sheet
	* Thick card stock (or 1/32" acrylic), 12"x12" sheet

# Step 1: Segmenting the BlinkyTape

First, remove the silicone plastic tubing from the BlinkyTape.  It won't be
needed anymore!

We need to cut the BlinkyTape into 8 sections:

* One 6-pixel long section that includes the BlinkyBoard controller and USB port
* Six 8-pixel long sections
* One final 6-pixel long section

The flexible PCB backing that makes up the BlinkyTape contains copper, so you
will want to use wire cutters to cut the tape.

When you're done, you'll have something like this:

![BlinkyTape cut into strips](/images/{{page.img}}/big/blinkytape-strips.jpg)

# Step 2: Cut and Strip Wires

We now have 8 segments that we need to join together.

![Data-out side of a strip](/images/{{page.img}}/big/tape-segment-cut.jpg)

You'll notice that each segment has arrows along the length of the strip.  These
arrows indicate the direction that data moves along the strip.  For example, the
top row's arrows point to the right, indicating that data comes in on the left
and goes out on the right.  When wiring up two sections, we'll need to make sure
that the arrows are facing the same direction.

To save wire and hassle, we'll be joining our 8 segments in a "S" curve, using
short jumper wires to connect one row to the next.  This means that each segment
will be "upside down" relative to the previous segment, but allows data to flow
in the correct direction.

8 segments means we need to make 7 jumper connections.  Each connection requires
three wires - Data, 5V, and GND.  Since these wires will be curving around to
make a "C"-shape at each connection, we'll need to cut them at different
lengths. Here is a set of links that worked for us.

| Connection | Data wire length | 5V wire length | GND wire length |
|---|---|----|---|
| 1 | 7mm | 6mm  | 5mm
| 2 | 5mm | 6mm  | 7mm
| 3 | 7mm | 6mm  | 5mm
| 4 | 5mm | 6mm  | 7mm
| 5 | 7mm | 6mm  | 5mm
| 6 | 5mm | 6mm  | 7mm
| 7 | 9mm | 8mm  | 7mm

![Some examples of pre-cut wires](/images/{{page.img}}/big/pre-cut-wires.jpg)

Above is an image of pre-cut and pre-stripped wire bundles for 4 connections.
We used blue for Data, red for 5V, and black for GND.

# Step 3: Reassembling the BlinkyTape

## Step 3a: Tin all of the wires and solder pads with solder.

To help make it easier ot mound the LEDs later, we'll be soldering the jumper
wires to the solder pads on the back of the strip.

## Step 3b: Solder the first jumper connection

![Jumper wires attached to the back of the first segment](/images/{{page.img}}/big/pre-cut-wires.jpg)

Solder the first three wires to its appropriate pad on the "DO" (Data Out) side
of the first segment (the segment with the BlinkyBoard attached).

It can be easy to lose track of which pad goes to which wire when you're looking
at the back of the strip, so be sure to double-check which wire is going where.

## Step 3c: Connect the next segment

![Front view of a complete connection](/images/{{page.img}}/big/jumpered-segments-front.jpg)

Solder the jumper wires from the first segment onto the next segment.  Be sure
to make the following connections:

* GND from segment 1 connects to GND on segment 2
* 5V from segment 1 connects to 5V on segment 2
* **DO** from segment 1 connects to **DIN** on segment 2

## Step 3*: Repeat!

![Completed soldering job](/images/{{page.img}}/big/reassembled-segments.jpg)

Repeat steps 3b and 3c, using the correct length wires at each step, to connect
the remaining segments of the board.  Above is an image of the reassembled
BlinkyTape with all jumpers soldered.

Now would be a great time to plug your reassembled tape into a computer to test
it out.  You'll want to find broken/missing/incorrect wiring now rather than
once you've closed the BlinkyTape up in a box!

# Step 4: Create the Enclosure

## Cutting the Pieces

We've provided DXF format laser cutting files for the pieces that we used to
construct our enclosure.  You can find them here:

[BlinkyTile hardware files on GitHub](https://github.com/blinkiverse/BlinkyTape/tree/master/examples/BlinkyTile/case_design)

You'll need to use your favorite software to arrange these files into "cutting
plates" to cut out of the appropriate plastic.  Here's a quick breakdown of
which parts should be made of which plastic:

* Main Frame (1/8" black or other opaque acrylic sheet, 12"x12")
	* frame-back.dxf
	* frame-bottom.dxf
	* frame-top.dxf
	* frame-left.dxf
	* frame-right.dxf
* Front Diffuser (1/8" semi-transparent acrylic, 12"x12")
	* frame-front.dxf
* LED Mount (1/32" acrylic or heavy card stock)
	* led-mount.dxf

# Step 5: Assembly!

## Mounting the LEDs

![LEDs secured to cardstock mount with clear tape](/images/{{page.img}}/big/cardstock-back-with-LEDs.jpg)

The LED mount has a space for the BlinkyBoard and USB connection and a succesion
of holes that each LED should "click" into.  Because the wire jumpers put a
torque on the strip that tends to make them pop out, we secured the ends of each
segment with some clear tape.

![LED mount secured to the frame back with M3 hardware](/images/{{page.img}}/big/LED-mount-secured.jpg)

Next, attach the LED mount to the frame back using M3 hardware.  We used 8mm
long bolts pushed through the back of the frame back, then used a washer and a
nut on the LED mount side, where -- once the lid is in place -- they won't be
seen.

With the current enclosure design, the USB cable must be plugged in before
assembling the final box, so go ahead and do that now.  You may want to add
some strain relief in the form of a small zip-tie on your USB cable that will
remain just inside the box to keep the cable from disconnecting if it is
pulled on.

## Assembling the Box

Do a "dry fit test" of all of your frame parts.  Start by identifying which of
the side pieces is which.

* One side piece has a hole for the USB cable. We'll call this the "right side".
* The "left side" goes opposite of the right side, and can be identified because
it is the same length as the right side.
* The "top side" is the shortest in length.  It is meant to sit snugly between
the left and right sides.
* The "bottom side" is the longest in length.  It is meant to be a "seat" for
the left and right pieces.

Starting with the frame back lying flat on a table, use acrylic glue to attach
each of the sides, starting with the "right side", followed by the "top side",
"left side", and finally "bottom side".

Once the sides are nicely affixed to the frame back, we can attach the
front of the frame using acrylic glue.  Start by placing the front piece on top
of the frame to get it lined up.  The front piece should just cover every edge
of the frame.  Then, use a syringe applicator to squirt acrylic glue into the
space between the front piece and the frame.  Do this on all four sides and
apply pressure to make sure that the glue makes a nice bond.

Finally, let the glue set according to the instructions.

# Power it Up!

![Completed BlinkyTile](/images/{{page.img}}/big/completed-blinkytile.jpg)

Plug the USB into your computer to see the results of your labor!

# Coming Soon...

This project is a work-in-progress.  We'll be making some revisions soon
including:

* Better photos and diagrams
* Software to make it easy to use your BlinkyTile
* Ways to customize your build

Thanks for reading!  Got some feedback?  Feel free to drop us a note via Twitter
at [@BlinkyTape](http://www.twitter.com/BlinkyTape)!
