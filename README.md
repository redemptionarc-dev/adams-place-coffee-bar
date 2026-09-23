# Adam's Place Coffee Bar

A staff-appreciation home-screen app built for the espresso bar event —
tap a drink name to pull up the full recipe card, sized to scale for
12 oz, 16 oz, or 20 oz cups. Built as a static site, no build step, no
backend.

## What's in here

```
index.html          the app
style.css             Adam's Place styling (Playfair Display + Karla, gold/sage palette)
app.js                 all the recipes + the tap-to-open logic
manifest.json          makes the site installable as an app
service-worker.js      lets it open even with a flaky connection
icons/                 the mountain-mark icon, pre-rendered at every size Android and iOS need
```

### Icon sizes included
- `icon-512.png`, `icon-192.png` — used by `manifest.json` for Android/Chrome install
- `icon-180.png`, `icon-167.png`, `icon-152.png`, `icon-120.png` — used by the `apple-touch-icon` tags for iPhone/iPad home screen icons at different device resolutions
- `icon-32.png` — browser tab favicon

## 1. Put it on GitHub

1. Create a new repository on GitHub (public repos get free Pages hosting) —
   something like `adams-place-coffee-bar`.
2. Upload every file in this folder to the repo, keeping the `icons/` folder
   structure intact.
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment", set **Source** to "Deploy from a branch",
   pick the `main` branch and the `/ (root)` folder, then **Save**.
5. GitHub will give you a URL like:
   `https://<your-username>.github.io/adams-place-coffee-bar/`
   It can take a minute or two to go live the first time.

## 2. Install it on an iPhone (no App Store needed)

1. Open the GitHub Pages link **in Safari** (it has to be Safari, not Chrome,
   for this to work on iOS).
2. Tap the **Share** icon (or, on iOS 26, the **•••** menu → **Share**).
3. Tap **Add to Home Screen** (make sure "Open as Web App" is on, if that
   toggle appears).
4. Tap **Add**.

A "Coffee Bar" icon shows up on the home screen. Opening it from there
launches full-screen, no address bar.

## 3. Install it on Android / other phones

Open the link in Chrome — you'll usually see an **"Add to Home screen"** or
**"Install app"** prompt automatically. If not, it's in the browser's
&#8942; menu.

## Updating the recipes later

All the drink data lives in `app.js`, near the top, in a `DRINKS` object with
`hot` and `iced` arrays. Each drink is an object like:

```js
{
  name: "Drink Name",
  source: "Inspired by ...",
  tag: "one-line description",
  ingredients: [["Ingredient", "Amount"], ...],
  steps: ["Step one.", "Step two.", ...],
  notes: "optional extra note",   // omit this line if there's no note
}
```

Add, edit, or remove entries there, commit the change on GitHub, and the
live site updates automatically — no rebuild needed.
