# Three.js X-Wing Viewer

An interactive Three.js scene that loads and displays an X-Wing GLTF model in the browser. The page uses OrbitControls for camera movement, a spotlight and ground plane for shadows, and a small loading overlay while the model assets are fetched.

Live demo: <https://boyuantian.github.io/threejs-xwing-lasttry.github.io/>

## Features

- Browser-based 3D X-Wing model viewer
- Three.js loaded through an import map from the unpkg CDN
- GLTF model loading with `GLTFLoader`
- Mouse/touch camera orbiting with `OrbitControls`
- Responsive full-window WebGL canvas
- Soft shadows, spotlighting, and a simple presentation floor
- Custom Star-Wars-inspired display font

## Project Structure

```text
.
|-- index.html              # Main HTML page and Three.js import map
|-- main.js                 # Three.js scene, camera, controls, lights, and model loading
|-- xwings/                 # Source GLTF model, binary data, textures, and model license
|-- dist/                   # GitHub Pages deployment files
|   `-- public/
|       |-- index.css       # Page styling
|       |-- fonts/          # Custom font asset
|       `-- xwings/         # Deployed copy of model assets
|-- package.json            # Deployment dependency and npm scripts
`-- LICENSE                 # Project license
```

## Getting Started

Because the app loads ES modules and GLTF assets in the browser, run it from a local web server instead of opening `index.html` directly.

Using Python:

```bash
python3 -m http.server 8080
```

Then open:

```text
http://localhost:8080
```

The app imports Three.js from the unpkg CDN, so an internet connection is required unless you change the imports to local files.

## Deployment

This repository includes `gh-pages` as a deployment dependency.

Install dependencies:

```bash
npm install
```

Publish the `dist` directory to GitHub Pages:

```bash
npm run deploy
```

The current deployment target serves the files from `dist`.

## Controls

- Drag to orbit around the model
- Scroll or pinch to zoom
- Panning is disabled
- Zoom distance is limited to keep the X-Wing framed

## Asset Credits

The 3D model is based on:

"X- Wings" by perceval-66 on Sketchfab: <https://sketchfab.com/3d-models/x-wings-5dc24fdbc09544df9388890bab2434ad>

Model license: CC BY 4.0. See [`xwings/license.txt`](xwings/license.txt) for the full attribution text.

## License

This project is licensed under the MIT License. See [`LICENSE`](LICENSE) for details.
