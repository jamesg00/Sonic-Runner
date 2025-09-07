# Sonic Runner (Kaplay + Vite)

An arcade-style endless runner inspired by classic Sonic vibes. Jump over gaps, collect rings, stomp Motobugs, and chase a high score with combo multipliers and letter grades.

https://github.com/jamesg00/Sonic-Runner

## 🎮 Gameplay
- **Jump**: press **Space**, **Left Click**, or **Tap** (mobile supported).
- **Collect Rings**: +1 point.
- **Stomp Motobugs** (jump *onto* them while airborne): **+10 × combo multiplier**.
- **Combo Multiplier** grows when you chain stomps without landing; it **resets when you touch the ground**.
- **Game Over** if you collide with an enemy while on the ground.
- Your **best score** is saved locally between runs.
- After a run, you’ll get a **rank** from **F → S** based on your score.

> Toggle Kaplay debug overlay with **D** (handy while developing).

## 🧰 Tech Stack
- [Vite](https://vitejs.dev/) for dev server and builds
- [Kaplay](https://kaplayjs.com/) (game framework) — version `^3001.0.19`

## 🗂️ Project Structure
```
sonic-runner-g/
├─ src/
│  ├─ entities/
│  │  ├─ sonic.js
│  │  ├─ motobug.js
│  │  └─ ring.js
│  └─ scenes/
│     ├─ mainMenu.js
│     ├─ game.js
│     └─ gameover.js
├─ index.html
├─ package.json
└─ public/            # recommended for assets in production
   ├─ graphics/       # .png sprites
   ├─ sounds/         # .wav/.mp3
   └─ fonts/          # .ttf
```

> **Note on assets:** This game loads images/sounds by **string paths** (e.g. `graphics/sonic.png`). For **production builds with Vite**, put these folders under `public/` so they’re copied as-is:
>
> - `public/graphics/`
> - `public/sounds/`
> - `public/fonts/`
>
> Paths in code may stay the same (`"graphics/sonic.png"`), because `public/` is served at the web root.

## 🛠️ Local Development
1. Install [Node.js LTS](https://nodejs.org/)
2. Install dependencies
   ```bash
   npm install
   ```
3. Start the dev server
   ```bash
   npm run dev
   ```
   Open the printed URL (usually `http://localhost:5173`).

## 🚀 Build
```
npm run build     # outputs to dist/
npm run preview   # serve the built files locally
```

## ☁️ Deploy (beginner-friendly)
### Option A — Vercel (auto-builds from GitHub)
1. Push this repo to GitHub.
2. Go to **vercel.com → Add New → Project**, import your repo.
3. Settings
   - Framework preset: **Vite** (auto-detected)
   - Build command: `npm run build`
   - Output directory: `dist`
4. Click **Deploy** → you’ll get `https://your-app.vercel.app`

### Option B — Netlify Drop (no account required)
1. Run `npm run build` to create `dist/`.
2. Go to **app.netlify.com/drop**.
3. Drag the **`dist/` folder** in → instant live URL.

### Option C — itch.io (great for web games)
1. Run `npm run build` to create `dist/`.
2. Zip the **contents** of `dist/`.
3. Create a new **HTML** game on itch.io and upload the zip.
4. Check “**This file will be played in the browser**”.

> **GitHub Pages** also works, but you’d need `base` config in `vite.config.js`. Vercel/Netlify are simpler.

## ⚙️ Config (optional)
If you want to be explicit about `public/` and base path for typical hosts:
```js
// vite.config.js
export default {
  publicDir: 'public', // where graphics/, sounds/, fonts/ live in production
  base: '/',           // fine for Vercel/Netlify
}
```

## 📦 Scripts
- `npm run dev` — start dev server
- `npm run build` — production build
- `npm run preview` — preview the build locally

## 📝 Credits
- Code uses the Kaplay framework.
- Sprites, font (`mania.ttf`), and audio are included for demo purposes. **Ensure you have rights** to distribute any assets you publish; replace with your own if needed.

## 📄 License
Choose a license (e.g., MIT) or keep it private. You can add a `LICENSE` file later.

---

### Contributing
PRs and suggestions are welcome!

### Contact
Questions or issues? Open an issue on the repo or ping me.
