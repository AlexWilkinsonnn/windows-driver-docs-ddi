---
UID: NS:d3d10umddi.D3D10DDI_CORELAYER_DEVICECALLBACKS
title: D3D10DDI_CORELAYER_DEVICECALLBACKS (d3d10umddi.h)
description: The D3D10DDI_CORELAYER_DEVICECALLBACKS structure contains Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.
old-location: display\d3d10ddi_corelayer_devicecallbacks.htm
ms.assetid: cced2221-7e8c-432a-9963-3b1de67037a3
ms.date: 05/10/2018
ms.keywords: D3D10DDI_CORELAYER_DEVICECALLBACKS, D3D10DDI_CORELAYER_DEVICECALLBACKS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_4c7782a0-4963-4f18-802e-98c8eb39c1a1.xml, d3d10umddi/D3D10DDI_CORELAYER_DEVICECALLBACKS, display.d3d10ddi_corelayer_devicecallbacks
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10DDI_CORELAYER_DEVICECALLBACKS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDI_CORELAYER_DEVICECALLBACKS
---

# D3D10DDI_CORELAYER_DEVICECALLBACKS structure


## -description


The D3D10DDI_CORELAYER_DEVICECALLBACKS structure contains Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.


## -struct-fields




### -field pfnSetErrorCb

A pointer to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, which the driver uses to send errors back to the Direct3D 10 runtime because many of the driver's functions (in <a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>) return void.


### -field pfnStateVsConstBufCb

A pointer to the <a href="https://msdn.microsoft.com/43aa7188-d6aa-4890-8eac-1342a984005b">pfnStateVsConstBufCb</a> function.


### -field pfnStatePsSrvCb

A pointer to the <a href="https://msdn.microsoft.com/ed49ce47-c56d-4d38-8f2c-562841b8e804">pfnStatePsSrvCb</a> function.


### -field pfnStatePsShaderCb

A pointer to the <a href="https://msdn.microsoft.com/0865e79e-7df9-4dc7-a655-4fbd0af72030">pfnStatePsShaderCb</a> function.


### -field pfnStatePsSamplerCb

A pointer to the <a href="https://msdn.microsoft.com/8cf25918-1acf-40b6-be51-2c1afc419f2a">pfnStatePsSamplerCb</a> function.


### -field pfnStateVsShaderCb

A pointer to the <a href="https://msdn.microsoft.com/f43f7dea-26a6-4e3f-99e2-5e3488a621b0">pfnStateVsShaderCb</a> function.


### -field pfnStatePsConstBufCb

A pointer to the <a href="https://msdn.microsoft.com/f4670f69-5154-4f6b-ba98-2b91a16e7b2f">pfnStatePsConstBufCb</a> function.


### -field pfnStateIaInputLayoutCb

A pointer to the <a href="https://msdn.microsoft.com/fce49c60-8573-4a28-9d1c-5cf33d260db3">pfnStateIaInputLayoutCb</a> function.


### -field pfnStateIaVertexBufCb

A pointer to the <a href="https://msdn.microsoft.com/15068932-b769-4027-986f-195b569a23eb">pfnStateIaVertexBufCb</a> function. 


### -field pfnStateIaIndexBufCb

A pointer to the <a href="https://msdn.microsoft.com/3925bf83-1900-4d88-8100-1ecaa952dead">pfnStateIaIndexBufCb</a> function. 


### -field pfnStateGsConstBufCb

A pointer to the <a href="https://msdn.microsoft.com/02468226-f0a4-4f24-a7f9-61a3b67dffb1">pfnStateGsConstBufCb</a> function. 


### -field pfnStateGsShaderCb

A pointer to the <a href="https://msdn.microsoft.com/2bcdc7bd-4327-4258-ad89-5e028cffd06b">pfnStateGsShaderCb</a> function. 


### -field pfnStateIaPrimitiveTopologyCb

A pointer to the <a href="https://msdn.microsoft.com/5a394a5b-afbc-41f5-8013-ab228e6284f9">pfnStateIaPrimitiveTopologyCb</a> function. 


### -field pfnStateVsSrvCb

A pointer to the <a href="https://msdn.microsoft.com/5102104e-b79c-40e5-87de-9ccf848288db">pfnStateVsSrvCb</a> function. 


### -field pfnStateVsSamplerCb

A pointer to the <a href="https://msdn.microsoft.com/5f5dd2ee-72fb-450c-850a-f5546401cd96">pfnStateVsSamplerCb</a> function. 


### -field pfnStateGsSrvCb

A pointer to the <a href="https://msdn.microsoft.com/4ab7444f-face-4ad0-a73c-18dd0b59a344">pfnStateGsSrvCb</a> function. 


### -field pfnStateGsSamplerCb

A pointer to the <a href="https://msdn.microsoft.com/086c565e-2747-4bbe-a9e1-af38373c3232">pfnStateGsSamplerCb</a> function. 


### -field pfnStateOmRenderTargetsCb

A pointer to the <a href="https://msdn.microsoft.com/d17cd31d-44a1-4f7d-82be-1201c0d5769f">pfnStateOmRenderTargetsCb</a> function. 


### -field pfnStateOmBlendStateCb

A pointer to the <a href="https://msdn.microsoft.com/3cec9d99-0d15-4c61-9de2-ab203a56441d">pfnStateOmBlendStateCb</a> function. 


### -field pfnStateOmDepthStateCb

A pointer to the <a href="https://msdn.microsoft.com/caa8ea5b-7167-444a-9d81-6e4ea9375dd6">pfnStateOmDepthStateCb</a> function. 


### -field pfnStateRsRastStateCb

A pointer to the <a href="https://msdn.microsoft.com/2ce213a6-8075-4ad9-9f58-204c2f7fd8d9">pfnStateRsRastStateCb</a> function. 


### -field pfnStateSoTargetsCb

A pointer to the <a href="https://msdn.microsoft.com/9000543b-00ab-4378-9fa5-d4fc7cb05b24">pfnStateSoTargetsCb</a> function. 


### -field pfnStateRsViewportsCb

A pointer to the <a href="https://msdn.microsoft.com/9390ddca-4658-4853-a45c-9fb306bbdef8">pfnStateRsViewportsCb</a> function. 


### -field pfnStateRsScissorCb

A pointer to the <a href="https://msdn.microsoft.com/4bb88e3c-2309-42f5-bc22-4c7182358e6e">pfnStateRsScissorCb</a> function. 


### -field pfnDisableDeferredStagingResourceDestruction

A pointer to the <a href="https://msdn.microsoft.com/f0328782-9b5b-44e6-ac58-7eb72685aa52">pfnDisableDeferredStagingResourceDestruction</a> function. By default, the Direct3D 10 runtime defers the destruction of staging resources until the driver indicates that the hardware no longer requires them. The driver can call this function to disable this feature if the driver does not require the deferred destruction functionality. 


### -field pfnStateTextFilterSizeCb

A pointer to the <a href="https://msdn.microsoft.com/f53f73bf-8297-4c56-81f9-443d10a6b701">pfnStateTextFilterSizeCb</a> function. 


## -remarks



Because the Direct3D 10 runtime might change the function pointers dynamically, the user-mode display driver cannot cache the function pointers directly. 

The driver uses the functions with "State" in their name to retrieve the current state of the pipeline. 




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>
 

 

