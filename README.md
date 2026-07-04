# Leganet Internet Solutions — Website

Standalone HTML/CSS/JS export of the Leganet website, cleaned up from the Canva-published version so it can be edited as normal code and hosted anywhere (GitHub Pages, Netlify, Vercel, your own server, etc.)

## What was changed from the Canva version

- Removed Canva's internal editor scripts (`telemetry_sdk.js`, `data_sdk.js`, `resizing_sdk.js`, `editing_sdk.js`) — these only work inside Canva's own hosting and live-editor.
- Removed a Cloudflare Turnstile bootstrap snippet Canva injects for its own bot protection.
- Removed `data-template-id` attributes — these were only used by Canva's editor to track elements; harmless either way, but not needed here.
- Replaced 4 private `canva://...` image references with local placeholder paths in an `assets/` folder (see below). Everything else (Pexels stock photos, fonts, icons, layout, JS behavior) works as-is.

## Before this goes live, replace the 4 placeholder images

The `assets/` folder ships with **temporary orange/navy placeholder images** so the site renders out of the box. These were originally private Canva-hosted assets and won't load outside Canva. Replace them with your own copies (same filenames) in the `assets/` folder next to `index.html`:

| File expected | Used for |
|---|---|
| `assets/logo.png` | Nav bar logo |
| `assets/hero-dish.jpg` | Homepage hero image |
| `assets/starlink-roof.jpg` | "Starlink Satellite Solutions" section image |
| `assets/technician.jpg` | About page "Our Story" image |

Easiest way to get these: open the design in Canva, right-click each image → **Download**, save it into `assets/` with the matching filename above (or update the `src=` paths in `index.html` to whatever filenames you use).

## Running locally

No build step needed — just open `index.html` in a browser, or serve it:

```bash
npx serve .
```

## Deploying

- **GitHub Pages**: push this repo, then enable Pages in repo Settings → Pages → set source to your branch/root.
- **Netlify / Vercel**: drag-and-drop this folder, or connect the GitHub repo — no build command needed since it's static HTML.

## Pointing your domain here

Once this is hosted somewhere (GitHub Pages, Netlify, etc.), update your domain's DNS to point at that host instead of Canva. If your domain is registered through Canva, you can edit DNS records or change nameservers from **Account → Web domains → [your domain] → Manage → Advanced settings**. Note: changing nameservers away from Canva will disconnect your Canva-hosted site.
