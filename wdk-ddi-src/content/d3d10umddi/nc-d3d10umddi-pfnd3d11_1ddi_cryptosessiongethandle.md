---
UID: NC:d3d10umddi.PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE
title: PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE
author: windows-driver-content
description: Returns a handle for a cryptographic session.
old-location: display\cryptosessiongethandle.htm
ms.assetid: 30700af0-79e8-4808-bec8-94f5e5152bcc
ms.date: 05/10/2018
ms.keywords: CryptoSessionGetHandle, CryptoSessionGetHandle callback function [Display Devices], PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE, PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE callback, d3d10umddi/CryptoSessionGetHandle, display.cryptosessiongethandle
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	D3d10umddi.h
api_name:
-	CryptoSessionGetHandle
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_CRYPTOSESSIONGETHANDLE callback function


## -description


Returns a handle for a cryptographic session.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param hCryptoSession [in]

A handle to the driver's private data for the cryptographic session. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a>.


### -param *pHandle [out]

A handle that is created by the driver for the cryptographic session.


## -returns



<b>CryptoSessionGetHandle</b> returns one of the following values:

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
The cryptographic session handle was returned successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was removed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.

</td>
</tr>
</table>
 




## -remarks



The <b>CryptoSessionGetHandle</b> function returns a driver-specified handle for the cryptographic session. This handle is used by the application when it associates the cryptographic session with the video decoder. This enables the decoder to decrypt data that is encrypted by using this session.


This function allows the driver to define its own handle to its state data for the cryptographic session. This bypasses any handle mapping that may be performed by the Direct3D runtime.

<div class="alert"><b>Note</b>  Drivers can return the same handle in the <i>pHandle</i> parameter that was passed  in the <i>hCryptoSession</i> parameter.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a>
 

 

