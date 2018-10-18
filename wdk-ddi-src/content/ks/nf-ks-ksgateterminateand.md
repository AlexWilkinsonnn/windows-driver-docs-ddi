---
UID: NF:ks.KsGateTerminateAnd
title: KsGateTerminateAnd function
author: windows-driver-content
description: The KsGateTerminateAnd function deletes an existing AND gate and removes an input from any attached OR gate.
old-location: stream\ksgateterminateand.htm
tech.root: stream
ms.assetid: 3f29fb48-5145-4b2c-8a0c-3130f4491675
ms.date: 4/23/2018
ms.keywords: KsGateTerminateAnd, KsGateTerminateAnd function [Streaming Media Devices], avfunc_e8c3af46-fdb4-4e95-8473-12e1fadff072.xml, ks/KsGateTerminateAnd, stream.ksgateterminateand
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
-	ks.h
api_name:
-	KsGateTerminateAnd
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGateTerminateAnd function


## -description


The<b> KsGateTerminateAnd</b> function deletes an existing AND gate and removes an input from any attached OR gate.


## -parameters




### -param AndGate [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a> structure that is the AND gate to delete. This gate must be at the beginning of a gate chain.


## -returns



None




## -remarks



Logical gates should be deleted in a front to back manner. <b>KsGateTerminateAnd</b> does not update the gate chain for gates that are deleted at the end or in the middle. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562574">KsGateInitializeAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562576">KsGateInitializeOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562588">KsGateTerminateOr</a>
 

 

