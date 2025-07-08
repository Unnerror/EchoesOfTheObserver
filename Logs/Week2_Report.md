# Week 2 Report – June 30 – July 4, 2025

Project: UE5 game "Echoes of the Observer"
Total Hours: 40
Student: Danila Sergienko

## Summary of Work
- Earth Environment Integration
  - Imported the Cassini Earth model and migrated it into the main project.
  - Set up a new level, EarthScaleTest, as a prototyping space for Earth-to-space cinematic transitions.
  - Oriented and scaled the Earth mesh for accurate curvature-based camera motion.
  - Positioned Montreal’s hillside as a takeoff point and aligned camera trajectory with global curvature.
- Texture & Material R&D (High-Resolution Earth Surface)
  - Investigated multi-part texture system to represent ultra-HD Earth (54k x 27k texture).
  - Created 8-tile material setup (each tile 13.5k x 13.5k).
  - Attempted both:
    - Hardcoded UV-based material routing using nested If nodes with tile index logic.
    - Runtime tiled blending using local UVs and conditional branching.
  - Explored Unreal’s Virtual Texture system to bypass the 16k texture cap.
  - Analyzed UV offsets, calculated tile indices and experimented with coordinate math for tiling.
- Fly-Out Sequence Setup
  - Planned and prototyped a three-stage space transition:
  - Launch from hillside at night.
  - Transition through volumetric fog into NASA's satellite plane (13.5k texture).
  - Fade into a sphere textured with full Earth VT (16k x 8k).

## Skills & Tools Practiced
- Runtime UV logic in UE5 Materials
- Virtual Texture importing and limitations
- Material scripting using nested If chains and dynamic material inputs
- Large-scale material debugging
- Scene sequencing for cinematic camera travel

## Issues Resolved
- Virtual Texturing import behavior clarified: only activates VT on textures >16k.
- Fixed SM6 compile errors from incomplete If node inputs (A > B, A < B).
- UV preview mismatch resolved by isolating active tile region per texture.

## Next Steps
- Finalize camera motion path through fog and between layers.
- Add atmospheric glow and Earth rim lighting for realism.
- Try to implement third mechanic (spaceship driving)
- Refine texture-switching material based on Z-height or fog density.
- Finalize an end-to-end playable loop with temporary assets.