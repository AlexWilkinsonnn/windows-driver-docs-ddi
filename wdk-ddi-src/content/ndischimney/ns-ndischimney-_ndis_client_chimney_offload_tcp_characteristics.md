---
UID: NS:ndischimney._NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
title: _NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS (ndischimney.h)
description: The NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure specifies a protocol or intermediate driver's TCP chimney offload-specific entry points.
old-location: netvista\ndis_client_chimney_offload_tcp_characteristics.htm
tech.root: netvista
ms.assetid: 1925cfd4-f83f-48a5-b928-2c663ac0dc61
ms.date: 05/02/2018
ms.keywords: "*PNDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, PNDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, ndischimney/NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, ndischimney/PNDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, netvista.ndis_client_chimney_offload_tcp_characteristics, tcp_chim_struct_8bfa1be6-3a5f-463a-a2c2-8f2a1f7e55e3.xml"
ms.topic: struct
req.header: ndischimney.h
req.include-header: Ndischimney.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndischimney.h
api_name:
- NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, *PNDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
---

# _NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure specifies a protocol or intermediate
  driver's TCP chimney offload-specific entry points.


## -struct-fields




### -field Header

The header of the NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure. The header is
     formatted as an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure and the size of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure, including the header, in bytes. The 
     <b>Type</b> member of the header is not significant.


### -field Flags

Reserved for system use.


### -field OffloadType

The chimney offload type. The only allowable value is 
     <b>NdisTcpChimneyOffload</b>, which specifies a TCP chimney.


### -field TcpOffloadSendCompleteHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/6f9c7964-e475-421c-99d6-f4fc31a26f02">
     ProtocolTcpOffloadSendComplete</a> function.


### -field TcpOffloadReceiveCompleteHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/78201512-6b70-4b4b-9016-0f42fed41ac6">
     ProtocolTcpOffloadReceiveComplete</a> function.


### -field TcpOffloadDisconnectCompleteHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/56244148-638f-4d93-82a6-2cced9744046">
     ProtocolTcpOffloadDisconnectComplete</a> function.


### -field TcpOffloadForwardCompleteHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/02a11841-d98a-4c74-8922-458826e2911e">
     ProtocolTcpOffloadForwardComplete</a> function.


### -field TcpOffloadEventHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/b64c0f9e-aa3d-43c5-bdf5-c40cae3929e3">
     ProtocolTcpOffloadEvent</a> function.


### -field TcpOffloadReceiveIndicateHandler

The entry point of the driver's 
     <a href="https://msdn.microsoft.com/8a400515-3619-4fe9-8e08-638859442ea3">
     ProtocolTcpOffloadReceiveIndicate</a> function.


## -remarks



To register its TCP chimney offload entry points, a protocol or intermediate driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function, the protocol or intermediate driver passes a pointer to the
    NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>



<a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a>



<a href="https://msdn.microsoft.com/56244148-638f-4d93-82a6-2cced9744046">
   ProtocolTcpOffloadDisconnectComplete</a>



<a href="https://msdn.microsoft.com/b64c0f9e-aa3d-43c5-bdf5-c40cae3929e3">ProtocolTcpOffloadEvent</a>



<a href="https://msdn.microsoft.com/78201512-6b70-4b4b-9016-0f42fed41ac6">
   ProtocolTcpOffloadReceiveComplete</a>



<a href="https://msdn.microsoft.com/8a400515-3619-4fe9-8e08-638859442ea3">
   ProtocolTcpOffloadReceiveIndicate</a>



<a href="https://msdn.microsoft.com/6f9c7964-e475-421c-99d6-f4fc31a26f02">
   ProtocolTcpOffloadSendComplete</a>
 

 

