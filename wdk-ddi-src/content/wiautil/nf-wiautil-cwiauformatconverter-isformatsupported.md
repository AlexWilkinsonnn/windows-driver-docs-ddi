---
UID: NF:wiautil.CWiauFormatConverter.IsFormatSupported
title: CWiauFormatConverter::IsFormatSupported
author: windows-driver-content
description: The CWiauFormatConverter::IsFormatSupported method verifies that GDI+ supports the image format that is to be converted.
old-location: image\cwiauformatconverter_isformatsupported.htm
tech.root: image
ms.assetid: 5bb69443-8ccd-4157-8815-fb3423b57e30
ms.date: 5/3/2018
ms.keywords: CWiauFormatConverter interface [Imaging Devices],IsFormatSupported method, CWiauFormatConverter.IsFormatSupported, CWiauFormatConverter::IsFormatSupported, IsFormatSupported, IsFormatSupported method [Imaging Devices], IsFormatSupported method [Imaging Devices],CWiauFormatConverter interface, image.cwiauformatconverter_isformatsupported, wiauFncs_894f0261-249e-4b7c-aaa1-43a52bd48fbf.xml, wiautil/CWiauFormatConverter::IsFormatSupported
ms.topic: method
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wiautil.h
api_name:
-	CWiauFormatConverter.IsFormatSupported
product:
- Windows
targetos: Windows
req.typenames: 
---

# CWiauFormatConverter::IsFormatSupported


## -description


The <b>CWiauFormatConverter::IsFormatSupported</b> method verifies that GDI+ supports the image format that is to be converted.


## -parameters




### -param pguidFormat

Points to the GUID of the format. The format GUIDs are defined in <i>gdiplusimaging.h</i>.


## -returns



The method returns <b>TRUE</b> if the format indicated by the format GUID is supported, and <b>FALSE</b> if it is not supported.




## -see-also




<a href="https://msdn.microsoft.com/b30c3336-ddc6-459d-97c4-244ca0b50cfc">CWiauFormatConverter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540369">CWiauFormatConverter::ConvertToBmp</a>
 

 

