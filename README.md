# 📺 Interdimensional Cable

A channel-flipping experience pulling free international TV from around the world — documentaries, classic anime, old comedies, news, and more.

**[▶ Live Demo →](https://YOUR-USERNAME.github.io/interdimensional-cable)**

---

## Deploy to GitHub Pages (5 minutes)

### Option A — GitHub website (no terminal needed)

1. Go to [github.com](https://github.com) and sign in (or create a free account)
2. Click **+** → **New repository**
3. Name it `interdimensional-cable`, set it to **Public**, click **Create repository**
4. Click **uploading an existing file**, drag in `index.html`, click **Commit changes**
5. Go to **Settings** → **Pages** → under *Branch* select `main` → click **Save**
6. Wait ~60 seconds, then visit `https://YOUR-USERNAME.github.io/interdimensional-cable`

### Option B — Terminal (git)

```bash
cd interdimensional-cable
git init
git add .
git commit -m "launch"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/interdimensional-cable.git
git push -u origin main
```

Then enable Pages in **Settings → Pages → Branch: main → Save**.

---

## Channels

| # | Show | Country | Source |
|---|------|---------|--------|
| 1–4 | Mr Bean | 🇬🇧 UK | YouTube (official) |
| 5–9 | DW Documentary | 🇩🇪 Germany | YouTube (official) |
| 10–14 | NHK World | 🇯🇵 Japan | YouTube (official) |
| 15–16 | Al Jazeera | 🇶🇦 Qatar | YouTube (official) |
| 17–20 | CGTN Documentary | 🇨🇳 China | YouTube (official) |
| 21–24 | Dragnet, Robin Hood, Lone Ranger, Peter Gunn | 🇺🇸 USA | archive.org (public domain) |
| 25–28 | Ulysses 31, Astro Boy, Maya the Bee, Speed Racer X | 🇫🇷🇯🇵 | archive.org |

## Adding channels

Edit the `channels` array in `index.html`. Each entry needs:

```js
// YouTube video
{ n:29, flag:"🇧🇷", country:"Brazil", name:"My Show", genre:"Drama", type:"yt", id:"YOUTUBE_VIDEO_ID" }

// Direct MP4 (archive.org or any CORS-friendly host)
{ n:30, flag:"🇮🇹", country:"Italy", name:"Old Film", genre:"Comedy", type:"mp4", id:"https://archive.org/download/IDENTIFIER/file.mp4", page:"https://archive.org/details/IDENTIFIER" }
```

## Why it needs a server

YouTube's embed API blocks playback when a page is opened via `file://` (double-clicking the HTML). GitHub Pages serves over HTTPS, which is exactly what YouTube requires.

To test locally without deploying:
```bash
python -m http.server 8080
# then open http://localhost:8080
```
