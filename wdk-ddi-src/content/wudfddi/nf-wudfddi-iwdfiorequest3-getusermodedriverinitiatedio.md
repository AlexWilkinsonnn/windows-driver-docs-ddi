---
UID: NF:wudfddi.IWDFIoRequest3.GetUserModeDriverInitiatedIo
title: IWDFIoRequest3::GetUserModeDriverInitiatedIo (wudfddi.h)
description: The GetUserModeDriverInitiatedIo method determines whether an I/O request is marked as initiated by a UMDF driver.
old-location: wdf\iwdfiorequest3_getusermodedriverinitiatedio.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFIoRequest3::GetUserModeDriverInitiatedIo"]
ms.keywords: GetUserModeDriverInitiatedIo, GetUserModeDriverInitiatedIo method, GetUserModeDriverInitiatedIo method,IWDFIoRequest3 interface, IWDFIoRequest3 interface,GetUserModeDriverInitiatedIo method, IWDFIoRequest3.GetUserModeDriverInitiatedIo, IWDFIoRequest3::GetUserModeDriverInitiatedIo, umdf.iwdfiorequest3_getusermodedriverinitiatedio, wdf.iwdfiorequest3_getusermodedriverinitiatedio, wudfddi/IWDFIoRequest3::GetUserModeDriverInitiatedIo
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFIoRequest3::GetUserModeDriverInitiatedIo
 - wudfddi/IWDFIoRequest3::GetUserModeDriverInitiatedIo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequest3::GetUserModeDriverInitiatedIo
---

# IWDFIoRequest3::GetUserModeDriverInitiatedIo


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   The 
  <b>GetUserModeDriverInitiatedIo</b> method determines whether an I/O request is marked as initiated by a UMDF driver.

## -returns

The method returns <b>TRUE</b> if the request is marked as UMDF driver-initiated and <b>FALSE</b> if the request is not marked as UMDF driver-initiated.

## -remarks

For additional information, see <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest3-setusermodedriverinitiatedio">SetUserModeDriverInitiatedIo</a>.

The UMDF 2 equivalent of this method is <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetusermodedriverinitiatedio">WdfRequestGetUserModeInitiatedIo</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest3">IWDFIoRequest3</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest3-setusermodedriverinitiatedio">SetUserModeDriverInitiatedIo</a>

