---
title: Optimizing Shader Load Time
category:
 - Graphics
 - Graphics Overview
 - Optimizing graphics performance
 - Optimizing Shader Load Time
date: 2017-07-07 18:18:47
---

___

[网址：Optimizing Shader Load Time](https://docs.unity3d.com/Manual/OptimizingShaderLoadTime.html)

# Optimizing Shader Load Time
- 太多 shader 影响 build time，还会增加游戏大小
- 读取太多 shader 会影响启动时间，也会增加内存

# Shader build time stripping
- Unity 会在 Build 的时候检查用到的 shader
- 检查 #pragma shader_feature 的使用
- 检查场景中 Fog 和 Lightmapping 的使用

# Default Unity shader loading behavior
- Unity 读取 shader 的时候，只有当使用到具体的变种的 shader 的时候，才会去创建，这样子可以减少读取时间还有内存占用

## Shader Variant Collections
- ShaderVariantCollection 用于标记 shader 关键字
-  Graphics Settings 可以根据场景状况显示使用的 shader variant（包括运行时）

___