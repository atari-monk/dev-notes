### Continuous webcam recording with FFmpeg

I needed a simple way to continuously record a USB webcam on Ubuntu while saving the recording into manageable 20-second MP4 files.

The setup uses FFmpeg with:

* 1280×720 at 30 FPS using the webcam's MJPEG mode
* JEEMAK USB microphone
* H.264 video with CRF 23 for good quality
* AAC audio at 128 kbps
* `yuv420p` for better mobile compatibility
* A keyframe every 2 seconds for more reliable segment boundaries
* Timestamp-based filenames using `yyyy-mm-dd_hh-mm-ss`

```bash
ffmpeg \
  -f v4l2 -input_format mjpeg -video_size 1280x720 -framerate 30 -i /dev/video2 \
  -f alsa -ac 2 -ar 48000 -i plughw:2,0 \
  -c:v libx264 -preset medium -crf 23 \
  -pix_fmt yuv420p \
  -profile:v high -level 3.1 \
  -force_key_frames "expr:gte(t,n_forced*2)" \
  -c:a aac -b:a 128k \
  -f segment \
  -segment_time 20 \
  -reset_timestamps 1 \
  -strftime 1 \
  "%Y-%m-%d_%H-%M-%S.mp4"
```

The result is a continuous recording producing files such as:

```text
2026-09-08_18-20-00.mp4
2026-09-08_18-20-20.mp4
2026-09-08_18-20-40.mp4
```

Recording continues until `Ctrl+C` is pressed.
