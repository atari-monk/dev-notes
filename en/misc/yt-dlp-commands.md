Absolutely — here’s the practical **360p → 1080p + Low/Medium/High audio** cheat sheet:

### 🎬 Video + audio

**📱 Low bandwidth — 360p**

```bash
yt-dlp -f "bv*[height<=360]+ba/b[height<=360]" "URL"
```

**📱 Balanced — 480p**

```bash
yt-dlp -f "bv*[height<=480]+ba/b[height<=480]" "URL"
```

**💻 Desktop — 720p**

```bash
yt-dlp -f "bv*[height<=720]+ba/b[height<=720]" "URL"
```

**🖥️ Full HD — 1080p**

```bash
yt-dlp -f "bv*[height<=1080]+ba/b[height<=1080]" "URL"
```

### 🎵 Audio only

**🔉 Low — up to ~64 kbps**

```bash
yt-dlp -f "ba[abr<=64]/ba" "URL"
```

**🔊 Medium — up to ~128 kbps**

```bash
yt-dlp -f "ba[abr<=128]/ba" "URL"
```

**🎧 High — best available**

```bash
yt-dlp -f "ba" "URL"
```

### 📋 Check formats & sizes first

```bash
yt-dlp -F "URL"
```

**My usual choices:**
`360p` → very limited data • `480p` → mobile • `720p` → desktop • `1080p` → Full HD • **64k** → small audio • **128k** → good balance • **best audio** → maximum quality.
