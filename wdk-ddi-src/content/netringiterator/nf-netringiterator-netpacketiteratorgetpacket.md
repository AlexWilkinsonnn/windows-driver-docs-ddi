---
UID: NF:netringiterator.NetPacketIteratorGetPacket
title: NetPacketIteratorGetPacket function
author: windows-driver-content
description: The NetPacketIteratorGetPacket method gets the NET_PACKET structure at a packet iterator's current Index in the packet ring.
tech.root: netvista
ms.assetid: 56c940bd-c792-4570-8d97-c14fa273c4dc
ms.author: windowsdriverdev
ms.date: 02/04/2019
ms.topic: function
f1_keywords:
 - "netringiterator/NetPacketIteratorGetPacket"
ms.keywords: NetPacketIteratorGetPacket
req.header: netringiterator.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib:
req.dll:
req.irql: Any level as long as target memory is resident
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- netringiterator.h
api_name: 
- NetPacketIteratorGetPacket
product:
- Windows
targetos: Windows

---

# NetPacketIteratorGetPacket function


## -description



The **NetPacketIteratorGetPacket** method gets the [**NET_PACKET**](../packet/ns-packet-_net_packet.md) structure at a packet iterator's current **Index** in the packet ring.

## -parameters

### -param Iterator

A pointer to a [**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md) structure.

## -returns

Returns a pointer to the [**NET_PACKET**](../packet/ns-packet-_net_packet.md) structure at the packet iterator's **Index**.

## -remarks

## -see-also

[Net rings and net ring iterators](https://docs.microsoft.com/windows-hardware/drivers/netcx/net-rings-and-net-ring-iterators)

[**NET_RING_PACKET_ITERATOR**](../netringiterator/ns-netringiterator-_net_ring_packet_iterator.md)

[**NET_PACKET**](../packet/ns-packet-_net_packet.md)
