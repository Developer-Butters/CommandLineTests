# Town banner detector screenshots

These 16 original 1920×1080 frames are from the stopped OBS recording `2026-11-07 21-21-37.mp4`. They are unchanged extracts, including the recorded overlays. `manifest.json` gives the source path, timestamp in seconds, and expected result for each file.

- `_True.png`: the entire location banner is visible in its settled top-left position.
- `_False.png`: no settled banner. This includes deliberately negative entering/leaving animation frames, ordinary overworld scenes and a battle.
- A Repel dialogue can coexist with a positive banner. Presence does not identify the displayed town or prove the player can move.

Canonical test location: `CommandLineTests/PokemonBDSP/TownBannerDetector/`. The corresponding cases are registered in `PokemonBDSP_Tests.cpp` and run at 1920×1080, 1280×720 and 960×540. This workspace folder retains a reviewable copy.

Validation: 16 registered image tests passed against the rebuilt library. A separate battery passed 1,632 image/profile/resolution combinations (16 images × 34 profiles × 3 resolutions), plus three uniform-frame rejection checks. Profiles include brightness, gamma, saturation, hue, channel offsets up to ±90, and red/blue 255-to-160 gain. Transformed images were generated in memory; originals are preserved here.

Coverage is from two Floaroma entries on one capture setup. Other town/route names, independent capture cards, menus, and other white panels still need held-out screenshot coverage before broader deployment. These files are detector fixtures, not live verification of the revised movement.
