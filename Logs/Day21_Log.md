## Day 21 Log – July 22, 2025

#Tasks Completed
- Volumetric Cloud Adjustment (Continued):
  - Refined cloud material properties and spatial placement to enhance visual fidelity during altitude transitions.
  - Worked on dissipation and vertical noise functions to simulate gradual thinning of atmosphere.
- Niagara Fog Shell for Planet Atmosphere:
  - Built a Niagara system shaped as a massive spherical shell to simulate fog layers around the planet (planet radius ~8,020,000 units).
  - Tuned emitter particle size and distribution to wrap around the planet at orbital view distances.
  - Investigated issues with particles disappearing when the camera moves far or turns away from the emitter.
- Fixed Bounds Configuration (In Progress):
  - Enabled Fixed Bounds at the Niagara System level with manually defined bounds of ±100 million units.
  - Added a Set Fixed Bounds module to the emitter update script, using the same large AABB values.
  - Confirmed that Local Space was disabled and Calculate Bounds Mode was set to Fixed.
  - Despite this, fog particles still vanish from view at distance — bounds setup appears ineffective so far.
- Material Visibility & Blending:
  - Resolved rendering issues where particles using Translucent blend appeared black and Additive mode yielded invisible results.
  - Final material now uses Emissive + Additive with masked alpha to maintain visibility and soft atmospheric glow.
- Distance Cull Debugging:
  - Tested r.ViewDistanceScale at extreme values (e.g., 1000000 and 0) — no observable effect in editor viewport.
  - Investigated culling mechanisms via component bounds, LOD behavior, or Niagara scalability — fog still disappears at long distance.
- Memory Sequence Camera Work:
  - Aligned actor transforms and retargeted root-motion animations to sync precisely with cinematic camera movement.
  - Built a “floating memory” visual effect by blending world-positioned actor animation with manual location keyframes in Sequencer.

# Issues Encountered
- Niagara fog shell particles continue to disappear at distance, even with maximum bounds and culling overrides applied.
- Bounding box debug tools are limited — could not visually confirm whether bounds were respected in runtime rendering.
- Some particle flickering still occurs when rotating or moving the camera — likely due to aggressive frustum or distance culling.
- Could not test Disable Depth Test option in material — checkbox remains grayed out in current setup.

# Next Steps
- Finalize Niagara-based atmosphere visibility from orbital camera perspectives.
- Investigate additional rendering flags or debug overlays to confirm particle culling behavior.
- Possibly introduce a secondary bounding mesh or forced bounding render module for testing.
- Add sky/cloud atmosphere for the planet when viewed from space — final step to complete transition sequence.