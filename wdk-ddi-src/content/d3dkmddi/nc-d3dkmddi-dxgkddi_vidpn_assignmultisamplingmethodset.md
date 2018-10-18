---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET
title: DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET
author: windows-driver-content
description: The pfnAssignMultisamplingMethodSet function assigns a set of multisampling methods to a particular video present source in a specified VidPN.
old-location: display\dxgk_vidpn_interface_pfnassignmultisamplingmethodset.htm
ms.assetid: 607e3294-7399-446c-b07c-f0d5416b997e
ms.date: 5/10/2018
ms.keywords: DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET, DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET callback, VidPnFunctions_836f1c8f-1690-4be1-9b77-43a7379278bd.xml, d3dkmddi/pfnAssignMultisamplingMethodSet, display.dxgk_vidpn_interface_pfnassignmultisamplingmethodset, pfnAssignMultisamplingMethodSet, pfnAssignMultisamplingMethodSet callback function [Display Devices]
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	pfnAssignMultisamplingMethodSet
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPN_ASSIGNMULTISAMPLINGMETHODSET callback function


## -description


The <b>pfnAssignMultisamplingMethodSet</b> function assigns a set of multisampling methods to a particular video present source in a specified VidPN.


## -parameters




### -param hVidPn [in]

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a>.


### -param VidPnSourceId [in]

[in] An integer that identifies one of the video present sources associated with the VidPN object.


### -param NumMethods [in]

[in] The number of elements in the <i>pSupportedMethodSet</i> array.


### -param D3DDDI_MULTISAMPLINGMETHOD

[in] A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544594">D3DDDI_MULTISAMPLINGMETHOD</a> structures, each of which describes a multisampling method.


## -returns



The <b>pfnAssignMultisamplingMethodSet</b> function returns one of the following values.

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
The function succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPn</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE</b></dt>
</dl>
</td>
<td width="60%">
The identifier supplied in <i>VidPnSourceId</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
The function failed because it was unable to allocate enough memory.

</td>
</tr>
</table>
 

This function might also return other error codes that are defined in Ntstatus.h.




## -see-also




<a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a>
 

 

