# Zimo studio website

A single-page site for GitHub Pages. No build step — just HTML/CSS/JS in `index.html`.

## Publish it on GitHub Pages

1. Create a repo (e.g. `zimo/zimo.github.io`, or any repo name).
2. Add `index.html` and the `images/` folder to it.
3. In the repo, go to **Settings → Pages**, set the source to your default branch (`main`) and root folder.
4. Your site will be live at `https://<username>.github.io/<repo>/` (or your custom domain if you set one up).

## Add your logo

Drop your logo file into `images/` (e.g. `images/zimo-logo.svg` or `.png`), then in `index.html` replace:

```html
<div class="logo-text">Zimo</div>
```

with:

```html
<img class="logo" src="images/zimo-logo.svg" alt="Zimo">
```

## Add a new game

Open `index.html`, find the `const games = [ ... ]` array near the bottom, and add one object. Everything else (layout, badges, which section it lands in) builds itself from this.

```js
{
  name: "Your Game Name",
  tier: "testing",           // "featured" | "testing" | "experiment"
  badge: "testing",          // "global" | "soft" | "testing" | "proto" | "dead"
  badgeLabel: "In Testing",  // text shown on the badge — can be anything you want
  description: "One or two sentences about the game.",
  image: "images/your-game.png",   // omit for "experiment" tier if you don't have one
  appStore: "https://apps.apple.com/...",   // omit or leave "" to hide the button
  googlePlay: "https://play.google.com/..." // omit or leave "" to hide the button
}
```

Notes:
- **Only one `featured` game at a time reads best** — that's meant to be your current best/live title (Upside Down right now). If you promote another game later, just switch its tier to `"featured"` and move Upside Down down.
- `appStore` and `googlePlay` are both fully optional and independent — set one, both, or neither. No button renders for a missing link.
- For `experiment` tier, `image` is optional — those render as a compact one-line row.
- Put game images in `images/`, roughly 16:9 for featured/testing cards (e.g. 1200×675px) works best.

## Badges

| badge value | label suggestion | meaning |
|---|---|---|
| `global` | Global Launch | fully released everywhere |
| `soft` | Soft Launch | live in limited regions, still tuning |
| `testing` | In Testing | closed/internal testing, iterating |
| `proto` | Prototype | early concept, not yet validated |
| `dead` | Dead | killed, no longer in development |

`badgeLabel` is free text, so you can rename these (e.g. "Testing" instead of "In Testing") without touching the CSS.

## Contact / footer

Edit the email and social links directly in the `<footer>` section of `index.html`.
