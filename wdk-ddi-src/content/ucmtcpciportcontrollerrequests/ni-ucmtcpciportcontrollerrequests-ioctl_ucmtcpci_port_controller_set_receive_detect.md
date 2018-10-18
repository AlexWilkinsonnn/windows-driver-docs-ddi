---
UID: NI:ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT
author: windows-driver-content
description: Sets the RECEIVE_DETECT Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.
old-location: buses\ioctl_ucmtcpci_port_controller_set_receive_detect.htm
tech.root: usbref
ms.assetid: D76C78F0-DCC3-4C63-91B9-38CC1D8BD513
ms.date: 5/7/2018
ms.keywords: IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT, IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT control, IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT control code [Buses], buses.ioctl_ucmtcpci_port_controller_set_receive_detect, ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT
ms.topic: ioctl
req.header: ucmtcpciportcontrollerrequests.h
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
-	UcmTcpciPortControllerRequests.h
api_name:
-	IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT IOCTL


## -description


Sets the RECEIVE_DETECT Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.


## -ioctlparameters




### -input-buffer

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805885">UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS</a> structure that contains the value to set.  To get the structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550014">WdfRequestRetrieveInputBuffer</a> by passing the received framework request object.


### -input-buffer-length

The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805885">UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS</a> structure.


### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



The UcmTcpciCx class extension sends this IOCTL request to set the RECEIVE_DETECT Register. The value to set is provided in the supplied structure. After setting the value in the register, client driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> to complete the request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

