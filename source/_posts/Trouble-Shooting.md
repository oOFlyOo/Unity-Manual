---
title: Trouble Shooting
date: 2017-06-29 20:34:25
category:
 - Working In Unity
 - Creating Gameplay
 - Trouble Shooting
---

___

[Trouble Shooting](https://docs.unity3d.com/Manual/TroubleShooting.html)

# Shadows
- 手游不支持软阴影
- 前向渲染仅支持一个方向光投影
## Some of my objects do not cast or receive shadows
- 只有不透明物体接受或者投射阴影
- 顶点 shader 不接受阴影，但是可以投射阴影
- 只有像素光照投射阴影

___