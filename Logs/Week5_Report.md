# Week 5 Report – July 21–25, 2025

Project: UE5 game "Echoes of the Observer"
Total Hours: 39
Student: Danila Sergienko

## Summary of Work
- Successfully created a layered planet system using concentric spheres:
  - Earth surface
  - Cloud layer
  - Cloud shadows
  - Outer atmosphere
- Resolved critical flickering issues between layers by assigning correct Translucency Sort Priority.
- Adjusted materials to use Emissive-only shading, enabling full visibility from space without scene lighting.
- Identified that Exponential Height Fog was occluding the outer layers — removed or disabled fog for space scenes.\
- Created a large Niagara-based spherical fog shell (~8 million units) to simulate atmosphere.

- Tuned particle bounds, system bounds, and material properties to retain visibility at orbital scale.
- Debugged persistent opacity loss in fog system:
  - Ensured opacity parameter (NUI-opacity) passed through correctly to material.
  - Confirmed that Sequencer control of float parameter required Set Niagara Variable (Float) track added through the component itself.
  - Built debug materials and dynamic material parameter bindings for visual confirmation.

- Finalized cinematic “Memory Sequence” featuring:
  - A character with emissive materials jumping from a concrete rooftop.
  - Red and blue lights flickering on a brutalist structure.
- Prepared Jacques Cartier Bridge environment for the first gameplay scene:
  - Imported assets from Hillside sample.
  - Added stylized red and blue lighting setup using hundreds of rectangular lights.

## Skills & Tools Practiced
- Multi-layered translucent material setup (with translucency sorting)
- Niagara system debugging and parameter animation via Sequencer
- Emissive shading workflows for unlit environments
- Level-based cinematic lighting setup using custom bridges and light rigs
- Sequencer + Blueprint integration for float parameter animation
- Debugging visibility and render-order issues in orbital-scale environments

## Issues Resolved
- Fixed flickering caused by overlapping translucent materials using Sort Priority
- Solved visibility issues caused by Exponential Height Fog
- Resolved problem of Niagara parameters not updating in Sequencer due to missing context and track setup
- Verified particle culling at large scale and ensured visual consistency from orbit

## Next Steps
- Finalize opacity behavior of fog during cinematic playback
- Continue cinematic layout for Montreal scene (bridge + character movement)
- Polish transitions between planetary orbit and memory/environment scenes
- Begin work on spaceship interior or orbital transition mechanics if time permits