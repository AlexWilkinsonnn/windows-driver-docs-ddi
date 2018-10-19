---
UID: NF:ndis.NdisWriteRegisterUlong
title: NdisWriteRegisterUlong macro
author: windows-driver-content
description: NdisWriteRegisterUlong is called by the miniport driver to write a ULONG to a memory-mapped device register.
old-location: netvista\ndiswriteregisterulong.htm
tech.root: netvista
ms.assetid: f21954a8-66a0-40c5-9116-da6e57d24f53
ms.date: 05/02/2018
ms.keywords: NdisWriteRegisterUlong, NdisWriteRegisterUlong macro [Network Drivers Starting with Windows Vista], miniport_register_ref_2f7b1091-df45-47d7-9dd7-9a6f39e0b19d.xml, ndis/NdisWriteRegisterUlong, netvista.ndiswriteregisterulong
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteRegisterUlong (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteRegisterUlong (NDIS   5.1)) in Windows XP.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisWriteRegisterUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisWriteRegisterUlong macro


## -description


<b>NdisWriteRegisterUlong</b> is called by the miniport driver to write a ULONG to a memory-mapped device
  register.


## -parameters




### -param Register [in]

Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>.


### -param Data [in]

Specifies the caller-supplied ULONG that this function transfers to the 
     <i>Register</i> .


## -remarks



If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564514">NdisReadRegisterUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564678">NdisWriteRegisterUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564685">NdisWriteRegisterUshort</a>
 

 

