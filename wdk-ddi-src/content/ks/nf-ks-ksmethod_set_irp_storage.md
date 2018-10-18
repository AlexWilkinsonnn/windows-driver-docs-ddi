---
UID: NF:ks.KSMETHOD_SET_IRP_STORAGE
title: KSMETHOD_SET_IRP_STORAGE macro
author: windows-driver-content
description: This macro returns a pointer to the KSMETHOD_SET in which the method is located.
old-location: stream\ksmethod_set_irp_storage.htm
tech.root: stream
ms.assetid: bc0a309d-305e-400a-b571-7958926dd1dc
ms.date: 4/23/2018
ms.keywords: KSMETHOD_SET_IRP_STORAGE, KSMETHOD_SET_IRP_STORAGE macro [Streaming Media Devices], ks/KSMETHOD_SET_IRP_STORAGE, ksfunc_d413bf2a-7d63-48c2-9e75-d84cf1344f5c.xml, stream.ksmethod_set_irp_storage
ms.topic: macro
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSMETHOD_SET_IRP_STORAGE
product:
- Windows
targetos: Windows
req.typenames: 
---

# KSMETHOD_SET_IRP_STORAGE macro


## -description


This macro returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563423">KSMETHOD_SET</a> in which the method is located.


## -parameters




### -param Irp [in]

Specifies the IRP passed to the handler routine.


## -remarks



The pointer to a KSMETHOD_SET structure is extracted from <b>Irp-&gt;Tail.Overlay.DriverContext</b>. Parameters in <b>DriverContext</b> are initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff563399">KsMethodHandler</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563401">KsMethodHandlerWithAllocator</a>.

The macro is defined as follows:

<pre class="syntax" xml:space="preserve"><code>#define KSMETHOD_SET_IRP_STORAGE(Irp)       (*(const KSMETHOD_SET**)&amp;(Irp)-&gt;Tail.Overlay.DriverContext[0])</code></pre>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563420">KSMETHOD_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563423">KSMETHOD_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561940">KsFastMethodHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563399">KsMethodHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563401">KsMethodHandlerWithAllocator</a>
 

 

