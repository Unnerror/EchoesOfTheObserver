## Day 24 Log – July 25, 2025

# Tasks Completed
- Fog Parameter Reactivity Finalized:
  - Implemented a workaround by exposing NUI-opacity1 as a user parameter in a Niagara Dynamic Material Parameter module.
  - Confirmed keyframes now propagate properly when using the Niagara Component track, not the system track.
  - Sequencer now smoothly transitions fog opacity between 0 and 1 over defined timeline range.
- Bridge Cinematic Polish:
  - Refined red/blue light timing on bridge — added random flicker behavior and adjusted emissive boost for cinematic impact.
  - Animated camera flythrough with subtle roll and tilt matching city glow curvature.
  - Replaced old camera rig with CineCameraActor and adjusted FOV/DOF for final render.
- Memory Scene FX Additions:
  - Added flash emission upon jump moment with burst fog ring.
  - Improved emissive shader with fresnel edge glow based on view angle.
  - Timed flicker and reflection of lights in nearby glass during flight sequence.

# Issues Encountered
- Camera cuts caused Niagara reinitialization — particles would reset mid-sequence.
- Had to re-sequence some events in “Memory Scene” timeline to avoid particle pops.
- Slight shadow flicker near bridge cables due to overlapping light volumes.

# Next Steps
- Lock camera animation for export sequence.
- Begin prep for Act I to Act II transition.
- Investigate LOD culling and bounds enforcement for final orbital fog pass.