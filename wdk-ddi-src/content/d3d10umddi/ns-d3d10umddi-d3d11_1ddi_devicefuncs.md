---
UID: NS:d3d10umddi.D3D11_1DDI_DEVICEFUNCS
title: D3D11_1DDI_DEVICEFUNCS (d3d10umddi.h)
description: Contains functions that a user-mode display driver that is optimized for the Microsoft Direct3D version 11.1 runtime can implement to render graphics primitives and process state changes.
old-location: display\d3d11_1ddi_devicefuncs.htm
ms.assetid: 5429D886-4CC0-438D-AC9F-739159802062
ms.date: 05/10/2018
ms.keywords: D3D11_1DDI_DEVICEFUNCS, D3D11_1DDI_DEVICEFUNCS structure [Display Devices], d3d10umddi/D3D11_1DDI_DEVICEFUNCS, display.d3d11_1ddi_devicefuncs
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_DEVICEFUNCS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_DEVICEFUNCS
---

# D3D11_1DDI_DEVICEFUNCS structure


## -description


Contains functions that a user-mode display driver that is optimized for the Microsoft Direct3D version 11.1 runtime can implement to render graphics primitives and process state changes.


## -struct-fields




### -field pfnDefaultConstantBufferUpdateSubresourceUP

A pointer to the driver's <a href="https://msdn.microsoft.com/67FCC9A4-B3C5-46FC-83ED-CFFB8186328F">DefaultConstantBufferUpdateSubresourceUP(D3D11_1)</a> function.


### -field pfnVsSetConstantBuffers

A pointer to the driver's <a href="https://msdn.microsoft.com/82C277EF-7FC9-43AF-B84A-CB464AB7D73C">VsSetConstantBuffers(D3D11_1)</a> function.


### -field pfnPsSetShaderResources

A pointer to the driver's <a href="https://msdn.microsoft.com/e30aabdd-52b7-40c0-bb92-50cbabdc5e1f">PsSetShaderResources</a> function.


### -field pfnPsSetShader

A pointer to the driver's <a href="https://msdn.microsoft.com/bc6213cd-8e0c-4f10-8942-c42818b512dc">PsSetShader</a> function. 


### -field pfnPsSetSamplers

A pointer to the driver's <a href="https://msdn.microsoft.com/3c4b36a9-842c-45dd-a261-74b5ceed5b12">PsSetSamplers</a> function.


### -field pfnVsSetShader

A pointer to the driver's <a href="https://msdn.microsoft.com/6bcafd44-3503-44f7-8676-c27eda585f9d">VsSetShader</a> function.


### -field pfnDrawIndexed

A pointer to the driver's <a href="https://msdn.microsoft.com/d1097bb6-35ac-4069-ae05-b74c75a98e21">DrawIndexed</a> function.


### -field pfnDraw

A pointer to the driver's <a href="https://msdn.microsoft.com/7a6f1d56-12be-4185-97bf-06f265ee6fe3">Draw</a> function.


### -field pfnDynamicIABufferMapNoOverwrite

A pointer to the driver's <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function. For more information about whether to implement a separate <i>DynamicIABufferMapNoOverwrite</i> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnDynamicIABufferUnmap

A pointer to the driver's <a href="https://msdn.microsoft.com/fb2b714e-232d-40b2-88ad-ee8dcd70a057">ResourceUnmap</a> function. For more information about whether to implement a separate <i>DynamicIABufferUnmap</i> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a>. 


### -field pfnDynamicConstantBufferMapDiscard

A pointer to the driver's <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function. For more information about whether to implement a separate <i>DynamicConstantBufferMapDiscard</i> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnDynamicIABufferMapDiscard

A pointer to the driver's <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function. For more information about whether to implement a separate <i>DynamicIABufferMapDiscard</i> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnDynamicConstantBufferUnmap

A pointer to the driver's <a href="https://msdn.microsoft.com/fb2b714e-232d-40b2-88ad-ee8dcd70a057">ResourceUnmap</a> function. For more information about whether to implement a separate <i>DynamicConstantBufferUnmap</i> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a>. 


### -field pfnPsSetConstantBuffers

A pointer to the driver's <a href="https://msdn.microsoft.com/052CACD8-7812-42B8-A5DD-E6DCD7BFA3D7">PsSetConstantBuffers(D3D11_1)</a> function.


### -field pfnIaSetInputLayout

A pointer to the driver's <a href="https://msdn.microsoft.com/905e4e7f-5bc5-487f-8d82-4ebc2db66135">IaSetInputLayout</a> function.


### -field pfnIaSetVertexBuffers

