# ContentCoverage

Browse **MedXplain** by specialty and export columns 1 & 2 (`Module`, `Topic`) as a PDF.

- **25 specialties** — one per sheet tab
- **3,459 topics** total
- Pick any combination of specialties, preview, then export
- Output matches the standard Eremedium PDF layout (company header, specialty banner, merged module cells)
- Installable PWA, works fully offline

## Export

- **Export selected as PDF** — one PDF; each selected specialty gets its own section/page
- **Export everything as one PDF** — all 25 specialties

In the print dialog choose *Save as PDF*. Page size: US Letter.

## Run locally

Static site — no build step.

```bash
python -m http.server 8000
# open http://localhost:8000/ContentCoverage/
```

## Deploy (GitHub Pages)

Push to this repo, then in **Settings → Pages** select *Deploy from a branch*, branch `main`, folder `/ (root)`.

Live at: `https://rsharmaeremedium.github.io/ContentCoverage/`

## Regenerating data

Data is embedded in `index.html` as a JSON payload generated from the source
spreadsheet (`Module` / `Topic` columns of each tab).

## Structure

```
index.html            app + embedded data
manifest.webmanifest  PWA manifest
sw.js                 service worker (offline cache)
icons/                app icons + Eremedium logo
```
