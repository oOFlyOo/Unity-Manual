---
title: Accessing shader properties in Cg/HLSL
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Writing vertex and fragment shaders
 - Accessing shader properties in Cg/HLSL
date: 2017-07-10 14:51:25
---

___

[网址：Accessing shader properties in Cg/HLSL](https://docs.unity3d.com/Manual/SL-PropertiesInPrograms.html)

# Accessing shader properties in Cg/HLSL
## Property types in ShaderLab map to Cg/HLSL variable types this way
- Color and Vector properties map to float4, half4 or fixed4 variables.
- Range and Float properties map to float, half or fixed variables.
- Texture properties map to sampler2D variables for regular (2D) textures; Cubemaps map to samplerCUBE; and 3D textures map to sampler3D.

___