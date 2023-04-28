####################
3. Installing FFmpeg
####################

For the most up-to-date instructions on how to install FFMPEG on your operating system, you should check the `FFmpeg Official Website <https://ffmpeg.org/download.html>`_.

************
3.1. Windows
************

3.1.1. Downloading
=============================
- The current builds for Windows are provided by gyan.dev.

- Follow the link from `FFmpeg's Downloads page <https://ffmpeg.org/download.html#build-windows>`_.

- It is generally recommended to use the latest "git master build" of FFmpeg.

- The "full" build will have more libraries enabled than "essentials", so download the "full" build.

.. image:: images/windows_install0.png

- Once the download is complete, extract the files (you will need to have 7-Zip installed to extract the  .7z files. Alternatively, .zip files are also available `on github <https://github.com/GyanD/codexffmpeg/releases>`_).

- Inside the extracted folder, you will see a folder named "bin" that contains the executables for FFmpeg.

- If you just double click these files, a command prompt window will briefly open, then close.

- For now, if you want to run FFmpeg, you'll either need to drag and drop the "ffmpeg" file in the "bin" folder onto the command line or use the command line to navigate to the "bin" folder and run FFmpeg commands from there.

3.1.2. Adding FFmpeg to Path
=============================

In order for FFmpeg to be easily callable by simply typing ``ffmpeg`` into the command line, we'll need to add it to the "Path" for your username.

- Start by placing the contents of the FFmpeg bin folder in an easy to remember location, such as a dedicated "Applications" folder in your "C" drive.

- Next search for "environment variables" in the search bar and select the option "Edit the system environment variables".

.. image:: images/windows_install1.png

- This will open the System Properties window.

- In this window, click the "Environment Variables" button near the bottom.

.. image:: images/windows_install2.png

- This will open the "Environment Variables" window.

- In the top section of this window, you'll notice an entry in the "Variable" column called "Path".

- Double click the "Path" entry, or select it and then click the "Edit" button below.

.. image:: images/windows_install3.png

- This will open the "Edit environment variable" window.

- In this new window, click the "New" button.

- Now enter the path to the folder that contains your FFmpeg folder (for example, if you put your files in an "Applications" folder in your "C" drive, you would enter "C:\\Applications").

.. image:: images/windows_install4.png

************
3.2. Mac
************
There are several options for installing FFmpeg on Mac computers

3.2.1. Option 1:
================
- For an experience similar to Linux you can use a third party package manager for Macs like `Homebrew <https://brew.sh/>`_ or `MacPorts <https://www.macports.org/>`_.

- Further information on this process can be found `HERE <https://trac.ffmpeg.org/wiki/CompilationGuide/macOS>`_.

3.2.2. Option 2:
=================
- Download the Static Build for Macs from the `FFmpeg website <https://ffmpeg.org/download.html#build-mac>`_.

- Extract the files in the downloaded folder.

- Put the files in an easy to find folder (for example, /Users/test/local).

- Open a Terminal window and add the directory to the PATH variable (REPLACE THE PATH WITH THE FULL PATH TO THE FOLDER YOU PUT FFmpeg IN)

.. code-block:: bash

   $ export PATH=$PATH:/Users/test/local

************
3.3. Linux
************
- FFmpeg can be installed using your operating system's package manager in most cases.

- On some Linux distributions, you may need to enable non-free repositories before you can install FFmpeg.

- For running the most recent or specific versions of FFmpeg, static builds are also an option.

**************
3.4. ChromeOS
**************
- NOTE - NEED TO TEST

- ChromeOS is based on Linux and should, in theory, be able to install FFmpeg using a .deb file

- Static builds for Linux may also work on ChromeOS(?)
