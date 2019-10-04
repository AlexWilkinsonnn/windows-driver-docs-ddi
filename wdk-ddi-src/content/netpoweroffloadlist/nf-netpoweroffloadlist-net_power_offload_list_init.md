---
UID: NF:netpoweroffloadlist.NET_POWER_OFFLOAD_LIST_INIT
title: NET_POWER_OFFLOAD_LIST_INIT function (netpoweroffloadlist.h)
author: windows-driver-content
description: TBD
tech.root:
ms.assetid: 69577bdf-fff6-498f-ba80-fb1678e8145f
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
f1_keywords:
 - "netpoweroffloadlist/NET_POWER_OFFLOAD_NS_PARAMETERS"
ms.keywords: NET_POWER_OFFLOAD_LIST_INIT
req.header: netpoweroffloadlist.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
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
- 
api_location: 
- 
api_name: 
- NET_POWER_OFFLOAD_LIST_INIT
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NET_POWER_OFFLOAD_LIST_INIT function


## -description

The **NET_POWER_OFFLOAD_LIST_INIT** method initializes a [**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md) structure.

## -parameters

### -param List

A handle to a driver-allocated [**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md) structure.

## -returns

This method does not return a value.

## -remarks

This method zeros out the memory for the **NET_POWER_OFFLOAD_LIST** structure, then fills in the **Size** member. After calling this method, call [**NetDeviceGetPowerOffloadList**](../netpoweroffloadlist/nf-netpoweroffloadlist-netdevicegetpoweroffloadlist.md) with the initialized structure to get the list of low power offloads to this net adapter.

For a code sample of working with NETPOWEROFFLOAD objects, see [Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_POWER_OFFLOAD_LIST**](../netpoweroffloadlist/ns-netpoweroffloadlist-_net_power_offload_list.md)

[**NetDeviceGetPowerOffloadList**](../netpoweroffloadlist/nf-netpoweroffloadlist-netdevicegetpoweroffloadlist.md)