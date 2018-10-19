---
UID: NS:d3dumddi._DXVADDI_PRIVATEDATA
title: "_DXVADDI_PRIVATEDATA"
author: windows-driver-content
description: The DXVADDI_PRIVATEDATA structure describes data that is required for a particular decoder to operate.
old-location: display\dxvaddi_privatedata.htm
tech.root: display
ms.assetid: 51e520db-fbec-4c6b-a23c-4d401de9ae63
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_8d49dc5e-8eff-4b7a-aa44-20b4f784a70f.xml, DXVADDI_PRIVATEDATA, DXVADDI_PRIVATEDATA structure [Display Devices], _DXVADDI_PRIVATEDATA, d3dumddi/DXVADDI_PRIVATEDATA, display.dxvaddi_privatedata
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	DXVADDI_PRIVATEDATA
product:
- Windows
targetos: Windows
req.typenames: DXVADDI_PRIVATEDATA
---

# _DXVADDI_PRIVATEDATA structure


## -description


The DXVADDI_PRIVATEDATA structure describes data that is required for a particular decoder to operate. 


## -struct-fields




### -field pData

[in] A pointer to a buffer that contains decoder data.


### -field DataSize

[in] The size, in bytes, of the buffer that is pointed to by <b>pData</b>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542927">D3DDDIARG_CREATEDECODEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543001">D3DDDIARG_DECODEEXECUTE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543009">D3DDDIARG_DECODEEXTENSIONEXECUTE</a>
 

 

