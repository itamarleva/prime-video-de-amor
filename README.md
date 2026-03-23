# 🎬 Prime Video de Amor — For Mariling ❤️

A romantic, funny personal "Prime Video" web page built with love.

---

## 🚀 COMPLETE HOSTING GUIDE

### Step 1: Host Your Hero Photo (Free with ImgBB)

1. Go to **[https://imgbb.com](https://imgbb.com)**
2. Upload your hero photo (the big banner photo of you two)
3. After upload, **right-click the image** → **"Copy Image Address"**
4. You need the URL that starts with `https://i.ibb.co/` and ends in `.jpg`
5. Paste it into `index.html` (see Step 5 below)

---

### Step 2: Host Your Videos (Free — Pick One Option)

You have several free options for hosting your short videos:

#### Option A: Streamable.com ⭐ (Easiest for short videos)
1. Go to **[https://streamable.com](https://streamable.com)**
2. Upload your video (up to 250MB, no account needed for basic)
3. After upload, **right-click the video** → **"Copy video address"**
4. You need a direct URL ending in `.mp4`
5. If you can only get a page URL like `streamable.com/abc123`, try: `https://cdn-cf-east.streamable.com/video/mp4/abc123.mp4`

#### Option B: Cloudinary.com (Best all-in-one for photos + videos)
1. Create a free account at **[https://cloudinary.com](https://cloudinary.com)**
2. Go to **Media Library** → Upload your videos AND photos
3. Click each file → Copy the URL
4. Works great for both images and videos!

#### Option C: Catbox.moe (No account, up to 200MB per file)
1. Go to **[https://catbox.moe](https://catbox.moe)**
2. Upload your video
3. Copy the direct link (e.g., `https://files.catbox.moe/abc123.mp4`)

#### Option D: Put videos in your GitHub repo
1. Add your `.mp4` files to the same folder as `index.html`
2. Use just the filename: `"video1.mp4"`
3. ⚠️ GitHub has a **100MB file size limit** per file — keep videos short!
4. Push everything together with `git push`

#### What videos do you need?
| Placeholder in code | What to upload | Recommended |
|---|---|---|
| `video1.mp4` | Your 1st funny moment video | Keep under 30 sec, <50MB |
| `video2.mp4` | Your 2nd funny moment video | Keep under 30 sec, <50MB |
| `video3.mp4` | Your 3rd funny moment video | Keep under 30 sec, <50MB |
| `video4.mp4` | Your 4th funny moment video | Keep under 30 sec, <50MB |

💡 **Tip:** Shorter videos (10-30 seconds) load faster on mobile!

---

### Step 3: Set Up Your Song (Free)

**Option A — Spotify Embed (Recommended):**
1. Find your song on Spotify
2. Copy the **track ID** from the URL (the part after `/track/`)
3. In `index.html`, uncomment the Spotify iframe and paste your track ID
4. Comment out the `<audio>` tag

**Option B — Host your own MP3:**
1. Upload MP3 to **[https://catbox.moe](https://catbox.moe)**
2. Copy the direct link
3. Replace `our-song.mp3` in the audio tag

---

### Step 4: Deploy Your Website (Free with GitHub Pages)

#### 4a. Create a GitHub Repository
1. Go to **[https://github.com/new](https://github.com/new)**
2. Repository name: `prime-video-de-amor`
3. Make it **Public** (required for free GitHub Pages)
4. Click **"Create repository"**

#### 4b. Push Your Code
```bash
cd ~/Desktop/prime-video-de-amor

git add .
git commit -m "🎬 Prime Video de Amor"

# Replace YOUR_USERNAME with your GitHub username:
git remote add origin https://github.com/YOUR_USERNAME/prime-video-de-amor.git
git branch -M main
git push -u origin main
```

#### 4c. Enable GitHub Pages
1. Go to your repo on GitHub
2. **Settings** → **Pages** (left sidebar)
3. Source: **Deploy from a branch**
4. Branch: **main** / Folder: **/ (root)**
5. Click **Save**
6. Wait 1-2 minutes ⏳
7. Your site is live at: **`https://YOUR_USERNAME.github.io/prime-video-de-amor/`**

#### 4d. Send to Mariling! 🎉
Copy that URL and send it on WhatsApp! 💕

---

### Step 5: How to Put Your URLs in the Code

#### Hero Photo:
Find this line in the CSS (search for `hero-photo.jpg`):
```css
background: url('hero-photo.jpg') center center / cover no-repeat;
```
Replace with your ImgBB URL:
```css
background: url('https://i.ibb.co/YOUR_ID/hero.jpg') center center / cover no-repeat;
```

#### Videos:
Find the `moments` array in the JavaScript section. For each moment, replace the `src`:
```javascript
{
    ep: 'Episode 1',
    title: 'The First Video Call Disaster 📹',
    type: 'video',
    src: 'https://files.catbox.moe/YOUR_VIDEO.mp4',  // ← Your video URL here
    poster: 'https://i.ibb.co/YOUR_ID/thumb.jpg',    // ← Optional thumbnail
    // ... rest of the fields
}
```

#### Song:
Find the audio tag and replace:
```html
<source src="https://files.catbox.moe/YOUR_SONG.mp3" type="audio/mpeg">
```

---

### Step 6: Mix Videos AND Photos!

You can mix videos and photos in the moments row! Just set the `type` field:
```javascript
// For a video moment:
{ type: 'video', src: 'https://your-video-url.mp4', ... }

// For a photo moment (shows image + message):
{ type: 'image', src: 'https://i.ibb.co/your-photo.jpg', ... }
```

---

## 🔄 Quick Update Workflow

After making changes:
```bash
cd ~/Desktop/prime-video-de-amor
git add .
git commit -m "Updated videos"
git push
```
Site updates in ~1 minute!

---

## ❓ Troubleshooting

| Problem | Solution |
|---|---|
| Video not playing | Make sure the URL is a **direct link** to the .mp4 file |
| Video loads slow | Compress videos first (use HandBrake app or ezgif.com/video-to-mp4) |
| Photos not showing | Use the **direct image URL** (starts with `i.ibb.co`, ends in `.jpg`) |
| Song won't play | Mobile browsers require a tap — she needs to press Play |
| Files too large for GitHub | Use external hosting (Streamable/Catbox) for large videos |

---

Made with ❤️ for Mariling