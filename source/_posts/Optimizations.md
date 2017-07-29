---
title: Optimizations
category:
 - Platform-specific
 - Mobile Developer Checklist
 - Optimizations
date: 2017-07-28 11:20:29
---

___

[网址：Optimizations](https://docs.unity3d.com/Manual/MobileOptimisation.html)

# Focus on GPUs
- 填充率 = 屏幕像素 * shader复杂度 * overdraw

## Good practice
1. 少用 material，方便 batch
2. 使用图集，加快载入时间，和方便 batch
3. 使用 Renderer.sharedMaterial 代替 Renderer.material
4. 前向像素光很耗
 - 使用光照贴图代替
 - 减少像素光照
5. 测试灯光效果，调节优先次序
6. 减少使用 cutout
7. 减少透明混合
8. 减少多光对同一个物体使用
9. 减少 pass
10. 渲染顺序很重要
11. Post Processing 很耗
12. 粒子减少 overdraw，使用简单的 shader
13. Double buffer for Meshes modified every frame

## Shader optimizations
- 使用 alpha 混合代替 alpha 测试
- 使用简单的优化的 shader
- 减少运算，考虑使用查图代替
- 减少精度

