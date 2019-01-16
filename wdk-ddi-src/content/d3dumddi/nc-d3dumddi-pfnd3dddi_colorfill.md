---
UID: NC:d3dumddi.PFND3DDDI_COLORFILL
title: PFND3DDDI_COLORFILL
description: The ColorFill function fills a rectangle on the surface with a particular color.
old-location: display\colorfill.htm
tech.root: display
ms.assetid: c120421d-6a10-4d37-b936-98dac75e236b
ms.date: 05/10/2018
ms.keywords: ColorFill, ColorFill callback function [Display Devices], PFND3DDDI_COLORFILL, PFND3DDDI_COLORFILL callback, UserModeDisplayDriver_Functions_ce1cba12-de0d-426d-981f-b95d58caa33d.xml, d3dumddi/ColorFill, display.colorfill
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	ColorFill
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_COLORFILL callback function


## -description


The <b>ColorFill</b> function fills a rectangle on the surface with a particular color.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *

*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542907">D3DDDIARG_COLORFILL</a> structure that describes the parameters of the color-fill operation.


## -returns



<b>ColorFill</b> returns S_OK or an appropriate error result if the color-fill operation is not successfully performed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542907">D3DDDIARG_COLORFILL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

