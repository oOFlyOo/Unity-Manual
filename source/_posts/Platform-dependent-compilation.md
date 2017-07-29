---
title: Platform dependent compilation
category:
 - Scripting
 - Scripting Overview
 - Platform dependent compilation
date: 2017-07-24 17:13:35
---

___

[网址：Platform dependent compilation](https://docs.unity3d.com/Manual/PlatformDependentCompilation.html)

# Global custom #defines
As an example, if you include the single line -define:UNITY_DEBUG in your mcs.rsp file, the #define directive UNITY_DEBUG exists as a global #define for C# scripts, except for Editor scripts.
Every time you make changes to .rsp files, you need to recompile in order for them to be effective. You can do this by updating or reimporting a single script (.js or .cs) file.

___