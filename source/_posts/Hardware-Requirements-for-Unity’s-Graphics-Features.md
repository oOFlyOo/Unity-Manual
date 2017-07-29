---
title: Hardware Requirements for Unity’s Graphics Features
category:
 - Graphics
 - Graphics Reference
 - Rendering Pipeline Details
 - Hardware Requirements for Unity’s Graphics Features
date: 2017-07-21 16:23:18
---

___

[网址：Hardware Requirements for Unity’s Graphics Features](https://docs.unity3d.com/Manual/RenderTech-HardwareRequirements.html)

# Realtime Shadows
Mobile shadows (iOS/Android) require OpenGL ES 2.0 and GL_OES_depth_texture extension, or OpenGL ES 3.0. Most notably, the extension is not present on Tegra-based Android devices, so shadows do not work there.

___