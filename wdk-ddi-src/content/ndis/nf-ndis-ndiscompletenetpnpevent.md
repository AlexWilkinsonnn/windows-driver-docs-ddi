---
UID: NF:ndis.NdisCompleteNetPnPEvent
title: NdisCompleteNetPnPEvent function
author: windows-driver-content
description: Protocol drivers call the NdisCompleteNetPnPEvent function to complete a response to a Plug and Play or Power Management event for which the caller's ProtocolNetPnPEvent function returned NDIS_STATUS_PENDING.
old-location: netvista\ndiscompletenetpnpevent.htm
tech.root: netvista
ms.assetid: 2a59e6a1-d018-4b95-8e50-8351a3b69d86
ms.date: 05/02/2018
ms.keywords: NdisCompleteNetPnPEvent, NdisCompleteNetPnPEvent function [Network Drivers Starting with Windows Vista], ndis/NdisCompleteNetPnPEvent, netvista.ndiscompletenetpnpevent, protocol_ndis_functions_ref_4f57d0f9-c9bf-4451-a612-caa665d0b6be.xml
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisCompleteNetPnPEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCompleteNetPnPEvent function


## -description


Protocol drivers call the 
  <b>NdisCompleteNetPnPEvent</b> function to complete a response to a Plug and Play or Power Management event
  for which the caller's 
  <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function returned
  NDIS_STATUS_PENDING.


## -parameters




### -param NdisBindingHandle [in]

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function. The handle
     identifies the binding between the caller and the underlying miniport adapter.


### -param NetPnPEventNotification

A pointer to a 
     <a href="https://msdn.microsoft.com/58d3baf3-a1fa-42ae-b795-2774a148aeda">
     NET_PNP_EVENT_NOTIFICATION</a> structure that NDIS passed to the caller's 
     <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">
     ProtocolNetPnPEvent</a> function.

### -param Status [in]

The protocol driver's response to the pending Plug and Play or Power Management event
     notification. To succeed such an event, specify NDIS_STATUS_SUCCESS. For information about other status
     values, see the return values of the 
     <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">
     ProtocolNetPnPEvent</a> function.


## -returns



None




## -remarks



When a protocol driver returns NDIS_STATUS_PENDING from its 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function, it
    must eventually call 
    <b>NdisCompleteNetPnPEvent</b> to indicate its response to the given Plug and Play or Power Management
    notification.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568752">NET_PNP_EVENT_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a>
 

 

