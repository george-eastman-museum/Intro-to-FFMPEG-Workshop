##########################
7. Make a Test Video
##########################

FFmpeg can generate many different patterns using its filtergraph functionality. Generating signals and patterns uses the ``lavfi`` command.

******************************************
7.1. Using FFplay to Preview Our Output
******************************************

.. code-block:: bash

   ffplay -f lavfi -i <filter_name>

******************************************
7.2. Generate a Mandelbrot Pattern
******************************************

.. code-block:: bash

   ffmpeg -f lavfi -i mandelbrot=s=1920x1080:r=24 -t 15 -c:v libx264 -crf 26 -preset fast -profile main -pix_fmt yuv420p output_file.mp4

Documentation about adjusting parameters for the Mandelbrot pattern can be found in `section 15.6 of the FFmpeg filters documentation <http://ffmpeg.org/ffmpeg-filters.html#mandelbrot>`_.

``ffmpeg``
=============================================================

- Call FFmpeg

``-f lavfi -i mandelbrot=s=1920x1080:r=24``
=============================================================

- Here we are passing the mandelbrot pattern as our input.

- We are including a few other settings (``s`` and ``r``) to set the size and framerate as well.

``-t 10``
=============================================================

- This sets the time/duration of our video to 10 seconds.

``-c:v libx264``
=============================================================

- This is setting libx264 as the encoder that we'll use.

``-crf 26 -preset fast -profile main``
=============================================================

- This is configuring the compression settings for libx264.

``-pix_fmt yuv420p``
=============================================================

- This sets the pixel format of our output video. This includes things like the chroma subsampling (4:2:0 in this case).

``output_file.mp4``
=============================================================

- This needs to be the full path to the output file that we want to create.

******************************************
7.3. Generate a Test Pattern Video
******************************************

The same command structure can be used and modified to fit your needs.

Here is a short list of some test patterns that FFmpeg can output: ``testsrc``, ``testsrc2``, ``smptebars``, ``smptehdbars``, ``pal75bars``, ``colorspectrum``

Documentation on the available test patterns that FFmpeg can generate can be found in `section 15.10 of the FFmpeg filters documentation <http://ffmpeg.org/ffmpeg-filters.html#allrgb_002c-allyuv_002c-color_002c-colorchart_002c-colorspectrum_002c-haldclutsrc_002c-nullsrc_002c-pal75bars_002c-pal100bars_002c-rgbtestsrc_002c-smptebars_002c-smptehdbars_002c-testsrc_002c-testsrc2_002c-yuvtestsrc>`_.



