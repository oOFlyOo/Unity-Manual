---
title: Android Manifest
category:
  - Platform-specific
  - Android
  - Android Manifest
date: 2018-01-11 11:48:54
---

___

[网址：Android Manifest](https://docs.unity3d.com/Manual/android-manifest.html)

# How Unity produces the Android Manifest
1. 使用主 Manifest
2. 找到所有插件的 Mainifest
3. 使用 Google’s manifmerger class 来合并
4. Unity 根据设置修改 Manifest

# Overriding the Android Manifest
- Assets/Plugins/Android/AndroidManifest.xml 可以在这里放进一个 Manifest 代替 Unity 的那个
- Unity 仅支持 launchMode - singleTask

___
