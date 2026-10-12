# 🖼️ ReadyChobi

**Passport photos, ready in seconds.**

ReadyChobi is a browser tool that removes backgrounds, auto-frames passport photos, and shrinks them to size — all without uploading a single byte anywhere. Everything runs on your device.

[![Live Demo](https://img.shields.io/badge/demo-live-brightgreen)](https://opirajbhor.github.io/ReadyChobi/)
[![Made with](https://img.shields.io/badge/made%20with-HTML%20%2B%20Tailwind-38bdf8)](https://tailwindcss.com/)
[![AI](https://img.shields.io/badge/AI-in--browser-8b5cf6)](#-how-it-works)
[![Privacy](https://img.shields.io/badge/100%25-local-yes-success)](#-privacy)

---

## Why

If you've ever applied for a passport, visa, or any government form online, you know the drill:

- The photo needs a specific size (usually 40×50 mm or 2×2 in).
- It needs a plain background — but you took it against a wall with a light switch on it.
- The file has to be under 50 KB, but your phone camera spits out 4 MB.
- You don't want to hand your photo to some random upload site.

ReadyChobi fixes all of that in one page. Drop your photo, pick a preset, click Process. Done.

---

## ✨ What it does

- **Bulk processing** — drop a stack of photos at once, they process one after another.
- **Background removal in your browser** — uses the `@imgly/background-removal` library (RMBG-1.4). No API keys, no uploads, no monthly quota. The model runs on WebAssembly/WebGPU right inside your browser tab.
- **Face-aware framing** — the browser's built-in `FaceDetector` finds the head and frames it like a real passport photo (head fills ~62% of the height, eyes ~38% from the top).
- **Passport / Visa presets**:
  - 🇧🇩 Bangladesh Passport — 40×50 mm
  - 🇧🇩 Bangladesh Visa — 35×45 mm
  - 🇺🇸 US Passport — 2×2 in
  - 🇪🇺 Schengen / Visa — 35×45 mm
  - 🇮🇳 India Passport — 35×35 mm
  - 🇨🇳 China Visa — 33×48 mm
  - Square — 1:1
  - Or enter your own dimensions
- **Background color** — swap the background to white, blue, grey, or any color. Default is the standard passport blue (`#ACC0FB`).
- **Manual crop** — click any processed photo to fine-tune the crop. Drag to move, drag corners to resize. `Ctrl+Z` to undo.
- **Size targeting** — set a range (default 20–50 KB) and the tool figures out the right quality for you.
- **Output formats** — WebP (default, fastest), JPEG, or PNG.
- **Download** — grab the whole batch as a ZIP, or click any single photo to save just that one. Filenames stay the same as the originals.
- **Extras** — dark mode, English/Bangla toggle, auto-enhance, trim empty edges, save your favourite settings as presets.

---

## 🔒 Privacy

This is the whole point. ReadyChobi **never sends your photos anywhere**.

- No backend, no database, no server.
- No analytics, no tracking, no accounts.
- The only network requests are for the CSS/JS libraries (Tailwind, JSZip) and the AI model weights — and even those get cached locally after the first load.
- Once loaded, the app works completely offline.

You can open DevTools → Network tab and watch for yourself. Nothing goes out.

---

## 🚀 Getting Started

There is **no build step**, no `npm install`, no bundler. Just one HTML file.

### Just open it

1. Download or clone this repo.
2. Double-click `index.html`.

That's it. Works in any modern browser (Chrome and Edge recommended for face detection).

### Or run a local server

```bash
# with Python
python -m http.server 8080

# or with Node
npx serve .
