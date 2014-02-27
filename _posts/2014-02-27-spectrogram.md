---
layout: post 
author: Ethan Hartman
category: post
title: New Audio Visualizer -- BlinkySpectrogram!
img: blog/2014-02-27-spectrogram
preview: spectrogram.jpg
---
Hey!

So, yes, as we were saying the blogging and such.  Well, it's been a fairly quiet time at global BlinkinLabs HQ as we cook up some new, amazing junk.  However, we've also been doing just a little in terms of smaller stuff.

[![Typewriter](/images/blog/2014-02-27-spectrogram/spectrograml.jpg)](/post/spectrogram.html)

Like this!  A brandy new audio visualization for your BlinkyTape!

<!--more-->
Still reading...that's awesome!  The new audio visualizer is called [BlinkySpectrogram](https://github.com/Blinkinlabs/BlinkyTape_Processing/tree/master/examples/BlinkySpectrogram) and, as you might have guessed, it's based on the concept of a [spectrogram](http://en.wikipedia.org/wiki/Spectrogram) which is a type of technical visualization of audio.  Basically, it does some clever analysis (called an [FFT](http://en.wikipedia.org/wiki/Fast_Fourier_transform)) that organizes the sound into time-based slices, and looks to see what frequencies are present in each slice.  This visualization is showing pretty much one slice at a time on yout BlinkyTape, and I like it a lot.

The frequencies are organized into bands, which are arranged in octaves...that means doubling instead of linear, which is closer to the way we hear things, [psychoacoustically](http://en.wikipedia.org/wiki/Psychoacoustics).  Bands with more energy are redder, and those with less are darker and bluer.

Cool right?  OH, well, I guess you want to try it first.  So grab [Processing](/blinkytape/docs/processing/) if you haven't already, then the [files](https://github.com/Blinkinlabs/BlinkyTape_Processing/tree/master/examples/BlinkySpectrogram), your favorite virtual audio cable (see the README, but basically you'll want [SoundFlower](https://code.google.com/p/soundflower/) on OS X or [VB-Cable](http://vb-audio.pagesperso-orange.fr/Cable/index.htm) in Win) and then fire up an example.  I suggest LCD Soundsystem's [_Sound of Silver_](http://open.spotify.com/album/1R8kkopLT4IAxzMMkjic6X) which should provide a good demo for you.

And as always, let us know what you think on the [forum](http://forums.blinkinlabs.com/index.php?p=/discussions) and we'd happily accept some improvements to the code if you're savvy!
