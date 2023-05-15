###############################################
Stream Mapping and Editing Metadata
###############################################

Streams can be copied when performing actions that do not require re-encoding. This includes things like changing metadata, removing or adding streams, or cutting/combining videos on intra-compressed frames.

Rather than specifying an encoder for the output, we can simply use ``-c:v copy`` to copy a video stream and ``-c:a copy`` to copy an audio stream. ``-map 0 -c copy`` will also copy all streams.

*************************************
Stream Mapping
*************************************

The ``-map`` command is useful for singling out particular streams within complex video files. Documentation about the ``-map`` command can be found `HERE <https://trac.ffmpeg.org/wiki/Map>`_.

``-map 0``

This is used to indicate all streams from the first input.

``-map 0:a:1``

- The first number in the map command indicates the input, with ``0`` corresponding to the first input. If passing multiple inputs to FFmpeg in a single command, the ``-map`` command  can be repeated to map streams from various inputs into the final output.

- The following letter identifies the type of stream (``a`` for audio, ``v`` for video, ``s`` for subtitle, etc.)

- The final number indicates that stream's number for that type of stream within the container, starting from ``0``. For example, ``a:1`` would be the second audio stream in the file.

*************************************
Changing Color Metadata
*************************************

The sample video files created in Section 7 did not include any commands to tag how the color should be decoded in the videos. Adding this information now does not require re-encoding the files.

The following command will update the Color Range, Color Primaries, Transfer Characteristics, and Color Space to be read as limited range Rec. 709 video in addition to re-wrapping the H.264 encoding in an mp4 wrapper.

.. code-block:: bash

   ffmpeg -i input_file.mov -c:v copy -color_range tv -colorspace bt709 -color_trc bt709 -color_primaries bt709 output_file.mp4
