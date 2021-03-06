---
title: Built-in shader helper functions
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Writing vertex and fragment shaders
 - Built-in shader helper functions
date: 2017-07-10 15:59:30
---

___

[网址：Built-in shader helper functions](https://docs.unity3d.com/Manual/SL-BuiltinFunctions.html)

# Built-in shader helper functions
## Vertex transformation functions in UnityCG.cginc
- float4 UnityObjectToClipPos(float3 pos) 将点从物体坐标空间转到齐次坐标
- float3 UnityObjectToViewPos(float3 pos) 将点从物体坐标空间转到视图坐标

## Generic helper functions in UnityCG.cginc
- float3 WorldSpaceViewDir (float4 v) Returns world space direction (not normalized) from given object space vertex position towards the camera.
- float3 ObjSpaceViewDir (float4 v)   Returns object space direction (not normalized) from given object space vertex position towards the camera.
- float2 ParallaxOffset (half h, half height, half3 viewDir)  calculates UV offset for parallax normal mapping.
- fixed Luminance (fixed3 c)  Converts color to luminance (grayscale).
- fixed3 DecodeLightmap (fixed4 color)    Decodes color from Unity lightmap (RGBM or dLDR depending on platform).
- float4 EncodeFloatRGBA (float v)    Encodes [0..1) range float into RGBA color, for storage in low precision render target.
- float DecodeFloatRGBA (float4 enc)  Decodes RGBA color into a float.
- float2 EncodeFloatRG (float v)  Encodes [0..1) range float into a float2.
- float DecodeFloatRG (float2 enc)    Decodes a previously-encoded RG float.
- float2 EncodeViewNormalStereo (float3 n)    Encodes view space normal into two numbers in 0..1 range.
- float3 DecodeViewNormalStereo (float4 enc4) Decodes view space normal from enc4.xy.

## Forward rendering helper functions in UnityCG.cginc
- float3 WorldSpaceLightDir (float4 v)    Computes world space direction (not normalized) to light, given object space vertex position.
- float3 ObjSpaceLightDir (float4 v)  Computes object space direction (not normalized) to light, given object space vertex position.
- float3 Shade4PointLights (...)  Computes illumination from four point lights, with light data tightly packed into vectors. Forward rendering uses this to compute per-vertex lighting.

## Screen-space helper functions in UnityCG.cginc
- float4 ComputeScreenPos (float4 clipPos)    Computes texture coordinate for doing a screenspace-mapped texture sample. Input is clip space position.
- float4 ComputeGrabScreenPos (float4 clipPos)    Computes texture coordinate for sampling a GrabPass texure. Input is clip space position.

## Vertex-lit helper functions in UnityCG.cginc
- float3 ShadeVertexLights (float4 vertex, float3 normal) Computes illumination from four per-vertex lights and ambient, given object space position & normal.

___