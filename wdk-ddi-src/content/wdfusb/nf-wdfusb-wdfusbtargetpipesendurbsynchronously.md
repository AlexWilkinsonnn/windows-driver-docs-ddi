---
UID: NF:wdfusb.WdfUsbTargetPipeSendUrbSynchronously
title: WdfUsbTargetPipeSendUrbSynchronously function (wdfusb.h)
description: The WdfUsbTargetPipeSendUrbSynchronously method builds an USB request for a specified USB pipe, using request parameters that a specified URB describes.
old-location: wdf\wdfusbtargetpipesendurbsynchronously.htm
tech.root: wdf
ms.assetid: 2ce7a843-0053-4351-ba79-161d83e245ac
ms.date: 02/26/2018
ms.keywords: DFUsbRef_3e797ee4-f454-4520-b4a0-84565515622f.xml, WdfUsbTargetPipeSendUrbSynchronously, WdfUsbTargetPipeSendUrbSynchronously method, kmdf.wdfusbtargetpipesendurbsynchronously, wdf.wdfusbtargetpipesendurbsynchronously, wdfusb/WdfUsbTargetPipeSendUrbSynchronously
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, IoctlReqs, KmdfIrql, KmdfIrql2, SyncReqSend, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfUsbTargetPipeSendUrbSynchronously
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetPipeSendUrbSynchronously function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfUsbTargetPipeSendUrbSynchronously</b> method builds an USB request for a specified USB pipe, using request parameters that a specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> describes.


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>. 


### -param Request [in, optional]

A handle to a framework request object. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


### -param RequestOptions [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the request. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


### -param Urb [in]

A pointer to a driver-initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure.

If the driver previously called <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a> to create <i>UsbDevice</i>, the driver must use <a href="https://msdn.microsoft.com/library/windows/hardware/hh439423">WdfUsbTargetDeviceCreateUrb</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/hh439420">WdfUsbTargetDeviceCreateIsochUrb</a> to create this URB.


## -returns



<b>WdfUsbTargetPipeSendUrbSynchronously</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure that the <i>RequestOptions</i> parameter specified was incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient memory was available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The caller's IRQL was not PASSIVE_LEVEL, or the specified I/O request was already queued to an I/O target.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The driver supplied a time-out value and the request did not complete within the allotted time. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The I/O request packet (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Use the <b>WdfUsbTargetPipeSendUrbSynchronously</b> method to send a USB request synchronously. To send such requests asynchronously, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff551139">WdfUsbTargetPipeFormatRequestForUrb</a>, followed by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>.

The <b>WdfUsbTargetPipeSendUrbSynchronously</b> method does not return until the request has completed, unless the driver supplies a time-out value in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure that the <i>RequestOptions</i> parameter points to, or unless an error is detected.

The framework does not examine the USB request. If the request changes the state of the USB pipe, the framework will not be aware of the change.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request.

To forward an I/O request that your driver received in an I/O queue, specify the received request's handle for the <b>WdfUsbTargetPipeSendUrbSynchronously</b> method's <i>Request</i> parameter.

To create and send a new request, either supply a <b>NULL</b> request handle for the <i>Request</i> parameter, or create a new request object and supply its handle:

<ul>
<li>
If you supply a <b>NULL</b> request handle, the framework uses an internal request object. This technique is simple to use, but the driver cannot cancel the request.

</li>
<li>
If you call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> to create one or more request objects, you can reuse these request objects by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>. This technique enables your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function to preallocate request objects for a device. Additionally, another driver thread can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549941">WdfRequestCancelSentRequest</a> to cancel the request, if necessary.

</li>
</ul>
Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetPipeSendUrbSynchronously</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example initializes a URB and sends the URB to a USB pipe.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>URB  urb;
PURB  pUrb = NULL;
NTSTATUS status;

pUrb = &urb;
pUrb-&gt;UrbHeader.Length = (USHORT) sizeof(struct _URB_GET_CURRENT_FRAME_NUMBER);
pUrb-&gt;UrbHeader.Function = URB_FUNCTION_GET_CURRENT_FRAME_NUMBER;
pUrb-&gt;UrbGetCurrentFrameNumber.FrameNumber = 0; 

status = WdfUsbTargetPipeSendUrbSynchronously(
                                              Pipe,
                                              Request,
                                              NULL,
                                              pUrb
                                              );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549941">WdfRequestCancelSentRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>
 

 

