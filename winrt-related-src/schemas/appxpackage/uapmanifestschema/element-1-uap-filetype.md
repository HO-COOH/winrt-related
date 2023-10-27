---
description: A file type specified as its file type extension (in uap:ShareTarget/uap:SupportedFileTypes).
Search.Product: eADQiWindows 10XVcnh
title: uap:FileType (in uap:ShareTarget/uap:SupportedFileTypes)
ms.assetid: cc88b643-eb73-4d25-b51c-ebbd1a338c5a
keywords: windows 10, uwp, schema, package manifest
ms.topic: reference
ms.date: 04/05/2017
---

# uap:FileType (in uap:ShareTarget/uap:SupportedFileTypes) 

A file type specified as its file type extension. It is unique per application in the package and is case sensitive.

## Element hierarchy

[\<Package\>](element-package.md)

&nbsp;&nbsp;&nbsp;&nbsp; [\<Applications\>](element-applications.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<Application\>](element-application.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<Extensions\>](element-extensions.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<uap:Extension\>](element-uap-extension.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<uap:ShareTarget\>](element-uap-sharetarget.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<uap:FileOpenPicker\>](element-uap-fileopenpicker.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;**\<uap:FileType\>**

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<uap:FileSavePicker\>](element-uap-filesavepicker.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;**\<uap:FileType\>**

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<uap:SupportedFileTypes\>](element-uap-supportedfiletypes.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;**\<uap:FileType\>**

## Syntax

```xml
<uap:FileType>
  <!-- A string between 1 and 64 characters in length that must begin with a period ("."), cannot have additional periods, and cannot contain these characters: <, >, :, ", /, \, |, ?, or *. -->
</uap:FileType>
```

## Attributes and elements

### Attributes

None.

### Child elements

None.

### Parent elements

| Parent element | Description |
|-|-|
| [uap:SupportedFileTypes (type: CT_CharmsSupportedFileTypes)](element-1-uap-supportedfiletypes.md) | Defines the file types that the app can share. |

## Related elements

The following elements have the same name as this one, but different content or attributes:

- **[uap:FileType (type: CT_FTASupportedFileTypes)](element-uap-filetype.md)**

## Examples

```xml
<uap:ShareTarget>
  <uap:SupportedFileTypes>
    <uap:FileType>.txt</uap:FileType>
    <uap:FileType>.html</uap:FileType>
  </uap:SupportedFileTypes>
  <uap:DataFormat>Text</uap:DataFormat>
  <uap:DataFormat>Uri</uap:DataFormat>
</uap:ShareTarget>
```

## Requirements

| Item  | Value  |
|--|--|
| Namespace | `http://schemas.microsoft.com/appx/manifest/uap/windows10` |
| **Minimum OS Version** | Windows 10 version 1511 (Build 10586) |
