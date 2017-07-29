---
title: 'ShaderLab: Culling & Depth Testing'
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - ShaderLab Syntax
 - ShaderLab SubShader
 - ShaderLab Pass
 - ShaderLab Culling & Depth Testing
date: 2017-07-11 15:20:35
---

___

[网址：ShaderLab: Culling & Depth Testing](https://docs.unity3d.com/Manual/SL-CullAndDepth.html)

# ShaderLab: Culling & Depth Testing
![PipelineCullDepth](https://docs.unity3d.com/uploads/SL/PipelineCullDepth.png)

# Syntax
## Cull
- 控制多边形的边的剔除
- Back 不渲染远离观察者的背面，默认
- Front 不渲染面向观察者的面
- Off 关闭剔除

## ZTest
- 控制深度测试
- ZTest Less | Greater | LEqual | GEqual | Equal | NotEqual | Always
- 默认 LEqual

## Offset
- Offset Factor, Units

___