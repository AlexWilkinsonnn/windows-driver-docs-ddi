---
UID: NC:d3dkmthk.PFND3DKMT_OUTPUTDUPLPRESENT
title: PFND3DKMT_OUTPUTDUPLPRESENT
author: windows-driver-content
description: Submits a present command from the Desktop Duplication API swapchain of the Desktop Window Manager (DWM) to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys).
old-location: display\d3dkmtoutputduplpresent.htm
ms.assetid: d5846165-f58d-44a8-9242-02a2f85d3a8d
ms.date: 05/10/2018
ms.keywords: D3DKMTOutputDuplPresent, D3DKMTOutputDuplPresent callback function [Display Devices], PFND3DKMT_OUTPUTDUPLPRESENT, PFND3DKMT_OUTPUTDUPLPRESENT callback, d3dkmthk/D3DKMTOutputDuplPresent, display.d3dkmtoutputduplpresent
ms.topic: callback
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmthk.h
api_name:
-	D3DKMTOutputDuplPresent
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DKMT_OUTPUTDUPLPRESENT callback function


## -description


Submits a present command from the <a href="https://msdn.microsoft.com/523FBFAD-5D78-4EE3-A3B7-8FD5BA39DC46">Desktop Duplication API</a> swapchain of the Desktop Window Manager (DWM) to the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys).


## -parameters




### -param *

*pData* 

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406509">D3DKMT_OUTPUTDUPLPRESENT</a> structure that describes parameters for the present operation.


## -returns




       Returns one of the following values:

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
The present operation was successfully performed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display context was reset.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439432">D3DKMTOutputDuplPresent</a> could not complete because of insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_ALLOCATION_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The primary surface handle was invalidated because of a display mode change. If the OpenGL installable client driver (ICD) receives this error code, it should reopen or re-create the primary handle, replace all references in the command buffer to the old handle with the new handle, and then resubmit the buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_GPU_EXCEPTION_ON_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
An error occurred on the rendering device context that the <b>hContext</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh406509">D3DKMT_OUTPUTDUPLPRESENT</a> specifies. 

<div class="alert"><b>Note</b>    This error code does not indicate the initiation of a Timeout Detection and Recovery (TDR) process or that the GPU stopped responding.</div>
<div> </div>
For example, the DirectX graphics kernel subsystem puts a device into an error state if the display miniport driver indicated that a DMA buffer that was submitted from this device caused a fault or if the video memory manager could not page-in all of the allocations that are required for a DMA buffer even after splitting the DMA buffer. After a device is in an error state, it cannot perform any more operations and must be destroyed and re-created. The ICD can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546959">D3DKMTGetDeviceState</a> function to determine a more precise reason for the error. 

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546959">D3DKMTGetDeviceState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406509">D3DKMT_OUTPUTDUPLPRESENT</a>
 

 

