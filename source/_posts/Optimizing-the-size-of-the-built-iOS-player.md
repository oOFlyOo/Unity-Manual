---
title: Optimizing the size of the built iOS player
category:
 - Platform-specific
 - iOS
 - iOS Advanced Topics
 - Optimizing Performance in iOS
 - Optimizing the size of the built iOS player
date: 2017-07-26 18:05:32
---

___

[网址：Optimizing the size of the built iOS player](https://docs.unity3d.com/Manual/iphone-playerSizeOptimization.html)

# iOS stripping level
The size optimizations activated by stripping work in the following way:
1. Strip assemblies level: the scripts’ bytecode is analyzed so that classes and methods that are not referenced from the scripts can be removed from the DLLs and thereby excluded from the AOT compilation phase. This optimization reduces the size of the main binary and accompanying DLLs and is safe as long as no reflection is used.
2. Strip ByteCode level: any .NET DLLs (stored in the Data folder) are stripped down to metadata only. This is possible because all the code is already precompiled during the AOT phase and linked into the main binary.
3. Use micro mscorlib level: a special, smaller version of mscorlib is used. Some components are removed from this library, for example, Security, Reflection.Emit, Remoting, non Gregorian calendars, etc. Also, interdependencies between internal components are minimized. This optimization reduces the main binary and mscorlib.dll size but it is not compatible with some System and System.Xml assembly classes, so use it with care.
每一层都包含上一层

# Stripping with IL2CPP
## Simple checklist for making your distribution as small as possible
1. 压缩贴图和音效
2. 调高 ios stripping level（难）
3. 设置 Fast but no exceptions（没人用）
4. 尽量不要使用 System.dll 和 System.xml.dll
5. 移除没必要的代码依赖
6. 使用 .net 2.0 subset
7. 不使用 JS Array
8. 不使用 泛型和值类型的结合（引用类型的泛型代码有优化，但是值类型没有）

___