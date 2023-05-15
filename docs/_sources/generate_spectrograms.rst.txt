##########################
Spectrograms
##########################

********************
Using FFmpeg
********************

Documentation on FFmpeg's spectrogram filter can be found `HERE <https://ffmpeg.org/ffmpeg-filters.html#showspectrum-1>`_.

Using FFplay
=============================

The following command creates a 1920x1080 spectrogram that scrolls as the audio plays.

.. code-block:: bash

   ffplay -f lavfi "amovie='input.wav', asplit [a][out1]; [a] showspectrum=mode=separate:color=rainbow:slide=scroll:scale=lin:size=1920x1080 [out0]"


Outputting to a File
=============================
      
For mono audio:

.. code-block:: bash

   ffmpeg -i input.wav -lavfi [a:0]showspectrumpic output.png


For multi-channel audio:

.. code-block:: bash

   ffmpeg -i input.wav -lavfi [a:0]showspectrumpic=mode=separate output.png

Changing the Orientation:

.. code-block:: bash

   ffmpeg -i input.wav -lavfi showspectrumpic=mode=separate:orientation=1 output.png

********************
Using SoX
********************

If installed, SoX can be used as an alternative to FFmpeg for generating spectrograms.

.. code-block:: bash

   sox input.wav -n spectrogram -o output.png
