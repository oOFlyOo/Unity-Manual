---
title: Accessing and Modifying Material parameters via script
category:
  - Graphics
  - Graphics Overview
  - Materials, Shaders & Textures
  - Accessing and Modifying Material parameters via script
date: 2017-07-01 14:46:45
---

___

[Accessing and Modifying Material parameters via script](https://docs.unity3d.com/Manual/MaterialsAccessingViaScript.html)

# Special requirements for Scripting with the Standard Shader
## You must enable the correct Keywords for your required Standard Shader variant
| Keyword | Feature
| :---    | :---
| _NORMALMAP | Normal Mapping
| _ALPHATEST_ON  | “Cut out” Transparency Rendering Mode
| _ALPHABLEND_ON | “Fade” Transparency Rendering Mode
| _ALPHAPREMULTIPLY_ON |   “Transparent” Transparency Rendering Mode
| _EMISSION |  Emission Colour or Emission Mapping
| _PARALLAXMAP  |  Height Mapping
| _DETAIL_MULX2 |  Secondary “Detail” Maps (Albedo & Normal Map)
| _METALLICGLOSSMAP |  Metallic/Smoothness Mapping in Metallic Workflow
| _SPECGLOSSMAP |  Specular/Smoothness Mapping in Specular Workflow

___