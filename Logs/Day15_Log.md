## Day 15 Log – July 14, 2025

# Tasks Completed
- Set up level streaming architecture:
  - Created a persistent main level with Montreal (Hillside-based) and Space as sublevels.
  - Disabled World Partition in Montreal to enable manual level streaming and better runtime control.
  - Assigned streaming method (Always Loaded) and confirmed sublevel loading behavior.
- Resolved lighting visibility issues:
  - Found that SunSky and other environmental actors were hidden due to Lighting Scenario flag.
  - Disabled Lighting Scenario and confirmed visibility in both editor and runtime.
  - Recommended moving lighting to persistent level for consistent control.
- Fixed ground collision problems:
  - Identified missing collision in key meshes (SM_Grass_All, Site_Hardscape_Update, etc.).
  - Used Auto Convex Collision and Player Collision view to validate updates.
  - Discussed use of invisible blocking volumes or proxy meshes for gameplay efficiency.
- Analyzed Hillside traffic system:
  - Confirmed that BP_SimpleTrafficGenerator spawns vehicles and assigns spline/follow component correctly.
  - Identified root cause for static vehicles: parent vehicle Blueprint (BP_Vehicle) has Tick disabled and lacks movement logic.
  - FollowSplineComponent is active but likely not executing Tick or applying actor movement.

# Issues Encountered
- No collision in Montreal meshes:
  - Caused player to fall through world; fixed on a case-by-case basis.
  - Too time-consuming to apply per mesh — alternative strategies needed.
- Spawned traffic vehicles don’t move:
  - Logic fires, splines assigned, but Tick and movement functions not enabled or executed.

#Next Steps
- Enable Tick and BeginPlay in BP_Vehicle and confirm FollowSplineComponent is ticking.
- Add debug prints to monitor spline-follow progress.
- Build a working test vehicle with runtime spline movement.
- Streamline collision setup using blocking volumes or simplified proxies.
- Begin implementing runtime streaming logic between Montreal and Space levels.