---
title: Using Depth Textures
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Advanced ShaderLab topics
 - Using Depth Textures
date: 2017-07-20 11:32:55
---

___

[网址：Using Depth Textures](https://docs.unity3d.com/Manual/SL-DepthTextures.html)

# Using Depth Textures
Depth Textures are supported on most modern hardware and graphics APIs. Special requirements are listed below:
- Direct3D 11+ (Windows), OpenGL 3+ (Mac/Linux), OpenGL ES 3.0+ (Android/iOS), Metal (iOS) and consoles like PS4/Xbox One all support depth textures.
- Direct3D 9 (Windows) requires a graphics driver to support “INTZ” texture format to get depth textures.
- OpenGL ES 2.0 (iOS/Android) requires GL_OES_depth_texture extension to be present.
- WebGL requires WEBGL_depth_texture extension.

# Depth Texture Shader helper macros
- UNITY_TRANSFER_DEPTH(o): computes eye space depth of the vertex and outputs it in o (which must be a float2). Use it in a vertex program when rendering into a depth texture. On platforms with native depth textures this macro does nothing at all, because Z buffer value is rendered implicitly.
- UNITY_OUTPUT_DEPTH(i): returns eye space depth from i (which must be a float2). Use it in a fragment program when rendering into a depth texture. On platforms with native depth textures this macro always returns zero, because Z buffer value is rendered implicitly.
- COMPUTE_EYEDEPTH(i): computes eye space depth of the vertex and outputs it in o. Use it in a vertex program when not rendering into a depth texture.
- DECODE_EYEDEPTH(i)/LinearEyeDepth(i): given high precision value from depth texture i, returns corresponding eye space depth.
- Linear01Depth(i): given high precision value from depth texture i, returns corresponding linear depth in range between 0 and 1.


___