---
ms.assetid: e4acf38c-ec61-411a-bec1-388106202881
title: com:Format (in SurrogateServer/Class, child of com:ReadWritable)
description: Specifies the file format an application can read and write (activate as) (in SurrogateServer/Class).
ms.date: 03/29/2017
ms.topic: reference
keywords: windows 10, uwp, schema, manifest, com
---

# com:Format (in SurrogateServer/Class, child of com:ReadWritable)

Specifies the file format an application can read and write (activate as).

## Element hierarchy

[\<Package\>](element-package.md)

&nbsp;&nbsp;&nbsp;&nbsp;[\<Applications\>](element-applications.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<Application\>](element-application.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<Extensions\>](element-1-extensions.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<com:Extension\>](element-com-extension.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<com:ComServer\>](element-com-comserver.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<com:SurrogateServer\>](element-com-surrogateserver.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<com:Class\>](element-com-surrogateserver-class.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<com:Conversion\>](element-com-surrogate-conversion.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<com:Readwritable\>](element-com-surrogate-readwritable.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;**\<com:Format\>**

## Syntax

```xml
<com:Format
    FormatName = 'An optional string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end.'
    StandardFormat = 'An optional string value in hexadecimal format containing numbers or the letters a, b, c, d, e, or f (capital or lower case).' />
```

## Attributes and elements

### Attributes

| Attribute | Description | Data type | Required | Default value |
|-|-|-|-|-|
| **FormatName** | The string file format name. | A string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end. | No |  |
| **StandardFormat** | The hexadecimal file format name. | An optional string value in hexadecimal format containing numbers or the letters `a`, `b`, `c`, `d`, `e`, or `f` (capital or lower case). | No |  |

### Child elements

None.

### Parent elements

| Parent element | Description |
|-|-|
| [com:Readwriteable](element-com-surrogate-readwritable.md) | Specifies that an application can read and write files. |

## Remarks

> [!NOTE]
> **FormatName** and **StandardFormat** are mutually exclusive.

## Requirements

| Item  | Value  |
|--|--|
| **Namespace** | `http://schemas.microsoft.com/appx/manifest/com/windows10` |
| **Minimum OS Version** | Windows 10 version 1703 (Build 15063) |
