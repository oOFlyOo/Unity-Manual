---
title: Optimizing graphics performance
category:
 - Graphics
 - Graphics Overview
 - Optimizing graphics performance
date: 2017-07-05 16:08:36
---

___

[Optimizing graphics performance](https://docs.unity3d.com/Manual/OptimizingGraphicsPerformance.html)

# Locate high graphics impact
## Common bottlenecks and ways to check for them
1. GPU 一般都限制于填充率或者带宽
- 因此可以降低分辨率
2. CPU 一般限制于 batches 数量

## Less-common bottlenecks:
- GPU 太多顶点数，受 shader 的复杂计算影响
- CPU 太多顶点数

# CPU optimization
##　Reduce the visible object count. To reduce the amount of work the CPU needs to do
- 合并物体
- 减少材质球，合并纹理
- 减少渲染次数

# GPU: Optimizing model geometry
- 相比建模软件，显卡为了表示模型，有可能会展开更多的顶点
- 如果顶点有多个法线、uv 坐标、顶点色之类的，必须划分成更多的顶点
- 虽然模型中的几何量大多和 GPU 相关，但是 Unity 也会在 CPU 处理模型（例如蒙皮网格）

# Lighting performance
- 使用光照贴图大概快2到3倍，并且表现更好

## Lights in forward rendering
- 防止间隔太远的地方的物体合并网格并且受不同的光照，因为光照会应用与整个合并后的网格，尽管并没受到光照
- 优化像素光照，可以减少 CPU draw calls

# GPU: Texture compression and mipmaps
- 压缩贴图，可以减少读取时间，更少的内存占用，显著提升渲染性能

## Texture mipmaps
- 打开 mipmaps，能让 GPU 使用更低像素的纹理

# LOD and per-layer cull distances
- 使用 LOD
- camera 设置远距离裁剪
- 给小物体单独一个 layer，然后通过 Camera.layerCullDistances 单独设置裁剪距离

# Realtime shadows
- 实时阴影会额外增加 CPU draw calls 和 GPU 的处理

# GPU: Tips for writing high-performance shaders
## Complex mathematical operations
- 考虑使用查找纹理代替负责数学运算
- 防止自己计算，尽量使用 Unity 提供的函数
- Alpha Test 会使片段着色器变慢

## Floating point precision
- 桌面 GPU 忽视浮点精确度

# Simple checklist to make your game faster
- 在 PC 上控制顶点数少于 200K 和 3M
- 手机上使用 Mobile 和 无光照 shader
- 尽量少用 material，并且共用一个
- 对于不动的物体开启 static
- 只使用一个像素光照
- 烘焙光照代替动态光
- 使用压缩纹理
- 防止使用雾效
- 使用 Occlusion Culling
- 使用 skybox “隐藏”远的物体
- 使用 pixel shaders 或者合并贴图
- shader 使用 half 精度
- shader 中减少复杂的数学运算
- 片段着色器少用贴图

___