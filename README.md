# YOS / after hours

Personal retro portfolio and AFTERLIGHT, an original ASCII browser game.

Static HTML, CSS and JavaScript. English, Polish and Russian interfaces; responsive controls for desktop and mobile.

## Local preview

Run `python -m http.server 8080 --directory dist` and open http://localhost:8080.

Only website assets are included. Server configuration, credentials, deployment backups and working documents are excluded. Project screenshots use synthetic demo data or a disconnected local interface.

## AFTERLIGHT / the lantern keeper

An original Canvas 2D adventure with a layered forest, a wandering swordsman, lantern checkpoints and six shadow enemies. The camera follows from a fixed angle; ASCII details are woven into the artwork. No engine, external packages, runtime downloads, analytics or game API.

- Physical WASD and arrows to move, including Cyrillic keyboard layouts.
- Hold Space or the mouse button to strike; Shift to dash, hold Q to guard, E to pulse. Early guards parry.
- Touch joystick and four thumb buttons; EN / PL / RU interfaces.
- Collect three lanterns and return to the gate. Lanterns save a checkpoint and restore health.
- Rendering capped at 45 fps on desktop and 30 on coarse-pointer devices. Eco mode caps at 30 / 24 fps and lowers pixel density. Hidden and paused games stop scheduling animation frames.
- Terrain and forest sprites are generated and cached once. Effects and rendering resolution are bounded. The server serves static assets only.

Regression checks use Node's built-in modules and a mock canvas to exercise the real input and simulation code:

```sh
node tests/game-input.cjs
node tests/game-journey.cjs
```

Browser checks additionally cover visuals, responsive controls and actual rendering. The simulation checks cover physical Cyrillic input, missing key codes, combat, lantern collection, the ending and paused/hidden animation shutdown.
