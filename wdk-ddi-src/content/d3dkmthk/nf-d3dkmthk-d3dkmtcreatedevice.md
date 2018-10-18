---
UID: NF:d3dkmthk.D3DKMTCreateDevice
title: D3DKMTCreateDevice function
author: windows-driver-content
description: The D3DKMTCreateDevice function creates a kernel-mode device context.
old-location: display\d3dkmtcreatedevice.htm
ms.assetid: 91f559cc-c84b-450d-b52c-8289e976f991
ms.date: 5/10/2018
ms.keywords: D3DKMTCreateDevice, D3DKMTCreateDevice callback function [Display Devices], OpenGL_Functions_09099f43-bae3-4859-9465-434915af774a.xml, PFND3DKMT_CREATEDEVICE, PFND3DKMT_CREATEDEVICE callback, d3dkmthk/D3DKMTCreateDevice, display.d3dkmtcreatedevice
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib 
req.dll: Gdi32.dll 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
api_name:
-	D3DKMTCreateDevice
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTCreateDevice function


## -description


The <b>D3DKMTCreateDevice</b> function creates a kernel-mode device context.


## -parameters




### -param Arg1






*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547819">D3DKMT_CREATEDEVICE</a> structure that describes the kernel-mode device context.


## -returns



<b>D3DKMTCreateDevice</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The device context was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546836">D3DKMTCreateDevice</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547819">D3DKMT_CREATEDEVICE</a>
 

 

