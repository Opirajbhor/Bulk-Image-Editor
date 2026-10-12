# 🖼️ Bulk Image Processor

A fully client-side web app that removes backgrounds, auto-frames passport photos, resizes to a target file size, and exports in JPEG / PNG / WebP — all without uploading a single byte to a server.

[![Live Demo](https://img.shields.io/badge/demo-live-brightgreen)](https://opirajbhor.github.io/)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Made with](https://img.shields.io/badge/made%20with-HTML%20%2B%20Tailwind-38bdf8)](https://tailwindcss.com/)
[![AI](https://img.shields.io/badge/AI-in--browser-8b5cf6)](#-how-it-works)
[![Privacy](https://img.shields.io/badge/100%25-local-yes-success)](#-privacy)

---

## ✨ Features

- 🎯 **Bulk processing** — drop multiple images at once and process them sequentially.
- 🧠 **In-browser AI background removal** — powered by [`@imgly/background-removal`](https://github.com/imgly/background-removal-js) (RMBG-1.4 model). Runs entirely on the user's device using WebAssembly/WebGPU. No API keys, no uploads, no quotas.
- 🙂 **Face-aware auto-framing** — uses the browser's native `FaceDetector` API to crop each photo to proper passport proportions:
  - Head fills ~62% of the photo height
  - Eyes sit ~38% from the top
  - Face centered horizontally
- 📐 **Passport / Visa presets**
  - Bangladesh Passport — 40×50 mm
  - Bangladesh Visa — 35×45 mm
  - US Passport — 2×2 in
  - Schengen/Visa — 35×45 mm
  - India Passport — 35×35 mm
  - China Visa — 33×48 mm
  - Square — 1:1
  - Custom dimensions
- 🎨 **Background color** — pick any solid color, with quick swatches (default: Passport Blue `#ACC0FB`). Live preview updates as you change color.
- ✂️ **Manual crop modal** — click any processed image to open a full-screen cropper. Drag to move, drag corners to resize (aspect-locked), reset to the face-centered default, apply. Non-destructive — your original pipeline output stays intact.
- 📉 **Smart size reduction** — binary-search over encoder quality to hit a target range (default 20–50 KB), with automatic downscaling if a file can't fit.
- 🗂️ **Multiple output formats** — JPEG (default), PNG, WebP.
- 📥 **Two download modes**
  - Download all as a single ZIP
  - Download individually, keeping the original filename (extension updated to match format)
- 🔒 **Privacy first** — nothing ever leaves the browser. No analytics, no tracking, no backend.

---

## 📸 Screenshots

> _Add screenshots here once you have them. Suggested: an idle state, a processing state, and the crop modal._

| Idle | Processing | Manual Crop |
| :---: | :---: | :---: |
| ![idle](docs/screenshot-idle.png) | ![processing](docs/screenshot-processing.png) | ![crop](docs/screenshot-crop.png) |

---

## 🚀 Getting Started

There is **no build step**. The entire app is one `index.html` file.

### Option 1 — Just open it

1. Download or clone this repo.
2. Open `index.html` in a modern browser (Chrome, Edge, or any Chromium-based browser recommended).

### Option 2 — Run a local server

```bash
# with Python
python -m http.server 8080

# or with Node
npx serve .
