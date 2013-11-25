## Using the BlinkyTape class
So now you've Processing installed, you have some example code, and you're all ready to get going. Fantastic. Let's get you going on a new project that demonstrates a helper class for using BlinkyTape with Processing, called (creatively) `BlinkyTape`.  You'll find it as a file called BlinkyTape.pde in several of the included examples, including the BlinkyTapeDirect.  When you open that project, you can find this file already open in a tab -- just copy & paste the contents of that tab into your Processing projects.

This class can be used in a couple of ways.  You can use it to set pixels individually with a `.pushPixel()` method, and then call `.update()` when you're done.  There are also `.getIndex()` and `.setIndex()` methods so you can go right to setting the LED you want.
There's another very clever way to use this class, however, which is the `.render()` method.  This takes an area of the screen and renders an approximation of it to an attached BlinkyTape. It's neat because it lets you use the robust functionality for drawing that's built into Processing and translate that into blinking LEDs!

If that sounds complicated, don't worry -- we'll got through this in greater detail in these examples.

### Let's get started.
Go ahead and start a new Processing sketch and call it something like 'BlinkyFoo'.

### Grab the BlinkyTape class and add it to your new sketch
The easiest way to use a class in Processing is to add it in as another tab in your new sketch. Open one of the other examples from BlinkyTape using the **File | Examples** menu -- I'd recommend 'BlinkyDirect.'

<!-- **Sorry this example & the accompanying class may not be packaged up correctly at this point (mid-September 2013)  [here's a link to the sketch](/blinkytape/BlinkyTapeDirect.zip) if not.** -->

This new sketch will open in a separate window and you'll see that it has a tab called BlinkyTape. Click on that tab and copy the entire contents (command-a or control-a is your friend here, so you don't miss anything.)

Go back to the new 'BlinkyFoo' sketch you created, then click on the down arrow near the tab.

![Processing Tab Menu](/images/blinkytape/big/BlinkyFoo.png)

This will give you an option to create a new tab. Make a new one, call it 'BlinkyTape' and past in the code you copied. This is a common way to add classes in Processing.

### Add this code
Download [this code](/blinkytape/BlinkyFoo.txt) and paste it into your new project. You'll also need to grab [this image](/images/blinkytape/big/bt.jpg) and save it in a folder called 'data' within your Processing sketch save folder.  Again, that will be something like Documents/Processing/BlinkyFoo.

### Let's give it a go!
Plug your Blinkytape in and press the icon that looks like a play button in the upper-right-hand corner of the Processing window. If all goes according to plan, you'll see a new window appear with that image you just downloaded, and a small rectangle in the middle. You can click the rectangle and move it around, and when you do that, you should see the colors changing to match (or at least approximate) what's being displayed in the rectangle on the screen.

### So, what's happening here?
That's a great question. There are a few things that you'll want to pay attention to.

First, we declare an `ArrayList` of `BlinkyTape` objects and call it `bt`:

	ArrayList<BlinkyTape> bt = new ArrayList<BlinkyTape>();

Next, in the processing `"setup()"` function:

	// auto connect to all blinkyboards
	  for(String p : Serial.list()) {
	    if(p.startsWith("/dev/cu.usbmodem") || p.startsWith("/dev/ttyUSB") || p.startsWith("COM")) {
	      bt.add(new BlinkyTape(this, p, numberOfLEDs));
	    }
	  }

Here, we're trying to auto-connect to any serial port as if it's a BlinkyBoard. We're instantiating a new `BlinkyTape` object with each seemingly-valid serial port we find -- this means it should work with several BlinkyTape strips (they will each show the same thing.) You might run into some trouble with this if you're still on dialup, but hopefully it will work for now.

And here is where we ask the BlinkyTape to update:

	for(int i = 0; i < bt.size(); i++) {
	    bt.get(i).render(bx, by, bx + (scaleFactor * numberOfLEDs), by + scaleFactor);
	    bt.get(i).send();
	  }

We just iterate through each of our instantiated leds objects, and then we ask each of them to do a `sendUpdate`. The sendUpdate method takes four coordinates, takes a look at what's there in the Processing image window, creates an approximation, and displays it on the BlinkyTape. Pretty cool right?

For some insight on the rest of the program, have a look at [this Processing example](http://processing.org/examples/mousefunctions.html).
