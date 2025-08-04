# RNG FC – Stand-Alone Fixture Generator (Version 6)

Simple, offline-ready web app that rolls a truly random football fixture from
the entire top 6 tiers of the English pyramid—no spreadsheet upload required.

> **Live demo**  
> If you publish this repo with GitHub Pages you’ll get a link like  
> `https://YOUR-USERNAME.github.io/rngfc-fixture-generator/` and the app will run
> right in the browser.

---

## Quick Start

1. **Download / clone** the repo.  
2. Drop your `logo.png` (club badge or project logo) next to **index.html**.  
3. Put crest images in a folder called `logos/` (see naming rules below).  
4. Double-click **index.html**.  
5. Hit **Generate Fixture**—a match card appears and is logged in the History
   panel.

---

## File Structure


*The `logos/` directory contains only images; if it’s empty keep a hidden file
like `.keep` so Git tracks the folder.*

---

## Crest-Naming Rules

| Club name (display)    | Filename in `logos/`          | Why                           |
|------------------------|--------------------------------|-------------------------------|
| Arsenal                | `arsenal.png`                 | lower-case, spaces → `-`      |
| Brighton & Hove Albion | `brighton-hove-albion.png`    | `&` and multiple spaces → `-` |
| King’s Lynn Town       | `kings-lynn-town.png`         | apostrophe removed            |

A short helper called **`slugify()`** converts every club name to the
corresponding filename at runtime.  
If an image is missing the `<img>` just hides—so the app still works.

---

## User Guide

| Action | What happens |
|--------|--------------|
| **Generate Fixture** | Picks two different teams at random, shows a vertical match card (good for 9 × 16 screens) and logs it in History. |
| **History panel**    | Scrollable list of every draw this session (newest first). |
| **Clear**            | Resets the History panel. |

No internet? No problem—everything is local and runs entirely in the browser.

---

## Prompt for Future ChatGPT Sessions  🗒️

> *You can literally paste this block into a new ChatGPT chat and ask for new
> features; it contains the full technical context.*


---

## How to Add More Teams or Leagues

1. Open **index.html**.  
2. Scroll to `const teams = [...]`.  
3. Append new club names **exactly as you want them displayed** (apostrophes,
   accents, etc.).  
4. Ensure you add matching crest files in `logos/` (slugify rules apply).  
5. Save, refresh—done.

---

## Common Customization Ideas

| Feature | One-liner notes |
|---------|-----------------|
| **No-repeat draws** | Keep a `Set` of `"home-away"` strings; loop until new. |
| **Export history**  | `URL.createObjectURL(new Blob([history.join("\\n")]))` → link. |
| **Animate card**    | Wrap `.fixture-vert` in a CSS keyframe or use Anime.js. |
| **Installable PWA** | Add a `/manifest.json` and a service-worker with offline caching. |
| **Switch themes**   | Toggle `data-theme` attr and overwrite `--bg`, `--accent`, etc. |

---

## Publishing with GitHub Pages

1. Repo → **Settings → Pages** → Branch: `main` (root).  
2. Save.  
3. Wait ~30 s → your site is live at  
   `https://<user>.github.io/<repo>/`.

Share that link—no extra hosting needed.

---

### License

Feel free to re-use or expand this project.  
Drop me a credit or star if it saved you time. Cheers!


