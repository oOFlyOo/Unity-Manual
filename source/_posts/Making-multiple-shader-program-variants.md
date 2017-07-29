---
title: Making multiple shader program variants
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Writing vertex and fragment shaders
 - Making multiple shader program variants
date: 2017-07-10 17:14:21
---

___

[网址：Making multiple shader program variants](https://docs.unity3d.com/Manual/SL-MultipleProgramVariants.html)

# How multi_compile works
## 一般的
- 每一个都是一个 variant，如果没有开启任何一个，默认启用第一个

## 特殊的
- 对于所有的都是以“__"开头的，则默认创建一个空的，避免另外创建一个关键词

# Difference between shader_feature and multi_compile
- shader_feature *** 等价于 multi_compile __***
- shader_feature 可以在面板上设置，multi_compile 通过代码来设置

# Built-in multi_compile shortcuts
- multi_compile_fwdbase compiles all variants needed by ForwardBase (forward rendering base) pass type. The variants deal with different lightmap types and main directional light having shadows on or off.
- multi_compile_fwdadd compiles variants for ForwardAdd (forward rendering additive) pass type. This compiles variants to handle directional, spot or point light types, and their variants with cookie textures.
- multi_compile_fwdadd_fullshadows - same as above, but also includes ability for the lights to have realtime shadows.
- multi_compile_fog expands to several variants to handle different fog types (off/linear/exp/exp2).

___