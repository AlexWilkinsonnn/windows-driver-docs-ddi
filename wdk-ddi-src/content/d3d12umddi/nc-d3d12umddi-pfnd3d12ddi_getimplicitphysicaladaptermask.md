---
UID: NC:d3d12umddi.PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK
title: PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK
author: windows-driver-content
description: Get implicit physical adapter mask.
ms.assetid: c9f5b9fc-5d92-4e27-bad2-67bba6d1f7c3
ms.date: 
ms.topic: callback
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK callback function

## -description

Get implicit physical adapter mask.

## -prototype

```cpp
//Declaration

PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK Pfnd3d12ddiGetimplicitphysicaladaptermask; 

// Definition

UINT Pfnd3d12ddiGetimplicitphysicaladaptermask 
(
	 D3D12DDI_HDEVICE
)
{...}

PFND3D12DDI_GETIMPLICITPHYSICALADAPTERMASK 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 



## -returns

Returns UINT.

## -remarks




## -see-also
