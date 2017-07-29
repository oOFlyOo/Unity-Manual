---
title: 'ShaderLab: Pass Tags'
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - ShaderLab Syntax
 - ShaderLab SubShader
 - ShaderLab Pass
 - ShaderLab Pass Tags
date: 2017-07-11 17:50:57
---

___

[网址：ShaderLab: Pass Tags](https://docs.unity3d.com/Manual/SL-PassTags.html)

# Details
## LightMode tag
- Always: Always rendered; no lighting is applied.
- ForwardBase: Used in Forward rendering, ambient, main directional light, vertex/SH lights and lightmaps are applied.
- ForwardAdd: Used in Forward rendering; additive per-pixel lights are applied, one pass per light.
- Deferred: Used in Deferred Shading; renders g-buffer.
- ShadowCaster: Renders object depth into the shadowmap or a depth texture.
- MotionVectors: Used to calculate per-object motion vectors.

## PassFlags tag
- OnlyDirectional: When used in ForwardBase pass type, this flag makes it so that only the main directional light and ambient/lightprobe data is passed into the shader. This means that data of non-important lights is not passed into vertex-light or spherical harmonics shader variables. See Forward rendering for details.

## RequireOptions tag
- SoftVegetation: Render this pass only if Soft Vegetation is on in Quality Settings.


___