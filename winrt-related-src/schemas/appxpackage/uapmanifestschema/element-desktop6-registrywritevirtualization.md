---
description: Indicates whether virtualization for the registry is enabled for your desktop application.
title: desktop6:RegistryWriteVirtualization
keywords: windows 10, uwp, schema, package manifest
ms.topic: reference
ms.date: 04/19/2019
ms.custom: 19H1
---

# desktop6:RegistryWriteVirtualization

Indicates whether virtualization for the registry is enabled for your desktop application. If disabled, other apps can read or write the same registry entries as your application.

> [!NOTE]
> This element is currently intended to be used only by certain types of desktop PC games that are published by Microsoft and our partners. It requires the  **unvirtualizedResources** [restricted capability](/windows/uwp/packaging/app-capability-declarations#restricted-capabilities).

## Element hierarchy

[\<Package\>](element-package.md)

&nbsp;&nbsp;&nbsp;&nbsp;[\<Properties\>](element-properties.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;**\<desktop6:RegistryWriteVirtualization\>**

## Syntax

``` xml
<desktop6:RegistryWriteVirtualization>"enabled" -or- "disabled"</desktop6:RegistryWriteVirtualization>
```

## Value

This element can have the value **enabled** or **disabled**. The default is **enabled**.

## Attributes and Elements

### Attributes

None.

### Child elements

None.

### Parent elements

| Parent element | Description |
|-|-|
| [Properties](element-properties.md) | Defines additional metadata about the package including attributes that describe how the package appears to users.  |

## Remarks

This element requires the **unvirtualizedResources** [restricted capability](/windows/uwp/packaging/app-capability-declarations#restricted-capabilities).

## Requirements

| Item  | Value  |
|--|--|
| Namespace | `http://schemas.microsoft.com/appx/manifest/desktop/windows10/6` |
| **Minimum OS Version** | Windows 10 version 1903 (Build 18362) |
