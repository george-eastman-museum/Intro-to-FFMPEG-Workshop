##########################
14. Frame and Stream MD5s
##########################

********************************************
14.1. FrameMD5
********************************************

.. code-block:: bash

   ffmpeg -i input_file.mov -f framemd5 output_file.framemd5

********************************************
14.2. Stream MD5
********************************************

.. code-block:: bash

   ffmpeg -loglevel quiet -i input.mp4 -map 0:v -f md5 -

.. code-block:: bash

   ffmpeg -loglevel quiet -pattern_type glob -i output_file-*.png -map 0:v -f md5 -
