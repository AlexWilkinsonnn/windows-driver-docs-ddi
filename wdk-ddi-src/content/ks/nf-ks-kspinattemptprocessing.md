---
UID: NF:ks.KsPinAttemptProcessing
title: KsPinAttemptProcessing function (ks.h)
description: The KsPinAttemptProcessing function is used to resume processing on a specific pin on a pin-centric filter. It attempts to initiate processing on Pin by sending a processing dispatch call to Pin's processing object.
old-location: stream\kspinattemptprocessing.htm
tech.root: stream
ms.assetid: 9b916114-85aa-4ab7-acaa-6b19d0a4d776
ms.date: 04/23/2018
ms.keywords: KsPinAttemptProcessing, KsPinAttemptProcessing function [Streaming Media Devices], avfunc_e17d5ad8-b0e3-4b5e-ab4c-a552f1650ed4.xml, ks/KsPinAttemptProcessing, stream.kspinattemptprocessing
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL (See Remarks)"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsPinAttemptProcessing
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinAttemptProcessing function


## -description


The<b> KsPinAttemptProcessing</b> function is used to resume processing on a specific pin on a pin-centric filter. It attempts to initiate processing on <i>Pin</i> by sending a processing dispatch call to <i>Pin</i>'s processing object.


## -parameters




### -param Pin [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure that represents the AVStream pin object on which to attempt processing.


<div class="alert"><b>Warning</b>  This parameter is mandatory. If you call <b>KsPinAttemptProcessing</b> with a <i>Pin</i> value of <b>NULL</b>, system instability may result.</div>
<div> </div>



### -param Asynchronous [in]

This parameter indicates the minidriver's preference whether the processing should occur synchronously or asynchronously. If <b>TRUE</b>, processing is always asynchronous. However, synchronous processing only happens under certain circumstances. For more information, see the Remarks section below.


## -returns



None




## -remarks



A minidriver may need to call <b>KsPinAttemptProcessing</b> to resume processing in various situations. For example, if the client has shut off the processing control gate with <a href="https://msdn.microsoft.com/library/windows/hardware/ff562589">KsGateTurnInputOff</a>, call this function when ready to attempt processing. Note that this only causes a processing dispatch if the process control gate is in the open state. Another situation involves the minidriver having previously returning STATUS_PENDING to a processing dispatch. For more details, see <a href="https://msdn.microsoft.com/f60d4dbd-61e6-4ae2-aa43-9edc8f36c3ff">Restarting Processing in AVStream</a> and <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

The processing dispatch occurs either synchronously or asynchronously, and <i>only</i> if the processing control gate is open. The <i>Asynchronous</i> flag specifies the minidriver's preference. If the minidriver requests an asynchronous process dispatch, the dispatch is always asynchronous. However, even if the caller sets <i>Asynchronous</i> to <b>FALSE</b>, a synchronous dispatch only occurs if the system is currently running at an IRQL less than the maximum processing IRQL. In other words, if the minidriver does not specify dispatch level processing and the call is made at IRQL = DISPATCH_LEVEL, then the call occurs in an asynchronous work item at PASSIVE_LEVEL regardless of the value of <i>Asynchronous</i>. For more information, see <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a> and <a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">Pin-Centric Processing</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562554">KSFILTER_DISPATCH</a>



<b>KSGATE</b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562527">KsFilterAttemptProcessing</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562571">KsGateCaptureThreshold</a>
 

 

