---
title: Built-in shader variables
category:
 - Graphics
 - Graphics Reference
 - Shader Reference
 - Writing vertex and fragment shaders
 - Built-in shader variables
date: 2017-07-10 16:20:42
---

___

[网址：Built-in shader variables](https://docs.unity3d.com/Manual/SL-UnityShaderVariables.html)

# Transformations
- 都是 float4
- UNITY_MATRIX_MVP    Current model * view * projection matrix.
- UNITY_MATRIX_MV Current model * view matrix.
- UNITY_MATRIX_V  Current view matrix.
- UNITY_MATRIX_P  Current projection matrix.
- UNITY_MATRIX_VP Current view * projection matrix.
- UNITY_MATRIX_T_MV   Transpose of model * view matrix.
- UNITY_MATRIX_IT_MV  Inverse transpose of model * view matrix.
- _Object2World   Current model matrix.
- _World2Object   Inverse of current world matrix.

# Camera and screen
- _WorldSpaceCameraPos    float3  World space position of the camera.
- _ProjectionParams   float4  x is 1.0 (or –1.0 if currently rendering with a flipped projection matrix), y is the camera’s near plane, z is the camera’s far plane and w is 1/FarPlane.
- _ScreenParams   float4  x is the camera’s render target width in pixels, y is the camera’s render target height in pixels, z is 1.0 + 1.0/width and w is 1.0 + 1.0/height.
- _ZBufferParams  float4  Used to linearize Z buffer values. x is (1-far/near), y is (far/near), z is (x/far) and w is (y/far).
- unity_OrthoParams   float4  x is orthographic camera’s width, y is orthographic camera’s height, z is unused and w is 1.0 when camera is orthographic, 0.0 when perspective.
- unity_CameraProjection  float4x4    Camera’s projection matrix.
- unity_CameraInvProjection   float4x4    Inverse of camera’s projection matrix.
- unity_CameraWorldClipPlanes[6]  float4  Camera frustum plane world space equations, in this order: left, right, bottom, top, near, far.

# Time
- _Time   float4  Time since level load (t/20, t, t*2, t*3), use to animate things inside the shaders.
- _SinTime    float4  Sine of time: (t/8, t/4, t/2, t).
- _CosTime    float4  Cosine of time: (t/8, t/4, t/2, t).
- unity_DeltaTime float4  Delta time: (dt, 1/dt, smoothDt, 1/smoothDt).

# Lighting
- _LightColor0 (declared in Lighting.cginc)   fixed4  Light color.
- _WorldSpaceLightPos0    float4  Directional lights: (world space direction, 0). Other lights: (world space position, 1).
- _LightMatrix0 (declared in AutoLight.cginc) float4x4    World-to-light matrix. Used to sample cookie & attenuation textures.
- unity_4LightPosX0, unity_4LightPosY0, unity_4LightPosZ0 float4  (ForwardBase pass only) world space positions of first four non-important point lights.
- unity_4LightAtten0  float4  (ForwardBase pass only) attenuation factors of first four non-important point lights.
- unity_LightColor    half4[4]    (ForwardBase pass only) colors of of first four non-important point lights.

- _LightColor float4  Light color.
- _LightMatrix0   float4x4    World-to-light matrix. Used to sample cookie & attenuation textures.

- unity_LightColor    half4[8]    Light colors.
- unity_LightPosition float4[8]   View-space light positions. (-direction,0) for directional lights; (position,1) for point/spot lights.
- unity_LightAtten    half4[8]    Light attenuation factors. x is cos(spotAngle/2) or –1 for non-spot lights; y is 1/cos(spotAngle/4) or 1 for non-spot lights; z is quadratic attenuation; w is squared light range.
- unity_SpotDirection float4[8]   View-space spot light positions; (0,0,1,0) for non-spot lights.

# Fog and Ambient
- unity_AmbientSky    fixed4  Sky ambient lighting color in gradient ambient lighting case.
- unity_AmbientEquator    fixed4  Equator ambient lighting color in gradient ambient lighting case.
- unity_AmbientGround fixed4  Ground ambient lighting color in gradient ambient lighting case.
UNITY_LIGHTMODEL_AMBIENT    fixed4  Ambient lighting color (sky color in gradient ambient case). Legacy variable.
- unity_FogColor  fixed4  Fog color.
- unity_FogParams float4  Parameters for fog calculation: (density / sqrt(ln(2)), density / ln(2), –1/(end-start), end/(end-start)). x is useful for Exp2 fog mode, y for Exp mode, z and w for Linear mode.

# Various
- unity_LODFade   float4  Level-of-detail fade when using LODGroup. x is fade (0..1), y is fade quantized to 16 levels, z and w unused.

___