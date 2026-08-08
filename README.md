# Portfolio

Single-page portfolio and service list. Plain HTML — no build step, no dependencies.

**Live:** https://alycoulibal2-sketch.github.io/

## Editing

Everything lives in `index.html`.

- **Projects** — each one is an `<article class="sheet">`. Copy a block, change the
  heading, part number, description, spec rows and links.
- **Prices** — the `.svc-row` blocks in the "What I can build for you" section.
- **Colours and fonts** — the CSS custom properties in `:root` at the top. Change a
  value there and it updates everywhere, in both light and dark themes.

Push to `main` and GitHub Pages redeploys in about a minute.

## Checked

- No horizontal overflow at 375 px (measured, `scrollWidth == clientWidth`).
- Light and dark themes both defined; follows the visitor's system setting.
- Keyboard focus states, reduced-motion respected.
- Every outbound link verified reachable at time of writing.
