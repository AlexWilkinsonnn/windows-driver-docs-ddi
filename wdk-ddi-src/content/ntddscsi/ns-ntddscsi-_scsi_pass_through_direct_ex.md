---
UID: NS:ntddscsi._SCSI_PASS_THROUGH_DIRECT_EX
title: "_SCSI_PASS_THROUGH_DIRECT_EX"
author: windows-driver-content
description: The SCSI_PASS_THROUGH_DIRECT_EX structure is used in conjunction with an IOCTL_SCSI_PASS_THROUGH_DIRECT_EX request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\scsi_pass_through_direct_ex.htm
tech.root: storage
ms.assetid: FE699F78-99AC-46E0-9C51-6F69A5C4932C
ms.date: 03/29/2018
ms.keywords: "*PSCSI_PASS_THROUGH_DIRECT_EX, PSCSI_PASS_THROUGH_DIRECT_EX, PSCSI_PASS_THROUGH_DIRECT_EX structure pointer [Storage Devices], SCSI_PASS_THROUGH_DIRECT_EX, SCSI_PASS_THROUGH_DIRECT_EX structure [Storage Devices], _SCSI_PASS_THROUGH_DIRECT_EX, ntddscsi/PSCSI_PASS_THROUGH_DIRECT_EX, ntddscsi/SCSI_PASS_THROUGH_DIRECT_EX, storage.scsi_pass_through_direct_ex"
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	ntddscsi.h
api_name:
-	SCSI_PASS_THROUGH_DIRECT_EX
product:
- Windows
targetos: Windows
req.typenames: SCSI_PASS_THROUGH_DIRECT_EX, *PSCSI_PASS_THROUGH_DIRECT_EX
---

# _SCSI_PASS_THROUGH_DIRECT_EX structure


## -description


The <b>SCSI_PASS_THROUGH_DIRECT_EX</b> structure is used in conjunction with an <a href="https://msdn.microsoft.com/library/windows/hardware/jj602800">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a> request to instruct the port driver to send an embedded SCSI command to the target device. <b>SCSI_PASS_THROUGH_DIRECT_EX</b> can contain a bi-directional data transfers and a variable length command data block.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Version

The version of this structure. Set to 0.


### -field Length

The size of the this structure. Set to <b>sizeof</b>(SCSI_PASS_THROUGH_DIRECT_EX).


### -field CdbLength

Indicates the size in bytes of the SCSI command descriptor block in <b>Cdb</b>.


### -field StorAddressLength

The length of the storage device address structure at the offset of <b>StorAddressOffset</b> after this structure. This is set to <b>sizeof</b>(STOR_ADDR_BTL8).


### -field ScsiStatus

Reports the SCSI status that was returned by the HBA or the target device.


### -field SenseInfoLength

Indicates the size in bytes of the request-sense buffer. This member is optional and can be set to 0.


### -field DataDirection



#####  This field must have one of these values:



######## 


### -field Reserved

Reserved. Set to 0.


### -field TimeOutValue

Indicates the interval in seconds that the request can execute before the port driver considers it timed out.


### -field StorAddressOffset

The location of the target device's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451521">STOR_ADDR_BTL8</a> address structure, in bytes, from the beginning of this structure.


### -field SenseInfoOffset

Offset from the beginning of this structure to the request-sense buffer. Set to 0 if no request-sense buffer is present.


### -field DataOutTransferLength

Indicates the size in bytes of the output data buffer. Many devices transfer chunks of data of predefined length. The value in <b>DataOutTransferLength</b> must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no output data buffer is present, this member is set to 0.


### -field DataInTransferLength

Indicates the size in bytes of the input data buffer. Many devices transfer chunks of data of predefined length. The value in <b>DataInTransferLength</b> must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no input data buffer is present, this member is set to 0.


### -field DataOutBuffer

A pointer to a output data buffer.


### -field DataInBuffer

A pointer to a input data buffer.


### -field Cdb

Specifies the SCSI command descriptor block to be sent to the target device.


## -remarks



The <b>SCSI_PASS_THROUGH_DIRECT_EX</b> structure is used with <a href="https://msdn.microsoft.com/library/windows/hardware/jj602800">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a>. With this request, the system locks down the buffer in user memory and the device accesses this memory directly. For a double-buffered equivalent of this device control request see <b>IOCTL_SCSI_PASS_THROUGH_EX</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/jj553715">SCSI_PASS_THROUGH_EX</a>.

<div class="alert"><b>Note</b>  Drivers executing on a 64 bit version of Windows must use the <b>SCSI_PASS_THROUGH_DIRECT32_EX</b> structure as the request data type  when handling an <a href="https://msdn.microsoft.com/library/windows/hardware/jj602800">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a> request from a 32 bit process.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560521">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj602800">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565346">SCSI_PASS_THROUGH_DIRECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451521">STOR_ADDR_BTL8</a>
 

 

