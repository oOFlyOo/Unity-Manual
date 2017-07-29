---
title: Platform-specific rendering differences
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Advanced ShaderLab topics
 - Platform-specific rendering differences
date: 2017-07-20 17:23:55
---

___

[网址：Platform-specific rendering differences](https://docs.unity3d.com/Manual/SL-PlatformDifferences.html)

# Render Texture coordinates
Vertical Texture coordinate conventions differ between two types of platforms: Direct3D-like and OpenGL-like.
- Direct3D-like: The coordinate is 0 at the top and increases downward. This applies to Direct3D, Metal and consoles.
- OpenGL-like: The coordinate is 0 at the bottom and increases upward. This applies to OpenGL and OpenGL ES.
Unity 会统一使用 OpenGL
特别注意使用的地方：
- Render Texture
- Image Effects
- UV Space

## Image Effects
## Rendering in UV space

# Clip space coordinates
Similar to Texture coordinates, the clip space coordinates (also known as post-projection space coordinates) differ between Direct3D-like and OpenGL-like platforms:
- Direct3D-like: The clip space depth goes from 0.0 at the near plane to +1.0 at the far plane. This applies to Direct3D, Metal and consoles.
- OpenGL-like: The clip space depth goes from –1.0 at the near plane to +1.0 at the far plane. This applies to OpenGL and OpenGL ES.

# Precision of Shader computations
PC GPUs treat all floating point types (float, half and fixed) as the same - they do all calculations using full 32-bit precision, while many mobile device GPUs do not do this.

# Const declarations in Shaders
- Microsoft’s HLSL const has much the same meaning as it does in C# and C++ in that the variable declared is read-only within its scope but can be initialized in any way.
- OpenGL’s GLSL const means that the variable is effectively a compile time constant, and so it must be initialized with compile time constraints (either literal values or calculations on other consts).

# Semantics used by Shaders
- Vertex Shader output (clip space) position: SV_POSITION. Sometimes Shaders use POSITION semantics to get Shaders working on all platforms. Note that this does not not work on Sony PS4 or with tessellation.
- Fragment Shader output color: SV_Target. Sometimes Shaders use COLOR or COLOR0 to get Shaders working on all platforms. Note that this does not work on Sony PS4.

# Direct3D Shader compiler syntax
# DirectX 11 (DX11) HLSL syntax in Shaders
# Using Shader framebuffer fetch
# The Depth (Z) direction in Shaders

___