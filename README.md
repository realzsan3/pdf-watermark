# PDF Watermark Tool

A lightweight, client-side tool for adding tiled text watermarks to PDF files. No server, no upload — everything runs in your browser.

## Features

- 🔒 **100% local** — files never leave your device
- 🌐 **Bilingual** — English / 中文, auto-detected from system language
- 📱 **Responsive** — works on desktop and mobile
- 📴 **PWA / Offline** — installable, works without internet after first load
- 🎨 **Customizable** — text, size, rotation, color, opacity, tile spacing
- 🖨️ **Real-time preview** — see watermark before downloading

## Files

```
index.html   # Main app (open this in a browser)
manifest.json        # PWA manifest
sw.js                # Service worker (offline caching)
```

All three files must be in the **same directory**.

## Usage

### Option A — Open locally
Just open `index.html` in any modern browser. PWA/offline features require a server (see Option B).

### Option B — Serve over HTTPS
Host the three files on any static server. Service workers require HTTPS (or `localhost`).

```bash
# Quick local server (Python)
python -m http.server 8080
# Then open http://localhost:8080/index.html
```

## How It Works

1. Drop or select a PDF
2. Adjust watermark settings
3. Click **Preview** to see the result
4. Click **Download** to save the watermarked PDF

## Font Strategy

The tool automatically picks the best available font with zero manual setup:

1. **System font** — detects installed CJK fonts (PingFang, Microsoft YaHei, SimHei, etc.) — zero network requests
2. **Google Fonts fallback** — downloads Noto Sans SC subset (~50–100 KB) only if no system font is found
3. **Generic fallback** — uses `sans-serif` if network is unavailable

## Browser Support

Chrome 80+, Edge 80+, Firefox 75+, Safari 14+

## License

MIT