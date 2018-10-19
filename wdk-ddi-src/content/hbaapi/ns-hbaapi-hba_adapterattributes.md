---
UID: NS:hbaapi.HBA_AdapterAttributes
title: HBA_AdapterAttributes
author: windows-driver-content
description: The HBA_AdapterAttributes structure is used in conjunction with the HBA_GetAdapterAttributes routine to report the attributes of an HBA.
old-location: storage\hba_adapterattributes.htm
tech.root: storage
ms.assetid: d86a5810-7014-41d5-bd88-3a1bd50032da
ms.date: 03/29/2018
ms.keywords: "*PHBA_ADAPTERATTRIBUTES, HBA_ADAPTERATTRIBUTES, HBA_ADAPTERATTRIBUTES structure [Storage Devices], HBA_AdapterAttributes, HBA_AdapterAttributes structure [Storage Devices], PHBA_ADAPTERATTRIBUTES, PHBA_ADAPTERATTRIBUTES structure pointer [Storage Devices], hbaapi/HBA_AdapterAttributes, hbaapi/PHBA_ADAPTERATTRIBUTES, storage.hba_adapterattributes, structs-Fibre_364bd5e8-0276-425b-a1f9-9659aabecd19.xml"
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
-	hbaapi.h
api_name:
-	HBA_ADAPTERATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: HBA_ADAPTERATTRIBUTES, *PHBA_ADAPTERATTRIBUTES
---

# HBA_AdapterAttributes structure


## -description


The HBA_AdapterAttributes structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556078">HBA_GetAdapterAttributes</a> routine to report the attributes of an HBA.


## -struct-fields




### -field Manufacturer

Contains a string not exceeding 64 bytes in length that indicates the name of the manufacturer of the HBA..


### -field SerialNumber

Contains a string not exceeding 64 bytes in length that indicates the serial number of the HBA. 


### -field Model

Contains a string not exceeding 256 bytes in length that indicates a vendor specific name or identifying text for the HBA model.  


### -field ModelDescription

Contains a string not exceeding 256 bytes in length that provides a description of the HBA model.


### -field NodeWWN

Contains the 64 bit world-wide name that indicates the name of the node (machine) that the HBA is located on. If an HBA has multiple ports associated with more than one node, the member will contain a name chosen by vendor-specific means from among the names of the associated nodes. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -field NodeSymbolicName

Contains a string not exceeding 256 bytes in length that indicates the symbolic name of the fibre channel node (machine) that the adapter is located on. 


### -field HardwareVersion

Contains a string not exceeding 256 bytes in length that indicates the hardware revision level of the HBA.


### -field DriverVersion

Contains a string not exceeding 256 bytes in length that indicates version of the driver that manages the HBA.


### -field OptionROMVersion

Contains a string not exceeding 256 bytes in length that specifies the option ROM or the version of the BIOS of the HBA. 


### -field FirmwareVersion

Contains a string not exceeding 256 bytes in length that identifies the version of the HBA's firmware.


### -field VendorSpecificID

Contains a vendor-specified ID. 


### -field NumberOfPorts

Indicates the number of ports on the HBA. 


### -field DriverName

Contains a string not exceeding 256 bytes in length that indicates name of the file that contains the binary image of the device driver for the HBA. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556078">HBA_GetAdapterAttributes</a>
 

 

