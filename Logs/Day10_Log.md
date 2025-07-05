## Day 10 Log – July 4, 2025

# Tasks Completed
- Migrated Cassini Earth project into main Unreal Engine project environment.
- Created test level titled EarthScaleTest to prototype large-scale flyable environment.
- Imported and placed accurately scaled Earth sphere model using data from the Cassini mission.
- Positioned Montreal downtown (hillside view) on the surface of the Earth sphere to serve as starting point.
- Rotated Earth mesh to align real-world orientation so camera fly-out path follows Earth's curvature naturally.
- Imported satellite textures from NASA into materials.
- Started setup for tiling ultra-high-resolution 54000x27000 texture, split into 8 square tiles (a1–d2), using Texture Coordinate nodes and custom UVs.
- Captured current Earth material and UV test setup screenshots for debugging and reference (screenshots: PlanetMat.png and PlanetLook.png).

# Issues Encountered
- Unreal Engine caps Maximum Texture Size at 16384x16384, even with Virtual Texture settings raised and streaming disabled.
- Despite setting Auto Virtual Texturing Size = 54000 and Auto Resize Large Textures = 0, UE5 limits runtime texture resolution to 16384x8192.
- Required switching to multi-tile layout approach to retain ultra-HD fidelity (ongoing).
- Minor delay in tiling logic due to needing manual UV assignments and material tiling structure (to continue tomorrow).

# Next Steps
- Finalize UV tiling logic and implement multi-texture material setup for Earth surface (a1–d2 grid).
- Test visual quality at various camera distances to validate that resolution holds up during space-to-ground transitions.
- Blended day and night satellite textures from NASA into a combined material using UV logic and time/lighting masking.
- Configured Material Graph to dynamically switch between daytime and nighttime views based on lighting direction.
- Explore adding atmospheric scattering or glow around Earth for enhanced visual realism during fly-out.
