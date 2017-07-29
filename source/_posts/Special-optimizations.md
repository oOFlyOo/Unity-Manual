---
title: Special optimizations
category:
 - Best practice guides
 - Understanding optimization in Unity
 - Special optimizations
date: 2017-07-29 17:12:07
---

___

[网址：Special optimizations](https://docs.unity3d.com/Manual/BestPracticeUnderstandingPerformanceInUnity8.html)

# Multidimensional vs. jagged arrays
- 使用数组的数组代替多维数组

# Particle System pooling
- 粒子很占内存，所以可以的话尽量通过配置表共用一种粒子来做池

# Update managers
- 减少 Update，尽可能在调用前做判断跳过

# Using C# delegates in an update manager
- C# deleagate 每次 add 和 remove 都会触发深度拷贝，因此考虑用别的类型代替这些操作

# Loading thread control
- 可以单独设置线程的优先度来优化效率

# Mass object movement & CullingGroups
- 优化不显示的物体

# Reducing method call overhead
- for 里面的赋值放到外面

## Trivial properties
- 固定属性值的访问，改为静态，或者只在第一次使用的时候进行计算

___