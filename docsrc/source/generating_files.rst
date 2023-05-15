##########################
Generating Files
##########################

FFmpeg can generate many different patterns using its filtergraph functionality. Generating signals and patterns uses the ``lavfi`` command.

******************************************
Using FFplay to Preview Outputs
******************************************

FFplay can be a useful tool for checking what the output will look/sound like before writing it to a file.

.. code-block:: bash

   ffplay -f lavfi -i {[filter] [parameters]}

******************************************
Video
******************************************


Mandelbrot Pattern
=============================================================

.. code-block:: bash

   ffmpeg -f lavfi -i mandelbrot=size=1280x720:r=24 -t 60 -c:v libx264 -crf 26 -preset fast -profile:v main -pix_fmt yuv420p output_file.mov

Documentation about adjusting parameters for the Mandelbrot pattern can be found in `section 15.6 of the FFmpeg filters documentation <http://ffmpeg.org/ffmpeg-filters.html#mandelbrot>`_.

``ffmpeg``

- Call FFmpeg

``-f lavfi -i mandelbrot=size=1280x720:r=24``

- Here we are passing the ``mandelbrot`` filter as our input.

- We are including a few other settings (``size`` and ``r``) to set the size and framerate as well.

``-t 60``

- This sets the time/duration of our video in seconds.

``-c:v libx264``

- This is setting libx264 as the encoder that we'll use.

``-crf 26 -preset fast -profile:v main``

- This is configuring the compression settings for libx264.

``-pix_fmt yuv420p``

- This sets the pixel format of our output video. This includes things like the chroma subsampling (4:2:0 in this case).

``output_file.mp4``

- This needs to be the full path to the output file that we want to create.


Test Patterns
=============================================================

The same command structure can be used and modified to fit your needs.

Here is a short list of some test patterns that FFmpeg can output: ``testsrc``, ``testsrc2``, ``smptebars``, ``smptehdbars``, ``pal75bars``, ``colorspectrum``

Documentation on the available test patterns that FFmpeg can generate can be found in `section 15.10 of the FFmpeg filters documentation <http://ffmpeg.org/ffmpeg-filters.html#allrgb_002c-allyuv_002c-color_002c-colorchart_002c-colorspectrum_002c-haldclutsrc_002c-nullsrc_002c-pal75bars_002c-pal100bars_002c-rgbtestsrc_002c-smptebars_002c-smptehdbars_002c-testsrc_002c-testsrc2_002c-yuvtestsrc>`_.

******************************************
Audio
******************************************

Noise Generator
=============================================================

FFmpeg can generate various types of noise using the ``anoisesrc`` filter. Documentation on this filter can be found in `section 9.8 of the FFmpeg filters documentation <https://ffmpeg.org/ffmpeg-filters.html#anoisesrc>`_.

.. code-block:: bash

   ffmpeg -f lavfi -i anoisesrc=color=pink:duration=100:sample_rate=48000 -af volume=-18dB -c:a pcm_s16le output_file.wav

The structure of this command is similar to the previous video examples, but uses some additional audio-specific settings, such as ``sample_rate`` to set the audio sample rate and ``-af`` to set the volume. In this case, we are also outputting to an uncompressed 16-bit PCM WAV file.

Sine Wave Generator
=============================================================

FFmpeg's sine wave generator is another filter that can be used to produce sine wave patterns at different frequencies. Documentation on this filter can be found in `section 9.11 of the FFmpeg filters documentation <https://ffmpeg.org/ffmpeg-filters.html#sine>`_.

.. code-block:: bash

   ffmpeg -f lavfi -i sine=frequency=1000:duration=100:sample_rate=48000 -c:a pcm_s16le output_file.wav
