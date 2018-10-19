---
UID: NF:ufxclient.UfxDevicePortDetectComplete
title: UfxDevicePortDetectComplete function
author: windows-driver-content
description: Notifies UFX about the port type that was detected.
old-location: buses\ufxdeviceportdetectcomplete.htm
tech.root: usbref
ms.assetid: D5F65152-54CD-45FA-99CE-F5B4DF444BB8
ms.date: 05/07/2018
ms.keywords: UfxDevicePortDetectComplete, UfxDevicePortDetectComplete method [Buses], buses.ufxdeviceportdetectcomplete, ufxclient/UfxDevicePortDetectComplete
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.lib: ufxstub.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ufxclient.h
api_name:
-	UfxDevicePortDetectComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# UfxDevicePortDetectComplete function


## -description


Notifies UFX about the port type that was detected.


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


### -param PortType [in]

Contains an enumeration value of type <a href="https://msdn.microsoft.com/library/windows/hardware/mt188004">USBFN_PORT_TYPE</a>.


## -returns



This method does not return a value.




## -remarks



The client driver calls <b>UfxDevicePortDetectComplete</b> when port detection is complete. On some platforms, UFX may use the reported port type to notify the battery manager of the maximum current it can draw from the USB port.

The client driver typically calls <b>UfxDevicePortDetectComplete</b> from its <a href="https://msdn.microsoft.com/library/windows/hardware/mt187855">EVT_UFX_DEVICE_PORT_DETECT</a> callback function, as shown in this example.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    // In this example we will return an unknown port type.  This will allow UFX to connect to a host if
    // one is present.  UFX will timeout after 5 seconds if no host is present and transition to
    // an invalid charger type, which will allow the controller to exit D0.
    //
    UfxDevicePortDetectComplete(ControllerContext-&gt;UfxDevice, UsbfnUnknownPort);
</pre>
</td>
</tr>
</table></span></div>


