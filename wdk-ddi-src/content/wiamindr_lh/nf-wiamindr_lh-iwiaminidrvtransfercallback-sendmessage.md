---
UID: NF:wiamindr_lh.IWiaMiniDrvTransferCallback.SendMessage
title: IWiaMiniDrvTransferCallback::SendMessage
author: windows-driver-content
description: Periodically called by the WIA mini-driver during a data transfer, to update the WIA application client about the progress and status of the transfer.
old-location: image\iwiaminidrvtransfercallback_sendmessage.htm
tech.root: image
ms.assetid: 9C4800E6-0F5F-4895-AD19-635C7F784462
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrvTransferCallback interface [Imaging Devices],SendMessage method, IWiaMiniDrvTransferCallback.SendMessage, IWiaMiniDrvTransferCallback::SendMessage, SendMessage, SendMessage method [Imaging Devices], SendMessage method [Imaging Devices],IWiaMiniDrvTransferCallback interface, image.iwiaminidrvtransfercallback_sendmessage, wiamindr_lh/IWiaMiniDrvTransferCallback::SendMessage
ms.topic: method
req.header: wiamindr_lh.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
-	Wiamindr_lh.h
api_name:
-	IWiaMiniDrvTransferCallback.SendMessage
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrvTransferCallback::SendMessage


## -description


Periodically called by the WIA mini-driver during a data transfer, to update the WIA application client about the progress and status of the transfer.

For more information about the progress data that is transferred, see <a href="https://msdn.microsoft.com/library/windows/desktop/ms629867(v=vs.85).aspx">WiaTransferParams</a>.


## -parameters




### -param lFlags [in]

Represents flag bits. This parameter is unused and should always be set to zero (0) by the caller.


### -param pWiaTransferParams [in]

Pointer to a <b>WiaTransferParams</b> object.


## -returns



This method returns S_OK when the call is successful. Otherwise it returns an appropriate HRESULT error code.




## -remarks



When the current transfer sequence is cancelled, the <b>SendMessage</b> method returns S_FALSE.




## -see-also




<a href="https://msdn.microsoft.com/0cdc02bf-23fe-4122-8d5f-f42c3c07da8b">Cancellation of Data Transfers in Windows Vista</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj151550">IWiaMiniDrvTransferCallback</a>



<a href="https://msdn.microsoft.com/library/windows/desktop/ms629867(v=vs.85).aspx">WiaTransferParams</a>
 

 

