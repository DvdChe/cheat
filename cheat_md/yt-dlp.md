# yt-dlp cheat sheet


## Specify video quality
```
-S "height:480" -f "bv*" <URL>
```

# Fast dl :

```
yt-dlp -f "bv*" --downloader aria2c --downloader-args '-c -j 3 -x 3 -s 3 -k 1M' <URL>
```
