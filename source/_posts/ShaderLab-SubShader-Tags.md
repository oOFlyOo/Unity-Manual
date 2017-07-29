---
title: 'ShaderLab: SubShader Tags'
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - ShaderLab Syntax
 - ShaderLab SubShader
 - ShaderLab SubShader Tags
date: 2017-07-12 09:52:43
---

___

[网址：ShaderLab: SubShader Tags](https://docs.unity3d.com/Manual/SL-SubShaderTags.html)

# Details
## Rendering Order - Queue tag
- Background - this render queue is rendered before any others. You’d typically use this for things that really need to be in the background.
- Geometry (默认) - this is used for most objects. Opaque geometry uses this queue.
- AlphaTest - alpha tested geometry uses this queue. It’s a separate queue from Geometry one since it’s more efficient to render alpha-tested objects after all solid ones are drawn.
- Transparent - this render queue is rendered after Geometry and AlphaTest, in back-to-front order. Anything alpha-blended (i.e. shaders that don’t write to depth buffer) should go here (glass, particle effects).
- Overlay - this render queue is meant for overlay effects. Anything rendered last should go here (e.g. lens flares).

## RenderType tag
- 用于 Shader Replacement 或者 camera's depth texture

## DisableBatching tag
- True：关闭 batching
- False：不关闭，默认
- LODFading：当开启 LOD 的时候关闭，一般用于树

## ForceNoShadowCasting tag
- True：一般用于渲染透明物体的时候，关闭从其它 subshader 那里的投影

## IgnoreProjector tag
- True：一般用于半透明物体，因为 Projectors 没办法很好的处理

## CanUseSpriteAtlas tag
- False：当用于 Sprite 的时候，如果使用了 Atlas，设定无效

## PreviewType tag
- Spheres：默认
- Plane
- Skybox
___