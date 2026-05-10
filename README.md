# 📺 Interdimensional Cable

A channel-flipping experience pulling free international TV from around the world — wildlife docs, anime, classic comedy, news, science, and more. Each channel loops continuously and drops you in at a random spot, just like real TV.

**[▶ Live Demo →](https://jtrain773.github.io/Interdimensional-Cable/)**

---

## Deploy to GitHub Pages (5 minutes)

### Option A — GitHub website (no terminal needed)

1. Go to [github.com](https://github.com) and sign in (or create a free account)
2. Click **+** → **New repository**
3. Name it `Interdimensional-Cable`, set it to **Public**, click **Create repository**
4. Click **uploading an existing file**, drag in `index.html`, click **Commit changes**
5. Go to **Settings** → **Pages** → under *Branch* select `main` → click **Save**
6. Wait ~60 seconds, then visit `https://YOUR-USERNAME.github.io/Interdimensional-Cable`

### Option B — Terminal (git)

```bash
cd Interdimensional-Cable
git init
git add .
git commit -m "launch"
git branch -M main
git remote add origin https://github.com/jtrain773/Interdimensional-Cable.git
git push -u origin main
```

Then enable Pages in **Settings → Pages → Branch: main → Save**.

---

## Channels (52 total)

| # | Source | Country | Genre |
|---|--------|---------|-------|
| 1–5 | BBC Earth (Attenborough) | 🇬🇧 UK | Wildlife |
| 6–8 | Mr Bean | 🇬🇧 UK | Comedy |
| 9–16 | DW Documentary | 🇩🇪 Germany | Documentary / Travel |
| 17–26 | NHK World | 🇯🇵 Japan | Documentary / Travel / Culture |
| 27–32 | ARTE.tv | 🇫🇷🇩🇪 Europe | History / Society / Science |
| 33–34 | Al Jazeera English | 🇶🇦 Qatar | News / Documentary |
| 35–39 | CGTN Documentary | 🇨🇳 China | Documentary / Culture |
| 40–44 | Kurzgesagt | 🌍 International | Science Animation |
| 45–48 | Dragnet, Robin Hood, Lone Ranger, Peter Gunn | 🇺🇸 USA | Classic TV (Public Domain) |
| 49–52 | Ulysses 31, Astro Boy, Maya the Bee, Speed Racer X | 🇫🇷🇯🇵 | Classic Anime |

## How it works

- **Looping broadcasts** — each channel plays on repeat
- **Random drop-in** — tuning in lands you at a random point in the video, like channel surfing real TV
- **⚡ Flip** — jump to a random channel instantly
- **Filter by region** — narrow the guide to one country or source

## Adding channels

Edit the `channels` array in `index.html`. Each entry needs:

```js
// YouTube video
{ n:53, flag:"🇧🇷", country:"Brazil", name:"My Show", genre:"Drama", type:"yt", id:"YOUTUBE_VIDEO_ID" }

// Direct MP4 (archive.org or any CORS-friendly host)
{ n:54, flag:"🇮🇹", country:"Italy", name:"Old Film", genre:"Comedy", type:"mp4", id:"https://archive.org/download/IDENTIFIER/file.mp4", page:"https://archive.org/details/IDENTIFIER" }
```

## Why it needs a server

YouTube's embed API blocks playback when opened via `file://` (double-clicking the HTML). GitHub Pages serves over HTTPS, which is what YouTube requires.

To test locally without deploying:
```bash
python -m http.server 8080
# then open http://localhost:8080
```

