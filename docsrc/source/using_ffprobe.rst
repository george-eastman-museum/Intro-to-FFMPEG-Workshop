########################
Using FFprobe
########################

************************
General Syntax
************************

.. code-block:: bash

   ffprobe -show_streams -show_format input_file

************************
Specifying Fields
************************

The following example uses the ``-show_entries`` command to specify a subset of stream fields that we want to look at. Note that ``-loglevel error`` is used to reduce the verbosity of FFprobe's output so it is easier to read. ``-of default=noprint_wrappers=1`` is also used to remove some of the formatting from the output and make it easier to read.

.. code-block:: bash

   ffprobe -loglevel error -show_entries stream=color_range,color_space,color_transfer,color_primaries -of default=noprint_wrappers=1 input_file
