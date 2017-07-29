---
title: Shader data types and precision
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Writing vertex and fragment shaders
 - Shader data types and precision
date: 2017-07-11 11:00:56
---

___

[网址：Shader data types and precision](https://docs.unity3d.com/Manual/SL-DataTypesAndPrecision.html)

# Basic data types
## High precision: float
- 32 bits
- 世界坐标
- 纹理坐标
- 复杂的三角函数和指数运算

## Medium precision: half
- 16 bits，-6000~6000，大致0.001精度
- 简单的向量
- 方向
- 物体坐标
- HDR 颜色

## Low precision: fixed
- 11 bits，-2~2，1/256 精度
- 一般颜色
- 简单计算

## Integer data types
- 像 ES2 这种 GPU 会不支持

# Composite vector/matrix types
- 像 ES2 这种 GPU 只支持正方形矩阵

# Precision, Hardware Support and Performance
- PC 上都是使用 32 bits 的，不管使用的是 half 还是 fixed
- 即使是在 Mobile 上，对精度类型的占位也是不一样的


___