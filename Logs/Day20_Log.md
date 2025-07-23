## Day 20 Log – July 21, 2025

# Tasks Completed
- Volumetric Cloud Altitude Adjustment:
  - Explored how to lower volumetric clouds closer to planet surface.
  - Tweaked material altitude bias, cloud layer height, and shape falloff.
  - Noted that volumetric clouds are designed to simulate atmosphere-scale distances, so extreme downscaling leads to artifacts.
- Planet Surface Integration:
  - Ensured that the volumetric cloud layer follows the curvature of the large-scale planet.
  - Investigated alternative approaches including custom Niagara-based fog domes.
- Lighting and Fog Interaction:
  - Experimented with Exponential Height Fog and Volumetric Fog settings.
  - Validated that Niagara fog effects can be blended with traditional fog for transitions.
- Batch Visibility Control in Sequencer:
  - Explored ways to hide multiple actors simultaneously without adding each to the Sequencer track individually.
  - Considered Blueprint grouping or folder-level visibility control.

# Issues Encountered
- Volumetric clouds behave poorly when scaled too low.
- Some actors still had visible fog artifacts depending on material settings and lighting interaction.

# Next Steps
- Finalize cloud and fog composition for launch-to-space moment.
- Polish batch visibility toggling for scene preparation.