A pointer to the driver's <a href="https://msdn.microsoft.com/3d5a7ea1-08c2-4594-93bc-97b985cd16dc">IaSetVertexBuffers</a> function.


### -field pfnIaSetIndexBuffer

A pointer to the driver's <a href="https://msdn.microsoft.com/042ebb72-b794-4cb8-9d81-bd52a785f1e0">IaSetIndexBuffer</a> function.


### -field pfnDrawIndexedInstanced

A pointer to the driver's <a href="https://msdn.microsoft.com/3dc64562-9dc0-4d43-835d-6fdd509435f8">DrawIndexedInstanced</a> function.


### -field pfnDrawInstanced

A pointer to the driver's <a href="https://msdn.microsoft.com/c539cf8b-e056-476a-9b23-7e360917a7d9">DrawInstanced</a> function.


### -field pfnDynamicResourceMapDiscard

A pointer to the driver's <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function. For more information about whether to implement a separate <i>DynamicResourceMapDiscard</i> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnDynamicResourceUnmap

A pointer to the driver's <a href="https://msdn.microsoft.com/fb2b714e-232d-40b2-88ad-ee8dcd70a057">ResourceUnmap</a> function. For more information about whether to implement a separate <i>DynamicResourceUnmap</i> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a>. 


### -field pfnGsSetConstantBuffers

A pointer to the driver's <a href="https://msdn.microsoft.com/9C7655F9-049E-47B7-90F4-D337D88C864E">GsSetConstantBuffers(D3D11_1)</a> function.


### -field pfnGsSetShader

A pointer to the driver's <a href="https://msdn.microsoft.com/9f40371d-4a74-4020-af8a-e3781d1bc632">GsSetShader</a> function.


### -field pfnIaSetTopology

A pointer to the driver's <a href="https://msdn.microsoft.com/c2ee9c8b-7e33-4fc9-9bd3-2b2984e94390">IaSetTopology</a> function.


### -field pfnStagingResourceMap

A pointer to the driver's <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function. For more information about whether to implement a separate <i>StagingResourceMap</i> function or to point to the multipurpose <i>ResourceMap</i>, see the Remarks section of <i>ResourceMap</i>. 


### -field pfnStagingResourceUnmap

A pointer to the driver's <a href="https://msdn.microsoft.com/fb2b714e-232d-40b2-88ad-ee8dcd70a057">ResourceUnmap</a> function. For more information about whether to implement a separate <i>StagingResourceUnmap</i> function or to point to the multipurpose <i>ResourceUnmap</i>, see the Remarks section of <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a>. 


### -field pfnVsSetShaderResources

A pointer to the driver's <a href="https://msdn.microsoft.com/4d432517-97f0-441f-ac49-0416ac19b319">VsSetShaderResources</a> function.


### -field pfnVsSetSamplers

A pointer to the driver's <a href="https://msdn.microsoft.com/3f2c08e2-8372-45a7-9d65-936889f21e27">VsSetSamplers</a> function.


### -field pfnGsSetShaderResources

A pointer to the driver's <a href="https://msdn.microsoft.com/b5cd87bb-7a08-444c-9120-d7ab79e512c5">GsSetShaderResources</a> function.


### -field pfnGsSetSamplers

A pointer to the driver's <a href="https://msdn.microsoft.com/a70b7b29-99d2-4e7e-aeb3-bf324d71ebaf">GsSetSamplers</a> function.


### -field pfnSetRenderTargets

A pointer to the driver's <a href="https://msdn.microsoft.com/cfe5f570-4e53-43ee-942d-56da8dfcfe80">SetRenderTargets(D3D11)</a> function.


### -field pfnShaderResourceViewReadAfterWriteHazard

A pointer to the driver's <a href="https://msdn.microsoft.com/bb391154-a9ff-4032-b86e-81fa4ea2e37c">ShaderResourceViewReadAfterWriteHazard</a> function.


### -field pfnResourceReadAfterWriteHazard

A pointer to the driver's <a href="https://msdn.microsoft.com/4d7dd4f5-9792-48cb-bf69-3903ac9dda75">ResourceReadAfterWriteHazard</a> function.


### -field pfnSetBlendState

A pointer to the driver's <a href="https://msdn.microsoft.com/8794413f-f4d5-4382-8886-2f0659d8a781">SetBlendState</a> function.


### -field pfnSetDepthStencilState

A pointer to the driver's <a href="https://msdn.microsoft.com/379f8113-b07c-4984-ba37-a06d6c21b9e9">SetDepthStencilState</a> function.


### -field pfnSetRasterizerState

A pointer to the driver's <a href="https://msdn.microsoft.com/8162c9c9-4ebd-45a9-adaf-576f25c3907e">SetRasterizerState</a> function.


