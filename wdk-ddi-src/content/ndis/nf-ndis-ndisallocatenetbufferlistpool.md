---
UID: NF:ndis.NdisAllocateNetBufferListPool
title: NdisAllocateNetBufferListPool function
author: windows-driver-content
description: Call the NdisAllocateNetBufferListPool function to allocate a pool of NET_BUFFER_LIST structures.
old-location: netvista\ndisallocatenetbufferlistpool.htm
tech.root: netvista
ms.assetid: b117b472-0c26-41a9-b364-3d0cfbd26cc9
ms.date: 5/2/2018
ms.keywords: NdisAllocateNetBufferListPool, NdisAllocateNetBufferListPool function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateNetBufferListPool, ndis_netbuf_functions_ref_763044cb-dfaf-4cb5-959c-7895e3e49fb0.xml, netvista.ndisallocatenetbufferlistpool
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: Ndis.sys
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	ndis.sys
api_name:
-	NdisAllocateNetBufferListPool
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAllocateNetBufferListPool function


## -description


Call the 
  <b>NdisAllocateNetBufferListPool</b> function to allocate a pool of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures.


## -parameters




### -param NdisHandle [in, optional]

An NDIS handle that was obtained during caller initialization.


### -param Parameters [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh205394">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure that defines the parameters for the pool.


## -returns



<b>NdisAllocateNetBufferListPool</b> returns a handle to the NET_BUFFER_LIST structure pool that NDIS
     allocates. If the allocation was unsuccessful, this handle is <b>NULL</b>. This handle is a required parameter
     in subsequent calls to NDIS functions that allocate and free NET_BUFFER_LIST structures from this
     pool.




## -remarks



In most cases, a caller that allocates a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure will allocate and
    queue at least one 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure on that NET_BUFFER_LIST
    structure. It is more efficient to preallocate NET_BUFFER structures when you allocate a pool of
    NET_BUFFER_LIST structures than allocating NET_BUFFER_LIST structures and NET_BUFFER structures
    separately.

You can call the 
    <b>NdisAllocateNetBufferListPool</b> function with the 
    <b>fAllocateNetBuffer</b> value set to <b>TRUE</b> when creating a NET_BUFFER_LIST structure pool. In this case,
    a NET_BUFFER structure is preallocated with each NET_BUFFER_LIST structure that the caller allocates from
    the pool. You can call the 
    <a href="https://msdn.microsoft.com/b872eff3-2d0a-4f01-874d-e00e09195801">
    NdisAllocateNetBufferAndNetBufferList</a> function or the 
    <a href="https://msdn.microsoft.com/9c821aac-9abd-4041-a15e-64306ada1c02">
    NdisAllocateNetBufferList</a> function to allocate NET_BUFFER_LIST structures from such a pool. Call 
    <b>NdisAllocateNetBufferAndNetBufferList</b> only if 
    <b>fAllocateNetBuffer</b> is <b>TRUE</b> and 
    <b>DataSize</b> is zero.

You can also call 
    <b>NdisAllocateNetBufferListPool</b> and set the 
    <b>DataSize</b> member to a nonzero value when creating a NET_BUFFER_LIST structure pool. In this case, a
    NET_BUFFER structure, MDL, and data are preallocated with each NET_BUFFER_LIST structure that the caller
    allocates from the pool.

NET_BUFFER structures, MDLs, and data buffers that are allocated with 
    <a href="https://msdn.microsoft.com/b872eff3-2d0a-4f01-874d-e00e09195801">
    NdisAllocateNetBufferAndNetBufferList</a> or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561609">NdisAllocateNetBufferList</a> should
    not be freed separate from the NET_BUFFER_LIST structure. Such structures are freed with the
    NET_BUFFER_LIST structure when you call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562583">NdisFreeNetBufferList</a> function.

Call the 
    <a href="https://msdn.microsoft.com/811df5ea-f5e6-4986-adc0-c5fa95e5f072">
    NdisFreeNetBufferListPool</a> function to free a NET_BUFFER_LIST structure pool.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568389">NET_BUFFER_LIST_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh205394">NET_BUFFER_LIST_POOL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/b872eff3-2d0a-4f01-874d-e00e09195801">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561609">NdisAllocateNetBufferList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562583">NdisFreeNetBufferList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562590">NdisFreeNetBufferListPool</a>
 

 

