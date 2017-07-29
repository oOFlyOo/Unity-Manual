---
title: Camera’s Depth Texture
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Advanced ShaderLab topics
 - Camera’s Depth Texture
date: 2017-07-20 14:43:09
---

___

[网址：Camera’s Depth Texture](https://docs.unity3d.com/Manual/SL-CameraDepthTexture.html)

# Camera’s Depth Texture
There are three possible depth texture modes:
- DepthTextureMode.Depth: a depth texture.
- DepthTextureMode.DepthNormals: depth and view space normals packed into one texture.*
- DepthTextureMode.MotionVectors: per-pixel screen space motion of each screen texel for the current frame. Packed into a RG16 texture.

# DepthTextureMode.Depth texture
- 深度图使用 shadow caster pass，所以如果 shader 不支持，则物体不会出现在深度图中
- 在 shader 的 fallback 添加那些有 shadow casting pass 的 shader，或者在 surfase shader 中添加 addshadow 也会生成 shadow pass
- 仅有 render queue <= 2500 的会渲染到深度图中

# DepthTextureMode.DepthNormals texture
- 32bits 深度图，View Space Normals Stereographic projection 加密到 RG Channel，depth 加密到 BA Channel
- DecodeDepthNormal 用于解密图到 0~1 范围

# DepthTextureMode.MotionVectors texture
- This builds a screen-sized RG16 (16-bit float/channel) texture, where screen space pixel motion is encoded into the R&G channels. The pixel motion is encoded in screen UV space.
- When sampling from this texture motion from the encoded pixel is returned in a rance of –1..1. This will be the UV offset from the last frame to the current frame.

# Shader variables
Depth textures are available for sampling in shaders as global shader properties. By declaring a sampler called _CameraDepthTexture you will be able to sample the main depth texture for the camera.
_CameraDepthTexture always refers to the camera’s primary depth texture. By contrast, you can use _LastCameraDepthTexture to refer to the last depth texture rendered by any camera. This could be useful for example if you render a half-resolution depth texture in script using a secondary camera and want to make it available to a post-process shader.
The motion vectors texture (when enabled) is avaialable in Shaders as a global Shader property. By declaring a sampler called ‘_CameraMotionVectorsTexture’ you can sample the Texture for the curently rendering Camera.

# Under the hood
Depth textures can come directly from the actual depth buffer, or be rendered in a separate pass, depending on the rendering path used and the hardware. Typically when using Deferred Shading or Legacy Deferred Lighting rendering paths, the depth textures come “for free” since they are a product of the G-buffer rendering anyway.
When the DepthNormals texture is rendered in a separate pass, this is done through Shader Replacement. Hence it is important to have correct “RenderType” tag in your shaders.
When enabled, the MotionVectors texture always comes from a extra render pass. Unity will render moving GameObjects into this buffer, and construct their motion from the last frame to the current frame.

___