### -field pfnQueryEnd

A pointer to the driver's <a href="https://msdn.microsoft.com/5a231d7e-7e47-40ad-99d1-82661dec41d0">QueryEnd</a> function.


### -field pfnQueryBegin

A pointer to the driver's <a href="https://msdn.microsoft.com/2f0a7462-83a6-47df-b5f6-b3706b875349">QueryBegin</a> function.


### -field pfnResourceCopyRegion

A pointer to the driver's <a href="https://msdn.microsoft.com/CA26FB37-1A4C-4057-90A5-64FFBE289E39">ResourceCopyRegion(D3D11_1)</a> function.


### -field pfnResourceUpdateSubresourceUP

A pointer to the driver's <a href="https://msdn.microsoft.com/7c2363ea-2191-4b99-94a2-d98a11ee8cce">ResourceUpdateSubresourceUP(D3D11_1)</a> function.


### -field pfnSoSetTargets

A pointer to the driver's <a href="https://msdn.microsoft.com/96f1c439-7323-456e-8c9c-793d8e0973d9">SoSetTargets</a> function.


### -field pfnDrawAuto

A pointer to the driver's <a href="https://msdn.microsoft.com/83d96dc0-dfd4-449e-9e14-18f354d44534">DrawAuto</a> function.


### -field pfnSetViewports

A pointer to the driver's <a href="https://msdn.microsoft.com/f5a55dd3-a8c4-4741-b99e-105021d79603">SetViewports</a> function.


### -field pfnSetScissorRects

A pointer to the driver's <a href="https://msdn.microsoft.com/ef61f50b-a82b-43df-865f-2f9d9ca906d4">SetScissorRects</a> function.


### -field pfnClearRenderTargetView

A pointer to the driver's <a href="https://msdn.microsoft.com/9dc95dd2-01ad-45d7-9e75-049026b25968">ClearRenderTargetView</a> function.


### -field pfnClearDepthStencilView

A pointer to the driver's <a href="https://msdn.microsoft.com/0474c154-1bec-4602-880c-ffdc48c738f0">ClearDepthStencilView</a> function.


### -field pfnSetPredication

A pointer to the driver's <a href="https://msdn.microsoft.com/df671478-859f-4ccd-9ab4-1986f9af10cf">SetPredication</a> function.


### -field pfnQueryGetData

A pointer to the driver's <a href="https://msdn.microsoft.com/78ee9813-e23e-4d46-acc4-f2fa88559b03">QueryGetData</a> function.


### -field pfnFlush

A pointer to the driver's <a href="https://msdn.microsoft.com/6f4bda19-2d51-4058-ba68-cbb5deb44a54">Flush(D3D11_1)</a> function.


### -field pfnGenMips

A pointer to the driver's <a href="https://msdn.microsoft.com/abd045f2-9c05-4579-8d80-aba31523157d">GenMips</a> function.


### -field pfnResourceCopy

A pointer to the driver's <a href="https://msdn.microsoft.com/9a837f42-0bea-4425-b693-dd7947ac24b1">ResourceCopy</a> function.


### -field pfnResourceResolveSubresource

A pointer to the driver's <a href="https://msdn.microsoft.com/f9f4a6e2-bc01-477f-a919-ec71871f665b">ResourceResolveSubresource</a> function.


### -field pfnResourceMap

A pointer to the driver's <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function.


### -field pfnResourceUnmap

A pointer to the driver's <a href="https://msdn.microsoft.com/fb2b714e-232d-40b2-88ad-ee8dcd70a057">ResourceUnmap</a> function.


### -field pfnResourceIsStagingBusy

A pointer to the driver's <a href="https://msdn.microsoft.com/df8498e2-a3b5-4bc8-b6d2-0d444f1d1485">ResourceIsStagingBusy</a> function.


### -field pfnRelocateDeviceFuncs

A pointer to the driver's <a href="https://msdn.microsoft.com/5d9f964e-5d7a-4b6c-977e-c718e3424f84">RelocateDeviceFuncs(D3D11_1)</a> function.


### -field pfnCalcPrivateResourceSize

A pointer to the driver's <a href="https://msdn.microsoft.com/3b3a2571-012e-4acd-b836-f52e7b88a2fb">CalcPrivateResourceSize(D3D11)</a> function.


### -field pfnCalcPrivateOpenedResourceSize

A pointer to the driver's <a href="https://msdn.microsoft.com/000688fb-6475-4dab-bb65-91c899a592a7">CalcPrivateOpenedResourceSize</a> function.


### -field pfnCreateResource

A pointer to the driver's <a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a> function.


### -field pfnOpenResource

