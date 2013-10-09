## Troubleshooting

If the program fails to compile or upload, or the BlinkyTape is not doing what you expected, there could be a number of things to check.

### Compile Errors
Sometimes, when you try to run your new BlinkyTape program, down at the bottom of the Processing window, you'll see something like this:

![Image of Compiling Failure](/images/blinkytape/big/processing_bork.png)

This means that there's a problem of some sort which won't let your program compile properly. Often, it's just a typo or another simple syntax error, like forgetting a semi-colon at the end of a line or using the wrong kind of parenthesis. If it's a bigger issue, you might need to check out the [Processing language reference](http://processing.org/reference/) or some of the other information available on the 'webs. **Pro tip:** Google searching specific bits of code will often quickly lead to useful forum or [stackoverflow](http://stackoverflow.com/) pages.

### BlinkyTape Not Acting Right

Uh oh. This is where it gets fun. ¯\\(°\_o)/¯

**First off, save your program, close Processing, and disconnect your BlinkyTape for a moment. Then reconnect your tape and try it again.**

This will fix a few common errors with the Java serial library. If that doesn't take care of it, but your program is acting right, take a moment to look through your code, thinking your logic through. If you've borrowed from examples around the web, make sure that you haven't skipped important parts. Go back to the language reference and make sure that your usage is proper. It might take some time to figure out what went wrong, but you'll get to the bottom of things eventually.
