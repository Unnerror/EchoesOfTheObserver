## Day 11 Log – July 7, 2025

# Tasks Completed
- Attempted to build a material using 8 separate 13.5k x 13.5k tiles to recreate a 54k x 27k NASA image.
- Created textures Tile_0_0 to Tile_1_3, and implemented If node chain using TileIndex and OffsetUV logic.
- Tested full material setup with runtime logic to route Base Color per tile — preview rendered black.
- Explored virtual texture workflow (VT enabled), but Unreal treated even 54k images as 16k max.
- Investigated alternate logic (per-tile UV ranges with normalization), but node complexity increased rapidly.
- Pivoted to cinematic solution:
  - Takeoff from hillside (/Media/hillsideView.png)
  - Enter fog with square plane (13.5k texture) (/Media/planeView.png)
  - Exit fog to full Earth sphere (16k texture) (/Media/sphereView.png)

# Issues Encountered
- Unreal texture size limit (16k max) made it impossible to fully use 54k images — even with virtual textures.
- Final material logic (using 8 tiled samples) rendered black, likely due to incorrect If chain or UV misalignment.
- No clear online reference or tutorial found — few or no working examples for this tiling technique in Unreal.

# Next Steps
- Finalize level sequence logic and camera animation: from hillside → fog → plane → sphere.
- Implement fog-triggered visibility toggles for plane and sphere layers.
- Test a 4-tile setup or consider level streaming for LOD transition instead of full 54k textures.
















