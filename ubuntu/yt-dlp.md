## yt-dlp

[pl](pl/yt-dlp.md)

The easiest way is to use the **yt-dlp** tool (a newer and better version of the old youtube-dl). It works great with long content like audiobooks.

### 1. Installation (Ubuntu)

```bash
sudo apt update
sudo apt install yt-dlp
```

(or the latest version:)

```bash
pip install -U yt-dlp
```

---

### 2. Downloading an audiobook (audio only)

```bash
yt-dlp -x --audio-format mp3 "<URL>"
```

This:

* `-x` → extracts audio only
* `--audio-format mp3` → converts it to MP3

---

### 3. Better quality (if bitrate matters)

```bash
yt-dlp -x --audio-format mp3 --audio-quality 0 "<URL>"
```

---

### 4. If it’s a very long file (e.g. 4h+) and you’re worried about interruptions:

```bash
yt-dlp -x --audio-format mp3 -o "%(title)s.%(ext)s" -N 4 "<URL>"
```

* `-N 4` → parallel downloading (faster and more stable)
* it will automatically resume if interrupted

---

### 5. Bonus: save with thumbnail and metadata

```bash
yt-dlp -x --audio-format mp3 --embed-thumbnail --add-metadata "<URL>"
```
