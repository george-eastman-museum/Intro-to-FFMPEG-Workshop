=================
Installing FFmpeg
=================

For the most up-to-date instructions on how to install FFMPEG on your operating system, you should check the `FFmpeg Official Website <https://ffmpeg.org/download.html>`_.

Windows
--------


Mac
--------
There are several options for installing FFmpeg on Mac computers

Option 1:
**********
- Download the Static Build for Macs from the FFmpeg website
- Extract the files in the downloaded folder
- Put the files in an easy to find folder (for example, /Users/test/local)
- Open a terminal window and add the directory to the PATH variable (REPLACE THE PATH WITH THE FULL PATH TO THE FOLDER YOU PUT FFmpeg IN)
``export PATH=$PATH:/Users/test/local``

Option 2:
***********
- For an experience similar to Linux you can use a third party package manager for Macs like `Homebrew <https://brew.sh/>`_ or `MacPorts <https://www.macports.org/>`_.
- Further information on this process can be found `HERE <https://trac.ffmpeg.org/wiki/CompilationGuide/macOS>`_.

Linux
--------
- FFmpeg can be installed using your operating system's package manager in most cases.
- Note on Chromebooks (untested)
- ChromeOS is based on Linux and should, in theory, be able to install FFmpeg using a .deb file
- Static builds for Linux may also work on ChromeOS(?)
