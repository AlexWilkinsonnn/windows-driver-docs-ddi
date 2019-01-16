---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEDEVICE_0003
title: PFND3D12DDI_CREATEDEVICE_0003
description: The PFND3D12DDI_CREATEDEVICE_0003 function creates a graphics context that is referenced in subsequent calls.
old-location: display\pfnd3d12ddi_createdevice_0003.htm
ms.assetid: 5F25CFE0-00C5-45CD-8EA1-50F01BA4EA0B
ms.date: 05/10/2018
ms.keywords: PFND3D12DDI_CREATEDEVICE_0003, PFND3D12DDI_CREATEDEVICE_0003 callback, PFND3D12DDI_CREATEDEVICE_0003 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATEDEVICE_0003, display.pfnd3d12ddi_createdevice_0003
ms.topic: callback
req.header: d3d12umddi.h
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
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_CREATEDEVICE_0003
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_CREATEDEVICE_0003 callback function


## -description


The PFND3D12DDI_CREATEDEVICE_0003 function creates a graphics context that is referenced in subsequent calls.


## -parameters




### -param Arg1

A handle to the graphics adapter object that was created with the <a href="https://msdn.microsoft.com/library/windows/hardware/mt779071">PFND3D12DDI_OPENADAPTER</a> function.

### -param *


A pointer to a <a href="https://msdn.microsoft.com/F139A61B-E074-4185-A934-17F6FDBA3F62">D3D12DDIARG_CREATEDEVICE</a> structure.



## -returns

PFND3D12DDI_CREATEDEVICE_0003 returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The graphics context was successfully created. | 
| **DXGI_STATUS_NO_REDIRECTION** | The graphics context was successfully created. However, the DirectX Graphics Infrastructure (DXGI) should not use the shared resource presentation path to effect communication with the Desktop Windows Manager (DWM). For more information about the DXGI DDI, see [Supporting the DXGI DDI](https://msdn.microsoft.com/3a49d7cb-984f-4e4f-a549-5c0442e1c45a) . | 
| **E_OUTOFMEMORY** |             PFND3D12DDI_CREATEDEVICE_0003 could not allocate the memory that was required for it to complete. |

 



