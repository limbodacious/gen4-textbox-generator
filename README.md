# Pokémon Gen 4 Textbox Generator

A pixel-accurate dialogue textbox generator for **Pokémon Gen 4** (Platinum, Diamond/Pearl, and HeartGold/SoulSilver), inspired by [meejle's Emerald textbox generator](https://meejle.github.io/). Pick from 20 authentic box styles ripped from the games, type your text, and download a PNG at the game's exact native resolution.

**Live page:** `https://limbodacious.github.io/gen4-textbox-generator/` (enable GitHub Pages — see below)

## Features

- **20 real textbox styles**, isolated from the original sprite sheets with transparent backgrounds, switchable with a style grid or the arrow buttons.
- **1:1 scale** — every box image keeps its exact native in-game pixel dimensions. Nothing is resized or stretched. The preview auto-scales to fit the panel; the downloaded PNG is always native size.
- **Authentic cutoff behavior** — text does not auto-wrap. A line that's too long simply gets clipped at the box's inner right edge, just like the source art.
- **The actual in-game font** — not a lookalike. Every character is stamped as a fixed grid of pixels extracted directly from Pokémon Gen 4's own font graphics (via the [pret/pokeplatinum](https://github.com/pret/pokeplatinum) decompilation project), so there's no canvas text rendering, no anti-aliasing, and no smoothing to introduce blur.
- **One-click PNG download** of exactly what's in the preview.

## Usage

Open `index.html` directly (double-click it, or drag it into a browser tab), or serve it via GitHub Pages / a local server — all work, since nothing on the page depends on `fetch`. Type your two lines of dialogue, pick a box style, and click **Download PNG**.

## Deploying to GitHub Pages

1. Create a new GitHub repository and push this project to it.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to "Deploy from a branch", branch `main`, folder `/ (root)`.
4. Save — GitHub will publish the site at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

No build step, no dependencies — it's a static site.

## Project structure

```
index.html               the app
style.css
script.js                box data, the in-game font's pixel grid (BITMAP_FONT), rendering, download logic
assets/
  fonts/
    LICENSE-FONT.txt         font source, extraction method & attribution
  textboxes/
    type1.png ... type20.png
    CREDITS.txt
```

## Licensing

This repo bundles assets with different licenses/ownership than the project code:

- **Code** (`index.html`, `style.css`, `script.js`) — MIT License, see [LICENSE](LICENSE).
- **Font** (the `BITMAP_FONT` data in `script.js`) — the actual Pokémon Gen 4 message font, glyph shapes extracted from the game's own ROM data via the [pret/pokeplatinum](https://github.com/pret/pokeplatinum) decompilation project. Same category as the textbox art below: a fan extraction of a Nintendo / Game Freak / Creatures Inc. asset, used unmodified in shape for this non-commercial project. Full extraction details and attribution in [assets/fonts/LICENSE-FONT.txt](assets/fonts/LICENSE-FONT.txt).
- **Textbox art** (`assets/textboxes/*.png`) — a fan rip of Pokémon Gen 4 assets (ripped by Dragoon). Pokémon and all related properties are trademarks of Nintendo / Game Freak / Creatures Inc. Used here for a non-commercial fan project only; no ownership is claimed.

See [LICENSE](LICENSE) for the full scope note.

## Credits

- Concept/inspiration: [meejle's Pokémon Emerald textbox generator](https://meejle.github.io/)
- Font: Pokémon Gen 4's own message font, via [pret/pokeplatinum](https://github.com/pret/pokeplatinum)
- Textbox art: ripped by Dragoon
- Generator: [Limbodacious](https://github.com/limbodacious)
