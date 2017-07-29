---
title: Writing vertex and fragment shaders
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Writing vertex and fragment shaders
date: 2017-07-10 14:24:00
---

___

[网址：Writing vertex and fragment shaders](https://docs.unity3d.com/Manual/SL-ShaderPrograms.html)

# HLSL snippets
- #pragma vertex name - compile function name as the vertex shader.
- #pragma fragment name - compile function name as the fragment shader.
- #pragma geometry name - compile function name as DX10 geometry shader. Having this option automatically turns on - #pragma target 4.0, described below.
- #pragma hull name - compile function name as DX11 hull shader. Having this option automatically turns on - #pragma target 5.0, described below.
- #pragma domain name - compile function name as DX11 domain shader. Having this option automatically turns on #pragma target 5.0, described below.

- #pragma target name - which shader target to compile to. See Shader Compilation Targets page for details.
- #pragma only_renderers space separated names - compile shader only for given renderers. By default shaders are compiled for all renderers. See Renderers below for details.
- #pragma exclude_renderers space separated names - do not compile shader for given renderers. By default shaders are compiled for all renderers. See Renderers below for details.
- #pragma multi_compile … - for working with multiple shader variants.
- #pragma enable_d3d11_debug_symbols - generate debug information for shaders compiled for DirectX 11, this will allow you to debug shaders via Visual Studio 2012 (or higher) Graphics debugger.
- #pragma hardware_tier_variants renderer name - generate multiple shader hardware variants of each compiled shader, for each hardware tier that could run the selected renderer. See Renderers below for details.

# Rendering platforms
- d3d9 - Direct3D 9
- d3d11 - Direct3D 11/12
- glcore - OpenGL 3.x/4.x
- gles - OpenGL ES 2.0
- gles3 - OpenGL ES 3.x
- metal - iOS/Mac Metal
- vulkan - Vulkan
- d3d11_9x - Direct3D 11 9.x feature level, as commonly used on WSA platforms
- xboxone - Xbox One
- ps4 - PlayStation 4
- psp2 - PlayStation Vita
- n3ds - Nintendo 3DS
- wiiu - Nintendo Wii U

___