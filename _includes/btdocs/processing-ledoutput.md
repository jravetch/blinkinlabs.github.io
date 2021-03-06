## Using the LedOutput class
So now you've Processing installed, you have some example code, and you're all ready to get going. Fantastic. Let's get you going on a new project that demonstrates a helper class for using BlinkyTape with Processing, called `LedOutput`.

This class takes an area of the screen and renders it to an attached BlinkyTape. It's neat because it lets you use the robust functionality for drawing that's built into Processing.

### Let's get started.
Go ahead and start a new Processing sketch and call it something like 'BlinkyFoo'.

### Grab the LedOutput class and add it to your new sketch
The easiest way to use a class in Processing is to add it in as another tab in your new sketch. Open one of the other examples from BlinkyTape using the **File | Examples** menu -- I'd recommend 'ColorChooser.'

ColorChooser will open in a separate window and you'll see that it has a tab called LedOutput. Click on that tab and copy the entire contents (command-a or control-a is your friend here, so you don't miss anything.)

Go back to the new 'BlinkyFoo' sketch you created, then click on the down arrow near the tab.

![Processing Tab Menu](/images/blinkytape/big/BlinkyFoo.png)

This will give you an option to create a new tab. Make a new one, call it 'LedOutput' and past in the code you copied. This is a common way to add classes in Processing.

### Add this code
Download [this code](/blinkytape/BlinkyFoo.txt) and paste it into your new project. You'll also need to grab [this image](/images/blinkytape/big/bt.jpg) and save it in a folder called 'data' within your Processing sketch save folder.  Again, that will be something like Documents/Processing/BlinkyFoo.

### Let's give it a go!
Plug your Blinkytape in and press the icon that looks like a play button in the upper-right-hand corder of the Processing window. If all goes according to plan, you'll see a new window appear with that image you just downloaded, and a small rectangle in the middle. You can click the rectangle and move it around, and when you do that, you should see the colors changing to match (or at least approximate) what's being displayed in the rectangle on the screen.

### So, what's happening here?
That's a great question. There are a few things that you'll want to pay attention to.

First, we declare an `ArrayList` of `LedOutput` objects:

	ArrayList<LedOutput> leds = new ArrayList<LedOutput>();

Next, in the processing `"setup()"` function:

	// auto connect to all blinkyboards
	  for(String p : Serial.list()) {
	    if(p.startsWith("/dev/cu.usbmodem") || p.startsWith("/dev/ttyUSB") || p.startsWith("COM")) {
	      leds.add(new LedOutput(this, p, numberOfLEDs));
	    }
	  }

Here, we're trying to auto-connect to any serial port as if it's a BlinkyBoard. We're instantiating a new LedOutput with each seemingly-valid serial port we find -- this means it should work with several BlinkyTape strips (they will each show the same thing.) You might run into some trouble with this if you're still on dialup, but hopefully it will work for now.

And here is where we ask the BlinkyTape to update:

	for(int i = 0; i < leds.size(); i++) {
	    leds.get(i).sendUpdate(bx, by, bx + (scaleFactor * numberOfLEDs), by + scaleFactor);
	}

We just iterate through each of our instantiated leds objects, and then we ask each of them to do a `sendUpdate`. The sendUpdate method takes four coordinates, takes a look at what's there in the Processing image window, creates an approximation, and displays it on the BlinkyTape. Pretty cool right?

For some insight on the rest of the program, have a look at [this Processing example](http://processing.org/examples/mousefunctions.html).
