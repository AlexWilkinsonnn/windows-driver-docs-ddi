---
UID: NF:fltkernel.FltAcknowledgeEcp
title: FltAcknowledgeEcp function
author: windows-driver-content
description: The FltAcknowledgeEcp routine is used to mark an extra create parameter context structure (ECP) as acknowledged.
old-location: ifsk\fltacknowledgeecp.htm
tech.root: ifsk
ms.assetid: 89fd8a33-9b2e-401a-9b48-49b4b19d3cb2
ms.date: 04/16/2018
ms.keywords: FltAcknowledgeEcp, FltAcknowledgeEcp routine [Installable File System Drivers], FltApiRef_a_to_d_17c8b1d4-47d1-4871-be9d-57986967a083.xml, fltkernel/FltAcknowledgeEcp, ifsk.fltacknowledgeecp
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltAcknowledgeEcp
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltAcknowledgeEcp function


## -description


The <b>FltAcknowledgeEcp</b> routine is used to mark an extra create parameter context structure (ECP) as acknowledged.


## -parameters




### -param Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param EcpContext [in]

Pointer to the ECP to mark as acknowledged.


## -returns



None




## -remarks



This routine is available in Windows Vista and later. 

The ECP pointed to by the <i>EcpContext</i> parameter is marked as "acknowledged" by this routine.  This acknowledgment could indicate a number of things, including whether the ECP has been looked at, used, processed, and so on.  Note that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543321">FltIsEcpAcknowledged</a> routine can be used to determine if a particular ECP has been marked as acknowledged.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541734">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543321">FltIsEcpAcknowledged</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543325">FltIsEcpFromUserMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>
 

 

