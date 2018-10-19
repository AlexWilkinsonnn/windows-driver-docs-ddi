---
UID: NI:gnssdriver.IOCTL_GNSS_STOP_BREADCRUMBING
title: IOCTL_GNSS_STOP_BREADCRUMBING
author: windows-driver-content
description: The IOCTL_GNSS_STOP_BREADCRUMBING control code is used to stop breadcrumbing.
old-location: gnss\ioctl_gnss_stop_breadcrumbing.htm
tech.root: gnss
ms.assetid: FAA8B6B0-A95C-4E12-BB0C-585E676F602F
ms.date: 02/15/2018
ms.keywords: IOCTL_GNSS_STOP_BREADCRUMBING, IOCTL_GNSS_STOP_BREADCRUMBING control, IOCTL_GNSS_STOP_BREADCRUMBING control code [Sensor Devices], gnss.ioctl_gnss_stop_breadcrumbing, gnssdriver/IOCTL_GNSS_STOP_BREADCRUMBING
ms.topic: ioctl
req.header: gnssdriver.h
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
-	gnssdriver.h
api_name:
-	IOCTL_GNSS_STOP_BREADCRUMBING
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_STOP_BREADCRUMBING IOCTL


## -description


The <b>IOCTL_GNSS_STOP_BREADCRUMBING</b> control code is used to stop breadcrumbing.


## -ioctlparameters




### -input-buffer

Pointer to the input buffer.


### -input-buffer-length

Size of the input buffer.


### -output-buffer

Pointer to the output buffer.


### -output-buffer-length

Size of the output buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

