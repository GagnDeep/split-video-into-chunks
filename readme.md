# segment video in 2 seconds chunks

```bash
ffmpeg -hide_banner  -err_detect ignore_err -i video.mp4 -r 24 -codec:v libx264  -vsync 1  -codec:a aac  -ac 2  -ar 48k  -f segment   -preset fast  -segment_format mpegts  -segment_time 2 -force_key_frames  "expr: gte(t, n_forced * 0.5)" output/out%d.mp4
```
