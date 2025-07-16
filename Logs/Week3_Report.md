# Week 3 Report - July 7–10, 2025

## Summary of Work
- Memory Scene Integration
  - Implemented the first interactive Memory Scene triggered by the “Key-to-Note” input mechanic.
  - Designed a Level Sequence that plays after puzzle completion, showing a symbolic flashback.
  - Controlled cinematic flow by triggering the sequence from the Level Blueprint using a dispatcher.
  - Blended smoothly into the Sequencer camera and returned control to the player via a timeline.
- Player Repositioning & Camera Transition
  - Repositioned the player character at the end of the memory sequence using stored transform values.
  - Used Timeline and Transform Curve for smooth player placement and orientation.
  - Ensured seamless blending back to third-person gameplay camera from Sequencer.
- Cinematic Scene Polish
  - Added visual elements and props to the memory environment to reinforce narrative context.
  - Inserted ambient background sounds and subtle music cues for emotional reinforcement.
  - Fine-tuned actor transforms and matched in-game perspective with editor camera views.
- Blueprint & Event Handling
  - Established dispatcher logic between character blueprint and level blueprint.
  - Cleaned up and organized Blueprint nodes for clarity and reusability.
  - Added delays and logic to avoid conflicts when accessing the player controller.
- Spaceship Scene Setup
  - Added placeholder logic and triggers for spaceship activation.
  - Started logic for recognizing full player input (for triggering launch).
  - Prepped for integration of Earth-to-space transition gameplay.

## Skills & Tools Practiced
- Level Blueprint scripting and event binding
- Use of Level Sequences and camera blending
- Actor control and movement during and after cinematics
- Multicast event dispatchers and runtime actor management
- Sequencer view targeting and blueprint-driven transitions

## Issues Resolved
- Couldn’t bind events from character → level blueprint: solved with BeginPlay bindings
- Sequencer couldn’t reference runtime-spawned actors: resolved by post-sequence reposition logic
- Ensured correct sequencing between camera blend and sequence play

## Next Steps
- Replace placeholder cinematic with polished visuals for the memory
- Begin prototyping the spaceship control mechanic
- Integrate fog and camera effects for Earth-to-space visual transitions
- Improve typing system to support full keyboard and better feedback