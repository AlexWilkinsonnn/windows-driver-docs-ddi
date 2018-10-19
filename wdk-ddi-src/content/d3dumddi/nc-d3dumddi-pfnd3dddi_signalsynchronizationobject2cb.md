---
UID: NC:d3dumddi.PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECT2CB
title: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECT2CB
author: windows-driver-content
description: Inserts a signal on the specified synchronization objects in the specified context direct memory access (DMA) stream. Used by WDDM 1.2 and later user-mode display drivers.
old-location: display\pfnsignalsynchronizationobject2cb.htm
tech.root: display
ms.assetid: 01B5E793-D075-42B5-9ADF-D033249AEE9F
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECT2CB, PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECT2CB callback, d3dumddi/pfnSignalSynchronizationObject2Cb, display.pfnsignalsynchronizationobject2cb, pfnSignalSynchronizationObject2Cb, pfnSignalSynchronizationObject2Cb callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	d3dumddi.h
api_name:
-	pfnSignalSynchronizationObject2Cb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECT2CB callback function


## -description


Inserts a signal on the specified synchronization objects in the specified context direct memory access (DMA) stream. Used by WDDM 1.2 and later user-mode display drivers.


## -parameters




### -param hDevice [in]

A handle to a display device (that is, the graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451164">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2</a> structure that describes the synchronization objects and context DMA stream that signaling is set up on. 


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
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The signaling was successfully set up.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other HRESULT values.




## -remarks



The <a href="https://msdn.microsoft.com/9B0F058C-B71F-4A4F-A053-F9381A5FD3A8">pfnCreateSynchronizationObject2Cb</a> function returns a kernel-mode handle to the newly created synchronization object in the <b>hSyncObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451156">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a> structure that the <i>pData</i> parameter points to. The user-mode display driver passes this handle in calls to the following functions:

<ul>
<li>

<a href="https://msdn.microsoft.com/7ba549a2-f165-4b5e-8cf4-ab707222532c">pfnDestroySynchronizationObjectCb</a>


</li>
<li>
<i>pfnSignalSynchronizationObject2Cb</i>

</li>
<li>

<a href="https://msdn.microsoft.com/4542C49F-C26C-45BE-B961-C5F65BDA78CF">pfnWaitForSynchronizationObject2Cb</a>


</li>
</ul>
The <i>pfnSignalSynchronizationObject2Cb</i> function submits a signal command to the command stream of all Microsoft Direct3D contexts that are specified by the <b>hContext</b> and <b>BroadcastContext</b> members of the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451164">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2</a> structure. The synchronization objects are signaled only when all submitted signal commands are processed.

If synchronization objects are of type <b>D3DDDI_FENCE</b> (where <a href="https://msdn.microsoft.com/library/windows/hardware/ff544658">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>.<b>Type</b> = <b>D3DDDI_FENCE</b>), they must be submitted only one at a time, and <a href="https://msdn.microsoft.com/library/windows/hardware/hh451164">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2</a>.<i>ObjectCount</i> must have a value of 1.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451156">D3DDDICB_CREATESYNCHRONIZATIONOBJECT2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451164">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2</a>



<a href="https://msdn.microsoft.com/9B0F058C-B71F-4A4F-A053-F9381A5FD3A8">pfnCreateSynchronizationObject2Cb</a>



<a href="https://msdn.microsoft.com/7ba549a2-f165-4b5e-8cf4-ab707222532c">pfnDestroySynchronizationObjectCb</a>



<a href="https://msdn.microsoft.com/4542C49F-C26C-45BE-B961-C5F65BDA78CF">pfnWaitForSynchronizationObject2Cb</a>
 

 

