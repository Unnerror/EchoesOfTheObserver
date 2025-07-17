# Day 17 Log – July 16, 2025

## Tasks Completed
- Debugged double player spawn issue:
  - Initially observed two characters spawning during PIE: one floating in air, the other half-submerged.
  - Identified that the second character was auto-spawned by default settings.
  - Resolved the issue by disabling “Auto Possess Player” in the project settings to prevent duplicate spawning.
- Collision debugging for Player Start:
  - Confirmed that PlayerStart capsule was placed correctly above a walkable Box Collision volume.
  - Verified alignment visually, but player still failed to register floor contact.
  - Switched to "Player Collision" view mode to inspect collision channel interaction.
  - Discovered that the custom collision boxes lacked proper "Block" settings for Pawn channel.
  - Adjusted Collision Presets to “BlockAll” and verified correct response in the viewer.
- Setup of cinematic transition and Montreal walkbox:
  - Implemented first successful cinematic demo transition inside the Hillside_Montreal sublevel.
  - Built walkable proxy volumes using multiple box collisions under the player’s starting area to simulate terrain.
  - Verified player smoothly transitions from cinematic control to grounded third-person movement.
- Unexpected laptop shutdown:
  - Experienced sudden shutdown during heavy editor use (Hillside loaded, Chrome with tabs).
  - Observed high post-reboot CPU temps (92°C), suggesting thermal shutdown.
  - Enabled monitoring and verified system stabilized after restart (temps dropped to 68°C).
  - Confirmed external cooling pad was used and power adapter connected; no other high-load apps were running.
- Level composition and scale challenge:
  - Observed large-scale water mesh overwhelming the Montreal city scale.
  - Started initial attempts to align city elements and Earth-scale meshes within one cohesive level structure.
  - Noted mismatch in scale and started planning adjustments for visual harmony.

#Issues Encountered
- Unclear collision feedback: Collision box visually in place but not responding until collision channel manually updated.
- Thermal shutdown: Laptop abruptly powered off due to likely overheating, despite cooling pad.
- Level scale mismatch: Water and city models exist on drastically different scales, requiring thoughtful placement strategy.

# Next Steps
 -Continue building out the Montreal environment with accurate player-scale collision.
 -Start assembling global composition: Earth sphere, city, and atmosphere layers.
 -Implement safety checks for thermal stress during long editor sessions.
- Expand current cinematic transition to include fade effects and lighting shifts.