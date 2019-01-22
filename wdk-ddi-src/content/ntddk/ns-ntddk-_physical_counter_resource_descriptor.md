---
UID: NS:ntddk._PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR
title: "_PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR"
author: windows-driver-content
description: The PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structure describes the counter resources available on the platform.
old-location: kernel\physical_counter_resource_descriptor.htm
tech.root: kernel
ms.assetid: 9b4c35a1-04b9-4d4d-9a57-2f5711ec7418
ms.date: 04/30/2018
ms.keywords: "*PPHYSICAL_COUNTER_RESOURCE_DESCRIPTOR, PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR, PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structure [Kernel-Mode Driver Architecture], PPHYSICAL_COUNTER_RESOURCE_DESCRIPTOR, PPHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structure pointer [Kernel-Mode Driver Architecture], _PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR, kernel.physical_counter_resource_descriptor, kstruct_c_d1ca3bce-f598-4c61-9832-defae021d224.xml, ntddk/PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR, ntddk/PPHYSICAL_COUNTER_RESOURCE_DESCRIPTOR"
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
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
-	ntddk.h
api_name:
-	PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR, *PPHYSICAL_COUNTER_RESOURCE_DESCRIPTOR
---

# _PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structure


## -description


The <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structure describes the counter resources available on the platform.


## -struct-fields




### -field Type

Indicates the type of counter resource described by the structure. Set this parameter to one of the following <a href="https://msdn.microsoft.com/library/windows/hardware/ff558797">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE</a> enumeration constants:

<ul>
<li>
<b>ResourceTypeSingle</b>

</li>
<li>
<b>ResourceTypeRange</b>

</li>
<li>
<b>ResourceTypeExtendedCounterConfiguration</b> (currently unsupported)

</li>
<li>
<b>ResourceTypeOverflow</b>

</li>
<li>
<b>ResourceTypeEventBuffer</b>

</li>
</ul>

### -field Flags

No flags are currently defined. Set this member to zero.


### -field u

A union that can contain a <b>CounterIndex</b>, <b>Range</b>, <b>OverflowHandler</b>, or <b>EventBufferConfiguration</b> value.


### -field u.CounterIndex

A physical counter index.


### -field u.Range.Begin

The starting counter index of a block of contiguous counters.


### -field u.Range.End

The ending counter index of a block of contiguous counters.

### -field u.Range

A range of counter indexes.


### -field u.OverflowHandler

A pointer to the <a href="..\ntddk\nc-ntddk-pphysical_counter_overflow_handler.md">PPHYSICAL_COUNTER_OVERFLOW_HANDLER</a> routine that will be called when an associated hardware counter (specified by another <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b>) overflows.


### -field u.EventBufferConfiguration

A configuration for event buffer based sampling (such as Intel's PEBS).


### -field u.EventBufferConfiguration.OverflowHandler


A pointer to the <a href="..\ntddk\nc-ntddk-pphysical_counter_event_buffer_overflow_handler.md">PPHYSICAL_COUNTER_EVENT_BUFFER_OVERFLOW_HANDLER</a> routine that will be called when the event buffer entries reach a threshold in the event buffer.


### -field u.EventBufferConfiguration.CustomEventBufferEntrySize

The size of the event buffer entries, for custom event buffer sizes. This should be set to 0.


### -field.u.EventBufferConfiguration.EventThreshold

The number of events to be recorded before the EventBufferOverflowHandler is invoked. This value is used as a maximum threshold. The actual number of events will depend on the number of actors using event buffer profiling.

## -remarks



Most processors have performance monitor units that contain a number of hardware counters for measuring various aspects of system performance. The <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structure describes a counter resource, which can be a single hardware counter, a block of contiguous counters, a counter overflow interrupt, or an event buffer configuration. This structure's <b>Type</b> member indicates which type of counter resource is described by the structure.

To specify a set of counter resources, a kernel-mode client can provide an array of <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structures. A <a href="https://msdn.microsoft.com/library/windows/hardware/ff558798">PHYSICAL_COUNTER_RESOURCE_LIST</a> structure serves as a header for the array. The client can allocate and free the set of counter resources described by the array as a single unit.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558797">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558798">PHYSICAL_COUNTER_RESOURCE_LIST</a>
 

 

