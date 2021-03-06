---
layout: doc
permalink: arduino/index.html
title: Programming your Blinkytape's firmware
---
We're about to do some very exciting stuff -- we're going to put a whole new program right on your Blinkytape. Since this is a pretty small program that runs on a piece of hardware, we're going to call it *firmware.* If you're not familiar with the term already, you'll probably hear the term again when you're updating the software on a new camera, TV, car, or smart fridge. At the end of the day, it's a program like any other that runs on a tiny computer in the Blinkytape (the Blinkyboard.)

So, in order to make new firmware for your Blinkytape, we're going to install the Arduino environment, followed by a few special libraries.  Then we're going to show you how to get a simple program on there. At that point, you should have the basic knowledge you need to get started on your own, so it'll be time for us to tearfully send you out into the world *by yourself.*

{% include btdocs/install-arduino.md %}

{% include btdocs/install-arduino-bt-libs.md %}

{% include btdocs/plug-it-in.md %}

{% include btdocs/arduino-pre-program.md %}

## Load the default firmware - ColorSwirl.

Let's just practice to make sure we have this part down.

1. In the menus for Arduino, choose **File | Examples | BlinkyTape_Arduino | ColorSwirl**

{% include btdocs/arduino-program.md %}

If that all went well, it should look just like when you first plugged in your BlinkyTape.

## Load the "Hello World" Program in Arduino

* Open Arduino
* In the menus, choose **Examples | BlinkyTape | HelloBlinky**
* You should see something like this:
![HelloBlinky loaded in Arduino](/images/blinkytape/big/HelloBlinky.png)


## Make Your Changes!
HelloBlinky will cycle through the BlinkyTape's primary colors, with a slight gradient that will make it look like the color is fading in from the end of the strip. First, let's change the speed at which it cycles to make it super fast.

Look for this lines:

	int waiting_time = 40; //time in ms for color scaling

Change the value from `"40"` to say, `"4"` so that your code looks like this:

	int waiting_time = 4; //time in ms for color scaling

Press the Upload button again, like we did in step 6. This will send your new version of the program to the BlinkyTape. When the upload is complete, the BlinkyTape should be flashing at your new preferred speed!

## Ok, Let's Try Some Bigger Changes!
OK, so that was super-easy right? Right. Let's try something a bit more fun.  

Now let's find the lines where we set the color.  There are three lines that look something like this:

	case 0: leds[i] = CRGB(i*3,0,0); break;

This is a line in a loop that increases that `"i"` variable, and `"i"` is going to be the number of the individual LED we're setting. We're giving each LED an RGB value, and we also use that `"i"` variable to help us set the color. This line will make the LEDs a brighter red at one end than the other.

But let's change each of them so they have a color gradient instead of just brightness. To do that, we need to set two colors in each line. Let's make the first one (and first means `"0"` since this is a computer!) go blue to red, the second one red to green, and the third green to blue. We'll use that `"i"` variable that holds the LED number twice now, so instead of just increasing the red one, we're going to use that number to decrease the blue setting at the same time.

For the first one, let's try this:

	case 0: leds[i] = CRGB(i*3,0, 180 - (i*3)); break;

And for the second, let's do:

	case 1: leds[i] = CRGB(180 - (i*3),i*3,0); break;

I think you can figure out what the third one should be. Punch it in, then click that arrow button one more time to put your new, modified program on your Blinkytape, and Wow! That really kicks up the awesome quotient, right? Now, I think you're starting to see the possibilities of this clever little LED strip.

{% include btdocs/arduino-serialloop.md %}

{% include btdocs/arduino-boardstuff.md %}

## Next Steps

* Learn more about how we're controlling the LEDs - check out FastSPI\_LED2 by going to  **File | Examples | FastSPI_LED2 | Fast2Dev**
* For even more information, check out [their documentation](https://code.google.com/p/fastspi/wiki/Documentation), which includes API reference materials like info on the CRGB color class and methods for setting LED color.
* It's a great idea to check out the [Arduino Programming Reference](http://arduino.cc/en/Reference/HomePage) if you're not already familiar.
<!--- when available add a line about this: Check out the BlinkyTape Hardware Schematics --->
* When you have a new firmware, share it with everybody! 

{% include btdocs/arduino-troubleshooting.md %}


