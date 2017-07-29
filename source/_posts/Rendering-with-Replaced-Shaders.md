---
title: Rendering with Replaced Shaders
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Advanced ShaderLab topics
 - Rendering with Replaced Shaders
date: 2017-07-20 11:16:30
---

___

[网址：Rendering with Replaced Shaders](https://docs.unity3d.com/Manual/SL-ShaderReplacement.html)

# Rendering with Replaced Shaders
- If replacementTag is empty, then all objects in the scene are rendered with the given replacement shader.
- If replacementTag is not empty, then for each object that would be rendered:
 - The real object’s shader is queried for the tag value.
 - If it does not have that tag, object is not rendered.
 - A subshader is found in the replacement shader that has a given tag with the found value. If no such subshader is found, object is not rendered.
 - Now that subshader is used to render the object.

# Shader replacement tags in built-in Unity shaders
All built-in Unity shaders have a “RenderType” tag set that can be used when rendering with replaced shaders. Tag values are the following:



___