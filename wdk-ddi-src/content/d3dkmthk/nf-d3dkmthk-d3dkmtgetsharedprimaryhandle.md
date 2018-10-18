---
UID: NF:d3dkmthk.D3DKMTGetSharedPrimaryHandle
title: D3DKMTGetSharedPrimaryHandle function
author: windows-driver-content
description: The D3DKMTGetSharedPrimaryHandle function retrieves the global shared handle for the primary surface.
old-location: display\d3dkmtgetsharedprimaryhandle.htm
ms.assetid: 927a6ddd-caac-4460-b9df-3ba22db69398
ms.date: 5/10/2018
ms.keywords: D3DKMTGetSharedPrimaryHandle, D3DKMTGetSharedPrimaryHandle function [Display Devices], OpenGL_Functions_bb0d000e-4846-4851-a6c5-c70330ef8921.xml, d3dkmthk/D3DKMTGetSharedPrimaryHandle, display.d3dkmtgetsharedprimaryhandle
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
-	D3DKMTGetSharedPrimaryHandle
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTGetSharedPrimaryHandle function


## -description


The <b>D3DKMTGetSharedPrimaryHandle</b> function retrieves the global shared handle for the primary surface.


## -parameters




### -param Arg1






*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548070">D3DKMT_GETSHAREDPRIMARYHANDLE</a> structure that describes the parameters that are required to retrieve the shared handle.


## -returns



<b>D3DKMTGetSharedPrimaryHandle</b> returns one of the following values:

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
The handle was successfully retrieved.

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
</table>
 

This function might also return other NTSTATUS values.




## -remarks



The primary surface is typically created by the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) every time the display mode changes (although, in some situations, the shared primary might not exist). If an OpenGL application attempts to create a primary surface, it typically must open the existing shared primary. To open the shared primary, the OpenGL application must use <b>D3DKMTGetSharedPrimaryHandle</b> to retrieve the global shared handle for the primary surface.

<b>Example</b>

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTGetSharedPrimaryHandle</b> to create a primary surface by opening the shared handle.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT OpenSharedPrimarySurface(D3DKMT_HANDLE hAdapter,
                                 D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId,
                                 D3DKMT_HANDLE hDevice, 
                                 VOID* pPrivateDriverData,
                                 UINT PrivateDriverDataSize,
                                 D3DKMT_HANDLE* phResource,
                                 D3DKMT_HANDLE* phAllocation)
{
    D3DKMT_CREATEALLOCATION CreateAllocation;
    D3DDDI_ALLOCATIONINFO AllocationInfo;
    D3DKMT_GETSHAREDPRIMARYHANDLE GetHandleData;

    *phResource = 0;
    *phAllocation = 0;

    // Get the shared handle.
    GetHandleData.hAdapter = hAdapter;
    GetHandleData.VidPnSourceId = VidPnSourceId;

    if (!NT_SUCCESS((*pfnKTGetSharedPrimaryHandle)(&amp;GetHandleData))) {
        return E_FAIL;
    }

    // Was a shared primary created by the kernel?
    if (GetHandleData.hSharedPrimary == NULL) {
        return E_FAIL;
    }

    CreateAllocation.hDevice = hDevice;
    CreateAllocation.hResource = NULL;
    CreateAllocation.hGlobalShare = GetHandleData.hSharedPrimary;
    CreateAllocation.Flags.CreateResource = 
    CreateAllocation.Flags.CreateShared = TRUE;
    CreateAllocation.pPrivateRuntimeData = NULL;
    CreateAllocation.PrivateRuntimeDataSize = 0;
    CreateAllocation.pPrivateDriverData = NULL;
    CreateAllocation.PrivateDriverDataSize = 0;
    CreateAllocation.NumAllocations = 1;
    CreateAllocation.pAllocationInfo = &amp;AllocationInfo;

    AllocationInfo.hAllocation = NULL;
    AllocationInfo.pSystemMem = NULL;
    AllocationInfo.pPrivateDriverData = pPrivateData;
    AllocationInfo.PrivateDriverDataSize = PrivateDataSize;

    if (NT_SUCCESS((*pfnKTCreateAllocation)(&amp;CreateAllocation))) {
        *phResource = CreateAllocation.hResource;
        *phAllocation = AllocationInfo.hAllocation;
        return S_OK;
    }
    return E_FAIL;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548070">D3DKMT_GETSHAREDPRIMARYHANDLE</a>
 

 

