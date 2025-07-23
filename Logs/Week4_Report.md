# Week 4 Report – July 14–18, 2025

# Summary of Work
- Montreal-to-Space Scene Refinement:
  - Completed structural planning for Montreal-to-Space transition by integrating both locations into a single persistent level.
  - Abandoned level streaming for this sequence due to instability and lack of reliability across shots.
  - Used visibility tracks in Sequencer to toggle grouped actors ("Montreal" / "Planet") for smooth transitions instead.
  - Ensured no glitches occur during level transition by preloading all elements in one unified level.
- Sky and Atmosphere Design:
  - Began implementing planetary sky-atmosphere system using Niagara and material-based fog shells.
  - Investigated how to emulate a realistic blue sky layer around a planet visible from orbit.
  - Started tuning cloud altitudes, planet scale adjustments, and atmosphere transition logic.
- Level Visibility & Streaming System:
  - Created a BP_LevelStreamer actor using Load Stream Level / Unload Stream Level nodes.
  - Successfully tested streamed level loading/unloading in Sequencer, with full integration into keyframes.
  - Verified that Level Visibility tracks fully hide the level in both the viewport and World Outliner.
  - Material Parameter Animation
  - Debugged Niagara user parameter animation (NUI-opacity) and confirmed visibility changes only appear during active simulation or scrubbing.
  - Validated animation playback for fog opacity based on animated float parameters during sequence.
- Volumetric Fog Layer (Niagara Fog Shell):
  - Created Niagara emitter to generate a massive spherical fog shell around the planet (~8 million units in scale).
  - Tuned bounds, emission rate, and material transparency to produce soft visual atmosphere effect.
  - Investigated particle visibility loss when moving the camera far from origin — determined fixed bounds and culling were factors.

# Skills & Tools Practiced
- Niagara System configuration for large-scale effects
- Material animation debugging in Sequencer
- Blueprint-based level streaming
- Sequencer visibility control and organizational structuring
- Fog, atmosphere, and cloud transition design for cinematic sequences

# Issues Resolved
- Sequencer could not visually update Niagara material changes in-editor; resolved via scrubbing/workflow understanding.
- Replaced unreliable level streaming with a unified level setup and visibility toggling.
- Clarified engine behavior of Level Visibility (also removes from World Outliner).
- Improved transition visuals by embedding cloud and fog logic into static levels rather than relying on streaming volumes.

# Next Steps
- Finalize visual shell around planet (sky atmosphere and volumetric clouds visible from space).
- Debug Niagara particle culling — particularly for extreme-scale systems.
- Continue prep for rendering Montreal-to-Space cinematic with finished sky, cloud, and fog visuals.
- Begin development of stylized spaceship scene logic, following completion of environmental transition.