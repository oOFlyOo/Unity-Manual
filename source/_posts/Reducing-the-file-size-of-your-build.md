---
title: Reducing the file size of your build
category:
  - Working In Unity
  - Advanced Development
  - Reducing the file size of your build
date: 2017-06-30 16:34:09
---

___

[Reducing the file size of your build](https://docs.unity3d.com/Manual/ReducingFilesize.html)

# Suggestions for reducing build size
## Meshes and Animations
- Mesh 压缩只减少精度，因此只减少硬盘，不减少内存
- Animation 帧减少，因此硬盘和内存都会减少

## DLLs
- 必有的 dll：mscorlib.dll，Boo.Lang.dll，UnityScript.Lang.dll，UnityEngine.dll

___