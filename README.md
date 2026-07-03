# 🎬 Prime Video: The Ayala Show

A parody Prime Video landing page built to roast (lovingly) my sister Ayala on her 22nd birthday.

Features 17 "episodes" — actual family video clips from her childhood — each with a funny title, description, and Prime Video–style presentation. (Episode 11 was lost to time.)

---

## 🚀 How to set it up

### 1. Add the videos

Create a folder called `videos/` in the project root and drop 17 MP4 files inside, named:

```
videos/
├── video1.mp4    Baby Ayala (4 months) — cute sounds
├── video2.mp4    Hula hoop incident (4s)
├── video3.mp4    ABBA Waterloo on Wii Just Dance (15s)
├── video4.mp4    Darbuka + bucket concert with Ofri (12s)
├── video5.mp4    iPad on the couch (34s)
├── video6.mp4    Wii Just Dance with Rotem (26s)
├── video7.mp4    Naked backyard dance (7s)
├── video8.mp4    Umbrella vs. water hose (9s)
├── video9.mp4    Dancing on stage with a performer (7s)
├── video10.mp4   "Chinese/Japanese/Indian face" song (4s)
├── (video11.mp4 skipped — lost)
├── video12.mp4   Grandfather-flower wish for Grandma (13s)
├── video13.mp4   Football: me vs. Ayala + Ofri (35s)
├── video14.mp4   Fake guitar playing (44s)
├── video15.mp4   Luna Park train "driving" (15s)
├── video16.mp4   Dutch dance in Netherlands (10s)
├── video17.mp4   Zipline at the kibbutz (15s)
└── video18.mp4   Baby Ayala lifts her chest / me copying her
```

**Tips**
- Use `.mp4` (H.264) for browser compatibility. Convert `.mov` files with:
  ```bash
  ffmpeg -i input.mov -vcodec h264 -acodec aac -movflags +faststart output.mp4
  ```
- Compress if the total gets big:
  ```bash
  ffmpeg -i input.mp4 -vf "scale=1280:-2" -crf 26 -preset medium -acodec aac output.mp4
  ```

### 2. Add a hero photo

Replace `hero.jpeg` in the root with a nice photo of Ayala. It's used as the big top banner and the WhatsApp preview image.

### 3. (Optional) Add a birthday song

Drop an MP3 in the root called `birthday-song.mp3`. Without it, the "Play Birthday Theme" button just does nothing gracefully.

### 4. Preview locally

```bash
# From the project folder:
python3 -m http.server 8080
```
Then open <http://localhost:8080> in your browser.

> ⚠️ Videos won't load if you open `index.html` directly via `file://` in some browsers. Always serve through a local server.

### 5. Deploy

**GitHub Pages** — commit + push, then repo settings → Pages → deploy from `main`.

**Vercel** — drag-and-drop the folder at vercel.com, or run `vercel` in the terminal.

---

## ✏️ Customizing text

All the funny titles, descriptions, and metadata are inside one JavaScript array called `episodes` near the bottom of `index.html`. Edit any field to change the card + modal content.

Other easy edits in `index.html`:
- **Hero title / subtitle** — inside `<section class="hero">`
- **Ratings strip** — `<section class="ratings-strip">`
- **Coming Soon message** — `<section class="coming-soon">`
- **Splash screen text** — `<div class="splash">`

---

## 📁 Final folder structure

```
prime-video-de-amor/
├── index.html
├── hero.jpeg
├── birthday-song.mp3     (optional)
├── videos/
│   ├── video1.mp4
│   ├── ...
│   └── video18.mp4
└── README.md
```

Happy 22nd, Ayala. 🎂