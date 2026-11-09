# Before / After

A tiny, zero-dependency web app to compare screenshots of an application across two states (before and after a redesign, a release, a refactor…). Drop your images, pick a comparison mode, and flip through every page of your app.

Everything runs in your browser: **no upload, no server, no build step.**

## Features

- **Multi-page comparison**: one tab per screen (home, pricing, checkout…), with `←` / `→` to navigate.
- **Four comparison modes**
  - **Slider**: drag anywhere on the image to reveal the before/after split.
  - **Side by side**: both versions next to each other.
  - **Toggle**: click the image (or press `Space`) to flip between versions.
  - **Fade**: blend the two versions with a range slider.
- **Smart pairing**: files are matched by name (`home-before.png` ↔ `home-after.png`), or by order when the names don't match.
- **Drag & drop** for batch import, or use the **+ Before** / **+ After** buttons.
- **Custom labels**: rename "Before" and "After" to anything (`v1.2`, `v2.0`, `staging`, `prod`…).
- **Long screenshots supported**: full-page captures scroll inside the frame, and the slider handle spans the full height.
- **Light and dark theme** following your system setting.
- **Demo mode** to try it without any image.

## Getting started

```bash
git clone https://github.com/<your-username>/before-after.git
cd before-after
```

Then simply open `index.html` in your browser. That's it.

Optionally, serve it locally:

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Usage

1. Export your screenshots with matching names:

   ```
   home-before.png      home-after.png
   pricing-before.png   pricing-after.png
   checkout-before.png  checkout-after.png
   ```

2. Drag all the files onto the drop zone. Files containing `before`, `old` or `avant` go to the first side; files containing `after`, `new` or `apres` go to the second. If no keyword is found, the first half of the files is used as "before" and the second half as "after".
3. Choose a mode, then use the page tabs or the arrow keys to go through your screens.

### Keyboard shortcuts

| Key     | Action                                  |
| ------- | --------------------------------------- |
| `←` `→` | Previous / next page                    |
| `Space` | Flip before/after (in **Toggle** mode)  |

## Tech

Single `index.html` file: vanilla JavaScript, plain CSS, no framework, no dependencies. Images are read locally with the `FileReader` API and never leave your machine.

## Roadmap

- [ ] Export a comparison as a standalone HTML file or PDF
- [ ] Persist comparisons (versions v1, v2, v3 of the same page) with shareable links
- [ ] Compare more than two states
- [ ] Zoom and synchronized panning
- [ ] Pixel-diff highlighting mode

## Contributing

Issues and pull requests are welcome. Since the whole app lives in a single file, it's easy to fork and tweak.

## License

[MIT](LICENSE)
