## Installing FFMPEG

For the most up-to-date instructions on how to install FFMPEG on your operating system, you should check the [FFMPEG Official Website](https://ffmpeg.org/download.html).

### Windows
- Download the Windows 

### Mac
There are several options for installing FFMPEG on Mac computers
#### Option 1:
- Download the Static Build for Macs from the FFMPEG website
- Extract the files in the downloaded folder
- Put the files in an easy to find folder (for example, /Users/test/local)
- Open a terminal window and add the directory to the PATH variable (REPLACE THE PATH WITH THE FULL PATH TO THE FOLDER YOU PUT FFMPEG IN)
```
export PATH=$PATH:/Users/test/local
```
#### Option 2:
- For an experience similar to Linux you can use a third party package manager for Macs like [Homebrew](https://brew.sh/) or [MacPorts](https://www.macports.org/).
    - Further information on this process can be found [HERE](https://trac.ffmpeg.org/wiki/CompilationGuide/macOS)

### Linux
- FFMPEG can be installed using your operating system's package manager in most cases.
- Note on Chromebooks (untested)
    - ChromeOS is based on Linux and should, in theory, be able to install FFMPEG using a .deb file
    - Static builds for Linux may also work on ChromeOS(?)

## Check if FFMPEG is Working
To verify that FFMPEG is working as expected, we'll run a couple of simple commands to check that we can successfully call the program and look at what those commands tell us.

### Checking the Version
- Let's start by checking the version of ffmpeg we have installed
- Try running the following command:
```
ffmpeg -version
```
- If the command worked, you should see something like this:
[IMAGE]
- Looking at the first line of the output, we can see that I have FFMPEG version ____ installed
- The large block of text following this tells us how our particular install of FFMPEG is configured
    - Some functions require that FFMPEG be configured with certain options
    - For example, if we look at my configuration, we can see that `--enable-libsoxr` is listed. This means that FFMPEG can use SoX as my resampler for audio.

### Bringing Up the Help Text
- Next let's bring up the help text for FFMPEG:
```
ffmpeg -hide_banner -help
```
- You should see a list of commands, each with a short description of what it does
- In addition to the `-help` command, we also used the `-hide_banner` command here
    - This is one of several commands that impacts the amount of information that FFMPEG outputs to the command line
    - In this case, the command simply keeps FFMPEG from printing the version and configuration information at the top of its output

### Reading the Manual
- Finally, lets bring up the manual for FFMPEG:
```
man ffmpeg
```
- This provides us with even more detailed information about how FFMPEG works and how to use it
- You can press `q` to exit the manual
