## Troubleshooting

If the program fails to compile or upload, or the BlinkyTape is not doing what you expected, there could be a number of things to check.

### Compile Errors
Sometimes, when you try to put your new firmware on your Blinkytape, you'll see something like this:

![Image of Compiling Failure](/images/blinkytape/big/Arduino_compile_fail.png)

This means that there's an issue with compiling your few program. You'll need to fix that before you can put the new firmware on your BlinkyTape. See if you can fix the compile errors -- the Arduino editor will give you some clues, including the line number where it ran into the problem. You'll find that these issues are often very simple, like a missing semicolon at the end of a line, or mismatched brackets. Check the
[Arduino programming reference](http://arduino.cc/en/Reference/HomePage)
if you get stuck.

### Upload Errors

* Check to make sure that your BlinkyTape is connected to your computer via a micro-USB cable.
* Check to make sure that your **Tools | Board** setting is set to **Arduino Leonardo**.
* Check to make sure that your **Tools | Serial Port** setting is set to the right thing.

### BlinkyTape Not Acting Right

¯\\(°\_o)/¯

Uh oh. This is where it gets fun. If your new program compiles, and you can flash it to your BlinkyTape, but isn't having the desired effect, it's time to rethink your approach. Read through your program again and think out each step. You'll often be able to use logic to figure out what's gone wrong. If all else fails, you can always go back to the original firmware, found at **File | Examples | BlinkyTape_Arduino | ColorSwirl** -- but make sure to save your custom program for later!
