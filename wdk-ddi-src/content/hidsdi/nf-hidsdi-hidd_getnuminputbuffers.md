---
UID: NF:hidsdi.HidD_GetNumInputBuffers
title: HidD_GetNumInputBuffers function
description: The HidD_GetNumInputBuffers routine returns the current size, in number of reports, of the ring buffer that the HID class driver uses to queue input reports from a specified top-level collection.
old-location: hid\hidd_getnuminputbuffers.htm
tech.root: hid
ms.assetid: f9ed28a5-835c-47c8-b9cf-888785013b69
ms.date: 04/30/2018
ms.keywords: HidD_GetNumInputBuffers, HidD_GetNumInputBuffers routine [Human Input Devices], hid.hidd_getnuminputbuffers, hidfunc_addf7040-0b62-45bc-8b43-1aa0157924e8.xml, hidsdi/HidD_GetNumInputBuffers
ms.topic: function
req.header: hidsdi.h
req.include-header: Hidsdi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hid.lib
req.dll: Hid.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hid.dll
api_name:
-	HidD_GetNumInputBuffers
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidD_GetNumInputBuffers function


## -description


The <b>HidD_GetNumInputBuffers</b> routine returns the current size, in number of reports, of the ring buffer that the HID class driver uses to queue input reports from a specified <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.


## -parameters




### -param HidDeviceObject [in]

Specifies an open handle to a top-level collection.


### -param NumberBuffers [out]

Pointer to a caller-allocated variable that the routine uses to return the maximum number of input reports the ring buffer can hold.


## -returns



<b>HidD_GetNumInputBuffers</b> returns <b>TRUE</b> if it succeeds; otherwise, it returns <b>FALSE</b>.




## -remarks



Only user-mode applications can call <b>HidD_GetNumInputBuffers</b>. Kernel-mode drivers can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541058">IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS</a> request.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539686">HidD_SetNumInputBuffers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541058">IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542087">IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS</a>
 

 

