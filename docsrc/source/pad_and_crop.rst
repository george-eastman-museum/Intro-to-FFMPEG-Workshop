################################
10. Pad, Crop, and Scale Videos
################################

********************************
10.1. Pad
********************************

.. code-block:: bash

   ffmpeg -i input.mp4 -vf "pad=width=640:height=480:x=0:y=120:color=black" -acodec copy output.mp4

will output to 640x480 with the video 120 pixels from the top

********************************
10.2. Crop
********************************

.. code-block:: bash

   ffmpeg -i in.mp4 -vf "crop=in_w:in_h" -c:a copy out.mp4

********************************
10.3. Scale
********************************

.. code-block:: bash

   ffmpeg -i input.avi -vf scale=320:240 output.avi

********************************
10.4. Scale and Pad
********************************

.. code-block:: bash

   ffmpeg -i input.mkv -vf "scale=iw*min(1920/iw\,1080/ih):ih*min(1920/iw\,1080/ih),pad=1920:1080:(1920-iw)/2:(1080-ih)/2" output.mov
