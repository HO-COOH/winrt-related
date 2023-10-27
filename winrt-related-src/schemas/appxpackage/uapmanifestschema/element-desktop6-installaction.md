﻿---
title: desktop6:InstallAction
description: Specifies an installer file (.exe or .msi) that is run before the first launch of your desktop application.
ms.date: 01/22/2020
ms.topic: reference
keywords: windows 10, uwp, schema, manifest, desktop, extension 
ms.custom: 19H1
---

# desktop6:InstallAction

Specifies an installer file (.exe or .msi) that is run before the first launch of your desktop application.

> [!NOTE]
> This element is currently intended to be used only by desktop PC games that are packaged in an MSIXVC container. It requires the **customInstallActions** [restricted capability](/windows/uwp/packaging/app-capability-declarations#restricted-capabilities).

## Element hierarchy

[\<Package\>](element-package.md)

&nbsp;&nbsp;&nbsp;&nbsp;[\<Extensions\>](element-1-extensions.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<desktop6:Extension\>](element-desktop6-package-extension.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<desktop6:CustomInstall\>](element-desktop6-custominstall.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<desktop6:InstallActions\>](element-desktop6-installactions.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<desktop6:InstallAction\>**

## Syntax

```xml
<desktop6:InstallAction
  File = 'A string with a value between 1 and 256 characters in length that cannot contain these characters: <, >, :, ", |, ?, or *.'
  Name = 'A string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end.'
  Arguments = 'A string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end.' />
```

## Attributes and elements

### Attributes

| Attribute | Description | Data type | Required | Default value |
|-|-|-|-|-|
| **File** | The name of the file to execute (.exe or .msi). This file must exist in your package. You can specify a path that is relative to the *Folder* attribute of the [desktop6.CustomInstall](element-desktop6-custominstall.md) element. You cannot specify an absolute path, and the relative path must not start with a `\` character. | A string with a value between 1 and 256 characters in length that cannot contain these characters: `<`, `>`, `:`, `"`, `|`, `?`, or `*`. | Yes |  |
| **Name** | The name for the install action. This name is used to identify the install action, and the OS uses this name to track which actions have been successfully executed. Make sure that this value matches the `Name` attribute for the corresponding [desktop6:RepairAction](element-desktop6-repairaction.md) and [desktop6:UninstallAction](element-desktop6-uninstallaction.md) elements that you want to run as part of the same sequence. This name must be unique in the parent [desktop6:InstallActions](element-desktop6-installactions.md) element, but it can be shared by other actions under the [desktop6:RepairActions](element-desktop6-repairactions.md) and [desktop6:UninstallActions](element-desktop6-uninstallactions.md) elements. | A string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end. | Yes |  |
| **Arguments** | Optional arguments to pass to the installer file. | A string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end. | No |  |

### Child elements

None

### Parent elements

| Parent element | Description |
|-|-|
| [desktop6:InstallActions](element-desktop6-installactions.md) | Specifies installer files (.exe or .msi) that are run before the first launch of your desktop application.  |

## Remarks

This element requires the **customInstallActions** [restricted capability](/windows/uwp/packaging/app-capability-declarations#restricted-capabilities).

## Examples

```xml
<Package
  xmlns:desktop6="http://schemas.microsoft.com/appx/manifest/desktop/windows10/6"
  xmlns:rescap="http://schemas.microsoft.com/appx/manifest/foundation/windows10/restrictedcapabilities"
  IgnorableNamespaces="rescap desktop6">

  <!-- ... -->
  <!-- Other entries omitted for brevity. -->
  <!-- ... -->

  <Extensions>
    <desktop6:Extension Category="windows.customInstall">
      <desktop6:CustomInstall Folder="MyInstallers">
        <desktop6:InstallActions>
          <desktop6:InstallAction File="Setup_AntiCheat.exe" Name="AC_1" Arguments="/add /silent" />
        </desktop6:InstallActions>
        <desktop6:RepairActions>
          <desktop6:RepairAction File="Setup_AntiCheat.exe" Name="AC_1" Arguments="/add /silent /force" />
        </desktop6:RepairActions>
        <desktop6:UninstallActions>
          <desktop6:UninstallAction File="Setup_AntiCheat.exe" Name="AC_1" Arguments="/remove /silent" />
        </desktop6:UninstallActions>
      </desktop6:CustomInstall>
    </desktop6:Extension>
  </Extensions>

  <Capabilities>
    <rescap:Capability Name="customInstallActions"/>
  </Capabilities>
</Package>
```

## Requirements

| Item  | Value  |
|--|--|
| Namespace | `http://schemas.microsoft.com/appx/manifest/desktop/windows10/6` |
| **Minimum OS Version** | Windows 10 version 1903 (Build 18362) |
