---
UID: NS:ks._KSDEVICE
title: _KSDEVICE (ks.h)
description: The KSDEVICE structure describes a WDM functional device that is managed by AVStream.
old-location: stream\ksdevice.htm
tech.root: stream
ms.assetid: 95b80298-a3b4-416b-8744-88873ac30037
ms.date: 04/23/2018
ms.keywords: "*PKSDEVICE, KSDEVICE, KSDEVICE structure [Streaming Media Devices], PKSDEVICE, PKSDEVICE structure pointer [Streaming Media Devices], _KSDEVICE, avstruct_0f140861-d58a-48cf-9bac-679acbd30d02.xml, ks/KSDEVICE, ks/PKSDEVICE, stream.ksdevice"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSDEVICE
product:
- Windows
targetos: Windows
req.typenames: KSDEVICE, *PKSDEVICE
---

# _KSDEVICE structure


## -description


The KSDEVICE structure describes a WDM functional device that is managed by AVStream.


## -struct-fields




### -field Descriptor

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561691">KSDEVICE_DESCRIPTOR</a> structure that describes the characteristics of the device and the static filters supported by it.


### -field Bag

This member specifies the KSOBJECT_BAG (equivalent to type PVOID) associated with the device. See <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a>.


### -field Context

A pointer to a memory location that contains context information for the device. AVStream stores a pointer to a device extension in this member for minidrivers that allocate a device extension in <a href="https://msdn.microsoft.com/library/windows/hardware/ff556297">AVStrMiniDeviceStart</a>. Memory allocated for context should be placed in the object bag using <a href="https://msdn.microsoft.com/library/windows/hardware/ff560941">KsAddItemToObjectBag</a>. <b>Context</b> is initialized to <b>NULL</b> at create time.


### -field FunctionalDeviceObject

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that is the WDM functional device object for the device being described.


### -field PhysicalDeviceObject

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that is the WDM physical device object for the device being described.


### -field NextDeviceObject

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that is the next device in the driver stack as determined by <a href="https://msdn.microsoft.com/library/windows/hardware/ff548300">IoAttachDeviceToDeviceStack</a>.


### -field Started

This member indicates whether this particular device has been started or not. If <b>TRUE</b>, the device has been started. If <b>FALSE</b>, the device has not been started. This flag is set during the processing of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> and is reset during the processing of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a>. A device that is not started returns STATUS_DEVICE_NOT_READY in response to all requests to create a filter.


### -field SystemPowerState

A SYSTEM_POWER_STATE-typed value that indicates the current power state of the system. SYSTEM_POWER_STATE values are defined in <i>wdm.h</i>.


### -field DevicePowerState

A DEVICE_POWER_STATE-typed value that indicates the current power state of the device. DEVICE_POWER_STATE values are defined in <i>wdm.h</i>.


## -remarks



Clients typically use this structure if they must implement specific PnP or Power Management behavior that is not provided by AVStream. A pointer to a KSDEVICE structure is the first parameter to all dispatch routines specified in <a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a>, and the client is free to use the context information to attach its own context for these routines. In addition, clients may obtain a pointer to the KSDEVICE structure from a WDM device object pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff562617">KsGetDeviceForDeviceObject</a>.

As mentioned above, <b>Context</b> is initialized to <b>NULL</b> at create time. However, descendants of this KSDEVICE structure have their corresponding <b>Context</b> members set to the value of the parent object's <b>Context</b> member. This happens when the new object is created. For more information, see <a href="https://msdn.microsoft.com/b7d6f06d-6c97-414e-a453-d375e2d7ccf5">AVStream Object Hierarchy</a> and <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a>. Also see the reference pages for the possible AVStream descendant objects: <a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561691">KSDEVICE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560941">KsAddItemToObjectBag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562617">KsGetDeviceForDeviceObject</a>
 

 

