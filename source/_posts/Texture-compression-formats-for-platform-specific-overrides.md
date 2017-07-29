---
title: Texture compression formats for platform-specific overrides
category:
 - Graphics
 - Graphics Reference
 - Texture Components
 - Textures
 - Texture compression formats for platform-specific overrides
date: 2017-07-21 14:15:30
---

___

[网址：Texture compression formats for platform-specific overrides](https://docs.unity3d.com/Manual/class-TextureImporterOverride.html)

# Texture compression formats for platform-specific overrides
##
- 当目标平台不支持贴图格式的时候，将会解压成 RGBA32，这样子内存不仅会有新的贴图，还会有原来的那一份
- Crunch compression 压缩慢，但是解压快

## Notes on Android
- Android 上最好是使用 ETC2
- RGBA16 适用于所有平台

___