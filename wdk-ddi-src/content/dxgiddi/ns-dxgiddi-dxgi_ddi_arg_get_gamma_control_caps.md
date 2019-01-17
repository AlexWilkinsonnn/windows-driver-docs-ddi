---
UID: NS:dxgiddi.DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
title: DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
description: The DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure contains gamma capabilities.
old-location: display\dxgi_ddi_arg_get_gamma_control_caps.htm
tech.root: display
ms.assetid: 1e7930e4-ab3e-4981-9533-ed1da8c777dc
ms.date: 05/10/2018
ms.keywords: DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS, DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_770eb1ba-2972-4133-b899-a096a53fc1de.xml, display.dxgi_ddi_arg_get_gamma_control_caps, dxgiddi/DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	dxgiddi.h
api_name:
-	DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
---

# DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure


## -description


The DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure contains gamma capabilities. 


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) from which the driver retrieves gamma capabilities. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function to create the display device. 


### -field pGammaCapabilities

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557521">DXGI_GAMMA_CONTROL_CAPABILIITES</a> structure that describes gamma capabilities. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557521">DXGI_GAMMA_CONTROL_CAPABILIITES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566790">GetGammaCapsDXGI</a>
 

 

