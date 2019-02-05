---
UID: NS:ntdddisk._DRIVE_LAYOUT_INFORMATION
title: _DRIVE_LAYOUT_INFORMATION (ntdddisk.h)
description: The DRIVE_LAYOUT_INFORMATION structure is obsolete and is provided only to support existing drivers.
old-location: storage\drive_layout_information.htm
tech.root: storage
ms.assetid: 980cd307-9048-4054-be8e-967d15862a14
ms.date: 03/29/2018
ms.keywords: "*PDRIVE_LAYOUT_INFORMATION, DRIVE_LAYOUT_INFORMATION, DRIVE_LAYOUT_INFORMATION structure [Storage Devices], PDRIVE_LAYOUT_INFORMATION, PDRIVE_LAYOUT_INFORMATION structure pointer [Storage Devices], _DRIVE_LAYOUT_INFORMATION, ntdddisk/DRIVE_LAYOUT_INFORMATION, ntdddisk/PDRIVE_LAYOUT_INFORMATION, storage.drive_layout_information, structs-disk_4b519d3d-0729-4390-a2e2-b5eb37738db1.xml"
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	ntdddisk.h
api_name:
-	DRIVE_LAYOUT_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: DRIVE_LAYOUT_INFORMATION, *PDRIVE_LAYOUT_INFORMATION
---

# _DRIVE_LAYOUT_INFORMATION structure


## -description


The DRIVE_LAYOUT_INFORMATION structure is obsolete and is provided only to support existing drivers. New drivers must use <a href="https://msdn.microsoft.com/library/windows/hardware/ff552662">DRIVE_LAYOUT_INFORMATION_EX</a>. 

The DRIVE_LAYOUT_INFORMATION structure is used to report information about a disk drive and its partitions. It is also used to write new drive layout information to the disk. 


## -struct-fields




### -field PartitionCount

Contains the number of partitions on the drive. 


### -field Signature

Contains the disk signature.


### -field PartitionEntry

Contains a variable-length array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563751">PARTITION_INFORMATION</a> structures, one for each partition on the drive. 


## -remarks



In Windows 2000 and later operating systems, disk drivers should use structures <a href="https://msdn.microsoft.com/library/windows/hardware/ff552662">DRIVE_LAYOUT_INFORMATION_EX</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563754">PARTITION_INFORMATION_EX</a> along with routines <b>IoReadPartitionTableEx</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561461">IoSetPartitionInformationEx</a> to read and alter partition information on the disk. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560361">IOCTL_DISK_GET_DRIVE_LAYOUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560373">IOCTL_DISK_GET_PARTITION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560408">IOCTL_DISK_SET_DRIVE_LAYOUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561452">IoReadPartitionTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561454">IoReadPartitionTableEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561456">IoSetPartitionInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561464">IoWritePartitionTable</a>
 

 

