# Shared design

All Evelina Neonatal Data Group tools use the same look. There is no shared package (each tool is a standalone static site), so the tokens below are copied into each tool. Keep them identical.

## Naming

Always write **Evelina Neonatal Data Group** (title case). Every tool shows it in the header (linking to the landing page), in the page `<title>` (`Tool name | Evelina Neonatal Data Group`), in its social meta tags, and in the footer credit ("A tool from the Evelina Neonatal Data Group").

## Typography

Fraunces (variable, serif) for text and headings; DM Mono for labels, kickers and numbers. Self-host the woff2 files; do not load fonts from a third-party CDN.

## Colour tokens

The palette is a four-colour combination in the spirit of Sanzo Wada's *A Dictionary of Colour Combinations* (data: [mattdesl/dictionary-of-colour-combinations](https://github.com/mattdesl/dictionary-of-colour-combinations)): warm paper, near-black ink, a red-orange and a deep green-teal. `--hot` is the dictionary's *Red Orange* (`#dd4027`).

| Token | Light | Dark | Use |
|---|---|---|---|
| `--paper` / `--paper2` | `#f3eee4` / `#ebe4d6` | `#15130f` / `#1d1a15` | page / card |
| `--ink` | `#1b1814` | `#f1ebdd` | text |
| `--mute` | `#675f54` | `#9b9384` | secondary text |
| `--line` | `#d6cdbb` | `#363126` | rules, borders |
| `--hot` | `#dd4027` | `#ff7a5c` | fills, rules, dots, focus ring (not small text) |
| `--hot-ink` | `#b3301a` | `#ff7a5c` | red **text** |
| `--hotbg` | `#f9ddd4` | `#3a1c14` | red tint |
| `--cool` / `--coolbg` | `#1d5e57` / `#d9e8e2` | `#6fd0c2` / `#13302c` | teal text and tint |
| `--amber` / `--amber-ink` / `--amberbg` | `#c5a56e` / `#7a5a12` / `#f3e7cb` | `#e0b866` / `#e0b866` / `#33290f` | caution (dictionary *Isabella Color*) |
| `--field` | `#fbf8f1` | `#110f0c` | form fields |

Semantics: **hot** = action or attention (e.g. screening required, at or above threshold), **cool** = clear or neutral-positive, **amber** = consider or caution, **mute** = not applicable.

### Contrast (WCAG 2.1 AA)

Small text must be at least 4.5:1 on `--paper`, `--paper2` and the tints. `--hot` on paper is only 3.4 to 3.8:1, which is why red text uses `--hot-ink` (4.9 to 5.4:1). `--mute` was darkened from `#7a7266` (3.75:1 on `--paper2`) to `#675f54` (4.97:1).

## Components

Header: red dot, group name (link), hairline rule. Then a mono uppercase kicker with a leading rule, then an `h1` in Fraunces 400 with the last word in italic 300. Cards: `--paper2`, 1px `--line` border, 4px radius, 5px left accent bar. Buttons: pill, DM Mono 0.85rem, ink fill for primary. Notices: `--paper2` with a 5px `--hot` left bar. Footer: mono small print, then an italic serif credit line.

## Behaviour

Hover styles only inside `@media (hover: hover) and (pointer: fine)`; press feedback via `:active` (scale .97, 100ms); transitions list exact properties and use `cubic-bezier(.23, 1, .32, 1)`; `prefers-reduced-motion` removes movement but keeps colour and opacity feedback; inputs are at least 16px so iOS does not zoom.