A pointer to the driver's <a href="https://msdn.microsoft.com/95f6d1e5-0c85-41ce-ad6d-f10d5103e2eb">OpenResource(D3D10)</a> function.


### -field pfnDestroyResource

A pointer to the driver's <a href="https://msdn.microsoft.com/3ff77844-eeee-4fda-8798-2e240bc51379">DestroyResource(D3D10)</a> function.


### -field pfnCalcPrivateShaderResourceViewSize

A pointer to the driver's <a href="https://msdn.microsoft.com/894f6ef1-a5a4-40aa-9a07-f66da4ce7d81">CalcPrivateShaderResourceViewSize(D3D11)</a> function.


### -field pfnCreateShaderResourceView

A pointer to the driver's <a href="https://msdn.microsoft.com/7ca462c7-ec43-4af7-92c8-ed69e5d324e2">CreateShaderResourceView(D3D11)</a> function.


### -field pfnDestroyShaderResourceView

A pointer to the driver's <a href="https://msdn.microsoft.com/dcdfe76e-a392-4a76-91fe-03648fec1278">DestroyShaderResourceView</a> function.


### -field pfnCalcPrivateRenderTargetViewSize

A pointer to the driver's <a href="https://msdn.microsoft.com/14d85e4a-960c-4438-9360-a4f2677603b8">CalcPrivateRenderTargetViewSize</a> function.


### -field pfnCreateRenderTargetView

A pointer to the driver's <a href="https://msdn.microsoft.com/bf9fc732-5f9a-4fee-8ea0-19b140789463">CreateRenderTargetView</a> function.


### -field pfnDestroyRenderTargetView

A pointer to the driver's <a href="https://msdn.microsoft.com/ec04fed3-8e43-4f76-af82-b36c7029f0cc">DestroyRenderTargetView</a> function.


### -field pfnCalcPrivateDepthStencilViewSize

A pointer to the driver's <a href="https://msdn.microsoft.com/d92e3bde-9527-401e-aafd-4ba39603d4a7">CalcPrivateDepthStencilViewSize(D3D11)</a> function.


### -field pfnCreateDepthStencilView

A pointer to the driver's <a href="https://msdn.microsoft.com/cf4c34da-71df-4b49-b1c8-73d1a2dbc3cb">CreateDepthStencilView(D3D11)</a> function.


### -field pfnDestroyDepthStencilView

A pointer to the driver's <a href="https://msdn.microsoft.com/5cd2b7bd-0231-4f00-a54e-960b9bffa98e">DestroyDepthStencilView</a> function.


### -field pfnCalcPrivateElementLayoutSize

A pointer to the driver's <a href="https://msdn.microsoft.com/9fc80cea-8e4a-467a-b232-74333d2ceb5f">CalcPrivateElementLayoutSize</a> function.


### -field pfnCreateElementLayout

A pointer to the driver's <a href="https://msdn.microsoft.com/5af2189a-a064-4c62-be09-733c1d632983">CreateElementLayout</a> function.


### -field pfnDestroyElementLayout

A pointer to the driver's <a href="https://msdn.microsoft.com/8b6a07b5-5358-45d3-af42-84f8a6327535">DestroyElementLayout</a> function.


### -field pfnCalcPrivateBlendStateSize

A pointer to the driver's <a href="https://msdn.microsoft.com/e53bb658-ef6c-4f44-aa5a-8c641046f90d">CalcPrivateBlendStateSize(D3D11_1)</a> function.


### -field pfnCreateBlendState

A pointer to the driver's <a href="https://msdn.microsoft.com/5956412e-ae35-4960-afc0-a82c6a2aa9f1">CreateBlendState(D3D11_1)</a> function.


### -field pfnDestroyBlendState

A pointer to the driver's <a href="https://msdn.microsoft.com/56fc1ecf-fd4c-4d36-941b-8fa6cca3b6b4">DestroyBlendState</a> function.


### -field pfnCalcPrivateDepthStencilStateSize

A pointer to the driver's <a href="https://msdn.microsoft.com/dcc02e1e-97e0-4ccd-8329-8219cad5d09a">CalcPrivateDepthStencilStateSize</a> function.


### -field pfnCreateDepthStencilState

A pointer to the driver's <a href="https://msdn.microsoft.com/ed2da104-c4e8-43eb-80e0-10273b575020">CreateDepthStencilState</a> function.


### -field pfnDestroyDepthStencilState

A pointer to the driver's <a href="https://msdn.microsoft.com/5fc537f6-2507-4edd-bfa0-c011dd834a22">DestroyDepthStencilState</a> function.


### -field pfnCalcPrivateRasterizerStateSize

