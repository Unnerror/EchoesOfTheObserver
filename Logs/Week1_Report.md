# Week 1 Report – June 23–27, 2025

Project: UE5 game "Echoes of the Observer"
Total Hours: 40
Student: Danila Sergienko

## Summary of Work
Core Systems Implemented
- Typing Detection System:
  - Tracked input speed in real-time using timestamp arrays.
  - Created a normalized TypingSpeed variable (0–1 scale) using MapRangeClamped.
  - Replaced Event Tick with optimized timer-based polling for idle detection.
  - Implemented fade-out animation when typing stops.

- UI & Feedback Systems:
  - Built a dynamic Typing Speedometer: rotating needle and radial fill controlled via Blueprint.
  - Created “good tempo” detection logic (typing speed between 0.4–0.6 keys/sec).
  - Animated a green overlay when typing stays in the target tempo range using timelines and scalar material parameters.

- Interaction System (Key & Door):
  - Added logic for picking up a key via trigger volumes.
  - Used blueprint variables to unlock specific doors only if the key has been collected.
  - HUD prompts appear near interactive objects: “Press E to Interact”.
  - Integrated subtitle system for narrative feedback and locked door messaging.

- Demo: Week1.mp4

## Skills & Tools Practiced
- Unreal Engine 5 Blueprint scripting
- Material parameter manipulation for UI animation
- Timeline control and optimization using timers
- Modular logic design: clean separation of UI, input, and gameplay flows
- Event dispatchers and conditional branching
- Git & version control (tracked project-relevant assets, maintained logs)

## Issues Resolved
- Needle & progress fill conflict (resolved via execution flow separation).
- Speed reset logic: ensured stability when typing intermittently.
- Prevented array overflow or reuse after typing pause.
- Fixed clamping/smoothing for consistent UI response.

## Next Steps
- Implement placeholder visuals for level transition sequences.
- Build logic bridges between cutscenes and gameplay.
- Create an end-to-end playable loop with temporary assets.
- Polish UI transitions with Lerp/smoothing and modular function flow.