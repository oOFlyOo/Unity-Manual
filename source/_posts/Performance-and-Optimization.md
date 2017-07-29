---
title: Performance and Optimization
category:
 - Animation
 - ﻿Performance and Optimization
date: 2017-07-25 18:19:28
---

___

[网址：﻿Performance and Optimization](https://docs.unity3d.com/Manual/MecanimPeformanceandOptimization.html)

# Character Setup
## Number of Bones
- 减少骨骼数，或者隐藏掉

## Multiple Skinned Meshes
- 合并 Skinned Meshes

# Animation System
## Scale Curves
- 比起位移旋转更加耗时，尽量不用

## Humanoid vs. Generic Modes
- 使用 BodyMask 移除 IK Goals 和 fingers animation 如果不用到的话
- root motion 比较耗，可以的话不要使用

# Runtime Optimizations
## Visibility and Updates
- Culling Mode Base On Renderers
- 关闭 skinned mesh renderer's update

___