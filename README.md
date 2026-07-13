# AR Card Scanner

Point a phone camera at a printed card and a 3D model appears on it:
**cat card → cat, skull card → skull.** Runs entirely in the phone browser
(AR.js + A-Frame) — no app install.

## Files
- `index.html` – the whole app
- `cat.patt`, `skull.patt` – marker pattern files (must sit next to `index.html`)
- `cat-card.png`, `skull-card.png` – the two markers, one per file
- `print-these-cards.png` – both markers on one sheet, ready to print

## Run it (about 5 minutes)
The camera needs **HTTPS**, so you can't just double-click the file — host it.
GitHub Pages is free and gives you HTTPS automatically:

1. Create a new GitHub repo.
2. Upload **all four** of these: `index.html`, `cat.patt`, `skull.patt`
   (the PNGs don't need to be uploaded — they're only for printing).
3. Repo **Settings → Pages → Deploy from branch → `main` / root → Save**.
4. Wait ~1 min, open the `https://<you>.github.io/<repo>/` link **on your phone**.
5. Tap **Start camera**, allow access.

## Print the cards
Print `print-these-cards.png`. Each card should end up roughly **7–10 cm**
square. Keep the white border around each card — the black frame is what the
camera locks onto, and the white margin (quiet zone) helps a lot.

## Tips if tracking is flaky
- **Good, even light.** Glare on glossy paper hurts; matte is better.
- Hold the card **flat and fairly still**, ~20–40 cm from the camera.
- Bigger print = detected from further away.
- If the model appears but faces the wrong way, tweak the model `rotation`
  values inside `index.html` (each marker block).

## Where to take it next
- Swap the primitive-built cat/skull for real `.glb` models
  (`<a-entity gltf-model="url"></a-entity>`) once the loop works.
- Add more cards: make a new marker image + `.patt`, add another `<a-marker>`.
- For nicer, picture-based cards, switch from AR.js pattern markers to
  **MindAR** image tracking.
