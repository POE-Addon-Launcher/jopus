JOpus
==

[![Build Status](https://travis-ci.org/Knetic/jopus.svg?branch=master)](https://travis-ci.org/Knetic/jopus)

Provides a Java wrapper for decoding Opus audio. 

What is Opus?
==

[Ogg Opus](http://www.opus-codec.org/) is an audio codec released by Skype and Xiph.org, which combines a variety of codec techniques into one single codec. This codec achieves high throughput, unbelievable compression, and excellent quality. That combination is attractive for practically any application.

I'd like to stress that I have no affiliation with Xiph, Skype, Microsoft, or anyone (that I'm aware of) who created Opus. I created this library without any specific commercial reason, and without compensation.


What do I need to build this?
==

You can try to build it right off the bat by using "build.sh". If your dev environment is set up correctly, it will succeed without error, and produce both "libjopus.so".

You'll need access to 'git', 'gcc', 'java', and 'jar'. This project pulls (and relies upon) "libopus" and "libopusfile" from Xiph's public git repositories, and those tools require 'make', and 'dh-autoreconf' to build. If you're on a debian-based system, this is as easy as 

    apt-get install git gcc openjdk-jre-7-jdk make dh-autoreconf 

I'm not sure the equivalents for brew, yum, or pacman.

If you're on Windows or OSX, I don't yet have a build script for you. I intend to have a cross-compile phase that will build OSX and Windows shared libraries as part of the Linux build process, and I'll just attach those binaries to each release. If you are desperate for compiling this on a non-Linux platform, contact me and we can work together on it.

How do I use this?
==

This library doesn't make any assumptions about how you want to use decoded data, it opens a file and streams decoded PCM data back to you.

A reference test class (that simply opens a file and plays it through your default sound device) can be found in the repository. Sample source is in "OpusTest.java", and can easily be run with "sample.sh" script. But before doing so, remember to use "build.sh" to build libjopus, first.

To include this in your own projects, build the project and copy the *.so and *.jar files to your project. Make sure to include the jar in your java build path, and to have the java.library.path point to the location of the *.so file.

Why doesn't this support feature XYZ?
==

Right now, the library only plays files and arbitrary streams (not yet http urls). These are goals of mine, and their status can be found on this repository's Issues page. Don't worry, I'd like those features too.

Activity
--

If this repository hasn't been updated in a while, it's probably because I don't have any outstanding issues to work on - it's not because I've abandoned the project. If you have questions, issues, or patches; I'm completely open to pull requests, issues opened on github, or emails from out of the blue.


Can I contribute?
==

Absolutely! This project is BSD-licensed. Feel free to contact me if you've got something to add, or if you'd just like to fork it, please do. I'd very much appreciate if any additions or fixes that are within the spirit of the project were fed back to me, so that they can be included in this repository.
