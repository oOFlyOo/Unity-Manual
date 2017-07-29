---
title: Performance tips when writing shaders
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Advanced ShaderLab topics
 - Performance tips when writing shaders
date: 2017-07-20 10:16:34
---

___

[网址：Performance tips when writing shaders](https://docs.unity3d.com/Manual/SL-ShaderPerformance.html)

# Optimized Surface Shaders
- The approxview directive for shaders that use view direction (i.e. Specular) makes the view direction normalized per vertex instead of per pixel. This is approximate, but often good enough.
- The halfasview for Specular shader types is even faster. The half-vector (halfway between lighting direction and view vector) is computed and normalized per vertex, and the lighting function receives the half-vector as a parameter instead of the view vector.
- noforwardadd makes a shader fully support one-directional light in Forward rendering only. The rest of the lights can still have an effect as per-vertex lights or spherical harmonics. This is great to make your shader smaller and make sure it always renders in one pass, even with multiple lights present.
- noambient disables ambient lighting and spherical harmonics lights on a shader. This can make performance slightly faster.

# Precision of computations
- For world space positions and texture coordinates, use float precision.
- For everything else (vectors, HDR colors, etc.), start with half precision. Increase only if necessary.
- For very simple operations on texture data, use fixed precision.
- PC 一般都是仅使用 float 的
- Mobile 一般都是仅使用 half 的
- 除了老显卡会支持使用 fixed，大部分都是直接使用 half

# Alpha Testing
- However, on PowerVR GPUs found in iOS and some Android devices, alpha testing is resource-intensive. Do not try to use it for performance optimization on these platforms, as it causes the game to run slower than usual.

# Color Mask
- On some platforms (mostly mobile GPUs found in iOS and Android devices), using ColorMask to leave out some channels (e.g. ColorMask RGB) can be resource-intensive, so only use it if really necessary.

___