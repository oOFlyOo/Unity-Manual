---
title: Built-in shader include files
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Writing vertex and fragment shaders
 - Built-in shader include files
date: 2017-07-10 15:16:11
---

___

[网址：Built-in shader include files](https://docs.unity3d.com/Manual/SL-BuiltinIncludes.html)

# Built-in shader include files
- HLSLSupport.cginc - (automatically included) Helper macros and definitions for cross-platform shader compilation.
- UnityShaderVariables.cginc - (automatically included) Commonly used global variables.
- UnityCG.cginc - commonly used helper functions.
- AutoLight.cginc - lighting & shadowing functionality, e.g. surface shaders use this file internally.
- Lighting.cginc - standard surface shader lighting models; automatically included when you’re writing surface shaders.
- TerrainEngine.cginc - helper functions for Terrain & Vegetation shaders.

UnityCG.cginc
## Data structures in UnityCG.cginc
- struct appdata_base: vertex shader input with position, normal, one texture coordinate.
- struct appdata_tan: vertex shader input with position, normal, tangent, one texture coordinate.
- struct appdata_full: vertex shader input with position, normal, tangent, vertex color and two texture coordinates.
- struct appdata_img: vertex shader input with position and one texture coordinate.

___