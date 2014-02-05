## Inside the BlinkyTape class
OK, great, so you've seen how to use BlinkyTape to render a section of your Processing window on your BlinkyTape. Great. Now, what happens if you want to go deeper?

Luckily, we can have a look inside to see how the BlinkyTape protocol works. What we'll find is that we're just sending three bytes to the BlinkyBoard (the BlinkyTape's controller) to set the color for each LED. To actually make the tape display, we send it a single byte with a value of 255. That means each normal RGB value has a maximum value of 254, not 255 (more on this later).


###So what else is in here?
As we saw earlier, the constructor takes the parent object, a string with the name of a serial port, and the number of LEDs in your strip. Right now, that's 60 for all BlinkyTapes, but you never know...

	BlinkyTape(PApplet parent, String portName, int numberOfLEDs) {

When you instantiate an `BlinkyTape` object, it creates a new `Serial` object for internal use.

To see what's going on with the `numberofLEDs` variable, let's go check out something in the `render()` routine we used earlier.
	    
	// Note: this should be sized appropriately
	byte[] data = new byte[m_numberOfLEDs*3 + 1];
	int dataIndex = 0;

So, here the method is creating an array of bytes that's sized to have one red value, one green value, and one blue value for each LED on the strip - and one more byte at the end for that '255' value which will make the strip update. And remember how we can't send any 255 values? Here's how we check when we're assigning the variables:

	data[dataIndex++] = (byte)min(254, r);
	data[dataIndex++] = (byte)min(254, g);
	data[dataIndex++] = (byte)min(254, b);

### Not so fast...
OK, so now you're thinking, awesome! Let's just load up that array with 180 color values and that last '255', then we just fire it off to the BlinkyBoard and we start blinking away. Well...that's basically true, but with one notable exception: the serial communication for a tiny little Atmel-powered board is not very fast, and if we send too much data at once, we'll crash it. Since that's the case, we need to send the data in smaller chunks.

The `BlinkyTape` class has a master `.update()` method which just checks to make sure that the last byte is the right one to tell the tape to update itself, and then calls `.send()`  That's method that starts this process, and then a few other routines that work together to make sure that the little board's USB serial doesn't get all choked with data. Most of the heavy lifting takes place in the `sendNextChunk()` method, so take a look there. The quick version is that it seems like sending chunks of no more than **64** bytes keeps the BlinkyTape happy.