A pointer to the driver's <a href="https://msdn.microsoft.com/76d0228e-a6e5-425e-a2b6-7d719dbfa43d">CalcPrivateRasterizerStateSize(D3D11_1)</a> function.


### -field pfnCreateRasterizerState

A pointer to the driver's <a href="https://msdn.microsoft.com/5640e1c9-6a38-4eca-9048-0bc9ff66c43c">CreateRasterizerState(D3D11_1)</a> function.


### -field pfnDestroyRasterizerState

A pointer to the driver's <a href="https://msdn.microsoft.com/7d730528-dc97-4490-a9fa-3d7916eef2e6">DestroyRasterizerState</a> function.


### -field pfnCalcPrivateShaderSize

A pointer to the driver's <a href="https://msdn.microsoft.com/e23c267f-41df-47a6-ae43-3bbcb48fd300">CalcPrivateShaderSize(D3D11_1)</a> function.


### -field pfnCreateVertexShader

A pointer to the driver's <a href="https://msdn.microsoft.com/8da896d3-b80c-409a-a838-99eb71668a93">CreateVertexShader(D3D11_1)</a> function.


### -field pfnCreateGeometryShader

A pointer to the driver's <a href="https://msdn.microsoft.com/A0C3826D-E4F3-4169-A899-41C11006DE69">CreateGeometryShader(D3D11_1)</a> function.


### -field pfnCreatePixelShader

A pointer to the driver's <a href="https://msdn.microsoft.com/8b5d6d2e-6a08-4841-8df5-ca88368a4e26">CreatePixelShader(D3D11_1)</a> function.


### -field pfnCalcPrivateGeometryShaderWithStreamOutput

A pointer to the driver's <a href="https://msdn.microsoft.com/316e30b9-eb06-483c-a124-476b4308cf5f">CalcPrivateGeometryShaderWithStreamOutput(D3D11_1)</a> function.


### -field pfnCreateGeometryShaderWithStreamOutput

A pointer to the driver's <a href="https://msdn.microsoft.com/1d06ef38-4eb9-4129-b409-74bbd1951f92">CreateGeometryShaderWithStreamOutput(D3D11_1)</a> function.


### -field pfnDestroyShader

A pointer to the driver's <a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a> function.


### -field pfnCalcPrivateSamplerSize

A pointer to the driver's <a href="https://msdn.microsoft.com/7231ba65-f6ed-4b00-a61f-21d8fe26398f">CalcPrivateSamplerSize</a> function.


### -field pfnCreateSampler

A pointer to the driver's <a href="https://msdn.microsoft.com/603bb033-390b-4965-b6ea-6acc2c7a8fcf">CreateSampler</a> function.


### -field pfnDestroySampler

A pointer to the driver's <a href="https://msdn.microsoft.com/8e66de90-c336-43b4-b0ad-cb24cea3638c">DestroySampler</a> function.


### -field pfnCalcPrivateQuerySize

A pointer to the driver's <a href="https://msdn.microsoft.com/59a59aa8-085e-4bf8-8a6f-e08f2aecd894">CalcPrivateQuerySize</a> function.


### -field pfnCreateQuery

A pointer to the driver's <a href="https://msdn.microsoft.com/abe6a82f-1613-4c74-9e81-01939db74bfd">CreateQuery(D3D10)</a> function.


### -field pfnDestroyQuery

A pointer to the driver's <a href="https://msdn.microsoft.com/74bb85df-6d64-49e8-b431-2f4a9954eff2">DestroyQuery(D3D10)</a> function.


### -field pfnCheckFormatSupport

A pointer to the driver's <a href="https://msdn.microsoft.com/463ab1e5-08b1-45a1-b7d8-bdfacb3d4bdb">CheckFormatSupport</a> function.


### -field pfnCheckMultisampleQualityLevels

A pointer to the driver's <a href="https://msdn.microsoft.com/2b6a0ab8-f197-48c3-baf2-305b77b7e8b5">CheckMultisampleQualityLevels</a> function.


### -field pfnCheckCounterInfo

A pointer to the driver's <a href="https://msdn.microsoft.com/5dcea47c-aac7-46e5-afd5-c3390c3c5286">CheckCounterInfo</a> function.


### -field pfnCheckCounter

A pointer to the driver's <a href="https://msdn.microsoft.com/592a5146-a2fe-41d1-854b-df27a97bd513">CheckCounter</a> function.


### -field pfnDestroyDevice

A pointer to the driver's <a href="https://msdn.microsoft.com/90ada8c8-8ad8-4992-aac1-6eb7fdf3f249">DestroyDevice(D3D10)</a> function.


### -field pfnSetTextFilterSize

