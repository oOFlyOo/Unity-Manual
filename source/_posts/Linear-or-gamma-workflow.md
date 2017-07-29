---
title: Linear or gamma workflow
category:
  - Graphics
  - Graphics Overview
  - Lighting
  - Related topics
  - Linear rendering overview
  - Linear or gamma workflow
date: 2017-06-30 19:42:05
---

___

[Linear or gamma workflow](https://docs.unity3d.com/Manual/LinearRendering-LinearOrGammaWorkflow.html)

- 图片一般保存在 Gamma 空间

# Linear color space workflow
- gamma texture 将会移除伽玛校正

## Linear Textures
- bypass sRGB Sampling：关闭的话，将会采集 sRGB，使纹理变成 sRGB 格式
- 如果纹理原本是在 linear 空间的，则需要关闭 bypass sRGB Sampling

## Notes
- 对于 colors，unity 在传入 GPU 前就会使用 floating
- 对于 texture，unity 会去除伽玛校正
- 当把结果写进 framebuffer，可能直接使用伽玛校正，或者保留，取决于后面的处理

___