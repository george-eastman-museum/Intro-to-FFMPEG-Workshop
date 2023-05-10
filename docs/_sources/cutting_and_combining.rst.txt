###############################
9. Cutting and Combining Video
###############################

********************************************
9.1. Cut Video
********************************************

********************************************
9.2. Combine Videos
********************************************

See `documentation <https://trac.ffmpeg.org/wiki/Concatenate>`_.

Approach depends on input: concat protocol, concat demuxer, concat video filter 

============================================
9.2.1. Concat Protocol
============================================

Formats such as DV, MPEG-1, and MPEG-2 can be combined with the concat protocol.

============================================
9.2.2. Concat Demuxer
============================================

Used to losslessly combine codecs such as h.264.

Files should have the same aspect ratio.

============================================
9.2.3. Concat Video Filter
============================================

Used when combining different codecs.

********************************************
9.3. Combine Separate Audio and Video Files
********************************************

.. code-block:: bash

   ffmpeg -i input_0.mp4 -i input_1.mp4 -c copy -map 0:v:0 -map 1:a:0 out.mp4

Include ``-shortest`` to tell FFmpeg to stop when the shorter of the two streams ends.
