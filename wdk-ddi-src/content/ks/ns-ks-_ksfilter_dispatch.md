---
UID: NS:ks._KSFILTER_DISPATCH
title: "_KSFILTER_DISPATCH"
description: The KSFILTER_DISPATCH structure describes the client callbacks that are made to notify the client of certain events on a given filter type.
old-location: stream\ksfilter_dispatch.htm
tech.root: stream
ms.assetid: 3b84c06f-774e-45e1-9a64-711749bb3a88
ms.date: 04/23/2018
ms.keywords: "*PKSFILTER_DISPATCH, KSFILTER_DISPATCH, KSFILTER_DISPATCH structure [Streaming Media Devices], PKSFILTER_DISPATCH, PKSFILTER_DISPATCH structure pointer [Streaming Media Devices], _KSFILTER_DISPATCH, avstruct_cfadb813-12c3-4960-89d7-72a75db1684a.xml, ks/KSFILTER_DISPATCH, ks/PKSFILTER_DISPATCH, stream.ksfilter_dispatch"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSFILTER_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: KSFILTER_DISPATCH, *PKSFILTER_DISPATCH
---

# _KSFILTER_DISPATCH structure


## -description


The KSFILTER_DISPATCH structure describes the client callbacks that are made to notify the client of certain events on a given filter type.


## -struct-fields




### -field Create

Optional. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556310">AVStrMiniFilterCreate</a> callback routine.


### -field Close

Optional. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556307">AVStrMiniFilterClose</a> callback routine.


### -field Process

Optional. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556315">AVStrMiniFilterProcess</a> callback routine.


### -field Reset

Optional. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556317">AVStrMiniFilterReset</a> callback routine.


## -remarks



Any of the callback pointers may be <b>NULL</b>, indicating that the driver does not wish to receive notification of a given event.

Also see <a href="https://msdn.microsoft.com/f60d4dbd-61e6-4ae2-aa43-9edc8f36c3ff">Restarting Processing in AVStream</a> and 


<a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564256">KSPROCESSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564260">KSPROCESSPIN_INDEXENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561025">KsCompletePendingRequest</a>
 

 

