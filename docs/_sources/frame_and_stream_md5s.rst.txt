##########################
Frame and Stream MD5s
##########################

FFmpeg has the ability to create MD5s of streams and frames. This can be especially helpful when attempting to determine if a transcode or stream copy is reversible/lossless. It also allows us to examine a stream's integrity at a granular level and better understand how different encodings of the same file may differ.

********************************************
FrameMD5
********************************************

Documentation about framemd5s can be found `HERE <https://trac.ffmpeg.org/wiki/framemd5%20Intro%20and%20HowTo>`_.

.. code-block:: bash

   ffmpeg -i input_file.mov -f framemd5 output_file.framemd5

********************************************
Stream MD5
********************************************

Using the ``-map`` command to select the primary video track:

.. code-block:: bash

   ffmpeg -loglevel quiet -i input.mp4 -map 0:v -f md5 -

Individually excluding other streams:

.. code-block:: bash

   ffmpeg -loglevel quiet -i input.mp4 -an -dn -sn -f md5 -
