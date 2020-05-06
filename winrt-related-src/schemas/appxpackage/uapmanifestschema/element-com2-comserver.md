---
title: com2:ComServer
description: Declares a package extension point of type windows.comServer.
ms.date: 04/04/2020
ms.topic: reference
keywords: windows 10, uwp, schema, manifest, com
---

# com2:ComServer

## Description

Declares a package extension point of type **windows.comServer**. The **comServer** extension may include the following types of registrations: **ServiceServer**, **ExeServer**, **SurrogateServer**, **ProgId**, or **TreatAsClass**.

## Element Hierarchy
<dl>
<dt><a href="element-package.md">&lt;Package&gt;</a></dt>
<dd>
<dl>
<dt><a href="element-applications.md">&lt;Applications&gt;</a></dt>
<dd>
<dl>
<dt><a href="element-application.md">&lt;Application&gt;</a></dt>
<dd>
<dl>
<dt><a href="element-1-extensions.md">&lt;Extensions&gt;</a></dt>
<dd>
<dl>
<dt><a href="element-com2-extension.md">&lt;com2:Extension&gt;</a></dt>
<dd><b>&lt;com2:ComServer&gt;</b></dd>
</dl>
</dd>
</dl>
</dd>
</dl>
</dd>
</dl>
</dd>
</dl>


## Syntax
```syntax
<com2:ComServer>
  <!-- Child elements -->
  ( com:ExeServer{0,1000},
  com:SurrogateServer{0,1000},
  com:ProgId{0,10000},
  com:TreatAsClass{0,10000},
  com3:ServiceServer{0,1000},
  com3:ExeServer{0,1000},
  com3:SurrogateServer{0,1000},
  com3:ProgId{0,10000},
  com3:TreatAsClass{0,10000}
  )
</com2:ComServer>
```

## Key
`{}`   specific range of occurrences

## Child Elements

| Child Element | Description |
|---------------|-------------|
| [ExeServer](element-com-exeserver.md) | Registers an ExeServer with one or many class registrations. |
| [SurrogateServer](element-com-surrogateserver.md) | Registers a SurrogateServer with one or many class registrations. |
| [ProgId](element-com-progid.md) | A programmatic identifier (ProgID) that can be associated with a CLSID. |
| [TreatAsClass](element-com-treatasclass.md) | A registration that corresponds to a CLSID registration with the TreatAs subkey. |
| [com3:ServiceServer](element-com3-serviceserver.md) | Registers a ServiceServer with one or many class registrations. |
| [com3:ExeServer](element-com3-exeserver.md) | Registers an ExeServer with one or many class registrations. |
| [com3:SurrogateServer](element-com3-surrogateserver.md) | Registers an SurrogateServer with one or many class registrations. |
| [com3:ProgId](element-com3-progid.md) | A programmatic identifier (ProgID) that can be associated with a CLSID. |
| [com3:TreatAsClass](element-com3-treatasclass.md) | A registration that corresponds to a CLSID registration with the TreatAs subkey. |


## Remarks
In multi-application packages, it's important to place the COM server registration under the correct Applications/Application manifest element, because COM server processes will run with the identity of the ancestor Applications/Application element.

COM servers registered in the manifest always get Activate As Package (AAP) behavior, which means the COM server runs with the user session default token with package and application claims added. This is different from the default activation behavior of classically registered COM servers, in which the COM server runs with the client's token. For most applications, this difference will not be noticeable because clients typically run with the user session default token. Other activation behaviors, such as [RunAs]( https://msdn.microsoft.com/library/windows/desktop/ms680046.aspx), are not supported.

> [!NOTE]
> Any registrations in **comServer** that depend on another registration (e.g. a **ProgId** references a **Class**) must be in the same **comServer** extension. 

It is possible to have multiple **comServer** extensions under the Applications/Application element, but that is neither necessary nor recommended.

## Requirements

|               |                                                             |
|---------------|-------------------------------------------------------------|
| **Namespace** | `http://schemas.microsoft.com/appx/manifest/com/windows10/2`<br/><br/>`http://schemas.microsoft.com/appx/manifest/com/windows10/3` (for the **com3** elements) |
