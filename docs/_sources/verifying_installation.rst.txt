##########################
5. Verifying Installation
##########################

To verify that FFmpeg is working as expected, we'll run a couple of simple commands to check that we can successfully call the program and look at what those commands tell us.

********************************************
5.1. Checking the Version
********************************************

- Let's start by checking the version of FFmpeg we have installed.

- Try running the following command:

.. code-block:: bash

   ffmpeg -version

- If the command worked, you should see something like this:

.. image:: images/ffmpeg-version_output.png

- Looking at the first line of the output, we can see that I have FFmpeg version 5.1.3 installed.

- The large block of text following this tells us how our particular install of FFmpeg is configured.

- Some functions require that FFmpeg be configured with certain options.

- For example, if we look at the output, we can see that ``--enable-libsoxr`` is listed in my configuration section. This means that FFmpeg can use the SoX Resampler library for audio.

********************************************
5.2. Bringing Up the Help Text
********************************************

- Next let's bring up the help text for FFmpeg:

.. code-block:: bash

   ffmpeg -hide_banner -help

- You should see a list of commands, each with a short description of what it does.

- In addition to the ``-help`` command, we also used the ``-hide_banner`` command here. This is one of several commands that impacts the amount of information that FFmpeg outputs to the command line. In this case, the command simply keeps FFmpeg from printing the version and configuration information at the top of its output.

********************************************
5.3. Reading the Manual (MacOS/Linux ONLY)
********************************************

- Finally, lets bring up the manual for FFmpeg:

.. code-block:: bash

   man ffmpeg

- You can press ``q`` to exit the manual.

- PowerShell and Command Prompt do not have an exact equivalent of the ``man`` command. However, you can still access the `full FFmpeg manual online <https://ffmpeg.org/ffmpeg.html>`_.
