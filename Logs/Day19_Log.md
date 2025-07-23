## Day 19 Log – July 18, 2025

# Tasks Completed
- Sublevel Streaming Trigger via Sequencer:
  - Created BP_LevelStreamer Blueprint actor with functionality to load and unload streamed levels using Load Stream Level and Unload Stream Level nodes.
  - Successfully triggered level loading/unloading via keyframes in Sequencer.
- Material Opacity Debugging (NUI-opacity):
  - Investigated if changes to Niagara material parameter NUI-opacity were visible in editor (without hitting Play).
  - Found that parameter updates are not reflected live in editor viewport unless sequencer is actively simulating or scrubbing.
  - Confirmed that NUI-opacity animates correctly during Sequencer playback.
- Level Visibility in Sequencer:
  - Observed that toggling level visibility via Level Visibility track in Sequencer hides the level both in the viewport and in World Outliner.
  - Identified this as intended behavior to fully unload levels visually and structurally during sequence playback.

# Issues Encountered
- Material parameter animation is not visually updated in editor while idle; previewing requires scrubbing or playback.
- Confusion over whether level hiding removes it from the world or only from render—clarified by World Outliner behavior.

# Next Steps
- Create better visual indicators for streamed level transitions.
- Proceed to space fog layer design (cloud blending during transition).