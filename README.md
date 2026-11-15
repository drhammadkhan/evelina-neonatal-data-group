# Evelina Neonatal Data Group

Landing page for the group's browser-based reference tools: **https://drhammadkhan.github.io/evelina-neonatal-data-group/**

| Tool | Live | Source |
|---|---|---|
| ROP screening window calculator | [open](https://drhammadkhan.github.io/ROP-Calculator/) | [ROP-Calculator](https://github.com/drhammadkhan/ROP-Calculator) |
| BCG tool (TB incidence check) | [open](https://drhammadkhan.github.io/tb-rate-check/) | [tb-rate-check](https://github.com/drhammadkhan/tb-rate-check) |
| Ventricular index chart | [open](https://drhammadkhan.github.io/levene-vi-chart/) | [levene-vi-chart](https://github.com/drhammadkhan/levene-vi-chart) |
| Jaundice treatment thresholds | [open](https://drhammadkhan.github.io/jaundice-thresholds/) | [jaundice-thresholds](https://github.com/drhammadkhan/jaundice-thresholds) |

Static site, no build step: `index.html`, `favicon.svg`, `og-image.png` and `fonts/` (the workflow publishes exactly these) (Fraunces and DM Mono, SIL Open Font License, self-hosted).

## Hosting

GitHub Pages, deployed by the `Deploy to GitHub Pages` workflow (`.github/workflows/pages.yml`) on every push to `main`, the same way as the other group tools. In Settings, Pages, set Source to "GitHub Actions".

## Adding a tool

1. Add a `<li class="tool ...">` card to `index.html` (accent classes: `hot`, `cool`, `amber`).
2. Give the tool the shared look and branding described in [DESIGN.md](DESIGN.md).

These tools display published guidance and reference data for the clinician to interpret. They support, and do not replace, clinical judgement and current guidance.

## Usage counter (private)

`stats/index.html` is an unlinked page (`/stats/`, marked `noindex`) that shows how many times each tool has been opened. Counts come from [GoatCounter](https://www.goatcounter.com/), which stores page paths only: no cookies, no personal data, nothing the user enters.

Setup:

1. Create a free GoatCounter site and note its code (`xxx` in `xxx.goatcounter.com`).
2. In GoatCounter, Settings, enable "Allow adding visitor counts on your website".
3. Set `CODE` in `stats/index.html`.
4. Add this to the `<head>` of ROP-Calculator, tb-rate-check and jaundice-thresholds (the path counted is the tool's own URL, e.g. `/ROP-Calculator/`):

```html
<script data-goatcounter="https://xxx.goatcounter.com/count" async src="//gc.zgo.at/count.js"></script>
```

The Levene chart cannot take the snippet: its Content-Security-Policy blocks all outside requests, which backs the "data stays on your device" promise (and saved patient files are copies of the app). Instead, `index.html` here sends one anonymous GoatCounter event when its card is clicked (path `/click/levene-vi-chart`). That count only includes opens from this landing page, not direct visits.
