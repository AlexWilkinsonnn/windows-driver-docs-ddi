---
UID: NS:usbfnattach._USBFN_ON_ATTACH
title: "_USBFN_ON_ATTACH"
author: windows-driver-content
description: Describes the detected port type and attach action.
old-location: buses\usbfn_on_attach.htm
tech.root: usbref
ms.assetid: 2CD75FA9-F77E-4AC5-870E-69CF05DB9312
ms.date: 05/07/2018
ms.keywords: "*PUSBFN_ON_ATTACH, PUSBFN_ON_ATTACH, PUSBFN_ON_ATTACH structure pointer [Buses], USBFN_ON_ATTACH, USBFN_ON_ATTACH structure [Buses], _USBFN_ON_ATTACH, buses.usbfn_on_attach, usbfnattach/PUSBFN_ON_ATTACH, usbfnattach/USBFN_ON_ATTACH"
ms.topic: struct
req.header: usbfnattach.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnattach.h
api_name:
-	USBFN_ON_ATTACH
product:
- Windows
targetos: Windows
req.typenames: USBFN_ON_ATTACH, *PUSBFN_ON_ATTACH
---

# _USBFN_ON_ATTACH structure


## -description


Describes the detected port type and attach action. 


## -struct-fields




### -field PortType

Detected port type defined by one of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188004">USBFN_PORT_TYPE</a>-typed values.


### -field AttachAction

The operation that must be performed depending on the port type. This value is defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187985">USBFN_ATTACH_ACTION</a> enumeration.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187995">USBFN_GET_ATTACH_ACTION</a>
 

 

