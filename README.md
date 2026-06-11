<div align="center">

# Valentine's 3D Memory Gallery 💕

**A tic-tac-toe game that hides two years of love inside it.**

[![Three.js](https://img.shields.io/badge/Three.js-v0.160-black?style=for-the-badge&logo=three.js)](https://threejs.org/)
[![MediaPipe](https://img.shields.io/badge/MediaPipe-v0.10.3-blue?style=for-the-badge)](https://mediapipe.dev/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6%2B-yellow?style=for-the-badge&logo=javascript)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![CSS3](https://img.shields.io/badge/CSS3-glassmorphism-blue?style=for-the-badge&logo=css3)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)](LICENSE)

---

</div>

## The Story

Valentine's Day was coming up. As a man in a relationship, I for sure need to find a special gift for my love one. My girlfriend and I are the kind of couple who play tic-tac-toe on paper napkins at restaurants and argue about who cheated on the last move.

So I went back to an old tic-tac-toe project I had lying around, and thought: *what if winning unlocked something?* What if instead of just winning a game, you unlocked two years of us?

That turned into this — a 3D gallery of our memories, shaped like a heart, floating in space, controlled by hand gestures through the webcam. I learned Three.js for the 3D rendering. I figured out MediaPipe for the hand tracking. I stared at a parametric heart equation at 2am and somehow made it work. A lot of JavaScript happened.

She cried a little. Worth it.

Now I'm putting this out there so you can make one too. Swap the photos, write your own captions, send your person the link. The game is the same. The memories are yours.

---

## What It Does

**First, you have to win.** The gift doesn't just open — you earn it by beating a tic-tac-toe game. (The AI isn't unbeatable. It just has a little pride.)

**Then the heart appears.** Your photos orbit a 3D parametric heart rendered with Three.js — bloom lighting, particle dust, the whole thing. It looks ridiculous in the best way.

**Then you can control it with your hands.** Point your webcam at yourself and:
- **Open your palm** → photos scatter out into space ✨
- **Make a fist** → the heart reassembles 💕
- **Pinch** → zoom into a random memory 🔍
- **Point** → click a specific photo

**Or just use the mouse.** Drag to rotate. Click to focus. Arrow keys in the viewer. Works on mobile too.

Every photo has a title, a date, and a caption. Because details matter.

---

## Tech Stack

No frameworks. No backend. No build step. Just files.

| Layer | What I used |
|-------|-------------|
| 3D rendering | Three.js v0.160 + UnrealBloomPass |
| Hand tracking | MediaPipe Tasks Vision v0.10.3 |
| Logic & UI | Vanilla JS (ES6 modules) |
| Styling | CSS3 — glassmorphism, gradients, keyframe animations |

Everything loads from CDN. You can serve this with one terminal command.

---

## Getting Started

```bash
git clone https://github.com/thanhzkda/Valentine-Demo.git
cd Valentine-Demo

# You need a local server for ES modules + camera permission
npx serve .
# or
python -m http.server 8080
```

Open `http://localhost:3000` (or `8080`). The demo runs with placeholder images from [Picsum Photos](https://picsum.photos) — no setup needed to try it out.

---

## Make It Yours

This is the part that matters. Here's how to swap in your own memories:

**1. Add your photos and videos**

Drop them into `media/photos/` and `media/videos/`. These folders are gitignored so your personal photos stay off GitHub.

**2. Edit `js/media-data.js`**

Each entry is one memory. Update the `src`, `title`, `date`, and `description`:

```js
{
    type: 'image',
    src: 'media/photos/our_first_date.jpg',
    thumbnail: 'media/photos/our_first_date.jpg',
    title: 'Our First Date',
    date: '2024-02-14',
    description: 'The day everything changed.'
}
```

**3. Add music (optional)**

Drop a `music.mp3` in the root folder, then find and uncomment the `<audio>` tag in `index.html`. It plays softly in the background after the game.

---

## Deploy

### Netlify (easiest)
Drag the project folder into [netlify.com/drop](https://app.netlify.com/drop) and you get a live link instantly. Send that link to them.

### GitHub Pages
```bash
gh repo create my-valentine --public --source=. --push
# Then: repo Settings → Pages → Deploy from branch: main
```

### Vercel
```bash
npx vercel --prod
```

> **One thing:** hand gesture control needs HTTPS to access the camera. All three options above give you HTTPS automatically. If you're testing locally, use `npx serve` — it handles this too.

---

## Project Structure

```
├── index.html            # Entry point
├── css/
│   ├── styles.css        # Game, transition, and gallery styles
│   └── heart-scene.css   # 3D heart scene styles
├── js/
│   ├── heart-scene.js    # Three.js scene, gesture handling, media viewer (the big one)
│   ├── media-data.js     # ← Edit this to personalize
│   ├── main.js           # Screen transitions and app controller
│   ├── game.js           # Tic-tac-toe logic
│   ├── gallery.js        # Legacy 2D gallery fallback
│   └── gestures.js       # Legacy gesture handler
└── media/
    ├── photos/           # Your photos go here (gitignored)
    └── videos/           # Your videos go here (gitignored)
```

---

## License

MIT — free to use, fork, and gift to someone you love.

---

<div align="center">

**If this made someone smile, it did its job.**

*Fork it. Fill it with your memories. Send it to your person.*

</div>
