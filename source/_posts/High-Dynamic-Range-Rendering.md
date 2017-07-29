---
title: High Dynamic Range Rendering
category:
 - Graphics
 - Graphics Overview
 - Advanced Rendering Features
 - High Dynamic Range Rendering
date: 2017-07-01 15:36:06
---

___

[High Dynamic Range Rendering](https://docs.unity3d.com/Manual/HDR.html)

- 正常渲染下，0代表最小，1代表最大
- 然而显示场景，人眼倾向于适应环境光照
- 因此白色物体在光亮的地方没有在灰暗的地方显得那么亮
- 人眼对于低光场景更为敏感
- 尽管使用 HDR，最终还是会将值调整为显示设备可用的范围
- 本质是让显卡内部支持用0-1之外的范围表示颜色

# Advantages of HDR
- 高光环境颜色不会丢失

# Disadvantages of HDR
- 使用浮点渲染纹理（渲染变慢，并且需要更多的内存）
- 不支持反锯齿
- 不是所有的硬件都支持

___