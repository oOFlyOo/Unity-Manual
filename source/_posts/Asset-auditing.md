---
title: Asset auditing
category:
 - Best practice guides
 - Understanding optimization in Unity
 - Asset auditing
date: 2017-07-28 17:15:37
---

___

[网址：Asset auditing](https://docs.unity3d.com/Manual/BestPracticeUnderstandingPerformanceInUnity4.html)

# Common Asset rules
## Textures
### Disable the read/write enabled flag
- 默认是关闭的
- 一般需要操控 texture 的 pixel 的时候需要使用到

### Disable Mipmaps if possible
- 关掉大概省3分1内存
- 对于那些会修改 Z-depth 的，关闭会印象 GPU 采集 Texture
- UI 一般不需要开启

### Compress all Textures
- 如果 Texture Format 在对应平台上无法正常使用，Unity 会解压出来，即耗 CPU 又耗 GPU

### Enforce sensible Texture size limits
- 手机一般 1024 图集，512 模型就足够了

## Models
### Disable the Read/Write enabled flag
- 默认开启
- MeshRender 和 Static Batching 都需要开启

### Disable rigs on non-character models
- 不需要动画的关掉

### Enable the Optimize Game Objects option on animated models
- 开启来优化骨骼，需要的添加到 Extra Transforms

### Use Mesh compression when possible
- 优化掉精度
- 可以针对 channel 来优化，只优化 tangents 和 normals，保留 UVS 和 顶点位置

### Note: Mesh Renderer Settings
- 不需要阴影和投射阴影的关掉，否则会导致 adds a full shadow pass to the rendering loop

## Audio
### Platform-appropriate compression settings
- Enable a compression format for audio that matches the available hardware. All iOS devices include hardware MP3 decompressors, and many Android devices support Vorbis natively.

### Force audio clips to mono
- 很少移动设备支持 3D 音效
- 强制单通道能减半内存

### Reduce audio bitrate
- 减少比特率，可以减少硬盘和内存消耗

___