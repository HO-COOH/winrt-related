---
ms.assetid: fcc97808-4b2a-4caa-9a29-41b73012e9c8
title: uap2:Verb
description: Defines the verbs associated with a file context menu (uap2:Verb).
ms.date: 04/05/2017
ms.topic: reference
keywords: windows 10, uwp, schema, manifest, desktop, extension 
---

# uap2:Verb

Defines the verbs associated with a file context menu and enables Windows Desktop Bridge apps to use ddeexec to launch.

## Element hierarchy

[\<Package\>](element-package.md)

&nbsp;&nbsp;&nbsp;&nbsp;[\<Applications\>](element-applications.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<Application\>](element-application.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<Extensions\>](element-1-extensions.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<uap:Extension\>](element-uap-extension.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<uap:FileTypeAssociation\>](element-uap-filetypeassociation.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<uap2:SupportedVerbs\>](element-uap2-supportedverbs.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;**\<uap2:Verb\>**

## Syntax

```xml
<uap2:Verb
  Id = 'An alphanumeric string with a value between 3 and 64 characters in length.'
  Extended = 'An optional boolean value.'
  rescap3:DdeExecCommand = 'An optional string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end.'
  rescap3:DdeExecApplication = 'An optional string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end.'
  rescap3:DdeExecTopic = 'An optional string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end.'
  rescap3:DdeExecIfExec = 'An optional string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end.'
  uap7:Default = 'An optional boolean value.' >
```

### Key

`?` optional (zero or one)

## Attributes and elements

### Attributes

| Attribute | Description | Data type | Required | Default value |
|-|-|-|-|-|
| **Id** | The name of the verb. | An alphanumeric string with a value between 3 and 64 characters in length. | Yes |  |
| **Extended** | Specifies that the verb should only appear if the user holds the *Shift* key before right-clicking the file to show the context menu. | An optional boolean value. | No |  |
| **rescap3:DdeExecCommand** | A DDE command string. | An optional string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end. | No |  |
| **rescap3:DdeExecApplication** | An application name used to establish the DDE conversion. | An optional string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end. | No |  |
| **rescap3:DdeExecTopic** | The topic name of the DDE conversion. | An optional string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end. | No |  |
| **rescap3:DdeExecIfExec** | The DDE command used if DDE conversion cannot be executed. | An optional string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end. | No |  |
| **uap7:Default** | Specifies whether the verb is the default verb. Only one verb within **SupportedVerbs** can be set as the default verb. | An optional boolean value. | No | False |

### Child elements

None.

### Parent elements

| Parent element | Description |
|-|-|
| [uap2:SupportedVerbs](element-uap2-supportedverbs.md) | Contains verbs for a file context menu. |

## Requirements

| Item | Value |
|--|--|
| **Namespace** | `http://schemas.microsoft.com/appx/manifest/uap/windows10/2`
| Minimum OS Version | Windows 10 version 1511 (Build 10586) |
