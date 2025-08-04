## Day 26 Log – July 29, 2025

# Tasks Completed
- Visibility Management via Tags:
  - Tested using actor tags in Blueprints to toggle visibility for grouped objects.
  - Implemented tag-based visibility event to simplify mass-light control in Sequencer.
- Character Spawning Debug:
  - Fixed dual-spawn issue caused by auto-spawn + Level Blueprint spawn.
  - Reconfigured GameMode to rely solely on BP_ThirdPersonCharacter_NUI with input possession.
- Niagara Parameter Sequencing:
  - Confirmed proper fog transition curve in Sequencer.
  - Adjusted fog density curve for smoother transition during camera flythrough.

# Issues Encountered
- Sequencer track for Set Niagara Variable (Float) not initially appearing — solved by binding Niagara Component instead of System.
- Minor input delay after character possession, resolved by ensuring controller handoff in Level Blueprint.

# Next Steps
- Organize level lighting into tagged groups for simplified cinematic control.
- Continue refining fog and light blending during transitions.