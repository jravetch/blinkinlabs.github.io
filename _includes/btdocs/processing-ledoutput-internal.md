## Inside the LedOutput class
OK, great, so you've seen how to use LedOutput to render a section of your Processing window on your BlinkyTape. Great. Now, what happens if you want to go deeper?

Luckily, we can have a look inside to see how the BlinkyTape protocol works. What we'll find is that we're just sending three bytes to the BlinkyBoard (the BlinkyTape's controller) to set the color for each LED. To actually make the tape display, we send it a single byte with a value of 255. That means each normal RGB value has a maximum value of 254, not 255. 


###So what's in here?
As we saw earlier, the constructor takes the parent object, a string with the name of a serial port, and the number of LEDs in your strip. Right now, that's 60 for all BlinkyTapes, but you never know...

	LedOutput(PApplet parent, String portName, int numberOfLEDs) {

When you instantiate an `LedOutput` object, it creates a new `Serial` object for internal use.

To see what's going on with the `numberofLEDs` variable, let's go check out something in the `sendUpdate` routine we used earlier.
	    
	    // Note: this should be sized appropriately
	    byte[] data = new byte[m_numberOfLEDs*3 + 1];
	    int dataIndex = 0;

So, here the method is creating an array of bytes that's sized to have one red value, one green value, and one blue value for each LED on the strip - and one more byte at the end for that '255' value which will make the strip update. Also check out that integer - we'll use that as the index for this array of Bytes.

### Not so fast...
OK, so now you're thinking, awesome! Let's just load up that array with 180 color values and that last '255', then we just fire it off to the BlinkyBoard and we start blinking away. Well...that's basically true, but with one notable exception: the serial communication for a tiny little Atmel board is not very fast, and if we send too much data at once, we'll crash it. Since that's the case, we need to send the data in smaller chunks.

Here's what it looks like:

	// Don't send data too fast, the arduino can't handle it.
	    int maxChunkSize = 5;
	    for(int currentChunkPos = 0; currentChunkPos < m_numberOfLEDs*3 + 1; currentChunkPos += maxChunkSize) {
	      int currentChunkSize = min(maxChunkSize, m_numberOfLEDs*3 + 1 - currentChunkPos);
	      byte[] test = new byte[currentChunkSize];
	      
	      for(int i = 0; i < currentChunkSize; i++) {
	          test[i] = data[currentChunkPos + i];
	      }
	    
	      m_outPort.write(test);
	    } 

So all we do is iterate through that `data[]` array, sending no more than `maxChunkSize` bytes each time we write to the serial port. This throttles the data flow a bit so the little board doesn't choke and keeps everything blinking happily.
