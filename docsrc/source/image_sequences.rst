########################
12. Image Sequences
########################

Make a video out of 1 frame:
ffmpeg -loop 1 -i image.png -c:v libx264 -t 15 -pix_fmt yuv420p -vf scale=320:240 out.mp4
Set -t to however many seconds you want the clip to be.  Set scale to the dimensions of the video it needs to match.
