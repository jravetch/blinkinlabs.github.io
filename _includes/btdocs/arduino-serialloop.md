## Compatibility! Or: you might want to keep serialLoop()
One important note: the above example won't work with other BlinkyTape software like PatternPaint. However, it's very easy to make your custom BlinkyTape firmware compatible with other BlinkyStuff!  All you have to do is to include the function called `serialLoop()`.

Look for a function that starts with this line:

	void serialLoop() {

Copy the whole function into your custom Arduino Sketch, and then include these lines in your main loop:

	if(Serial.available() > 0) {
	  serialLoop();
	}

That should do it! Now you can use your own custom firmware with PatternPaint and other BlinkyTape software.
