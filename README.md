# Vaughn Concha — Junior Graphic Designer

A responsive portfolio featuring graphic, packaging, digital, sportswear, and print design work, with an interactive 3D basketball jersey.

## Pages

- `index.html` — Main portfolio with selected projects, skills, a quick tour, the scroll-driven 3D jersey story, jersey editorial gallery, about section, and contact details.
- `showcase.html` — Alternate presentation with the 3D jersey viewer, project gallery, and portfolio sections.

Both pages use `viewer.js` for the shared 3D model gallery. On the main page, scrolling through the viewer reveals and rotates the jersey through 360 degrees. On the showcase page, the jersey auto-rotates; drag to orbit and use the scroll wheel to zoom.

## Run locally

Serve this folder over HTTP, for example by opening it in VS Code and starting the Live Server extension. Open `index.html` for the main portfolio or `showcase.html` for the alternate page.

Do not open the pages directly with a `file://` URL. The 3D viewer uses JavaScript modules and loads Three.js from jsDelivr. The pages also request fonts from Google Fonts, and the main page loads Lenis from jsDelivr, so an internet connection is needed for those resources.

## Portfolio assets

- `assets/mockups/` — Selected packaging and product mockups.
- `assets/rt pics/` — Basketball photos used in the jersey editorial gallery.
- `assets/jersey.glb` and `assets/jersey-texture.png` — Model and texture used by the interactive viewer.

The jersey model is about 44.5 MB. The viewer starts loading it as it approaches the viewport and pauses rendering while it is offscreen. The model is still demanding during active 3D interaction; use an optimized, lower-poly model when replacing it to improve load time and frame rate.

## Add a model to the 3D gallery

1. Copy the `.glb` model and its matching texture into `assets/`.
2. Add an entry to the `models` array in `viewer.js`, following the basketball jersey entry. Set `name`, `type`, `modelUrl`, `textureUrl`, `project`, `format`, `design`, and `artist`.
3. Set `credit` with the model creator, attribution link, license, and original model link.
4. Keep attribution and license details accurate, and check the model in both pages.

The gallery cards, navigation, model count, loading state, and model details are generated from the `models` array. The included jersey model is credited in the 3D collection section on each page.
