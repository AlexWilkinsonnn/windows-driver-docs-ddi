---
UID: NC:d3dumddi.PFND3DDDI_PRESENTCB
title: PFND3DDDI_PRESENTCB (d3dumddi.h)
description: The pfnPresentCb function copies content from a source allocation.
old-location: display\pfnpresentcb.htm
tech.root: display
ms.assetid: 460b9be5-5817-4225-9089-f86ad64f4554
ms.date: 05/10/2018
ms.keywords: D3Druntime_Functions_0c10afaf-9bcf-42d9-9bdf-0be67780875c.xml, PFND3DDDI_PRESENTCB, PFND3DDDI_PRESENTCB callback, d3dumddi/pfnPresentCb, display.pfnpresentcb, pfnPresentCb, pfnPresentCb callback function [Display Devices]
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dumddi.h
api_name:
- pfnPresentCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_PRESENTCB callback function


## -description


The <b>pfnPresentCb</b> function copies content from a source allocation.


## -parameters

### -param hDevice [in]

A handle to a display device (graphics context).


### -param *

*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544218">D3DDDICB_PRESENT</a> structure that describes the source allocation that content is copied from.


## -returns



<b>pfnPresentCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|Content was successfully copied.|
|E_OUTOFMEMORY|pfnPresentCb could not complete because of insufficient memory.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
 

This function might also return other HRESULT values.




## -remarks



The user-mode display driver sets the <b>hContext</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544218">D3DDDICB_PRESENT</a> structure that is pointed to by the <i>pData</i> parameter to a context that it previously created by calling the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function. The user-mode display driver must create at least one context when the Microsoft Direct3D runtime calls the driver's <a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a> or <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function to create a device. The Direct3D runtime sends the present operation to a created context.
     


<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnPresentCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.




#### Examples

The following code example shows how to color-fill a destination surface.

```cpp
    HRESULT hr=S_OK;
    // A color-fill request that does not have a source surface
    D3DDDICB_PRESENT    PresentCBData = {0};

    PresentCBData.hContext = m_sContexts[MULTI_ENGINE_NODE_3D].hContext;
    PresentCBData.hSrcAllocation = NULL;

    if (pPresent->hDstResource) {
        DWORD   dwDstSurf = ((DWORD)(DWORD_PTR)pPresent->hDstResource) + pPresent->DstSubResourceIndex;
        _ASSERT(dwDstSurf < m_RTbl.Size());
        m_RTbl[dwDstSurf].m_qwBatch = m_qwBatch;
        PresentCBData.hDstAllocation = R200GetSurfaceAllocHandle(m_pR200Ctx, dwDstSurf);
    }

    hr = m_d3dCallbacks.pfnPresentCb(m_hD3D, &PresentCBData);

    return hr;
```


## -see-also




<a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a>



<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544218">D3DDDICB_PRESENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>
 

 

