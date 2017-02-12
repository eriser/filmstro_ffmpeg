
filmstro_ffmpeg
===============

by Daniel Walz / Filmstro Ltd.
Published under the BSD License (3 clause)

This is a module to read video files and play/display it using the JUCE 
framework (juce.com). The audio will be available as a juce::AudioSource and 
can be processed through a regular processing chain.

Dependencies
============

The reading is done using ffMpeg (ffmpeg.org). you will have to build ffmpeg
and link your project to it. We use this flags:

OSX:
./configure --cc=CC --arch=x86_64 --disable-static --enable-shared --disable-stripping --disable-debug --install-name-dir='@loader_path'

Windows:
./configure --toolchain=msvc --disable-static --enable-shared --prefix=../build/windows --arch=x86 

make -j10
make install


It also uses a helper class of our module filmstro_audiobasics
(Sorry Jules to borrow the name, it is supposed to sit besides the juce_audiobasics)

Current State
=============

It works for us with mp4 files. However, there are many formats, and many create
problems, mostly to do with the sequence of packets / frames in the stream. Here
any insights and findings are very welcome.

The VideoWriter is leftover from a previous test and will be completely rewritten.

********************************************************************************

We hope it is of any use, let us know of any problems or improvements you may 
come up with...

Brighton, 9th February 2017

********************************************************************************