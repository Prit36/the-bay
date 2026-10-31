# The Bay

A walkable 3D coastal world by [Prit Prajapati](https://prit36.github.io/). Wander through a village, row a boat, fly a balloon, meet the wildlife and find eleven paper lanterns. The sky follows the time in Surat, India, or any hour you choose.

[Explore the bay](https://prit36.github.io/the-bay/).

Hand-written HTML, CSS and JavaScript with Three.js. No build step, package installation or backend is required.

## Run locally

Serve this directory over HTTP, for example with Python:

```sh
python -m http.server 8080
```

Open [localhost:8080](http://localhost:8080/). Opening `index.html` directly with `file://` will not load the ES modules correctly.

Use a browser with WebGL 2 support. Three.js is pinned to version `0.160.0` in the import map in `index.html` and loaded from jsDelivr. Google Fonts supplies the typefaces, with local fallbacks. The initial load needs an internet connection for Three.js; the world does not request the portfolio or use a backend.

## Explore

| Control | Action |
| --- | --- |
| Mouse / WASD | Look / walk |
| Shift / Space | Run / jump; hold Space in the air to use the parasol |
| E / Click | Interact / skip a stone |
| Scroll / N / T | Change the hour / return to now / watch a day |
| Tab / P | Map / save a postcard |
| M / H / Esc | Sound / hide the HUD / menu |
| R | Return to the nearest path |

Touch controls, camera comfort and detail settings are available in the menu. Lantern progress and preferences are saved in the browser's local storage. Hosting under the portfolio's domain may retain earlier progress.

Append `?skew=60` to move the sky one hour ahead of the current time. For development, `?dev` exposes the existing `window.bay` inspection controls.

## Source layout

| File | Responsibility |
| --- | --- |
| `index.html`, `world.css` | Entry page, menus and HUD |
| `main.js` | Scene setup, controls and interactions |
| `projects.js` | The eleven lanterns' names, descriptions and links |
| `land.js`, `build.js`, `flora.js` | Terrain, buildings and vegetation |
| `sky.js`, `water.js`, `style.js`, `post.js` | Lighting, water, materials and postprocessing |
| `life.js`, `balloon.js`, `fx.js`, `sound.js` | Wildlife, balloon, effects and procedural audio |

All runtime files are in this repository. The lantern catalog is a snapshot owned by this project; edit `projects.js` to change its descriptions and links. Each project key has a corresponding lantern location in `SPOTS` in `main.js`.

## Deploy

Publish this directory on any static host. All local assets use relative paths, so the world works at a domain root or a project subpath such as `/the-bay/`.

For GitHub Pages, choose **Settings → Pages → Deploy from a branch → main → / (root)**. No build command is needed; `.nojekyll` keeps the files served as plain static assets.

## Origin

Extracted from the `world/` directory in [Prit36/Prit36.github.io](https://github.com/Prit36/Prit36.github.io), retaining its three original development commits and authorship. The standalone project owns its favicon, project catalog and navigation; it does not depend on the portfolio's files or deployment.
