# R2 Hours

Local time and meeting overlap across R2 Capital's countries — a lightweight, installable **PWA** that works offline.

## What it does

R2 Hours shows, at a glance, who's working and when the whole team can meet across R2's locations.

- **Now** — a live view of every location: who's open, hours ahead/behind, UTC offset, and whether China is open.
- **Plan** — a 24-hour overlap board to find meeting slots that work across time zones, with best-window suggestions, a clock-change (DST) watch, and shareable slot links.
- **Presets** — quick filters: Everyone, LatAm ops, Ant sync, Americas.

### Locations covered

| Country | City | Zone |
|---|---|---|
| United States (West) | Los Angeles | `America/Los_Angeles` |
| United States (East) | New York | `America/New_York` |
| Mexico | Mexico City | `America/Mexico_City` |
| Colombia | Bogotá | `America/Bogota` |
| Peru | Lima | `America/Lima` |
| Chile | Santiago | `America/Santiago` |
| Brazil | São Paulo | `America/Sao_Paulo` |
| Argentina | Buenos Aires | `America/Argentina/Buenos_Aires` |
| China | Shanghai · Hangzhou | `Asia/Shanghai` |

Working bands are local to each country: **office hours 09:00–18:00**, **edge hours 07:00–09:00 and 18:00–22:00**, **closed 22:00–07:00**. Time-zone and daylight-saving handling is done natively in the browser via `Intl.DateTimeFormat`.

## Features

- Fully offline — single self-contained `index.html` with an embedded logo, cached by a service worker.
- Installable to the home screen on mobile and desktop (standalone PWA).
- Automatic west → east ordering of locations.
- Copy and share a specific meeting slot as a link that opens on the same moment in the reader's own time zone.
- Light / dark theme.

## Project structure

```
index.html      App — markup, styles, and logic in one self-contained file
manifest.json   PWA manifest (name, icons, theme, standalone display)
sw.js           Service worker — offline shell, network-first with cache fallback
icon-192.png    App icon (192×192)
icon-512.png    App icon (512×512)
```

## Running locally

Because it's a PWA with a service worker, serve it over HTTP rather than opening the file directly.

```bash
# from the project folder, using Python's built-in server
python3 -m http.server 8000
```

Then open http://localhost:8000 in your browser.

## Deploying with GitHub Pages

This is a static site, so GitHub Pages hosts it directly:

1. Go to **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to *Deploy from a branch*.
3. Choose branch **`main`** and folder **`/ (root)`**, then **Save**.
4. After a minute the site is published at `https://mgalves1978-hub.github.io/R2Hours/`.

Once live, open the URL on a phone and use **Add to Home Screen** to install it as an app.

> Note: Serving GitHub Pages from a **private** repository requires GitHub Pro. If Pages isn't available, either upgrade or make the repository public.

## Version

Current: **v0.01**
