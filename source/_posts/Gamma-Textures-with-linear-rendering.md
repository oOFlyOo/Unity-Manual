---
title: Gamma Textures with linear rendering
category:
  - Graphics
  - Graphics Overview
  - Lighting
  - Related topics
  - Linear rendering overview
  - Gamma Textures with linear rendering
date: 2017-06-30 18:12:07
---

___

[Gamma Textures with linear rendering](https://docs.unity3d.com/Manual/LinearRendering-GammaTextures.html)

# Lightmapping
- 光照计算是在 linear 下完成的
- 光照贴图存储是 gamma 空间
- linear 模式得转换贴图，gamma 模式不用转换（那为什么切换模式需要重新烘焙？）

## Importing lightmaps
- 光照数据 EXR 文件是在 linear 空间创建的，导入的时候会转成 gamma 空间
- 使用外部光照纹理，纹理标记为 lightmap，这时候 bypass sRGB Sampling 是开启的

# Linear supported platforms
- 如若开启 linear 不支持，将会运行时退出
- 支持 win，mac，iOS，Android
- Android 需要 GLES3，Android 4.3
- iOS 需要 Metal

___