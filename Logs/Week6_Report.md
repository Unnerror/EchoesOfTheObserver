# Week 6 Report – July 28–August 1, 2025

Project: UE5 game "Echoes of the Observer"
Total Hours: 40
Student: Danila Sergienko

## Summary of Work
- Completed StJaque2 master sequence combining:
  - Jacques Cartier Bridge flythrough with traffic generator.
  - Cinematic lighting with synchronized red/blue flickering rigs.
  - City building shots with custom FOV adjustments.
  - BioSphere transition enhanced by Niagara fog blending.
- Added automated level transition from StJaque2 to Mission 1 using Blueprint logic.
- Gameplay Loop Implementation
  - Implemented interactive key pickup (E to interact).
  - Created boat boarding mechanic with fog-heavy cinematic leading to BioSphere.
  - Established seamless transition from cinematics to ThirdPersonCharacter_NUI gameplay.
  - Integrated ragdoll death system with delayed return to main menu.
- Lighting & Optimization
  - Grouped large numbers of lights under parent actors for Sequencer-driven visibility control.
  - Refined fog opacity behavior using Niagara parameters animated in Sequencer.
  - Polished scene performance to minimize hitches during level transitions.
- Mission 1 Setup
  - Positioned player spawn near Cirque du Soleil.
  - Prepared Mission 1 gameplay environment for initial testing.

## Skills & Tools Practiced
- Sequencer-driven level transitions and Blueprint event handling.
- Niagara fog control with parameter animation.
- Advanced light grouping for bulk control in cinematics.
- Ragdoll physics setup with velocity-based death triggers.
- Level streaming alternatives via visibility toggling and scene optimization.
- UE5 cinematic workflow: multi-sequence chaining, FOV tuning, and camera blending.

## Issues Resolved
- Fixed duplicate character spawn and ensured proper possession of ThirdPersonCharacter_NUI.
- Resolved Niagara opacity desynchronization after level load.
- Addressed performance hitches during level transition by preloading critical assets.
- Eliminated visibility inconsistencies when managing large groups of lights in Sequencer.

## Next Steps
- Polish Mission 1 gameplay loop (interaction prompts, cinematic pacing).
- Refine Niagara fog blending for planet-view sequences.
- Begin sound integration using MetaSounds for environmental and cinematic effects.
- Continue improving transition timing between cinematics and gameplay to achieve a seamless experience.