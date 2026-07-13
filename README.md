# AR Card Lab

Point a phone/tablet camera at any printed card and its 3D model appears on
top of it, with a caption naming and explaining it. Runs in the browser
(AR.js + A-Frame) — no app install.

Nine cards, each wired to its own animated model:

| Card | Shows |
|------|-------|
| Enzyme & Substrate | animated enzyme reaction cycle (binding -> reaction -> release) |
| Heart | a beating heart |
| Skeleton | a simplified skull / spine / ribcage |
| Muscle | a contracting skeletal muscle |
| Lungs | lungs inflating and deflating |
| DNA | a rotating double helix |
| Atom | electrons orbiting a nucleus |
| CPU chip | a processor with a pulsing core |
| Network | nodes with a data packet hopping between them |

> Note on realism: the models are built from simple 3D shapes (spheres,
> cylinders, etc.) and animated — clear, self-contained *schematics*, good for
> explaining a concept, not photorealistic anatomy. To make one look realistic,
> load a real model file: <a-entity gltf-model="heart.glb">.

## Files
- index.html — the app
- *.patt — the 9 marker pattern files (must sit next to index.html)
- marker-cards.html — printable page of all 9 cards (open -> Save as PDF)

## Run it (~5 min)
The camera needs HTTPS, so host it — GitHub Pages is free and HTTPS by default:
1. New GitHub repo -> upload index.html AND all nine .patt files together.
2. Settings -> Pages -> Deploy from branch -> main / root -> Save.
3. Open the https://<you>.github.io/<repo>/ link on the phone, tap Start camera, allow access.

## Print the cards
Open marker-cards.html, click Print / Save as PDF. Set paper to A4 and scale
100% (not "Fit to page"). Print ~7-10 cm per card, keep the white border, cut
on the dashes.

## How it's wired (so you can change it)
Near the top of the script in index.html there's a CARDS list — each entry maps
a marker to its .patt file, a name, and a description. The 3D content for each
lives in the M.<markerId> blocks just below. To change what a card shows, edit
that block. The card picture is only a label; the app matches the pattern, so
any card can show anything.

Want a realistic version of one (real .glb model) or a new computing demo
(packet routing, a stack, binary)? That's the next step.
