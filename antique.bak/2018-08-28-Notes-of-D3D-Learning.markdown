---
layout: post
title: Notes of Direct 3D 11 Learning
date: 2018-08-28 17:00:00 +0800
tags: [Notes]
---

# Notes of Direct 3D 11 Learning

## Keys To Initialize a empty D3D 11 project (without DXUT)

- Make sure that the Visual Studio is up-to-date.
- Make sure the latest version of Windows SDK is installed. (currently 10.0.17134.0)
- Add the following to lib dependencies (Properties->Linker->Input->Additional Dependencies):
    - d3d11.lib
    - d3dcompiler.lib
    - dxguid.lib
    - winmm.lib
    - comctl32.lib
- If `.vs` & `.ps` files are implemented through "including a `.fx` file(that's actually how [these samples](https://github.com/walbourn/directx-sdk-samples)" do), you may exclude the `.fx` file from the build.
    - Right click the `.fx` file -> Properties -> General -> Set `Yes` to "Excluded from Build".
    - Otherwise FXC.exe(the HLSL Compiler) will throw an error when (unexpectedly) compiling the `.fx` file.
- Also Remember to Set ['EntryPoint Name', 'Shader Type', 'Shader Model'] to what you desired at the target shader files (Properties of those files).

## Others

- To install D3D11 SDK Layers for Windows 10:
    - Run `Dism /online /add-capability /capabilityname:Tools.Graphics.DirectX~~~~0.0.1.0` on Powershell as an administrator.
- If global variables are needed in a C++ Project in VS, it's better to declare them in an **xxx.h** file and **not** initialize them right there. The initialization of these global vars shall be in the correlated **xxx.cpp** file. Or it will cause error of repeated symbol.

Like this:

```cpp
// .h File
extern int a;

// .cpp File
extern int a = 0;
```
