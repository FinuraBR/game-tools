## Maximum Graphics

```json
{
  "DFFlagTextureQualityOverrideEnabled": "True",
  "DFIntTextureQualityOverride": "3",
  "FIntDebugForceMSAASamples": "4",
  "DFIntDebugFRMQualityLevelOverride": "21",
  "DFIntCSGLevelOfDetailSwitchingDistance": "1000",
  "DFIntCSGLevelOfDetailSwitchingDistanceL12": "1000",
  "DFIntCSGLevelOfDetailSwitchingDistanceL23": "1000",
  "DFIntCSGLevelOfDetailSwitchingDistanceL34": "1000",
  "FIntFRMMaxGrassDistance": "1000",
  "FIntFRMMinGrassDistance": "1000",
  "DFFlagDisableDPIScale": "True",
  "DFIntDebugDynamicRenderKiloPixels": "8300",
  "FFlagDebugGraphicsPreferD3D11": "True",
  "FIntGrassMovementReducedMotionFactor": "0"
}
```

---

## Maximum Performance

```json
{
  "DFFlagTextureQualityOverrideEnabled": "True",
  "DFIntTextureQualityOverride": "0",
  "FIntDebugForceMSAASamples": "0",
  "DFIntDebugFRMQualityLevelOverride": "1",
  "DFIntCSGLevelOfDetailSwitchingDistance": "0",
  "DFIntCSGLevelOfDetailSwitchingDistanceL12": "0",
  "DFIntCSGLevelOfDetailSwitchingDistanceL23": "0",
  "DFIntCSGLevelOfDetailSwitchingDistanceL34": "0",
  "FIntFRMMaxGrassDistance": "0",
  "FIntFRMMinGrassDistance": "0",
  "FIntGrassMovementReducedMotionFactor": "100",
  "DFIntDebugDynamicRenderKiloPixels": "1000",
  "DFFlagDebugPauseVoxelizer": "True",
  "FFlagDebugSkyGray": "True"
}
```

---

## Explanation of Options Used

### Texture Overrides
*   **`DFFlagTextureQualityOverrideEnabled`**
    *   Controls whether the engine obeys manual texture settings or dynamically streams and compresses them based on system memory.
*   **`DFIntTextureQualityOverride`**
    *   Determines the target resolution tier for the texture streaming system, regulating how sharp or compressed game assets appear [1].

### Anti-Aliasing (Edge Smoothing)
*   **`FIntDebugForceMSAASamples`**
    *   Configures the sample rate for Multi-Sample Anti-Aliasing (MSAA), which is the technique used to smooth out jagged "staircase" lines on the edges of 3D geometry.

### Internal Quality Override
*   **`DFIntDebugFRMQualityLevelOverride`**
    *   Directly dictates the engine's internal Feature Rendering Manager (FRM) quality tier (on a scale of 1 to 21). This overrides the standard in-game slider to lock engine parameters like shadow resolution, shader complexity, and water fidelity.

### Geometry Level of Detail (LOD)
*   **`DFIntCSGLevelOfDetailSwitchingDistance`** (and L12, L23, L34)
    *   Determines the distance thresholds (measured in studs) at which complex 3D Constructive Solid Geometry (CSG unions) switch to lower-polygon detail levels to conserve system resources [1.1.2].

### Environment & Foliage
*   **`FIntFRMMaxGrassDistance` & `FIntFRMMinGrassDistance`**
    *   Sets the minimum and maximum distance boundaries (in studs) for rendering dynamic 3D terrain grass around the player's camera.
*   **`FIntGrassMovementReducedMotionFactor`**
    *   Scales the wind-sway physics and movement intensity of dynamic terrain grass [1]. Higher values reduce the physical motion, while a zero value allows full wind simulation [1].

### Display & Resolution Scaling
*   **`DFIntDebugDynamicRenderKiloPixels`**
    *   Directly controls the internal rendering resolution of the 3D viewport in "kilopixels" [1.1.8]. This acts as a manual resolution scale multiplier, allowing you to downsample for performance or supersample for extreme image clarity [1.1.8].
*   **`DFFlagDisableDPIScale`**
    *   Bypasses the automatic downscaling behavior triggered by Windows High-DPI Display Scaling on high-resolution monitors, forcing native, pixel-for-pixel rendering [1].

---

### Graphics API Selection
*   **`FFlagDebugGraphicsPreferD3D11`**
    *   Instructs the Roblox client to prioritize the Microsoft Direct3D 11 (DirectX 11) rendering API as its primary graphics backend.

---

### Debug & Optimization Overrides
*   **`DFFlagDebugPauseVoxelizer`**
    *   Freezes/pauses real-time updates to the voxel lighting grid and dynamic ambient occlusion updates [1.1.6].
*   **`FFlagDebugSkyGray`**
    *   Disables the rendering of skyboxes, clouds, atmospheric fog, and dome textures, replacing the background with a flat, solid gray color [1.1.1].
