# Three.js Content — Interactive 3D for the Web

Use this skill when Zeesh asks for anything 3D in the browser: a 3D scene, product viewer, 3D hero section for a website, an interactive 3D page, a simple 3D game or animation "Three.js se". Deliverable is always a **single self-contained HTML file** (plus model/texture files only when the scene truly needs them) that opens in any modern browser — no build step, no server required beyond a static host.

A working starter is in this folder: `starter-template.html` — copy it and build on it instead of starting from a blank page.

## Stack rules (never deviate without a reason)

- **Three.js via ES modules + import map**, pinned version, from a public CDN:
  ```html
  <script type="importmap">
  {"imports": {
    "three": "https://unpkg.com/three@0.160.0/build/three.module.js",
    "three/addons/": "https://unpkg.com/three@0.160.0/examples/jsm/"
  }}
  </script>
  <script type="module"> import * as THREE from 'three'; ... </script>
  ```
- Renderer: `antialias: true`, `renderer.outputColorSpace = THREE.SRGBColorSpace`, `renderer.toneMapping = THREE.ACESFilmicToneMapping`, shadows `PCFSoftShadowMap`.
- Realistic light without HDR files: `scene.environment = pmrem.fromScene(new RoomEnvironment()).texture` (from `three/addons/environments/RoomEnvironment.js`) + one directional key light with shadows.
- Camera: PerspectiveCamera 45–60° FOV. Controls: `OrbitControls` from `three/addons/controls/OrbitControls.js` with damping ON.
- Animation: `THREE.Clock` delta-based loop via `renderer.setAnimationLoop`. Never `setInterval` for motion.
- Resize handler is mandatory. `renderer.setPixelRatio(Math.min(devicePixelRatio, 2))` — cap at 2 for performance.

## The build workflow

1. **Decide the scene in one line** before coding: what the user sees, what moves, what they can click/drag. If it can't be said in one line, simplify until it can.
2. **Copy `starter-template.html`** and replace the demo objects with the real scene.
3. **Build in layers:** ground/environment → main subject → secondary props → lights → camera moves → interaction → UI overlay (HTML/CSS on top of the canvas, never 3D text for UI).
4. **Models:** prefer primitives + materials for stylized scenes. For realistic objects, load `.glb` with `GLTFLoader` (`three/addons/loaders/GLTFLoader.js`); keep models under ~5MB, textures under 2048px.
5. **Verify before delivering:** open the file, confirm the scene renders (no black canvas), controls respond, no console errors, and it survives a window resize. A black screen is a failed delivery — the usual causes are a wrong import path, a CORS-blocked model, or an exception before the first frame; fix the cause, don't ship and hope.

## Scene patterns (pick one, don't invent a new structure each time)

1. **Product viewer** — one product centered, soft studio environment, auto-rotate until the user drags, color/variant buttons swap material colors. For shops and demos.
2. **3D hero section** — a slow-moving object/scene behind or beside the page headline; pointer parallax (camera eases toward the mouse). Light enough to never block the page.
3. **Explainer scene** — labeled parts; clicking a part highlights it (emissive pulse) and shows an HTML info card. The web cousin of a mechanism cutaway.
4. **Walkthrough diorama** — a small room/garden/building model, OrbitControls with distance limits, hotspots as numbered sprites.
5. **Particle/field background** — points field or floating shapes, subtle motion, used as a living background. Cap particle counts (≤20k points) for phones.

## Interaction rules

- Raycaster for clicks/hovers on meshes; store interactive meshes in one array.
- Hover = cursor pointer + slight emissive highlight. Click = the action (info card, camera move, color change).
- Camera moves are eased (lerp toward a target in the animation loop), never teleport cuts — unless a cut is the point.
- Touch must work: OrbitControls handles it; test tap targets are the meshes themselves, keep them big enough.

## Performance rules (phones are the audience)

- Total draw calls under ~100; merge static geometry or use `InstancedMesh` for repeated objects (trees, stars, bricks).
- No per-frame allocations in the loop (reuse Vector3/Quaternion temporaries).
- Shadows: one shadow-casting light only, shadow map 1024 or 2048, tight shadow camera bounds.
- If FPS is a concern, offer a quality toggle (pixelRatio 1 / shadows off) rather than silently degrading.

## Styling the page around the canvas

- Canvas fills its container; UI is HTML/CSS absolutely positioned over it (title, buttons, info card) using the page's own fonts and colors.
- Loading state: a simple "Loading…" overlay removed on the first rendered frame; model loads report progress via the loader callbacks.
- Dark scenes read better with a subtle vignette and one accent color; match Zeesh's site palette when the scene belongs to a site (e.g. Zeexy, Patch & Plant, DimeWise).

## Common failures and fixes

| Symptom | Cause | Fix |
|---|---|---|
| Black canvas, no error | Script exception before first frame, or module failed to load | Check console; verify import map URLs; wrap init in try/catch and show the error in the overlay during development |
| Model invisible | Wrong scale/position, or normals/lighting | Center with Box3, scale to a known size, add environment light |
| Model black | No environment/ambient light | Add RoomEnvironment or hemisphere light |
| Washed-out colors | Double tone mapping / wrong color space | sRGB output + ACES as above; set texture `colorSpace = SRGBColorSpace` |
| Stutter on phone | Pixel ratio too high, too many draw calls | Cap pixelRatio at 2 (or 1.5), instance repeats, shrink shadow map |
| OrbitControls import fails | Addons path not mapped | Import map must include the `three/addons/` entry exactly |

## Deliverable checklist

- Single HTML file (models/textures listed separately only if used), opens from a static host or local server.
- Scene renders on first load, controls + interaction work, resize-safe, no console errors.
- Mobile-checked: pixel ratio capped, touch orbit works, UI overlay doesn't cover the subject.
- Tell Zeesh in one line what the scene does and how to interact with it.
