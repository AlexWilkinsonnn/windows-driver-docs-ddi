---
UID: NI:lamp.IOCTL_LAMP_GET_CAPABILITIES_COLOR
title: IOCTL_LAMP_GET_CAPABILITIES_COLOR
description: The IOCTL_LAMP_GET_CAPABILITIES_COLOR control code queries the capabilities of the lamp when the device is configured to emit color light.
old-location: stream\ioctl_lamp_get_capabilities_color.htm
tech.root: stream
ms.assetid: CC7B1824-E397-414A-8EB6-130AEC031304
ms.date: 04/23/2018
ms.keywords: IOCTL_LAMP_GET_CAPABILITIES_COLOR, IOCTL_LAMP_GET_CAPABILITIES_COLOR control, IOCTL_LAMP_GET_CAPABILITIES_COLOR control code [Streaming Media Devices], lamp/IOCTL_LAMP_GET_CAPABILITIES_COLOR, stream.ioctl_lamp_get_capabilities_color
ms.topic: ioctl
req.header: lamp.h
req.include-header: 
req.target-type: Windows
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
-	HeaderDef
api_location:
-	lamp.h
api_name:
-	IOCTL_LAMP_GET_CAPABILITIES_COLOR
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_LAMP_GET_CAPABILITIES_COLOR IOCTL


## -description


The <b>IOCTL_LAMP_GET_CAPABILITIES_COLOR</b> 
   control code queries the capabilities of the lamp when the device is configured to emit color light.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define IOCTL_LAMP_GET_CAPABILITIES_COLOR \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0001, METHOD_BUFFERED, FILE_ANY_ACCESS)</pre>
</td>
</tr>
</table></span></div>

## -ioctlparameters




### -input-buffer

<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> points to a buffer of type <a href="https://msdn.microsoft.com/library/windows/hardware/dn936998">LAMP_CAPABILITIES_COLOR</a>.


### -input-buffer-length

Length of the buffer.


### -output-buffer

<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> is filled with all capabilities supported by the lamp hardware.



### -output-buffer-length

<code>IO_STACK_LOCATION.Parameters.DeviceIoControl.OutputBufferLength</code> is the length of the buffer (in bytes) passed in the <code>Irp-&gt;AssociatedIrp.SystemBuffer</code> field.



### -in-out-buffer








### -inout-buffer-length








### -status-block

The driver sets <code>Irp-&gt;IoStatus.Status</code> to <b>STATUS_SUCCESS</b> or the appropriate error status. It will set <code>Irp-&gt;IoStatus.Information</code> to the number of bytes required to hold the buffer.


## -remarks



The payload of this IOCTL is a <a href="https://msdn.microsoft.com/library/windows/hardware/dn936998">LAMP_CAPABILITIES_COLOR</a> structure.

The <b>IsSupported</b> field indicates whether the lamp can emit color light. If the hardware does not support color light, the driver should set this field to <b>FALSE</b>.

The <b>IsLightIntensityAdjustable</b> field indicates whether the luminance level can be programmed. If the lamp does not support color light (<b>IsSupported</b> evaluates to <b>FALSE</b>), a client should discard the value of <b>IsLightIntensityAdjustable</b>.



