## Day 25 Log – July 28, 2025

# Tasks Completed
- Light Grouping Optimization:
  - Created an empty actor container for bridge lights to organize and control them collectively in Sequencer.
  - Verified manual toggle visibility works for the parent actor in Outliner.
  - Investigated parent visibility in Sequencer — discovered it doesn’t propagate to children, requiring Blueprint or visibility track per mesh.
- Niagara Fog Debugging:
  - Added Niagara fog opacity parameter to Sequencer.
  - Confirmed correct binding via Dynamic Material Parameters for runtime control.
  - Verified fog fade works correctly during play.
- Camera Viewport Setup:
  - Configured CineCamera as default viewport camera on level load using Level Blueprint.
  - Linked to Player Controller to ensure cinematic perspective consistency.

# Issues Encountered
- Parent actor visibility in Sequencer not affecting child meshes.
- Temporary mismatch between Niagara parameter in editor vs runtime requiring manual refresh.

# Next Steps
- Blueprint solution for toggling all child actors’ visibility.
- Prepare lighting folders for Sequencer to reduce manual track management.