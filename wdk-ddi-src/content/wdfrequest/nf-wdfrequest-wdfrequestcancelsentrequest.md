---
UID: NF:wdfrequest.WdfRequestCancelSentRequest
title: WdfRequestCancelSentRequest function
author: windows-driver-content
description: The WdfRequestCancelSentRequest method attempts to cancel an I/O request that the caller previously submitted to an I/O target.
old-location: wdf\wdfrequestcancelsentrequest.htm
tech.root: wdf
ms.assetid: 24319054-5e5c-4330-86e5-b1527c48eaf2
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_203c9cb4-5e9d-4a6b-b30d-b60b8eadf6db.xml, WdfRequestCancelSentRequest, WdfRequestCancelSentRequest method, kmdf.wdfrequestcancelsentrequest, wdf.wdfrequestcancelsentrequest, wdfrequest/WdfRequestCancelSentRequest
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, EvtIoStopCancel, EvtIoStopCompleteOrStopAck, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfRequestCancelSentRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestCancelSentRequest function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestCancelSentRequest</b> method attempts to cancel an I/O request that the caller previously submitted to an I/O target.


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



<b>WdfRequestCancelSentRequest</b> returns <b>TRUE</b> if it successfully delivers the cancel request to the driver's I/O target. This method returns <b>FALSE</b> if the request has already been completed or canceled, or if the I/O target driver has not called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A driver can call <b>WdfRequestCancelSentRequest</b> to attempt to cancel an I/O request that it previously had sent to an I/O target by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>.

If the request is in the I/O target's queue, the framework cancels the request. If the framework has already delivered the request to the I/O target's driver, and if that driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> to enable canceling, the framework calls that driver's <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> callback function. If the target's driver has not called <b>WdfRequestMarkCancelable</b> or <b>WdfRequestMarkCancelableEx</b>, the request is not canceled unless the request becomes cancelable.

If the driver has registered a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function for the request, the framework calls the callback function after the request has been canceled.

Typically, if your driver calls <b>WdfRequestCancelSentRequest</b>, it must increment the request object's reference count. For more information, see <a href="https://msdn.microsoft.com/e7ec65c9-bc7b-46ea-853d-3e23b1763666">Synchronizing Cancellation of Sent Requests</a>.

For more information about request cancellation, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.


#### Examples

The following code example is from the <a href="http://go.microsoft.com/fwlink/p/?linkid=256131">kmdf_fx2</a> sample driver. This example is an <a href="https://msdn.microsoft.com/71a789f1-4f10-44c3-8bd0-a0ea74ec28ab">EvtIoStop</a> callback function. Because this driver sends each request to its I/O target, the <i>EvtIoStop</i> callback function calls <b>WdfRequestCancelSentRequest</b> if the device has been removed.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
OsrFxEvtIoStop(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN ULONG  ActionFlags
    )
{
    UNREFERENCED_PARAMETER(Queue);

    if (ActionFlags &amp; WdfRequestStopActionSuspend) {
        WdfRequestStopAcknowledge(Request, FALSE);
    } else if (ActionFlags &amp; WdfRequestStopActionPurge) {
        WdfRequestCancelSentRequest(Request);
    }
    return;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a>



<a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>
 

 

