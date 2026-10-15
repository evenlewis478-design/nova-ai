# Nova Core Gun Model Viewer (v2.6.8)

A single-page browser tool for viewing, editing and animating FPS gun models
(OBJ, FBX, GLB, or zips containing them).

## Run it

Open `index.html` in a modern browser, or host the folder with any static host
(GitHub Pages works). The page loads Three.js, JSZip and related loaders from
CDNs, so the browser needs internet access.

## Features

- 3D viewer with orbit controls, animated recoil, magazine and bolt animations
- Shooter check (geometry, UV, material and degenerate-face validation)
- Live animated camo presets and theme skins
- Attachments (muzzle, grip, stock, sight, scope) with position and rotation controls
- Scope styles and zoom, muzzle flash, casings and tracers
- Per-action sound uploads (fire, reload, silencer) and live background media
- Rebindable Shoot / Reload / Aim controls
- AI Studio: describe changes to a gun and the AI edits it, with a self-review pass and undo
- AI Maker: three built-in AIs (Forge, Sentinel, Muse) plus your own, each with
  rules, knowledge notes, video teaching, backups and an optional Claude model per AI
- Developer panel: theme settings, health check, error log and shooter check
- Library stored in the browser (IndexedDB), so guns persist between visits

## About the AI features

The AI Studio and AI Maker replies call Claude through the Claude artifact runtime
(`window.claude.use('sample')`). They only work when the page is opened as a
published Claude artifact and access is allowed. On GitHub Pages or any other
plain host, the AI replies show a message saying so, and everything else still works.

Wiring the AI to a direct API key would mean changing `callClaude`-style calls
in the script to call the Anthropic API from your own backend. Do not put an API
key in this file.

## Files

- `index.html`: the whole application (HTML, CSS and JavaScript in one file)
- `README.md`: this file
