---
UID: NF:ks.KsGateRemoveOffInputFromOr
title: KsGateRemoveOffInputFromOr function (ks.h)
description: The KsGateRemoveOffInputFromOr function removes an existing input that is in the OFF state from an OR gate.
old-location: stream\ksgateremoveoffinputfromor.htm
tech.root: stream
ms.assetid: 191874ec-5d08-430e-ad14-520392e1a904
ms.date: 04/23/2018
ms.keywords: KsGateRemoveOffInputFromOr, KsGateRemoveOffInputFromOr function [Streaming Media Devices], avfunc_6431bb18-7f16-4a0f-b012-c0137d85fba8.xml, ks/KsGateRemoveOffInputFromOr, stream.ksgateremoveoffinputfromor
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KsGateRemoveOffInputFromOr
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGateRemoveOffInputFromOr function


## -description


The<b> KsGateRemoveOffInputFromOr</b> function removes an existing input that is in the OFF state from an OR gate.


## -parameters




### -param OrGate [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a> structure representing the OR gate from which to remove an OFF input.


## -returns



None




## -remarks



<b>KsGateRemoveOffInputFromOr</b> should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is truly an AND gate.

For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

This call is an empty function. It should be used for code readability and clarity. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562568">KsGateAddOffInputToOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562570">KsGateAddOnInputToOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562585">KsGateRemoveOnInputFromOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562589">KsGateTurnInputOff</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562591">KsGateTurnInputOn</a>
 

 

