---
title: Asynchronous Texture Upload
category:
 - Graphics
 - Graphics Overview
 - Advanced Rendering Features
 - Asynchronous Texture Upload
date: 2017-07-03 18:19:10
---

___

[Asynchronous Texture Upload](https://docs.unity3d.com/Manual/AsyncTextureUpload.html)

- Asynchronous Texture Upload enables asynchronous loading of Texture Data from disk and enables time-sliced upload to GPU on the Render-thread
- 对于没有开启读写的纹理，这个是自动开启的
- 目测不支持AB，所以并没卵用

# Simple & Full Control Over Memory / Time-Slicing
- 在 QualitySettings 里面可以设置异步提交时间和 Buffer 大小

___