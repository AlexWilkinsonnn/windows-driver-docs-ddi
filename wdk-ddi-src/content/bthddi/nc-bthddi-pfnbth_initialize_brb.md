---
UID: NC:bthddi.PFNBTH_INITIALIZE_BRB
title: PFNBTH_INITIALIZE_BRB
author: windows-driver-content
description: The BthInitializeBrb function initializes a Bluetooth request block (BRB) allocated on the local stack.
old-location: bltooth\bthinitializebrb.htm
tech.root: bltooth
ms.assetid: 0b822d28-edaa-40cc-a678-112a356d9022
ms.date: 4/27/2018
ms.keywords: BthInitializeBrb, BthInitializeBrb callback function [Bluetooth Devices], PFNBTH_INITIALIZE_BRB, PFNBTH_INITIALIZE_BRB callback, bltooth.bthinitializebrb, bth_funcs_11ec7e91-bfca-404f-a029-a3fbb8c56d47.xml, bthddi/BthInitializeBrb
ms.topic: callback
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	bthddi.h
api_name:
-	BthInitializeBrb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNBTH_INITIALIZE_BRB callback function


## -description


The 
  <i>BthInitializeBrb</i> function initializes a Bluetooth request block (BRB) allocated on the local
  stack.


## -parameters




### -param pBrb [in, out]

Pointer to the BRB to initialize.


### -param brbType [in]

Specifies a value from the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536631">BRB_TYPE</a> enumeration to initialize the BRB
     with.


## -returns



None.




## -remarks



Profile drivers should use 
    <i>BthInitializeBrb</i> for stack based allocations, such as declaring variables at the beginning of a
    function.

It is not necessary to call this function for a BRB that was allocated using 
    <a href="https://msdn.microsoft.com/e1ac9d4c-75e2-4d37-86d7-3c3f1486222e">BthAllocateBrb</a>.

Profile drivers obtain a pointer to the 
    <i>BthInitializeBrb</i> function when they query the Bluetooth driver stack for an instance of the
    BTHDDI_PROFILE_DRIVER_INTERFACE driver interface. See 
    <a href="https://msdn.microsoft.com/56db29cd-26ab-4262-9b9f-40d46372ffe9">Querying for Bluetooth
    Interfaces</a> for more information about querying the Bluetooth driver stack.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536631">BRB_TYPE</a>



<a href="https://msdn.microsoft.com/e1ac9d4c-75e2-4d37-86d7-3c3f1486222e">BthAllocateBrb</a>
 

 