A pointer to the driver's <a href="https://msdn.microsoft.com/663fd3c3-7a8f-446d-b45a-392716116407">SetTextFilterSize</a> function.


### -field pfnResourceConvert

A pointer to the driver's <a href="https://msdn.microsoft.com/9a837f42-0bea-4425-b693-dd7947ac24b1">ResourceCopy</a> function. For more information about whether to implement a separate <i>ResourceConvert</i> function or to point to the multipurpose <i>ResourceCopy</i>, see the Remarks section of <i>ResourceCopy</i>.


### -field pfnResourceConvertRegion

A pointer to the driver's <a href="https://msdn.microsoft.com/CA26FB37-1A4C-4057-90A5-64FFBE289E39">ResourceCopyRegion(D3D11_1)</a> function. For more information about whether to implement a separate <i>ResourceConvertRegion(D3D11_1)</i> function or to point to the multipurpose <i>ResourceCopyRegion(D3D11_1)</i>, see the Remarks section of <i>ResourceCopyRegion(D3D11_1)</i>.


### -field pfnResetPrimitiveID

 


### -field pfnSetVertexPipelineOutput

 


### -field pfnDrawIndexedInstancedIndirect

A pointer to the driver's <a href="https://msdn.microsoft.com/3debfb11-4de9-456b-a094-feb2f68e96a5">DrawIndexedInstancedIndirect</a> function.


### -field pfnDrawInstancedIndirect

A pointer to the driver's <a href="https://msdn.microsoft.com/99520dae-3934-496f-80bf-e5b306554415">DrawInstancedIndirect</a> function.


### -field pfnCommandListExecute

A pointer to the driver's <a href="https://msdn.microsoft.com/49f44f29-52f6-40d9-8617-a24aa3d30736">CommandListExecute</a> function. The driver is only required to implement <i>CommandListExecute</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnHsSetShaderResources

A pointer to the driver's <a href="https://msdn.microsoft.com/54449d80-4943-4178-99cb-0ceed498600c">HsSetShaderResources</a> function.


### -field pfnHsSetShader

A pointer to the driver's <a href="https://msdn.microsoft.com/ee70f44c-f160-4fd1-971d-9a4f8b9bd906">HsSetShader</a> function.


### -field pfnHsSetSamplers

A pointer to the driver's <a href="https://msdn.microsoft.com/7aeb4bbc-7405-4795-afdd-d20def3c2c9c">HsSetSamplers</a> function.


### -field pfnHsSetConstantBuffers

A pointer to the driver's <a href="https://msdn.microsoft.com/35A2EE73-940B-4CC8-B49D-8FCA48F23369">HsSetConstantBuffers(D3D11_1)</a> function.


### -field pfnDsSetShaderResources

A pointer to the driver's <a href="https://msdn.microsoft.com/4e108415-4259-4382-8971-63c879f079e7">DsSetShaderResources</a> function.


### -field pfnDsSetShader

A pointer to the driver's <a href="https://msdn.microsoft.com/3824f8b1-d3ee-45be-991f-196ef6eec9c3">DsSetShader</a> function.


### -field pfnDsSetSamplers

A pointer to the driver's <a href="https://msdn.microsoft.com/1d398a7f-9f1b-42bc-862f-457ebbd41761">DsSetSamplers</a> function.


### -field pfnDsSetConstantBuffers

A pointer to the driver's <a href="https://msdn.microsoft.com/9D82F689-E68B-4A15-8532-7BF696E84753">DsSetConstantBuffers(D3D11_1)</a> function.


### -field pfnCreateHullShader

A pointer to the driver's <a href="https://msdn.microsoft.com/5461f9d4-5eff-4ff7-9eeb-cf94bc243dba">CreateHullShader(D3D11_1)</a> function.


### -field pfnCreateDomainShader

A pointer to the driver's <a href="https://msdn.microsoft.com/74e6457f-4a99-4b19-9a7e-3ebac5aef48e">CreateDomainShader(D3D11_1)</a> function.


### -field pfnCheckDeferredContextHandleSizes

A pointer to the driver's <a href="https://msdn.microsoft.com/0ddaec86-79e6-4d09-8403-6588b35f8b0f">CheckDeferredContextHandleSizes</a> function. The driver is only required to implement <i>CheckDeferredContextHandleSizes</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCalcDeferredContextHandleSize

A pointer to the driver's <a href="https://msdn.microsoft.com/d26c26ef-be8e-434a-b3d3-623ed539c541">CalcDeferredContextHandleSize</a> function. The driver is only required to implement <i>CalcDeferredContextHandleSize</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCalcPrivateDeferredContextSize

