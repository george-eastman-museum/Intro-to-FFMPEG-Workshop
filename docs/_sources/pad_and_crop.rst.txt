################################
Pad, Crop, and Scale Videos
################################

********************************
Pad
********************************

.. code-block:: bash

   ffmpeg -i input.mp4 -vf "pad=width=1280:height=720:x=0:y=120:color=black" output.mp4


Will output to 1280x720 with the video 120 pixels from the top

********************************
Crop
********************************

.. code-block:: bash

   ffmpeg -i in.mp4 -vf "crop=in_w:in_h" output.mp4

********************************
Scale
********************************

Documentation about scaling can be found `HERE <https://trac.ffmpeg.org/wiki/Scaling>`_.

Scale to a Specific Size
============================================

.. code-block:: bash

   ffmpeg -i input.mp4 -vf scale=1920:1080 output.mp4

Downscale and Maintain Aspect Ratio
============================================

.. code-block:: bash

   ffmpeg -i input.mp4 -vf scale="trunc(oh*a/2)*2:720" output.mp4

Scale and Pad
============================================

.. code-block:: bash

   ffmpeg -i input.mp4 -vf "scale=iw*min(1280/iw\,720/ih):ih*min(1280/iw\,720/ih),pad=1280:720:(1280-iw)/2:(720-ih)/2" -c:v libx264 output.mp4
