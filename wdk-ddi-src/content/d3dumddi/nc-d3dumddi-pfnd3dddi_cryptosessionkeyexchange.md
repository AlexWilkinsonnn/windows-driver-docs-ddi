---
UID: NC:d3dumddi.PFND3DDDI_CRYPTOSESSIONKEYEXCHANGE
title: PFND3DDDI_CRYPTOSESSIONKEYEXCHANGE
author: windows-driver-content
description: The CryptoSessionKeyExchange function negotiates a session key.
old-location: display\cryptosessionkeyexchange.htm
tech.root: display
ms.assetid: f8055bb3-b8f1-47f5-9ae0-8e7a26989871
ms.date: 5/10/2018
ms.keywords: CryptoSessionKeyExchange, CryptoSessionKeyExchange callback function [Display Devices], PFND3DDDI_CRYPTOSESSIONKEYEXCHANGE, PFND3DDDI_CRYPTOSESSIONKEYEXCHANGE callback, UserModeDisplayDriver_Functions_36eab785-562d-4f2d-bcf2-2da53708f98d.xml, d3dumddi/CryptoSessionKeyExchange, display.cryptosessionkeyexchange
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: CryptoSessionKeyExchange is supported beginning with the Windows 7 operating system.
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	CryptoSessionKeyExchange
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CRYPTOSESSIONKEYEXCHANGE callback function


## -description


The <b>CryptoSessionKeyExchange</b> function negotiates a session key. 


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542981">D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE</a> structure that describes a session key that is used for encryption. 


## -returns



<b>CryptoSessionKeyExchange</b> returns one of the following values:

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
The session key is successfully exchanged. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/f8055bb3-b8f1-47f5-9ae0-8e7a26989871">CryptoSessionKeyExchange</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



The driver should only support a single key exchange mechanism for each encryption type. Microsoft has standardized the key exchange type D3DKEYEXCHANGE_RSAES_OAEP. However, hardware vendors can use proprietary key exchange mechanisms. 

For D3DKEYEXCHANGE_RSAES_OAEP, the <b>pData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542981">D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE</a> structure points to a buffer that contains the session key that an application previously RSAES-OAEP-encrypted with the public key from the driver's crypto session certificate. The actual size of the buffer is 256 bytes. This exchange is identical to how the <a href="https://msdn.microsoft.com/2c138dbd-55ca-4c71-8c8b-b2efd1ca80f2">Output Protection Manager</a> (OPM) key exchange works, except the OPM buffer contains additional data besides the session key. The same certificate that is used for OPM key exchange can be used for the D3DKEYEXCHANGE_RSAES_OAEP key exchange. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542981">D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE</a>
 

 

