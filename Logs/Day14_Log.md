## Day 14 Log – July 10, 2025

#Tasks Completed
- Completed full prototype of the core game loop:
  - Starts with Sequence 1, guiding player to find and collect a hidden key on the map.
  - Upon key pickup, a platform activates and transitions to Sequence 2 (space).
- Implemented smooth camera transitions:
  - Between player and cinematic cameras using Set View Target with Blend.
  - Transition from cinematic to player control in space with correct character positioning.
- Built full typing + sound mechanic:
  - Once player enters trigger volume, character freezes and keyboard inputs switch to note-playing mode.
  - Each key press plays a musical note.
  - Typing rate is tracked to calculate BPM in real time.
  - BPM value drives both visual typing speedometer needle and audio pitch shift in Metasound.
- Finalized Metasound ↔ Blueprint BPM logic:
  - Blueprint calculates BPM and sends it to Metasound.
  - Metasound shifts pitch and compensates with delay pitch shift (to retain original key).
- Implemented word detection + speed check:
  - Player must type the word LOVE in correct order.
  - Each correct letter increases progression bar.
  - If typed at correct pace (matching 110 BPM), green progress grows.
  - When progress fills, it begins pulsating and triggers 5-second timer.
  - Holding the correct speed/word for 5 seconds results in success.
- Success triggers smooth camera transition to Sequence 3:
  - Character is hidden, repositioned, then shown from new angle as camera blends back in.
  - Character walks through a corridor and enters the final trigger to start the last cinematic.

#Issues Encountered
- Logic for resetting progression on incorrect letter input:
  - Solved by validating expected index and current key match before advancing.
  - Incorrect sequence resets the index to 0 without breaking other logic.
- BPM synchronization challenges:
  - Real-time BPM fluctuations caused pitch instability.
  - Stabilized using delay compensation in Metasound and clamped mapping in Blueprint.

# Next Steps
- Polish visual feedback: enhance speedometer UI, glow effects, and camera shakes for feedback.
- Integrate optional mission element: Added object that, if mistakenly picked up, triggers character death for challenge variation.
- Add fail state cinematic when wrong object is picked.
- Fine-tune transitions between sequences to ensure smoothness.
- Replace placeholder assets and notes with final content for typing sound design.