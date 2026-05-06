## yt-dlp

[en](../yt-dlp.md)

Najprościej użyć narzędzia yt-dlp (to nowsza i lepsza wersja starego youtube-dl). Działa świetnie z długimi materiałami typu audiobooki.

### 1. Instalacja (Ubuntu)

```bash
sudo apt update
sudo apt install yt-dlp
```

(albo najnowsza wersja:)

```bash
pip install -U yt-dlp
```

---

### 2. Pobranie audiobooka (audio only)

```bash
yt-dlp -x --audio-format mp3 "<URL>"
```

To:

* `-x` → wyciąga tylko audio
* `--audio-format mp3` → konwertuje do MP3

---

### 3. Lepsza jakość (jeśli zależy Ci na bitrate)

```bash
yt-dlp -x --audio-format mp3 --audio-quality 0 "<URL>"
```

---

### 4. Jeśli to bardzo długi plik (np. 4h+) i boisz się przerwania:

```bash
yt-dlp -x --audio-format mp3 -o "%(title)s.%(ext)s" -N 4 "<URL>"
```

* `-N 4` → równoległe pobieranie (szybciej i stabilniej)
* automatycznie wznowi pobieranie jeśli przerwiesz

---

### 5. Bonus: zapis z miniaturką i metadanymi

```bash
yt-dlp -x --audio-format mp3 --embed-thumbnail --add-metadata "<URL>"
```

---
