---
title: 'ShaderLab: Blending'
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - ShaderLab Syntax
 - ShaderLab SubShader
 - ShaderLab Pass
 - ShaderLab Blending
date: 2017-07-11 15:55:46
---

___

[网址：ShaderLab: Blending](https://docs.unity3d.com/Manual/SL-Blend.html)

# ShaderLab: Blending
![PipelineBlend](https://docs.unity3d.com/uploads/SL/PipelineBlend.png)

# Syntax
- Blend Off: Turn off blending (this is the default)
- Blend SrcFactor DstFactor: Configure and enable blending. The generated color is multiplied by the SrcFactor. The color already on screen is multiplied by DstFactor and the two are added together.
- Blend SrcFactor DstFactor, SrcFactorA DstFactorA: Same as above, but use different factors for blending the alpha channel.
- BlendOp Op: Instead of adding blended colors together, carry out a different operation on them.
- BlendOp OpColor, OpAlpha: Same as above, but use different blend operation for color (RGB) and alpha (A) channels.
- AlphaToMask On: Turns on alpha-to-coverage. When MSAA is used, alpha-to-coverage modifies multisample coverage mask proportionally to the pixel Shader result alpha value. This is typically used for less aliased outlines than regular alpha test; useful for vegetation and other alpha-tested Shaders.

___