# Test3d — Enclosed Car Hauler Studio

Interactive 3D studio presentation of an enclosed car-hauler trailer, built with
[three.js](https://threejs.org/) and [GSAP](https://gsap.com/).

**Live demo:** https://developerscompany.github.io/Test3d/

## Features

- **Studio scene** — gradient backdrop, three-point lighting, soft contact shadows
  and PBR environment reflections.
- **Cinematic camera** — GSAP-driven intro sweep and a continuous 360° orbit. Drag to
  inspect (orbit pauses), release to resume.
- **Open & unload** — one button swings the rear doors open, the camera flies to the
  rear, and the coupe drives out down to the ground. Press again to load it back in.
- **Branding** — placeholder `VELOCITY` wordmark applied as a decal on the body and
  the rear door (swap in a real logo by replacing the canvas generator).

## Pages

- `index.html` — the trailer studio (above).
- `spline.html` — a Spline scene (`box.spline`) rendered with `@splinetool/runtime`,
  with studio key/fill/rim lights added on top of the scene via three.js, controllable
  with live sliders. Live: https://developerscompany.github.io/Test3d/spline.html

## Run locally

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Structure

```
index.html        # the whole app (three.js + GSAP via CDN import map)
assets/
  trailer.fbx     # trailer model (VRay materials rebuilt as PBR by name)
  map/            # trailer textures (Metal, Tire2)
  car/            # coupe OBJ + texture
```

## Notes

- The trailer FBX ships VRay materials that three's `FBXLoader` can't translate, so
  materials are rebuilt as PBR by name at load time.
- The car's original FBX is v6100 (unsupported), so the OBJ version is used.
- The rear doors are built geometry — the model itself has no separate door mesh.
