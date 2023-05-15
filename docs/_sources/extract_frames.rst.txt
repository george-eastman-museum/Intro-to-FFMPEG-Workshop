##################################
Extracting Frames and Streams
##################################

Note about using ``-fps_mode passthrough`` : If using an older version of ffmpeg, you may need to use ``-vsync 0`` instead. This is telling FFmpeg to passthrough the original input framerate. By default this is set to ``auto``, which could result in dropped or skipped frames that would cause inaccurate results when trying to extract specific frames.

**********************************
Extract One Frame
**********************************

.. code-block:: bash

    ffmpeg -i input_file -vf "select=gte(n\,frame_number)" -vframes 1 output_file.png

**********************************
Extract Multiple Frames
**********************************

.. code-block:: bash

    ffmpeg -i input_file -vf "select=eq(n\,frame_number1)+eq(n\,frame_number2)+eq(n\,frame_number3)" -fps_mode passthrough output_file_%03d.png

**********************************
Extract All Keyframes
**********************************

.. code-block:: bash

    ffmpeg -i input_file -vf "select=eq(pict_type\,I)" -fps_mode passthrough output_file-%03d.png

**********************************
Extract a Stream
**********************************

If the video only has a single video and audio track, we can simply exclude the video track.

.. code-block:: bash

   ffmpeg -i input.mkv -vn -c:a copy output.wav

For more complex videos, we can use ``-map`` to identify the exact audio stream that we want to extract. The following example extracts the primary audio track:

.. code-block:: bash

   ffmpeg -i input.mkv -map a:0 -c:a copy output.wav

