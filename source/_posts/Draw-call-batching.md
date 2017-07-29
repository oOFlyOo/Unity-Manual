---
title: Draw call batching
category:
 - Graphics
 - Graphics Overview
 - Optimizing graphics performance
 - Draw call batching
date: 2017-07-07 10:17:42
---

___

[网址：Draw call batching](https://docs.unity3d.com/Manual/DrawCallBatching.html)

# Draw call batching
1. 动态合批：for small enough Meshes, this transforms their vertices on the CPU, groups many similar vertices together, and draws them all in one go.
2. 静态合批： combines static (not moving) GameObjects into big Meshes, and renders them in a faster way.
- 动态合批会增加 CPU 消耗，静态合批会增加内存和存储消耗

## Material set-up for batching
- 只有共用一个 material 的物体可以合批
- 如果两个 material 仅仅是贴图不一样，可以合并图集
- 阴影可以动态合批，因为使用的相同的 pass

# Dynamic batching
- 由于需要在 CPU 将所有物体的顶点转到世界坐标，所以仅对小物体有更好的优化效果

## 限制要求
- Batching dynamic GameObjects has certain overhead per vertex, so batching is applied only to Meshes containing fewer than 900 vertex attributes in total.
    - If your Shader is using Vertex Position, Normal and single UV, then you can batch up to 300 verts, while if your Shader is using Vertex Position, Normal, UV0, UV1 and Tangent, then only 180 verts.
    - Note: attribute count limit might be changed in future.
- GameObjects are not batched if they contain mirroring on the transform (for example GameObject A with +1 scale and GameObject B with –1 scale cannot be batched together).
- Using different Material instances causes GameObjects not to batch together, even if they are essentially the same. The exception is shadow caster rendering.
- GameObjects with lightmaps have additional renderer parameters: lightmap index and offset/scale into the lightmap. Generally, dynamic lightmapped GameObjects should point to exactly the same lightmap location to be batched.
- Multi-pass Shaders break batching.
    - Almost all Unity Shaders support several Lights in forward rendering, effectively doing additional passes for them. The draw calls for “additional per-pixel lights” are not batched.
    - The Legacy Deferred (light pre-pass) rendering path has dynamic batching disabled, because it has to draw GameObjects twice.

# Static batching
- 一般比动态合批更有效率（不消耗 CPU 转换顶点），但是需要更多的内存
- 并不减少 draw calls，减少状态转换
- Batches are limited to 64k vertices and 64k indices on most platforms (48k indices on OpenGLES, 32k indices on macOS).
- 是在 Build Player 阶段进行的合并网格（尽管如此还是得开启 read write enable，并且会同时存在合并后的网格和原始网格）

# Tips
- Currently, only Mesh Renderers, Trail Renderers, Line Renderers, Particle Systems and Sprite Renderers are batched. This means that skinned Meshes, Cloth, and other types of rendering components are not batched.
- Semi-transparent Shaders usually require GameObjects to be rendered in back-to-front order for transparency to work. Unity first orders GameObjects in this order, and then tries to batch them, but because the order must be strictly satisfied, this often means less batching can be achieved than with opaque GameObjects.
- Manually combining GameObjects that are close to each other can be a very good alternative to draw call batching. For example, a static cupboard with lots of drawers often makes sense to just combine into a single Mesh, either in a 3D modeling application or using Mesh.CombineMeshes.

___