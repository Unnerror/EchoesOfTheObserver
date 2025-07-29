## Day 23 Log – July 24, 2025

# Tasks Completed
- Niagara Opacity Control Fixes:
  - Diagnosed broken float keyframe propagation in Sequencer.
  - Discovered that “Set Niagara Variable (Float)” didn’t appear due to context mismatch, resolved by selecting the Niagara Component explicitly before adding the track.
  - Manually added a new float variable via blueprint and verified in system emitter that values were passed correctly.
 - Material Parameter Debugging:
  - Traced NUI-opacity through Niagara to material — ensured binding was set to Dynamic Material Parameter.
  - Updated material to include debug emissive override — visually confirmed that opacity changes worked via external blueprint but not through Sequencer alone.
- Scene Validation Pass:
  - Tweaked cloud fog shell material and particle LODs to stay visible at high altitudes.
  - Confirmed that disabling Exponential Height Fog resolved invisible particle issue from space view.
  - Cleaned up scene-level lighting and disabled unused fog volumes to avoid rendering conflicts.

# Issues Encountered
- Niagara emitter parameter change not respected during runtime playback.
- Depth fade values caused unintended opacity spikes when camera moved too close.
- Editor viewport sometimes didn’t reflect true opacity until level reloaded.

# Next Steps
- Refactor fog system to respond to parameter updates during timeline playback.
- Attempt indirect control using dynamic material instance inside level blueprint.