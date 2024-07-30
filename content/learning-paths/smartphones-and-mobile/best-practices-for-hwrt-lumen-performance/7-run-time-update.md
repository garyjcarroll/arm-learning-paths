---
title: Reduce Acceleration Structure Run-time Update Cost
weight: 8

### FIXED, DO NOT MODIFY
layout: learningpathall
---

The acceleration structure for static meshes is built offline and does not require updates at run-time. However, the acceleration structure for skinned meshes needs to be updated at run-time, which incurs a performance cost due to the need to update geometry data on the GPU and rebuild the acceleration structure. When the polygon count of a skinned mesh is high, the update cost can be too high for real-time applications. To reduce this cost, you can use a higher LOD (Level of Detail) level for skinned meshes in ray tracing, resulting in fewer polygons needing updates at run-time.

![Figure 1. Select higher LOD for ray tracing in Unreal editor.](images/skin-lod.png)

It is important to note that using a higher LOD level for skinned meshes in ray tracing may cause self-shadowing artifacts if ray tracing shadows are enabled. These artifacts are caused by differences between the rendering mesh and the ray tracing mesh.

![Figure 2. The black areas are the self-shadowing artifacts generated by using different LODs for rendering and ray tracing shadows.](images/skin-lod-error.png)