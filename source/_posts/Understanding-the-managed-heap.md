---
title: Understanding the managed heap
category:
 - Best practice guides
 - Understanding optimization in Unity
 - Understanding the managed heap
date: 2017-07-29 14:17:39
---

___

[网址：Understanding the managed heap](https://docs.unity3d.com/Manual/BestPracticeUnderstandingPerformanceInUnity4-1.html)

# Technical details: how the managed heap operates and why it expands
- 每次 GC 会移动内存块，没回收的移动到一块，使其紧密
- 大内存占用的不移动，因为移动消耗巨大

# Key problems with the heap
- 堆内存只增不减

# Basic memory conservation
## Collection and array reuse
- 重复利用数组，减少浪费

## Closures and anonymous methods
- 减少匿名函数的使用，特别是闭包

## Anonymous methods under IL2CPP
- Prefer coding styles that do not require passing methods as arguments.
- When unavoidable, prefer anonymous methods over predefined methods.
- Avoid closures, regardless of scripting backend.

# Boxing
## Dictionaries and enums
- 定义一个类实现 IEqualityComparer

## Empty array reuse
- 重复利用空数组

___