# Evelina Neonatal Data Group

Landing page for the group's browser-based reference tools: **https://drhammadkhan.github.io/evelina-neonatal-data-group/**

| Tool | Live | Source |
|---|---|---|
| ROP screening window calculator | [open](https://drhammadkhan.github.io/ROP-Calculator/) | [ROP-Calculator](https://github.com/drhammadkhan/ROP-Calculator) |
| BCG tool (TB incidence check) | [open](https://drhammadkhan.github.io/tb-rate-check/) | [tb-rate-check](https://github.com/drhammadkhan/tb-rate-check) |
| Ventricular index chart | [open](https://drhammadkhan.github.io/levene-vi-chart/) | [levene-vi-chart](https://github.com/drhammadkhan/levene-vi-chart) |

Static site, no build step: `index.html`, `favicon.svg`, `og-image.png` and `fonts/` (Fraunces and DM Mono, SIL Open Font License, self-hosted).

## Hosting

GitHub Pages, deployed from the `main` branch root (Settings, Pages, "Deploy from a branch", `main` / `(root)`).

## Adding a tool

1. Add a `<li class="tool ...">` card to `index.html` (accent classes: `hot`, `cool`, `amber`).
2. Give the tool the shared look and branding described in [DESIGN.md](DESIGN.md).

These tools support, and do not replace, clinical judgement and current guidance. They are reference aids, not certified medical devices.
