# Day 5 Log – June 27, 2025

## Tasks Completed
- Refactored typing detection logic to avoid using Event Tick; implemented a SetTimerByFunctionName system checking every second for typing inactivity.
- Created CheckTypingInactivity function: compares LastKeyTimestamp to current time and triggers FadeOutTimeline if typing has paused for over 0.5 seconds.
- Improved UI logic by clamping TypingSpeed range (0–1) using MapRangeClamped node instead of Clamp Float, allowing better scaling sensitivity.
- Adjusted progress fill behavior to only grow when speed is within the “good tempo” range (0.4–0.6), using In Range (Inclusive) node.
- Configured separate execution paths for TypingSpeed tracking and ProgressTimeline triggering using custom events (OnGoodTempoEnter, OnGoodTempoExit).
- Verified material behavior: radial fill grows correctly while in tempo zone, and resets when exiting zone or pausing typing.
- Reorganized Blueprint: moved progress and speed logic into separate lanes to prevent cross-triggering issues (UI_KeyToNote graph cleanup).
- Added key pickup functionality.
- Implemented unlocking of a specific door using the found key.
- Created HUD prompts (“Press E to interact”) when overlapping trigger boxes for key and door.
- Added subtitles: first story subtitle on overlap, followed by “Press E” prompt; If door is locked, show specific subtitle: “Door is locked – find the key.”

## Issues Fixed
- Resolved UI bug where connecting scalar updates to both needle and progress would freeze updates, fixed by isolating execution flow per feature.
- Addressed timeline logic not triggering on slow typing by adding proper fallback condition when TypingSpeed drops below 0.4.
- Ensured timestamp array resets cleanly only after sustained inactivity, not on sporadic key delays.

## Next Steps
- Implement placeholder visuals for all level sequence videos.
- Build game logic between level sequences.
- Create a full game loop from start to finish using temporary assets to validate core progression.