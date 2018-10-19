---
UID: NC:ufxclient.EVT_UFX_DEVICE_USB_STATE_CHANGE
title: EVT_UFX_DEVICE_USB_STATE_CHANGE
author: windows-driver-content
description: The client driver's implementation to update the state of the USB device.
old-location: buses\evt_ufx_device_usb_state_change.htm
tech.root: usbref
ms.assetid: 81D4F3C5-7412-4148-A5B4-0C56DD9ADB35
ms.date: 05/07/2018
ms.keywords: EVT_UFX_DEVICE_USB_STATE_CHANGE, EVT_UFX_DEVICE_USB_STATE_CHANGE callback, EvtUfxDeviceUsbStateChange, EvtUfxDeviceUsbStateChange callback function [Buses], PFN_UFX_DEVICE_USB_STATE_CHANGE, PFN_UFX_DEVICE_USB_STATE_CHANGE callback function pointer [Buses], buses.evt_ufx_device_usb_state_change, ufxclient/EvtUfxDeviceUsbStateChange
ms.topic: callback
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ufxclient.h
api_name:
-	PFN_UFX_DEVICE_USB_STATE_CHANGE
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UFX_DEVICE_USB_STATE_CHANGE callback function


## -description


The client driver's implementation to update the state of the USB device.


## -parameters












#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


#### - UsbDeviceState [in]

A USBFN_DEVICE_STATE-typed flag that indicates state of the USB device.


## -returns



This callback function does not return a value.




## -remarks



The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_USB_STATE_CHANGE</i> implementation with the USB function class extension (UFX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a> method.

UFX invokes this event callback to inform the client driver about the new state of the device.

The client driver indicates completion of this event by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a> method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_UFX_DEVICE_USB_STATE_CHANGE UfxDevice_EvtDeviceUsbStateChange;

VOID
UfxDevice_EvtDeviceUsbStateChange (
    _In_ UFXDEVICE UfxDevice,
    _In_ USBFN_DEVICE_STATE NewState
)
/*++

Routine Description:

    EvtDeviceUsbStateChange handler for the UFXDEVICE object.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

    NewState - The new device state.

--*/
{
    NTSTATUS Status;
    PUFXDEVICE_CONTEXT Context;
    PCONTROLLER_CONTEXT ControllerContext;
    ULONG EpIndex;
    USBFN_DEVICE_STATE OldState;
 
    PAGED_CODE();

    TraceEntry();

    Context = UfxDeviceGetContext(UfxDevice);
    ControllerContext = DeviceGetControllerContext(Context-&gt;FdoWdfDevice);
    OldState = Context-&gt;UsbState;

    TraceInformation("New STATE: %d", NewState);

    Status = UfxDeviceStopOrResumeIdle(UfxDevice, NewState, Context-&gt;UsbPort);
    LOG_NT_MSG(Status, "Failed to stop or resume idle");

    WdfWaitLockAcquire(ControllerContext-&gt;InitializeDefaultEndpointLock, NULL);
    if (ControllerContext-&gt;InitializeDefaultEndpoint == TRUE) {
        //
        // Reset endpoint 0. This is the last part of soft reset, which was postponed
        // until now, since we need to make sure EP0 is created by UFX.
        //
        DeviceInitializeDefaultEndpoint(Context-&gt;FdoWdfDevice);
        ControllerContext-&gt;InitializeDefaultEndpoint = FALSE;
    }
    WdfWaitLockRelease(ControllerContext-&gt;InitializeDefaultEndpointLock);

    if (NewState == UsbfnDeviceStateConfigured &amp;&amp; OldState != UsbfnDeviceStateSuspended) {

        for (EpIndex = 1; EpIndex &lt; WdfCollectionGetCount(Context-&gt;Endpoints); EpIndex++) {
            UfxEndpointConfigure(WdfCollectionGetItem(Context-&gt;Endpoints, EpIndex));
        }

        // 
        // #### TODO: Insert code to allow the controller to accept U1/U2, if supported ####
        //
       
    }


    if (NewState == UsbfnDeviceStateDetached) {
        KeSetEvent(&amp;ControllerContext-&gt;DetachEvent,
                   IO_NO_INCREMENT,
                   FALSE);
    }

    UfxDeviceEventComplete(UfxDevice, STATUS_SUCCESS);
    TraceExit();
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a>
 

 

