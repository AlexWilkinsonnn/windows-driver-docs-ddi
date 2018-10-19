---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_DS_SRV_CB
title: PFND3D11DDI_STATE_DS_SRV_CB
author: windows-driver-content
description: The pfnStateDsSrvCb function causes the Microsoft Direct3D 11 runtime to refresh the constant shader resource view state for the domain shader.
old-location: display\pfnstatedssrvcb.htm
ms.assetid: 23f92c9a-7f2c-4340-ad5e-101b13883bea
ms.date: 05/10/2018
ms.keywords: PFND3D11DDI_STATE_DS_SRV_CB, PFND3D11DDI_STATE_DS_SRV_CB callback, d3d10umddi/pfnStateDsSrvCb, d3d11state_functions_bbd5c336-5316-47d4-a8c9-f7b79b18b540.xml, display.pfnstatedssrvcb, pfnStateDsSrvCb, pfnStateDsSrvCb callback function [Display Devices]
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnStateDsSrvCb is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
api_name:
-	pfnStateDsSrvCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_STATE_DS_SRV_CB callback function


## -description


The <b>pfnStateDsSrvCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the constant shader resource view state for the domain shader. 


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D runtime. This handle is supplied to the driver in a call to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function. 

### -param Arg2

Base [in]

The beginning resource view for which the runtime should refresh state.

### -param Arg3

Count [in]

The total number of resource views. The number can be -1, which specifies that the Direct3D runtime uses its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value.



## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542137">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>
 

 

