# FFMPEG Commands

### Crop Video

```
ffmpeg -i input -filter:v "crop=width:height:x:y" output
```

### Replace audio in video

```
ffmpeg -i video -i audio -map 0:v -map 1:a -shortest output
```

### Change speed of video

```
ffmpeg -i video -filter:v "setpts=PTS/2" output
```
Will 2x the video. Change '2' as required.

> ⚠️ Will not affect the audio. Use -an flag to remove audio

```
ffmpeg -i video -filter:v "setpts=PTS/2" -an output
```

### Add padding to a video (eg: black bars)

```
ffmpeg -i video -filter:v "pad=w:h:x:y" output
```

Where
- w, h are dimensions of the output video
- x, y coordinates of the original video

### Overlay video over image

```
ffmpeg \
    -i video \
    -loop 1 -i image \
    -filter_complex "[0][1]overlay=x:y:shortest=1" \
    output
```

**Note:**
- `[0]` and `[1]` are the inputs to the overlay filter, which correspond to first two inputs 