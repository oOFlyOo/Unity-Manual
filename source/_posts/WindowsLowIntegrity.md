---
title: WindowsLowIntegrity
category:
 - Platform-specific
 - Windows
 - Windows General
 - WindowsLowIntegrity
date: 2017-07-28 10:24:28
---

___

[网址：WindowsLowIntegrity](https://docs.unity3d.com/Manual/WindowsLowIntegrity.html)

# WindowsLowIntegrity
Windows Standalone player can detect if it’s running at Low Integrity Level (see Microsoft’s documentation on Designing Applications to Run at a Low Integrity Level for more information). In this case, several things happen:
- The log file is written to %USER PROFILE%\AppData\LocalLow\CompanyName\ProductName
- PlayerPrefs is saved to HKCU\Software\AppDataLow\Software\CompanyName\ProductName

___