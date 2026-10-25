# It's Fiction. — Teto Easter Egg Playground

A GitHub-ready test page for the Kasane Teto click interaction. This is a standalone **playground**, not an automatic edit to your existing portfolio. Once you provide the real portfolio HTML/CSS/JS, this interaction can be adapted into that original project card.

## Package note

This is the refreshed package of the current playground files. It includes the current dialogue persistence behavior: dialogue stays visible after speech, can be dismissed by clicking again when the interaction is idle, and auto-dismisses after 30 seconds. It is still a standalone playground, not integrated into the original portfolio.

## 1. Add the PNG images

Put these files inside `assets/teto/` exactly as named below (lowercase, `.png` extension):

- `teto-sleep.png` — Frame 1: sleeping / idle
- `teto-annoyed.png` — Frame 2: annoyed, eyes closed
- `teto-waking.png` — Frame 3: waking transition
- `teto-talking.png` — Frame 4: talking, mouth open
- `teto-neutral.png` — Frame 5: mouth closed, resting
- `teto-angry.png` — angry reaction
- `teto-confused.png` — confused / suspicious reaction
- `teto-shocked.png` — big shocked / disbelief reaction
- `teto-shy.png` — embarrassed / flustered reaction
- `teto-smug.png` — smug / mischievous reaction

The `assets/teto/.gitkeep` file only preserves the folder before you add images. It is not an image. The page displays an obvious placeholder for any missing PNG, so you can test the page structure before uploading all ten pictures.

## 2. Add your MV link

Open `teto.js` and replace the empty value near the top:

```js
const MV_URL = '';
```

with your actual MV URL, for example:

```js
const MV_URL = 'https://www.youtube.com/watch?v=YOUR_VIDEO_ID';
```

Use the real video URL; `YOUR_VIDEO_ID` above is only an example.

## 3. Preview locally

Keep `index.html`, `styles.css`, `teto.js`, and the `assets/` folder together. Open `index.html` in a browser. A simple local web server is also fine. For GitHub Pages, upload the files with this same relative structure and enable Pages for your repository.

The image paths are resolved relative to `document.baseURI`, so they work from a normal project subdirectory on GitHub Pages too.

## Interaction behavior

1. First encounter: click once to get the annoyed face, then click again within four seconds to wake Teto. She says “Whatcha want?”, then returns to sleep.
2. Second encounter: the next click plays the quick wake-up and “Bro.” reaction, then leaves her on the neutral frame.
3. Later clicks play from the **76 unique dialogue lines**. Special expressions (angry, confused, shocked, shy, smug) stay frozen during that line; normal lines use subtle talking-frame changes and settle on neutral.
4. Clicks are ignored while a line or animation is running. The “Ay ay, why not click on her?” hint disappears after the first click.
5. One random tap-count warning triggers at a threshold between 20 and 40. After 40 taps, there is a chance for one additional reaction. There is no 70-tap special event.
6. Dialogue lines use a shuffle bag, so every line is shown once before the pool is shuffled again. Consecutive lines try to avoid repeating the same topic category.

## File layout

```text
fiction-teto-playground/
├── index.html
├── styles.css
├── teto.js
├── README.md
└── assets/
    └── teto/
        ├── teto-sleep.png
        ├── teto-annoyed.png
        ├── teto-waking.png
        ├── teto-talking.png
        ├── teto-neutral.png
        ├── teto-angry.png
        ├── teto-confused.png
        ├── teto-shocked.png
        ├── teto-shy.png
        └── teto-smug.png
```
