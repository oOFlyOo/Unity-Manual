---
title: GPU instancing
category:
 - Graphics
 - Graphics Overview
 - Advanced Rendering Features
 - GPU instancing
date: 2017-07-03 11:06:49
---

___

[GPU instancing](https://docs.unity3d.com/Manual/GPUInstancing.html)

# Introduction
- 选多同一个 mesh 多次在同一时刻，牺牲一点 draw call
- 虽然是渲染同一个 mesh，但是可以有不同的参数

# Adding instancing to your Materials
## GPU Instancing is available on the following platforms and APIs:
- DirectX 11 and DirectX 12 on Windows
- OpenGL Core 4.1+/ES3.0+ on Windows, macOS, Linux, iOS and Android
- Metal on macOS and iOS
- Vulkan on Windows and Android
- PlayStation 4 and Xbox One
- WebGL (requires WebGL 2.0 API)

# Advanced GPU instancing tips
## Batching priority
- 优先顺序：静态合并 -》GPU Instancing -》动态合并

## UnityObjectToClipPos
- 这玩意效率更高，比起自己写转换

# Further notes
- For Graphics.DrawMeshInstanced, you need to enable GPU Instancing on the Material that is being passed into this method. However, Graphics.DrawMeshInstancedIndirect does not require you to enable GPU Instancing. The indirect instancing keyword PROCEDURAL_INSTANCING_ON is not affected by stripping.
- Instanced draw calls appear in the Frame Debugger as Draw Mesh (instanced).
- When using forward rendering, Unity cannot efficiently instance objects that are affected by multiple lights. Only the base pass can make effective use of instancing, not the added passes. For more information about lighting passes, see documentation on Forward Rendering and Pass Tags
- Objects that use lightmaps, or are affected by different light or Reflection Probes, can’t be instanced.
- If you have more than two passes for multi-pass Shaders, only the first passes can be instanced. This is because Unity forces the later passes to be rendered together for each object, forcing Material changes.

___