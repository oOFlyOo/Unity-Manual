---
title: Unity’s Rendering Pipeline
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Advanced ShaderLab topics
 - Unity’s Rendering Pipeline
date: 2017-07-12 14:52:53
---

___

[网址：Unity’s Rendering Pipeline](https://docs.unity3d.com/Manual/SL-RenderPipeline.html)

# Rendering Paths
- 前向渲染，使用 ForwardBase 和 ForwardAdd
- 延迟渲染，使用 Deferred
- 对于上述任何光照，ShaowCaster 用于渲染阴影和深度图

# Forward Rendering path
- 如果使用前向渲染，但是没有设置 pass，将会使用 Vertex Lit Path

## ForwardBase
- 环境光
- 光照贴图
- 主要的方向光
- 不重要的顶点光照
## ForwardAdd
- 像素光照，每个光照对对象使用了一次

# Deferred Shading path
- Deferred pass renders all information needed for lighting (in built-in shaders: diffuse color, specular color, smoothness, world space normal, emission). It also adds lightmaps, reflection probes and ambient lighting into the emission channe

___