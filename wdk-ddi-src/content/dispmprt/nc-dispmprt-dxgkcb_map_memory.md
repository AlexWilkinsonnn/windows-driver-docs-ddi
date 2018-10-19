---
UID: NC:dispmprt.DXGKCB_MAP_MEMORY
title: DXGKCB_MAP_MEMORY
author: windows-driver-content
description: The DxgkCbMapMemory function maps a range of translated physical addresses (associated with a memory resource assigned to a display adapter) into system space or the virtual address space of a user-mode process.
old-location: display\dxgkcbmapmemory.htm
tech.root: display
ms.assetid: 916a4d1d-0c40-4125-89ae-488251b04810
ms.date: 05/10/2018
ms.keywords: DXGKCB_MAP_MEMORY, DXGKCB_MAP_MEMORY callback, DpFunctions_51d99a74-2fae-40b7-9e04-8afe0fc38805.xml, DxgkCbMapMemory, DxgkCbMapMemory callback function [Display Devices], display.dxgkcbmapmemory, dispmprt/DxgkCbMapMemory
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkCbMapMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKCB_MAP_MEMORY callback function


## -description


The <b>DxgkCbMapMemory</b> function maps a range of translated physical addresses (associated with a memory resource assigned to a display adapter) into system space or the virtual address space of a user-mode process.


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>.


### -param TranslatedAddress [in]

The base translated physical address of the memory range to be mapped. The display miniport driver previously obtained this address by calling <a href="https://msdn.microsoft.com/cb627eab-93b9-49c5-bd35-4a57220366e7">DxgkCbGetDeviceInformation</a>.


### -param Length [in]

The size, in bytes, of the range to be mapped.


### -param InIoSpace [in]

A Boolean value that specifies whether the range is in I/O space (<b>TRUE</b>) or memory space (<b>FALSE</b>).


### -param MapToUserMode [in]

A Boolean value that specifies whether the range is mapped into user-mode space or system space. If <b>TRUE</b>, the range is mapped into the (user-mode) virtual address space of the current process. If <b>FALSE</b>, the range is mapped into system space. If <i>InIoSpace</i> is <b>TRUE</b>, this parameter is ignored.


### -param CacheType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff554430">MEMORY_CACHING_TYPE</a> enumerator that specifies the caching behavior of the mapped range.


### -param *VirtualAddress [out]

A pointer to a variable that receives the address of the beginning of the mapped range. The way that the mapped range is accessed depends on the values of <i>InIoSpace</i> and <i>MapToUserMode</i>. The following table summarizes the different ways that the mapped range is accessed.

<table>
<tr>
<td></td>
<td><i>MapToUserMode</i> is <b>FALSE</b></td>
<td><i>MapToUserMode</i> is <b>TRUE</b></td>
</tr>
<tr>
<td><i>InIoSpace</i> is <b>FALSE</b></td>
<td>READ_REGISTER_X WRITE_REGISTER_X</td>
<td>User-mode code performs ordinary memory access.</td>
</tr>
<tr>
<td><i>InIoSpace</i> is <b>TRUE</b></td>
<td>READ_PORT_X WRITE_PORT_X</td>
<td>Not possible.</td>
</tr>
</table>
 


## -returns



<b>DxgkCbMapMemory</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



The PHYSICAL_ADDRESS data type is defined in <i>Ntdef.h</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554430">MEMORY_CACHING_TYPE</a>
 

 

