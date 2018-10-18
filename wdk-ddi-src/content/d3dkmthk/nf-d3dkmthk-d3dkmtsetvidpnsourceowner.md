---
UID: NF:d3dkmthk.D3DKMTSetVidPnSourceOwner
title: D3DKMTSetVidPnSourceOwner function
author: windows-driver-content
description: The D3DKMTSetVidPnSourceOwner function sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN.
old-location: display\d3dkmtsetvidpnsourceowner.htm
ms.assetid: e75020cf-39b4-434c-b071-dc75de6cc81b
ms.date: 5/10/2018
ms.keywords: D3DKMTSetVidPnSourceOwner, D3DKMTSetVidPnSourceOwner function [Display Devices], OpenGL_Functions_3c0b89d9-b3d6-4668-a227-3bc7d0ed2f2f.xml, d3dkmthk/D3DKMTSetVidPnSourceOwner, display.d3dkmtsetvidpnsourceowner
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
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTSetVidPnSourceOwner
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTSetVidPnSourceOwner function


## -description


The <b>D3DKMTSetVidPnSourceOwner</b> function sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN.


## -parameters




### -param D3DKMT_SETVIDPNSOURCEOWNER






*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548317">D3DKMT_SETVIDPNSOURCEOWNER</a> structure that describes the parameters for setting or releasing.


## -returns



<b>D3DKMTSetVidPnSourceOwner</b> returns one of the following values:

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
The video present source was successfully set or released.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display device was reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_VIDPN_SOURCE_IN_USE</b></dt>
</dl>
</td>
<td width="60%">
The video present source that is specified by an element in the array that the  <b>pVidPnSourceId</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548317">D3DKMT_SETVIDPNSOURCEOWNER</a> specifies is already owned by a display mode manager (DMM) client and cannot be used until the client releases the video present source.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE</b></dt>
</dl>
</td>
<td width="60%">
The video present source that is specified by an element in the array that the  <b>pVidPnSourceId</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548317">D3DKMT_SETVIDPNSOURCEOWNER</a> specifies is invalid. 

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
</table>
 

This function might also return other NTSTATUS values.




## -remarks



To set ownership of video present sources, the OpenGL installable client driver (ICD) sets values in the array that the <b>pType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548317">D3DKMT_SETVIDPNSOURCEOWNER</a> structure specifies, identifiers of the video present sources in the array that the <b>pVidPnSourceId</b> member of D3DKMT_SETVIDPNSOURCEOWNER specifies, and the number of video present sources in the <b>VidPnSourceCount</b> member of D3DKMT_SETVIDPNSOURCEOWNER. 

To release ownership of any video present sources, the ICD sets <b>pType</b> and <b>pVidPnSourceId</b> to <b>NULL</b> and <b>VidPnSourceCount</b> to zero in D3DKMT_SETVIDPNSOURCEOWNER.

The ICD passes a pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548317">D3DKMT_SETVIDPNSOURCEOWNER</a> in the <i>pData</i> parameter in a call to <b>D3DKMTSetVidPnSourceOwner</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548317">D3DKMT_SETVIDPNSOURCEOWNER</a>
 

 

