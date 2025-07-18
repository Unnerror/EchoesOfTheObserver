## Day 18 Log – July 17, 2025

# Tasks Completed
- User Parameter Opacity Control (Niagara):
  - Successfully implemented a user parameter named NUI-opacity to dynamically control particle opacity inside a Niagara system.
  - Exposed this parameter through the User Parameters tab and linked it to a Scalar Parameter inside the Niagara emitter stack.
  - Verified that the sequencer can animate this opacity parameter over time, enabling fade-in/out behavior during cinematic sequences.
- Debugging Visibility Blocking Issue:
  - Despite setting Niagara material opacity to 0, the particles’ bounding box still occluded the camera view in Cinematic.
  - Tested Deactivate and AutoActivate toggles on NiagaraComponent in Sequencer, but they didn’t fully hide the system.
  - Found success using the Visibility track in Sequencer, which cleanly hides the entire Niagara Actor including its bounds.
- Initial Event Trigger Setup for Sequencer:
  - Created an Events Track in Sequencer and added keyframes to emit calls at specific frame indices.
  - Used Quick Bind to link event endpoints to functions inside the Sequencer Director Blueprint, enabling timeline-based function execution.
  - Confirmed that events fire properly and can affect bound objects via the Director.
- Sublevel Streaming Setup (Partial):
  - Began setting up level streaming triggered by Sequencer events.
  - Linked event keys in Sequencer to custom Blueprint events that will handle Load Stream Level and Unload Stream Level nodes.
  - Verified access to Director Blueprint functions but noted limitation: cannot call Level Blueprint events directly from Sequencer.

# Issues Encountered
- Niagara bounding box occlusion: Material opacity alone is insufficient to fully “hide” Niagara systems in camera shots. Only the Visibility track truly removes rendering obstructions.
- Sequencer Event Binding Limitation: Unable to directly bind Sequencer event keys to Level Blueprint events—only Sequencer Director Blueprint is exposed. Workaround: Route the call through the Director using custom events or cast-to logic to trigger streaming logic in another actor.

# Next Steps
- Finalize the event-driven sublevel streaming system:
  - Refactor level streaming logic into an Actor or Component that can be triggered by Sequencer events.
  - Use Load Stream Level and Unload Stream Level nodes with soft references to sublevels.
- Continue building out cinematic timing:
  - Refine timing and interpolation of the NUI-opacity value for smooth visual transitions.
  - Sequence visibility toggles and level loading to ensure perfect handoff between scenes.
  - Begin implementing final fog toggle and environment fade for launch-to-space sequence.