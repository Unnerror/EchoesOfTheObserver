## Day 22 Log – July 23, 2025

# Tasks Completed
- Memory Scene Implementation:
  - Assembled and animated the “Memory Scene” sequence: a girl with emissive material idling on a rooftop, then jumping and flying through windows.
  - Synced animation timing with dynamic red and blue light flicker to enhance emotional tension.
  - Emissive material layered with dynamic glow and camera depth fade.
  - Added particle FX trail during the jump, bound to root motion via Attach Component.
- Jacques Cartier Bridge Scene Setup:
  - Imported hillside environment assets and constructed a replica of the bridge with detailed light posts and cables.
  - Created hundreds of rectangular lights, alternating red and blue — and arranged them along the bridge.
  - Configured all light intensities, flicker intervals, and attenuation radii for stylized nighttime mood.
- Niagara Fog Sequencer Binding – Phase 1:
  - Set up a new Niagara system actor for sequencer-driven cloud opacity control.
  - Added “NUI-opacity1” user parameter to Niagara system and confirmed material binding.
  - Began investigating why Sequencer tracks weren’t modifying opacity values at runtime.

# Issues Encountered
- Niagara variable NUI-opacity1 appears in Sequencer but has no visual impact on fog.
- Suspect emitter update doesn’t react to float value changes during playback.
- Could not locate “Set Niagara Variable (Float)” track as expected — missing in add-track options.

# Next Steps
- Confirm user parameter propagation in Niagara through Print to Log.
- Test opacity modulation via blueprint override as a workaround.
- Finalize bridge scene lighting animation for initial cinematic flythrough.