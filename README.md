# 🗓️ My Day Planner — iPhone PWA

A personal daily planner that lives on your iPhone home screen.  
Tasks save between sessions, history persists, and it auto-updates whenever you push to GitHub.

---

## 🚀 Setup (one time)

### 1. Create a GitHub repo
- Go to [github.com](https://github.com) → **New repository**
- Name it anything, e.g. `my-day-planner`
- Set it to **Public**
- Click **Create repository**

### 2. Upload these files
Upload all files from this folder into the repo root:
```
index.html
sw.js
manifest.json
icon-192.png
icon-512.png
```
You can drag-and-drop them all at once on the GitHub website.

### 3. Enable GitHub Pages
- In your repo, go to **Settings → Pages**
- Under **Source**, choose **Deploy from a branch**
- Branch: `main` / folder: `/ (root)`
- Click **Save**

After ~60 seconds, your planner will be live at:
```
https://YOUR-USERNAME.github.io/my-day-planner/
```

### 4. Add to iPhone Home Screen
1. Open the URL above in **Safari** on your iPhone
2. Tap the **Share** button (box with arrow) at the bottom
3. Scroll down and tap **Add to Home Screen**
4. Tap **Add** — done! 🎉

---

## 🔄 Auto-updates

Whenever you push changes to GitHub, the app will **automatically update** next time you open it — no manual steps needed.

The only thing to keep in mind: if you significantly change `sw.js` or add new files to cache, bump the version number at the top of `sw.js`:
```js
const CACHE_VERSION = 'v2'; // was v1
```

---

## 💾 What saves between sessions

| Data | Storage | Clears |
|---|---|---|
| Today's tasks | `localStorage` | Automatically at midnight (new day = fresh list) |
| Quick-add history | `localStorage` | Never (until you remove chips manually) |

---

## 📁 File overview

| File | Purpose |
|---|---|
| `index.html` | The entire app |
| `sw.js` | Service worker — offline support + auto-update |
| `manifest.json` | PWA metadata (name, icon, colors) |
| `icon-192.png` | Home screen icon (small) |
| `icon-512.png` | Home screen icon (large / splash) |