A pointer to the driver's <a href="https://msdn.microsoft.com/282898b1-45e1-4d85-9ab7-fd400623bdc5">CalcPrivateDeferredContextSize</a> function. The driver is only required to implement <i>CalcPrivateDeferredContextSize</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCreateDeferredContext

A pointer to the driver's <a href="https://msdn.microsoft.com/464a2291-55c8-4e51-ba08-219ce426d038">CreateDeferredContext</a> function. The driver is only required to implement <i>CreateDeferredContext</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnAbandonCommandList

A pointer to the driver's <a href="https://msdn.microsoft.com/fc8347da-25ac-47ea-b482-61b7873ca5bc">AbandonCommandList</a> function. The driver is only required to implement <i>AbandonCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCalcPrivateCommandListSize

A pointer to the driver's <a href="https://msdn.microsoft.com/04725df2-6373-4e04-862e-d533363af00b">CalcPrivateCommandListSize</a> function. The driver is only required to implement <i>CalcPrivateCommandListSize</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCreateCommandList

A pointer to the driver's <a href="https://msdn.microsoft.com/583bde52-ba21-44ce-9f48-8ace6f7a70cc">CreateCommandList</a> function. The driver is only required to implement <i>CreateCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnDestroyCommandList

A pointer to the driver's <a href="https://msdn.microsoft.com/9f03c193-f017-4189-a082-908e28a2e9f7">DestroyCommandList</a> function. The driver is only required to implement <i>DestroyCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability. 


### -field pfnCalcPrivateTessellationShaderSize

A pointer to the driver's <a href="https://msdn.microsoft.com/606b50c0-4070-4694-9299-f20e28743958">CalcPrivateTessellationShaderSize(D3D11_1)</a> function. 


### -field pfnPsSetShaderWithIfaces

A pointer to the driver's <a href="https://msdn.microsoft.com/8d8d4449-1770-4a57-b8b9-e1cfc64b96cb">PsSetShaderWithIfaces</a> function. 


### -field pfnVsSetShaderWithIfaces

A pointer to the driver's <a href="https://msdn.microsoft.com/cc360e57-8c0a-441a-a072-7dc792ce201c">VsSetShaderWithIfaces</a> function. 


### -field pfnGsSetShaderWithIfaces

A pointer to the driver's <a href="https://msdn.microsoft.com/f1db3ed8-7621-4d3a-820d-f50298967404">GsSetShaderWithIfaces</a> function. 


### -field pfnHsSetShaderWithIfaces

A pointer to the driver's <a href="https://msdn.microsoft.com/c0dd4504-33d3-4a49-ac4e-169375f81430">HsSetShaderWithIfaces</a> function. 


### -field pfnDsSetShaderWithIfaces

A pointer to the driver's <a href="https://msdn.microsoft.com/fce9447a-459d-4446-9764-5b7daedce041">DsSetShaderWithIfaces</a> function. 


### -field pfnCsSetShaderWithIfaces

A pointer to the driver's <a href="https://msdn.microsoft.com/2e7170e8-2b77-45a7-9ff5-834452c13ddf">CsSetShaderWithIfaces</a> function. 


### -field pfnCreateComputeShader

A pointer to the driver's <a href="https://msdn.microsoft.com/e62ad086-f652-4e2c-bc2d-f1ccb197f01e">CreateComputeShader</a> function. 


### -field pfnCsSetShader

A pointer to the driver's <a href="https://msdn.microsoft.com/ab689c60-3099-4d69-a7e2-5edfb623cbc3">CsSetShader</a> function. 


### -field pfnCsSetShaderResources

A pointer to the driver's <a href="https://msdn.microsoft.com/29570c3b-eb3b-4d8f-b471-8f3ea6226e23">CsSetShaderResources</a> function. 


### -field pfnCsSetSamplers

A pointer to the driver's <a href="https://msdn.microsoft.com/7bf05fb6-e959-464a-9e6b-74c568d1d88c">CsSetSamplers</a> function. 


### -field pfnCsSetConstantBuffers

A pointer to the driver's <a href="https://msdn.microsoft.com/6A2B50BF-415D-47BB-9514-B15F717A76EA">CsSetConstantBuffers(D3D11_1)</a> function. 


### -field pfnCalcPrivateUnorderedAccessViewSize

A pointer to the driver's <a href="https://msdn.microsoft.com/6aca5d33-c8c6-4c6b-a66a-e28a958cbc2e">CalcPrivateUnorderedAccessViewSize</a> function. 


### -field pfnCreateUnorderedAccessView

A pointer to the driver's <a href="https://msdn.microsoft.com/c5a258e7-6645-46bb-ab2c-a1c8f5e593b7">CreateUnorderedAccessView</a> function. 


