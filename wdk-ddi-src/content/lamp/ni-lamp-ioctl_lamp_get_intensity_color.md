---
UID: NI:lamp.IOCTL_LAMP_GET_INTENSITY_COLOR
title: IOCTL_LAMP_GET_INTENSITY_COLOR
author: windows-driver-content
description: The IOCTL_LAMP_GET_INTENSITY_COLOR control code queries the light intensity when the lamp is configured to emit color light.
old-location: stream\ioctl_lamp_get_intensity_color.htm
tech.root: stream
ms.assetid: 8BAAB861-677D-4945-92B7-BDBE7A29695E
ms.date: 04/23/2018
ms.keywords: IOCTL_LAMP_GET_INTENSITY_COLOR, IOCTL_LAMP_GET_INTENSITY_COLOR control, IOCTL_LAMP_GET_INTENSITY_COLOR control code [Streaming Media Devices], lamp/IOCTL_LAMP_GET_INTENSITY_COLOR, stream.ioctl_lamp_get_intensity_color
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
-	IOCTL_LAMP_GET_INTENSITY_COLOR
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_LAMP_GET_INTENSITY_COLOR IOCTL


## -description


The <b>IOCTL_LAMP_GET_INTENSITY_COLOR</b> 
   control code queries the light intensity when the lamp is configured to emit color light.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define IOCTL_LAMP_GET_INTENSITY_COLOR \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0006, METHOD_BUFFERED, FILE_ANY_ACCESS)</pre>
</td>
</tr>
</table></span></div>

## -ioctlparameters




### -input-buffer

<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn937004">LAMP_INTENSITY_COLOR</a> structure.


### -input-buffer-length

Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/dn937004">LAMP_INTENSITY_COLOR</a> structure.


### -output-buffer

<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> is filled with the light intensity information.


### -output-buffer-length

<code>IO_STACK_LOCATION.Parameters.DeviceIoControl.OutputBufferLength</code> is the length of the buffer in bytes passed in the <code>Irp-&gt;AssociatedIrp.SystemBuffer</code> field.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The driver sets <code>Irp-&gt;IoStatus.Status</code> to <b>STATUS_SUCCESS</b> or the appropriate error status.

If the device has been acquired by a camera driver, the lamp driver should return a error <b>STATUS_RESOURCE_IN_USE</b> via <code>Irp-&gt;IoStatus.Status</code>.


## -remarks



The payload type of this IOCTL is a <a href="https://msdn.microsoft.com/library/windows/hardware/dn937004">LAMP_INTENSITY_COLOR</a> structure.



