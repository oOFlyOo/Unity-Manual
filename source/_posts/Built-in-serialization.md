---
title: Built-in serialization
category:
 - Scripting
 - Scripting Overview
 - Script Serialization
 - Built-in serialization
date: 2017-07-24 17:55:07
---

___

[网址：Built-in serialization](https://docs.unity3d.com/Manual/script-Serialization-BuiltInUse.html)

# Built-in serialization
## Unloading unused assets
当读取一个场景并且检查到对象（例如贴图）不再被引用的时候，Unity 将会调用 Resource.GarbageCollectSharedAssets() 来释放资源

___