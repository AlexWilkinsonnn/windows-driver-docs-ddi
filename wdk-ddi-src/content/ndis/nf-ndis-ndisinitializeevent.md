---
UID: NF:ndis.NdisInitializeEvent
title: NdisInitializeEvent function
description: The NdisInitializeEvent function sets up an event object during driver initialization to be used subsequently as a synchronization mechanism.
old-location: netvista\ndisinitializeevent.htm
tech.root: netvista
ms.assetid: 7f7eac7e-f512-4446-a83b-92d313c14420
ms.date: 05/02/2018
ms.keywords: NdisInitializeEvent, NdisInitializeEvent function [Network Drivers Starting with Windows Vista], ndis/NdisInitializeEvent, ndis_event_ref_35523d4a-3084-43ea-9dc0-6e9017b9ed22.xml, netvista.ndisinitializeevent
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInitializeEvent (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInitializeEvent (NDIS   5.1)) in Windows XP.
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisInitializeEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisInitializeEvent function


## -description


The 
  <b>NdisInitializeEvent</b> function sets up an event object during driver initialization to be used
  subsequently as a synchronization mechanism.


## -parameters




### -param Event [out]

A pointer to caller-supplied storage for the event object, which is opaque to drivers.


## -returns



None




## -remarks



The 
    <b>NdisInitializeEvent</b> function creates an event object that has an event type of 
    <b>NotificationEvent</b> and an initial state of 
    <i>not-signaled</i>. For more information about notification events, see 
    <a href="https://msdn.microsoft.com/4b7807f0-bbea-4402-b028-9ac73724717f">Defining and Using an Event
    Object</a>.

The 
    <i>Event</i> pointer passed to 
    <b>NdisInitializeEvent</b> is a required parameter to all other 
    <b>Ndis<i>Xxx</i>Event</b> functions.

While driver functions that must run at IRQL &lt;= DISPATCH_LEVEL can call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564539">NdisSetEvent</a> and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564526">NdisResetEvent</a> functions ,calling 
    <b>NdisWaitEvent</b> from any IRQL &gt; PASSIVE_LEVEL is a fatal error.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564526">NdisResetEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564539">NdisSetEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564651">NdisWaitEvent</a>
 

 

