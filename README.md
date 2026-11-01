# XCAT-3

Project webpage for **XCAT-3: A Comprehensive Library of Personalized Digital Twins Derived from CT Scans**.

Live at: [https://xcat-3.github.io](https://xcat-3.github.io)

## Features

- **Phantoms tab** — Title page with authors, affiliations and links (paper, code, phantom requests); abstract; video overview; an interactive 3D anatomy viewer with sex / race / BMI / age filtering over 2,500+ computational phantoms derived from real CT scans; a phantom-diversity figure; and a copyable BibTeX entry.
- **4D Motion tab** — Respiratory motion explorer. Pick one of five chest phantom cases (`XCAT3_Chest_00001`–`00005`) and one of nine breathing patterns (quiet resting, normal tidal, chest dominant, diaphragm dominant, deep full, maximum effort, and the pathological shallow restricted, restrictive and COPD-like patterns). Three precomputed animated views (full anatomy, pulmonary vessels, rib cage) update together; click a view to open it full size.

## Repository layout

| Path | Purpose |
| --- | --- |
| `index.html` | The page: markup and the small motion-explorer / copy-button script. |
| `static/css/xcat.css` | Page theme (design tokens at the top: colours, type, widths). |
| `webapp.html`, `assets/` | The bundled 3D viewer, embedded as an iframe. `assets/` is build output; do not edit by hand. |
| `static/css/webapp-theme.css` | Restyles the viewer's controls to match the page without touching the bundle. |
| `static/phantoms/`, `static/draco/` | Phantom meshes (`.glb`), their index (`database.json`) and the Draco decoder. |
| `gifs/<case>/<pattern>/` | `full_anatomy_animation.gif`, `pulmonary_tubes_animation.gif`, `ribs_animation.gif` for each case and pattern. |
| `static/svg/` | Phantom-diversity figure. |

## Run locally

The viewer loads assets with absolute paths, so serve the repository root:

```
python3 -m http.server 8000
```

Then open <http://localhost:8000/> (the motion tab is at `/#motion`).

## Design

Editorial academic styling: off-white page, charcoal text, a single navy accent, Source Serif 4 for headings and Inter for text and controls. No framework or build step; the page is plain HTML and CSS.

## Paper

Dahal, L. et al. *XCAT 3.0: A comprehensive library of personalized digital twins derived from CT scans.* Medical Image Analysis, 2025.
[https://doi.org/10.1016/j.media.2025.103636](https://doi.org/10.1016/j.media.2025.103636)

## Contact

Lavsen Dahal | Duke University · Center for Virtual Imaging Trials
