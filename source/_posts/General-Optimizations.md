---
title: General Optimizations
category:
 - Best practice guides
 - Understanding optimization in Unity
 - General Optimizations
date: 2017-07-29 17:04:28
---

___

[网址：General Optimizations](https://docs.unity3d.com/Manual/BestPracticeUnderstandingPerformanceInUnity7.html)

# Address Properties by ID
- 使用 Hash 代替 string 作为索引

# Use non-allocating physics APIs
- 使用 non-allocating 接口

# Transform manipulation
- Transform 的改变会引起 OnTransformChanged，合并或者尽量减少修改

## Vector and quaternion math and order of operations
- 由于类型转换的原因，尽量先计算简单的类型

# Built-In ColorUtility
- 使用 Unity 内置的这个颜色转换接口

# Find and FindObjectOfType
- 减少调用

## Camera locators
Internally, Unity’s Camera.main property calls Object.FindObjectWithTag, a specialized variant of Object.FindObject. Accessing this property is no more efficient than a call to Object.FindObjectOfType. If code must address the main camera, it is strongly recommended to do one of two things:
- Access Camera.main in a Start orOnEnable callback and cache the resulting reference.
- Construct a Camera Manager class that can provide or inject a reference to the active camera.

# Debug code & the [conditional] attribute
- 懒人谁会用啊

___