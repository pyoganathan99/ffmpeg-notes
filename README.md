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