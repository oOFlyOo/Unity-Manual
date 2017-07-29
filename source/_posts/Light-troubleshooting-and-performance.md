---
title: Light troubleshooting and performance
category:
 - Graphics
 - Graphics Overview
 - Lighting
 - Global Illumination
 - Light troubleshooting and performance
date: 2017-07-06 11:48:14
---

___

[Light troubleshooting and performance](https://docs.unity3d.com/Manual/LightPerformance.html)

# Shadow performance
- 软阴影比起硬阴影，会更多的影响 GPU，CPU 消耗是相同的

# How the size of a shadow map is calculated
- 点光源比起其它光源更限制贴图大小，是因为使用了立方体贴图阴影，必须同时载入6张图

# Troubleshooting shadows
- 如果发现没有阴影可以根据以下去查
1. 旧显卡可能不支持阴影
2. Quality Settings 可以关闭阴影
3. Mesh Renderers 是否开启了接收和投射阴影
4. 仅有不透明物体接受和投射阴影
5. 自定义 shader 必须使用几何队列，并且是像素光照
6. VertexLit Shader （顶点光照 Shader）可以投射阴影，但是不能接受阴影
7. 使用前向渲染，一些 shader 只允许最亮的光投射阴影；使用延迟渲染或者使用支持 fullforwardshadows 的表面着色器

# Hardware support for shadows
- Built-in shadows work on almost all devices supported by Unity. The following cards are supported on each platform

## PC (Windows/Mac/Linux)
- Generally all GPUs support shadows. Exceptions might occur in some really old GPUs (for example, Intel GPUs made in 2005).

## Mobile
- iPhone 4 does not support shadows. All later models starting with iPhone 4S and iPad 2 support shadows.
- Android: Requires Android 4.0 or later, and GL_OES_depth_texture support. Most notably, some Android Tegra 2/3-based Android devices do not have this, so they don’t support shadows.
- Windows Phone: Shadows are only supported on DX11-class GPUs (Adreno 4xx/5xx).

___