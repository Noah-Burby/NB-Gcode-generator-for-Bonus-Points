# Image → G-code Static Web App

This is a client-side static web page that converts an image into raster-style G-code suitable for a laser cutter or a pen plotter, and previews the toolpaths.

Features
- Load an image (PNG, JPG, SVG).
- Configure physical width, DPI, feed rate, line spacing, and laser/pen parameters.
- Generate G-code (M3/M5 for laser with S power, or pen up/down via Z moves).
- Preview approximate toolpaths superimposed on the image.
- Download the G-code as a .gcode file.

Usage (local)
1. Add the files in this repository:
   - `index.html`
   - `script.js`
   - `style.css`
   - `README.md`
   - `sample-output.svg`

2. Open `index.html` in a modern browser (Chrome, Firefox, Edge). No server needed.

3. Click "Use Sample Image" or load your own image. Adjust settings and click "Generate G-code". Use "Download G-code" to save.

Notes and safety
- The generated G-code is a reasonable starting point but may not match your machine controller exactly. Some controllers expect different commands for laser power (e.g., `M106/M107` or different S ranges) or different coordinate origin conventions.
- Test on a safe material or in a simulator before running on a real machine.
- You may need to adapt header/footer commands to match your controller (GRBL, Marlin, Smoothieware, etc.).
- This tool does raster engraving (scanlines). It is not intended for optimized vector tracing of shapes.

Tips
- For laser on GRBL, ensure your GRBL supports laser mode or map M3/M5 + S values as needed. For Marlin, S power ranges and M3 semantics may differ.
- Adjust DPI and width to match desired physical resolution.
- For pen plotters, set Z up/down and test pen throw before running.

Further improvements
- Add presets for common controllers.
- Add vector tracing option (SVG/edge tracing) for cut paths.
- Support acceleration-aware motion planning or dwell optimization.

License
- Place any license you prefer in the repo.