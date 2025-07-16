## Day 16 Log – July 15, 2025

#Tasks Completed
- Finalized vehicle movement and spline system:
  - Identified root cause of runtime crash: missing FollowSplineComponent and Chaos Vehicle Plugin disabled.
  - Enabled Chaos Vehicle Plugin, reloaded project, and verified that vehicles now move properly at runtime.
  - Used “Get Components by Class” to dynamically assign FollowSplineComponent and resolved previous compile error.
- Debugged and restored Hillside traffic system:
  - Investigated Set Throttle node errors; traced issue to missing vehicle movement component.
  - Re-migrated vehicle BPs and verified dependencies.
  - Tracked Set Throttle origin and verified no compilation errors in original Hillside sample.
- Built clean streaming hierarchy:
  - Created persistent MainLevel with only Level Blueprint and triggers, no meshes.
  - Added Hillside_Exterior and Space as sublevels.
  - Resolved problem with Hillside’s nested sublevels not auto-loading when added as a sublevel.
  - Understood that only direct sublevels are streamed; nested sublevels in a sublevel aren’t automatically included.
- Organized actor placement and level structure:
  - Faced issue where actors were placed into sublevels (e.g., Lighting) even when locked.
  - Learned to unlock the persistent level and lock all others to enforce correct placement.
  - Used invisible Box Collision volumes to provide ground surface where Hillside assets lack collision.
Managed streaming settings:
  - Discovered that “Streaming Method” dropdown was grayed out due to level being locked.
  - Unlocked sublevel in Levels window to enable streaming method selection.
  - Set appropriate loading method per sublevel.

#Issues Encountered

- Crash due to FollowSplineComponent compilation error:
  - Caused by missing component reference and Chaos Vehicle Plugin being disabled.
- Inability to place actors in persistent level:
  - Actors kept snapping into sublevels due to incorrect level locking and visibility states.
- Streaming method option unavailable:
  - Locked level prevented settings from being edited until manually unlocked.

#Next Steps
- Optimize level streaming logic: trigger Space and Hillside load/unload via gameplay.
- Add ground proxy collision volumes to key walkable areas.
- Begin structuring logic for lighting transitions and nested level streaming scenarios.
- Investigate performance difference between packaged game and Play-in-Editor for streamed levels.
- Start profiling memory and streaming time on packaged build.