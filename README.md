# ffmpeg-code-summary-table


## **Audio Extraction from Video**
```
ffmpeg -i "download.mp4" -vn -acodec copy "audio.mp4"
```

## **Overwrites the specified audio to the audio of the video.**
```
ffmpeg -i "out.mp4" -i "audio.mp4" -c:v copy -c:a aac -map 0:v:0 -map 1:a:0 "videooo.mp4"
```

## **Convert many still images with sequential name numbers to Xfps video**
```
ffmpeg -framerate X -i %15d.png -vcodec libx264 -pix_fmt yuv420p oust.mp4
```
## **If you want to convert to 30 fps video**
```
ffmpeg -framerate 30 -i %15d.png -vcodec libx264 -pix_fmt yuv420p out.mp4
```
```
ffmpeg -r 30 -i %15d.png -vcodec libx264 -pix_fmt yuv420p out.mp4
```
-r and -framerate play the same role.

The %15d.png indicates that the file name of the still image has 15 numbers, such as 000000000000001.png.
If the image was sequentially numbered starting with 00001.png, it should be %5d.png

## **Convert all frames of download.mp4 to a still image in png format with file name starting with image_0001.png**
```
ffmpeg -i download.mp4 -vcodec png image_%04d.png
```

## **Convert aaa.ts video to aaa.mp4**
```
ffmpeg -i "aaa.ts" -vcodec copy -acodec copy "aaa.mp4"
```

## **Combine the two files. Specifically, copy the audio in aaa.mp4, encode the audio stream in out.mp4 with the AAC codec, and output a video file named output.mp4**
```
ffmpeg -i "aaa.mp4" -i ""out.mp4" -c:v copy -c:a aac output.mp4
```

## **Convert aaa.mov to as.mp4 without changing the encoding of the video and audio streams**
```
ffmpeg -i "aaa.mov" -vcodec copy -acodec copy "as.mp4"
```
