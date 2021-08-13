# FFMPEG Commands

### Crop Video

```
ffmpeg -i input -filter:v "crop=width:height:x:y" output
```

### Replace audio in video

```
ffmpeg -i video -i audio -map 0:v -map 1:a -shortest output
```