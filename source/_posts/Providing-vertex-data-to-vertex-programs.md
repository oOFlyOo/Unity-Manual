---
title: Providing vertex data to vertex programs
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Writing vertex and fragment shaders
 - Providing vertex data to vertex programs
date: 2017-07-10 15:04:03
---

___

[网址：Providing vertex data to vertex Providing-vertex-data-to-vertex-programs.md](https://docs.unity3d.com/Manual/SL-VertexProgramInputs.html)

# Providing vertex data to vertex programs
- appdata_base: position, normal and one texture coordinate.
- appdata_tan: position, tangent, normal and one texture coordinate.
- appdata_full: position, tangent, normal, four texture coordinates and color.

- POSITION is the vertex position, typically a float3 or float4.
- NORMAL is the vertex normal, typically a float3.
- TEXCOORD0 is the first UV coordinate, typically float2, float3 or float4.
- TEXCOORD1, TEXCOORD2 and TEXCOORD3 are the 2nd, 3rd and 4th UV coordinates, respectively.
- TANGENT is the tangent vector (used for normal mapping), typically a float4.
- COLOR is the per-vertex color, typically a float4.

___