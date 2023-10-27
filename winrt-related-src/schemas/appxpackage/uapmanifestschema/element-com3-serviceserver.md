---
title: com3:ServiceServer
description: "Learn more about: com3:ServiceServer"
ms.date: 04/04/2020
ms.topic: reference
keywords: windows 10, uwp, schema, manifest, com
---

# com3:ServiceServer

Registers a COM server (with one or more class registrations) hosted in a Windows service that is declared with a corresponding [desktop6:Service](element-desktop6-service.md) element.

## Element hierarchy

[\<Package\>](element-package.md)

&nbsp;&nbsp;&nbsp;&nbsp;[\<Applications\>](element-applications.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<Application\>](element-application.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<Extensions\>](element-1-extensions.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<com2:Extension\>](element-com2-extension.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[\<com2:ComServer\>](element-com2-comserver.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;**\<com3:ServiceServer\>**

## Syntax

```xml
<com3:ServiceServer
    ServiceName = 'A string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end.'
    Arguments = 'A string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end.'
    DisplayName = 'An optional string with a value between 1 and 256 characters in length. This string is localizable.'
    LaunchAndActivationPermission = 'An optional [SDDL string](/windows/win32/secauthz/security-descriptor-string-format) value.' >

  <!-- Child elements -->
  com3:Class{1,10000}

</com3ServiceServer>
```

## Key

`{}`   specific range of occurrences

## Attributes and elements

### Attributes

| Attribute | Description | Data type | Required | Default value |
|-|-|-|-|-|
| **ServiceName** | The name of the Windows service that hosts the COM server. This service name must match the name of a corresponding [desktop6:Service](element-desktop6-service.md) element in the same application-level [Extensions](element-1-extensions.md) element in the package manifest. | A string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end. | Yes |  |
| **Arguments** | The command-line parameters of the service. | A string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end. | No |  |
| **DisplayName** | A localizable string corresponding to the default AppID key value. | An optional string with a value between 1 and 256 characters in length. | No |  |
| **LaunchAndActivationPermission** | An [SDDL string](/windows/win32/secauthz/security-descriptor-string-format) that corresponds to the LaunchPermission value of the AppID key. | An optional [SDDL string](/windows/win32/secauthz/security-descriptor-string-format) value. | No |  |

### Child elements

| Child element | Description |
|-|-|
| [com3:Class](element-com3-class.md) | Defines a class registration for the COM server. |

### Parent elements

| Parent element | Description |
|-|-|
| [com2:ComServer](element-com2-comserver.md) | Declares a package extension point of type **windows.comServer**. The **comServer** extension may include the following types of registrations: *ServiceServer*, *ExeServer*, *SurrogateServer*, *ProgId*, or *TreatAsClass*. |

## Remarks

A **ServiceServer** can have one or more class registrations. Multiple class registrations should share a **ServiceServer** if their [LocalService](/windows/win32/com/localservice) keys match and they have the same [AppID](/windows/win32/com/appid) (or if they don't have an AppID), unless they need to be registered under different Applications/Application manifest elements.

## Examples

```xml
<?xml version="1.0" encoding="utf-8"?>
<Package IgnorableNamespaces="uap com com2 com3 desktop6"
         xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
         xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10"
         xmlns:desktop6="http://schemas.microsoft.com/appx/manifest/desktop/windows10/6"
         xmlns:com="http://schemas.microsoft.com/appx/manifest/com/windows10"
         xmlns:com2="http://schemas.microsoft.com/appx/manifest/com/windows10/2"
         xmlns:com3="http://schemas.microsoft.com/appx/manifest/com/windows10/3">
...
    <Applications>
        <Application ...>
            <Extensions>
                <desktop6:Extension Category="windows.service" Executable="ContosoPackagedService.exe" EntryPoint="packagedServiceComServer.service">
                    <desktop6:Service Name="examplePackagedServiceComServer" StartupType="manual" StartAccount="localService" /> 
                </desktop6:Extension>
                <com2:Extension Category="windows.comServer">
                    <com2:ComServer>
                        <com3:ServiceServer ServiceName="examplePackagedServiceComServer" DisplayName="ServicePackage public service server" 
                            LaunchAndActivationPermission="O:SYG:SYD:(A;;11;;;WD)(A;;11;;;RC)(A;;11;;;AC)(A;;11;;;AN)S:P(ML;;NX;;;S-1-16-0)">
                            <com3:Class Id="1BB09D24-6A0F-4C1F-BCB5-FB924324B2F5" DisplayName="CLSID_ContosoPublicServiceNoHandler"/>
                        </com3:ServiceServer>
                        <com3:TreatAsClass Id="2DAA3C97-F340-4C0E-B23C-92338974C5E9" DisplayName="CLSID_ContosoPublicServiceTreatAs" 
                            TreatAs="1BB09D24-6A0F-4C1F-BCB5-FB924324B2F5"/>
                        <com3:ProgId Id="ContosoPublicServiceNoHandler" Clsid="1BB09D24-6A0F-4C1F-BCB5-FB924324B2F5"/>
                        <com3:ProgId Id="ContosoPublicServiceNoHandler.1" CurrentVersion="ContosoPublicServiceNoHandler"/>
                    </com2:ComServer>
                </com2:Extension>
            </Extensions>
        </Application>
    </Applications>
</Package>
```

## Requirements

| Item | Value |
|--|--|
| **Namespace** | `http://schemas.microsoft.com/appx/manifest/com/windows10/3` |
| **Minimum OS Version** | Windows 10 version 2004 (Build 19041) |
