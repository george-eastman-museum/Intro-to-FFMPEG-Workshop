###############################
Cutting and Combining Video
###############################

********************************************
Cut Video
********************************************

Cutting video can be done several different ways using FFmpeg. Note that you can only copy video streams if cutting on intra-compressed frames.

Define a Duration
=============================================

You can define a start point for the video and then a duration for how long the video should run using the following command.

.. code-block:: bash

   ffmpeg -i input.mkv -ss 00:01:00 -t 00:00:05 -c copy output.mp4


Define a Timecode Range
=============================================

You can define a range of timecodes using the following command.

.. code-block:: bash

   ffmpeg -i input.mkv -ss 00:01:00 -to 00:01:05 -c copy output.mp4

Cutting from the End of the File
=============================================

You can use the following command to seek backwards from the end of the file to the point that you want to cut as well. Note that this takes a negative time value.

.. code-block:: bash

   ffmpeg -i input.mkv -sseof -00:01:00 -c copy output.mp4


********************************************
Combine Videos
********************************************

See `documentation <https://trac.ffmpeg.org/wiki/Concatenate>`_.

There are several ways to combine videos with FFmpeg depending on your inputs: 

- concat demuxer: Used to losslessly combine codecs such as H.264. Files should have the same aspect ratio.

- concat protocol: Formats such as DV, MPEG-1, and MPEG-2 can be combined with the concat protocol.

- concat video filter: Used when combining different codecs.

Using the Concat Demuxer
============================================

The concat demuxer takes a list of files as an input and combines them to create the output. The text list uses the following structre:

.. code-block:: bash

   file 'file1.mp4'
   file 'file2.mp4'

The file list can be manually created, or automatically created using a command similar to this:

.. tabs::
   .. group-tab:: MacOS
      .. code-block:: bash
      
         for f in *.mp4 ; do echo "file '$f'" >> mylist.txt ; done
         
   .. group-tab:: Linux
      .. code-block:: bash
      
         for f in *.mp4 ; do echo "file '$f'" >> mylist.txt ; done
         
   .. group-tab:: Windows
      
      If using CMD:

      .. code-block:: bash
      
         (for %i in (*.mp4) do @echo file '%i') > mylist.txt

      If using Powershell:

      .. code-block:: bash

         foreach ($i in Get-ChildItem .\*.mp4) {echo "file '$i'" >> mylist.txt}

Once the text list is created, the files can be combined with the folowing FFmpeg command:

.. code-block:: bash

   ffmpeg -f concat -safe 0 -i mylist.txt -c copy output.mp4

********************************************
Combine Separate Audio and Video Files
********************************************

``-map`` can be used to combine streams from different sources into a single output file.

.. code-block:: bash

   ffmpeg -i input_0.mp4 -i input_1.mp4 -c copy -map 0:v:0 -map 1:a:0 out.mp4

If the two files have different durations, the ``-shortest`` command can be used to tell FFmpeg to stop when the shorter of the two streams ends.

.. code-block:: bash

   ffmpeg -i input_0.mp4 -i input_1.mp4 -c copy -map 0:v:0 -map 1:a:0 -shortest out.mp4

Note that the output container must be compatible with all of the streams for this to work.
