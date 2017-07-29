---
title: Shader Compilation Target Levels
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Writing vertex and fragment shaders
 - Shader Compilation Target Levels
date: 2017-07-11 10:18:46
---

___

[网址：Shader Compilation Target Levels](https://docs.unity3d.com/Manual/SL-ShaderCompileTargets.html)

# Default compilation target
- Unity 默认使用2.5
- 使用 geometry 会导致使用4.0
- 使用 hull 或者 domain 会导致使用4.6

# Supported #pragma target names
- Note that all OpenGL-like platforms (including mobile) are treated as “capable of shader model 3.0”. WP8/WinRT platforms (DX11 feature level 9.x) are treated as only capable of shader model 2.5.

## #pragma target 2.0
- Works on all platforms supported by Unity. DX9 shader model 2.0.
- Limited amount of arithmetic & texture instructions; 8 interpolators; no vertex texture sampling; no derivatives in fragment shaders; no explicit LOD texture sampling.

## #pragma target 2.5 (default)
- Almost the same as 3.0 target (see below), except still only has 8 interpolators, and does not have explicit LOD texture sampling.
- Compiles into SM3.0 on DX9, and DX11 feature level 9.3 on Windows Phone.

## #pragma target 3.0
- DX9 shader model 3.0: derivative instructions, texture LOD sampling, 10 interpolators, more math/texture instructions allowed.
- Not supported on DX11 feature level 9.x GPUs (e.g. most Windows Phone devices).
- Might not be fully supported by some OpenGL ES 2.0 devices, depending on driver extensions present and features used.

## #pragma target 3.5 (or es3.0)
- OpenGL ES 3.0 capabilities (DX10 SM4.0 on D3D platforms, just without geometry shaders).
- Not supported on DX9, DX11 9.x (WinPhone), OpenGL ES 2.0.
- Supported on DX11+, OpenGL 3.2+, OpenGL ES 3+, Metal, Vulkan, PS4/XB1 consoles.
- Native integer operations in shaders, texture arrays, etc.

## #pragma target 4.0
- DX11 shader model 4.0.
- Not supported on DX9, DX11 9.x (WinPhone), OpenGL ES 2.0/3.0/3.1, Metal.
- Supported on DX11+, OpenGL 3.2+, OpenGL ES 3.1+AEP, Vulkan, PS4/XB1 consoles.
- Has geometry shaders and everything that es3.0 target has.

## #pragma target 4.5 (or es3.1)
- OpenGL ES 3.1 capabilities (DX11 SM5.0 on D3D platforms, just without tessellation shaders).
- Not supported on DX9, DX11 before SM5.0, OpenGL before 4.3 (i.e. Mac), OpenGL ES 2.0/3.0.
- Supported on DX11+ SM5.0, OpenGL 4.3+, OpenGL ES 3.1, Metal, Vulkan, PS4/XB1 consoles.
- Has compute shaders, random access texture writes, atomics etc. No geometry or tessellation shaders.

## #pragma target 4.6 (or gl4.1)
- OpenGL 4.1 capabilities (DX11 SM5.0 on D3D platforms, just without compute shaders). This is basically the highest OpenGL level supported by Macs.
- Not supported on DX9, DX11 before SM5.0, OpenGL before 4.1, OpenGL ES 2.0/3.0/3.1, Metal.
- Supported on DX11+ SM5.0, OpenGL 4.1+, OpenGL ES 3.1+AEP, PS4/XB1 consoles.

## #pragma target 5.0
- DX11 shader model 5.0.
- Not supported on DX9, DX11 before SM5.0, OpenGL before 4.3 (i.e. Mac), OpenGL ES 2.0/3.0/3.1, Metal.
- Supported on DX11+ SM5.0, OpenGL 4.3+, OpenGL ES 3.1+AEP, Vulkan, PS4/XB1 consoles.
- Note that all OpenGL-like platforms (including mobile) are treated as “capable of shader model 3.0”. WP8/WinRT platforms (DX11 feature level 9.x) are treated as only capable of shader model 2.5.

___