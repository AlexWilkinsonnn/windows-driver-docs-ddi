---
UID: NC:d3dkmthk.PFND3DKMT_OPENKEYEDMUTEX2
title: PFND3DKMT_OPENKEYEDMUTEX2
author: windows-driver-content
description: Opens a keyed mutex object that includes private data.
old-location: display\d3dkmtopenkeyedmutex2.htm
ms.assetid: 33140445-e312-4495-990a-033a87598fa1
ms.date: 5/10/2018
ms.keywords: D3DKMTOpenKeyedMutex2, D3DKMTOpenKeyedMutex2 callback function [Display Devices], PFND3DKMT_OPENKEYEDMUTEX2, PFND3DKMT_OPENKEYEDMUTEX2 callback, d3dkmthk/D3DKMTOpenKeyedMutex2, display.d3dkmtopenkeyedmutex2
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
-	D3DKMTOpenKeyedMutex2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DKMT_OPENKEYEDMUTEX2 callback function


## -description


Opens a keyed mutex object that includes private data.


## -parameters




### -param *


*pData* 

[in, out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406490">D3DKMT_OPENKEYEDMUTEX2</a> structure that describes a keyed mutex object that includes private data.


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
The keyed mutex object was successfully opened. 

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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439405">D3DKMTOpenKeyedMutex2</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -remarks



<b>D3DKMTOpenKeyedMutex2</b> behaves like the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547054">D3DKMTOpenKeyedMutex</a> function but lets the caller specify private data to associate with the keyed mutex.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547054">D3DKMTOpenKeyedMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406490">D3DKMT_OPENKEYEDMUTEX2</a>
 

 

