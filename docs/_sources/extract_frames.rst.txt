##################################
11. Extracting Frames and Streams
##################################

extract one frame:
    ffmpeg -i input_file -vf "select=gte(n\,frame_number)" -vframes 1 output_file.png


Extract multiple frames:
    ffmpeg -i input_file -vf "select=eq(n\,frame_number1)+eq(n\,frame_number2)+eq(n\,frame_number3)" -fps_mode passthrough output_file_%03d.png


extract all keyframes:
    ffmpeg -i input_file -vf "select=eq(pict_type\,I)" -fps_mode passthrough output_file-%03d.png

-fps_mode passthrough : If using an older version of ffmpeg, you may need to use -vsync 0 instead. Here we are telling ffmpeg to passthrough the original input framerate. By default this is set to auto, which could result in dropped or skipped frames that would cause inaccurate results when trying to extract specific frames.

Extract exact copy of audio (example uses aac):
ffmpeg -i input.mp4 -vn -c:a copy output.aac
