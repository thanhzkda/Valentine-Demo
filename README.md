# Valentine's 3D Memory Gallery 💕

An interactive, immersive Valentine's gift built with vanilla JavaScript — no frameworks, no backend. Win a tic-tac-toe game to unlock a 3D heart scene where memories orbit in space, controlled by your hands.

---

## Features

- **Tic-tac-toe unlock** — the gift only opens when you win
- **3D heart formation** — photos orbit a parametric 3D heart rendered with Three.js
- **Hand gesture controls** — use your webcam to control the scene with your hands (MediaPipe)
  - Open palm → scatter photos into space
  - Fist → reassemble the heart
  - Pinch → zoom focus on a random photo
  - Point → click on a photo
- **Three view modes** — Heart 💕 · Scatter ✨ · Focus 🔍
- **Fullscreen media viewer** — click any photo for a fullscreen view with caption
- **5000+ particle effects** — bloom post-processing, sparkles, dust, and dynamic lighting
- **Touch & keyboard support** — drag to rotate, arrow keys in viewer, swipe on mobile

## Tech Stack

![Three.js](https://img.shields.io/badge/Three.js-0.160-black?logo=three.js)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0.10.3-blue)
![Vanilla JS](https://img.shields.io/badge/JavaScript-ES6%2B-yellow?logo=javascript)
![CSS3](https://img.shields.io/badge/CSS3-animations-blue?logo=css3)

| Layer | Tech |
|-------|------|
| 3D rendering | Three.js v0.160 + post-processing bloom |
| Hand tracking | MediaPipe Tasks Vision v0.10.3 |
| Logic & UI | Vanilla JS (ES6 modules) |
| Styling | CSS3 — glassmorphism, gradients, keyframe animations |

## Live Demo

> Deploy to GitHub Pages or Netlify — see [Deploy](#deploy) below.

## Getting Started

```bash
# Clone the repo
git clone https://github.com/thanhzkda/Valentine-Demo.git
cd Valentine-Demo

# Serve locally (required for ES modules + camera access)
npx serve .
# or
python -m http.server 8080
```

Open `http://localhost:3000` (or `8080`) in your browser. The demo uses placeholder images from [Picsum Photos](https://picsum.photos) — no setup needed.

## Personalize It

Replace the demo content with your own memories:

1. Drop your photos into `media/photos/` and videos into `media/videos/`
2. Edit `js/media-data.js` — update each entry's `src`, `title`, `date`, and `description`
3. Add a `music.mp3` to the root folder and uncomment the `<audio>` tag in `index.html`

```js
// Example entry in js/media-data.js
{
    type: 'image',
    src: 'media/photos/our_first_date.jpg',
    thumbnail: 'media/photos/our_first_date.jpg',
    title: 'Our First Date',
    date: '2024-02-14',
    description: 'The day everything changed.'
}
```

## Deploy

### GitHub Pages
```bash
gh repo create my-valentine --public --source=. --push
# Then enable Pages in repo Settings → Pages → Deploy from branch: main
```

### Netlify
Drag the project folder into [netlify.com/drop](https://app.netlify.com/drop) — instant live URL.

### Vercel
```bash
npx vercel --prod
```

> **Note:** Hand gesture control requires HTTPS (camera permission). All hosting options above provide HTTPS automatically.

## Project Structure

```
├── index.html          # Entry point
├── css/
│   ├── styles.css      # Game + transition + gallery styles
│   └── heart-scene.css # 3D heart scene styles
├── js/
│   ├── heart-scene.js  # Three.js 3D scene, gestures, media viewer (main)
│   ├── media-data.js   # Your media entries — edit this to personalize
│   ├── main.js         # Screen transitions & app controller
│   ├── game.js         # Tic-tac-toe game logic
│   ├── gallery.js      # Legacy 2D gallery fallback
│   └── gestures.js     # Legacy gesture handler
└── media/
    ├── photos/         # Your photos go here (gitignored)
    └── videos/         # Your videos go here (gitignored)
```

## License

MIT — free to use, fork, and gift to someone you love.