### -field pfnDestroyUnorderedAccessView

A pointer to the driver's <a href="https://msdn.microsoft.com/1bce3519-f333-4b47-b29b-bde1b5c3005c">DestroyUnorderedAccessView</a> function. 


### -field pfnClearUnorderedAccessViewUint

A pointer to the driver's <a href="https://msdn.microsoft.com/7cdc81a9-e468-4da8-bc32-9e9cea1fd60d">ClearUnorderedAccessViewUINT</a> function. 


### -field pfnClearUnorderedAccessViewFloat

A pointer to the driver's <a href="https://msdn.microsoft.com/31734efd-0c17-4476-918d-942c015072bd">ClearUnorderedAccessViewFLOAT</a> function. 


### -field pfnCsSetUnorderedAccessViews

A pointer to the driver's <a href="https://msdn.microsoft.com/ab8c529b-19e2-4a2a-af68-0e3998829788">CsSetUnorderedAccessViews</a> function. 


### -field pfnDispatch

A pointer to the driver's <a href="https://msdn.microsoft.com/6fbbf05a-efb0-4f24-8811-b87141cf2daa">Dispatch</a> function. 


### -field pfnDispatchIndirect

A pointer to the driver's <a href="https://msdn.microsoft.com/0c818515-163f-48ba-ad57-f4405672c98f">DispatchIndirect</a> function. 


### -field pfnSetResourceMinLOD

A pointer to the driver's <a href="https://msdn.microsoft.com/a54b2fa7-c0c2-42b7-ae89-7984282d4af4">SetResourceMinLOD</a> function. 


### -field pfnCopyStructureCount

A pointer to the driver's <a href="https://msdn.microsoft.com/39f20ff3-859f-4933-8be0-e2bb7c05e7e1">CopyStructureCount</a> function. 


### -field pfnRecycleCommandList

A pointer to the driver's <a href="https://msdn.microsoft.com/4cff7f3d-ba13-4389-bafc-edffc0697ce9">RecycleCommandList</a> function. 


### -field pfnRecycleCreateCommandList

A pointer to the driver's   <a href="https://msdn.microsoft.com/c387545e-2891-401d-b7ca-ee7549a52603">RecycleCreateCommandList</a> function. 


### -field pfnRecycleCreateDeferredContext

A pointer to the driver's  <a href="https://msdn.microsoft.com/c9e08048-683a-4f43-b3b8-1914c2933a5c">RecycleCreateDeferredContext</a> function. 


### -field pfnRecycleDestroyCommandList

A pointer to the driver's  <a href="https://msdn.microsoft.com/9f03c193-f017-4189-a082-908e28a2e9f7">RecycleDestroyCommandList</a> function.


### -field pfnDiscard

A pointer to the driver's  <a href="https://msdn.microsoft.com/d94234ab-712b-4449-96de-16b9e310d250">Discard(D3D11_1)</a> function. 


### -field pfnAssignDebugBinary

A pointer to the driver's  <a href="https://msdn.microsoft.com/eb1e3c27-71c1-4920-9aa4-3253306fa3f4">AssignDebugBinary</a> function.


### -field pfnDynamicConstantBufferMapNoOverwrite

A pointer to the driver's  <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function. 


### -field pfnCheckDirectFlipSupport

A pointer to the driver's  <a href="https://msdn.microsoft.com/2acf84cb-5e51-4aa8-96ce-96abc6ceec8c">CheckDirectFlipSupport(D3D11_1)</a> function. 


### -field pfnClearView

A pointer to the driver's <a href="https://msdn.microsoft.com/c3cc08ea-22db-4fae-a180-76f3babd1c5c">ClearView</a>  function. 


## -remarks



The order of user-mode display driver functions (that is, the order of the members of the <b>D3D11_1DDI_DEVICEFUNCS</b> structure) is in decreasing order of priority (in regard to performance).

The user-mode display driver can use different names for these functions because the address of the function table (this structure) is shared between the Direct3D 11.1 runtime and the driver through the call to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function.

The <b>pfnResetPrimitiveID</b> and  <b>pfnSetVertexPipelineOutput</b> members (not shown here) and their data types are reserved for system use and should not be used in your driver.

<h3><a id="Deferred_contexts"></a><a id="deferred_contexts"></a><a id="DEFERRED_CONTEXTS"></a>Deferred contexts</h3>
For a list of the functions that are not leveraged for deferred contexts, see <a href="https://msdn.microsoft.com/f6e7898a-7fb8-4a70-ab2e-3372a28db6f4">Excluding DDI Functions for Deferred Contexts</a>.




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>
 

 

