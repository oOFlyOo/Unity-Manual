---
title: Modeling characters for optimal performance
category:
 - Graphics
 - Graphics Overview
 - Optimizing graphics performance
 - Modeling characters for optimal performance
date: 2017-07-07 15:27:57
---

___

[网址：Modeling characters for optimal performance](https://docs.unity3d.com/Manual/ModelingOptimizedCharacters.html)

# Modeling characters for optimal performance
## Use a single skinned Mesh Renderer
- Unity 使用剔除和包围盒来优化动画
- 限制是使用一个动画组件和一个蒙皮网格

# Use as few materials as possible
- 一般一个模型一个 material 就行了，除非是为了使用不一样的 shader，一般一个模型两到三个材质球就足够了

# Use as few bones as possible
- PC 一般50~60骨骼
- 手机低于30

# Polygon count
- PC 一般1500~4000个面
- 手机一般300~1500个面

# Keep forward and inverse kinematics separate
- When animations are imported, a model’s inverse kinematic (IK) nodes are baked into forward kinematics (FK) and as a result, Unity doesn’t need the IK nodes at all. However, if they are left in the model then they will have a CPU overhead even though they don’t affect the animation. You can delete the redundant IK nodes in Unity or in the modeling tool, according to your preference. Ideally, you should keep separate IK and FK hierarchies during modeling to make it easier to remove the IK nodes when necessary.

___