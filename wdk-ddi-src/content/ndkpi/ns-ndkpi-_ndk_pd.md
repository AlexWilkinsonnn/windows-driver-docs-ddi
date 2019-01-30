---
UID: NS:ndkpi._NDK_PD
title: "_NDK_PD" (ndkpi.h)
description: The NDK_PD structure specifies the attributes of an NDK protection domain (PD) object.
old-location: netvista\ndk_pd.htm
tech.root: netvista
ms.assetid: 77D3503A-8544-4E73-AD17-56F9C8603068
ms.date: 05/02/2018
ms.keywords: NDK_PD, NDK_PD structure [Network Drivers Starting with Windows Vista], PNDK_PD, PNDK_PD structure pointer [Network Drivers Starting with Windows Vista], _NDK_PD, ndkpi/NDK_PD, ndkpi/PNDK_PD, netvista.ndk_pd
ms.topic: struct
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
-	ndkpi.h
api_name:
-	NDK_PD
product:
- Windows
targetos: Windows
req.typenames: NDK_PD
---

# _NDK_PD structure


## -description


The <b>NDK_PD</b> structure specifies the attributes of an NDK protection domain (PD) object.


## -struct-fields




### -field Header

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a> structure for the <b>NDK_PD</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypePd</b>.


### -field Dispatch

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439932">NDK_PD_DISPATCH</a> structure that defines dispatch functions for the NDK PD object.


## -remarks



An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439932">NDK_PD_DISPATCH</a> table before returning the  created PD object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.




## -see-also




<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439871">NDK_FN_CREATE_COMPLETION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439877">NDK_FN_CREATE_PD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439932">NDK_PD_DISPATCH</a>
 

 

