---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO
title: DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO
author: windows-driver-content
description: The pfnCreateNewPathInfo function returns a pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure that the display miniport driver populates before calling pfnAddPath.
old-location: display\dxgk_vidpntopology_interface_pfncreatenewpathinfo.htm
ms.assetid: 2d9a4e10-514d-4ea9-9d60-0bbb7cdca29d
ms.date: 5/10/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO, DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO callback, VidPnFunctions_50591912-0f93-4049-a230-1fc5d96b2132.xml, d3dkmddi/pfnCreateNewPathInfo, display.dxgk_vidpntopology_interface_pfncreatenewpathinfo, pfnCreateNewPathInfo, pfnCreateNewPathInfo callback function [Display Devices]
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
-	pfnCreateNewPathInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO callback function


## -description


The <b>pfnCreateNewPathInfo</b> function returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a> structure that the display miniport driver populates before calling <a href="https://msdn.microsoft.com/893e0be1-aa29-429a-a3ca-a9f19053fd92">pfnAddPath</a>.


## -parameters




### -param hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/2bc43cd0-97a2-4120-8e6f-425664d3d28c">pfnGetTopology</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param ppNewVidPnPresentPathInfo [out]

[out] A pointer to a variable that receives a pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure allocated by the VidPN manager.


## -returns



The <b>pfnCreateNewPathInfo</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnTopology </i>was invalid.

</td>
</tr>
</table>
 




## -remarks



After you call <b>pfnCreateNewPathInfo</b> to obtain a D3DKMDT_VIDPN_PRESENT_PATH structure, you must do one, but not both, of the following:

<ul>
<li>
Populate the structure and pass it to <a href="https://msdn.microsoft.com/893e0be1-aa29-429a-a3ca-a9f19053fd92">pfnAddPath</a>.

</li>
<li>
Release the structure by calling <a href="https://msdn.microsoft.com/fdd34377-6b11-4005-93f1-ab42be7633c2">pfnReleasePathInfo</a>.

</li>
</ul>
The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://msdn.microsoft.com/893e0be1-aa29-429a-a3ca-a9f19053fd92">pfnAddPath</a>



<a href="https://msdn.microsoft.com/fdd34377-6b11-4005-93f1-ab42be7633c2">pfnReleasePathInfo</a>
 

 

