## Install the BlinkyTape Arduino Libraries

Our next step is to download and install a couple of things that we've used to make the Blinkytape firmware better. If you don't know what a *library* is, don't worry -- just think of it as some helper code. We'll download and install these libraries so we can use the example code. Later on, when you're making your own firmware, you'll see how some of these libraries make it easier to program for BlinkyTape.

First install [this](https://code.google.com/p/fastspi/downloads/list) -- it's called 'FastSPI\_LED2' and it's for talking with LED strips like the one in your BlinkyTape. Grab the latest version, 'RC5' as of this writing.
and then [this](https://github.com/Blinkinlabs/BlinkyTape_Arduino)! This one is called 'BlinkyTape\_Arduino' and it's the stuff we wrote.

### Get 'em. 

If you're not a Git expert, the quickest way to get our BlinkyTape\_Arduino package is to use the 'Download Zip' button on the right-hand side of the page. The button should look something like this:

![zip download button](/images/blinkytape/big/git_download_zip.png)

### Install 'em.

The best to install these particular libraries is to unzip them into the your Arduino libraries folder - they way they are named can cause trouble with the [automatic method of installing Arduino libraries.](http://arduino.cc/en/Guide/Libraries) Scroll down on that page for detailed info, but you'll basically take the zipfile and extract it into a folder called Documents/Arduino/libraries (or My Documents\Arduino\libraries on Windows.) 

If you downloaded them as recommended above, **you'll need to snip off the '-master' part of the name from the subfolder.**  In other words, you want it to look like 'Documents/Arduino/libraries/FastSPI\_LED2' not 'Documents/Arduino/libraries/FastSPI\_LED2-master' -- otherwise Arduino won't use them. (It doesn't like special characters in libary names.)

### Restart Arduino if it is running.

You can handle this one on your own!
