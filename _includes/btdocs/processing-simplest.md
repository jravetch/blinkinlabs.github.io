## The Simplest BlinkyTape Program
Here's a Processing sketch that talks to your BlinkyTape in just about the simplest way possible. Just paste this in to a new Processing window, plug in your BlinkyTape, and press the 'play' button in the upper right. In a few moments, you should see a slowly-changing rainbow.

Here's the code:

	// The simplest possible way to talk to a BlinkyTape
	import processing.serial.*;
	
	Serial s;
	
	void setup() {
  	// Connect to the first serial port we can find
  	// We assume there is a BlinkyTape there
  	  for(String p : Serial.list()) {
            // NOTE: you'll need to change the next line to match the serial port system, i.e. COMx on Windows
    	    if (p.startsWith("/dev/tty.usbmodem")) { 
      	    s = new Serial(this, p, 115200);
    	    }
  	  }
	}
	
	float phase = 0;
	
	void draw() {
  	for(int i = 0; i < 60; i++) {
    	// Make up a pretty color based on the current phase      
    	color c = color((sin(phase*.9         +i*.2)+1)*128,
                    	(sin(phase     + PI/2 +i*.2)+1)*128,
                    	(sin(phase*1.1 + PI   +i*.2)+1)*128);
                    	
    	// Send the color for the current LED to the strip,
    	// being careful not to send 255 (because that would
    	// cause the strip to display the pixels
    	s.write((byte)min(254, red(c)));
    	s.write((byte)min(254, green(c)));
    	s.write((byte)min(254, blue(c)));
  	}
  	
  	// Send a 0xFF byte to the strip, to tell it to display the pixels
  	s.write((byte)255);
  	
  	phase += .1;
	}

Most everything here is in the single `for` loop within the `draw()` routine. It goes through 60 times (once for each LED on the BlinkyTape) and calculates a color value; it then sends each one over as an individual byte. Each LED on the strip gets three bytes, one each for red, green, and blue. Then, after the `for` loop ends, we send a byte with the value 255 (aka 0xFF) to tell the BlinkyTape to display the colors it just received.

Sending 3 x 60 bytes for color followed by a single 255 is about all it takes to talk to your BlinkyTape. This will always work, as long as you have a standard firmware on your Blinkytape.  However, if you're programming in Processing, you're probably not going to want to use your BlinkyTape like this.
