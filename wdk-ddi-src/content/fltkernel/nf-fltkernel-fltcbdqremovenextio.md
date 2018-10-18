---
UID: NF:fltkernel.FltCbdqRemoveNextIo
title: FltCbdqRemoveNextIo function
author: windows-driver-content
description: FltCbdqRemoveNextIo removes the next matching item in a minifilter driver's callback data queue.
old-location: ifsk\fltcbdqremovenextio.htm
tech.root: ifsk
ms.assetid: 4f207ef2-e999-4410-aaa1-5d32c4f22864
ms.date: 4/16/2018
ms.keywords: FltApiRef_a_to_d_fec6e01e-c699-45cf-b9fb-c4dea9b2e462.xml, FltCbdqRemoveNextIo, FltCbdqRemoveNextIo function [Installable File System Drivers], fltkernel/FltCbdqRemoveNextIo, ifsk.fltcbdqremovenextio
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
req.lib: 
req.dll: 
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltkernel.h
api_name:
-	FltCbdqRemoveNextIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCbdqRemoveNextIo function


## -description


<i>FltCbdqRemoveNextIo</i> removes the next matching item in a minifilter driver's callback data queue. 


## -parameters




### -param Cbdq [in, out]

Pointer to a cancel-safe callback data queue. This queue must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541802">FltCbdqInitialize</a>. 


### -param PeekContext [in, optional]

Pointer to caller-defined information that identifies the matching item. This parameter is optional and can be <b>NULL</b>. 


## -returns



<i>FltCbdqRemoveNextIo</i> returns a pointer to the callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure for the item that was removed from the queue or <b>NULL</b> if no matching items were found. <i>FltCbdqRemoveNextIo</i> only returns items for I/O operations that have not yet been canceled. 




## -remarks



<i>FltCbdqRemoveNextIo</i> removes the next matching item from a minifilter driver's callback data queue. 

Minifilter drivers can use the <b>FltCbdq</b><i>Xxx</i> routines to implement a callback data queue for IRP-based I/O operations. By using these routines, minifilter drivers can make their queues cancel-safe; the system transparently handles I/O cancellation for the minifilter drivers. 

The <b>FltCbdq</b><i>Xxx</i> routines can only be used for IRP-based I/O operations. To determine whether a given callback data (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>) structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

A callback data queue is initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff541802">FltCbdqInitialize</a>. <i>FltCbdqRemoveNextIo</i> uses the routines provided in the queue's dispatch table to lock the queue and remove the next matching item from the queue. The remove operation itself is performed by the minifilter driver's <i>CbdqRemoveIo</i> callback routine. 

<i>FltCbdqRemoveNextIo</i> uses the queue's <i>CbdqPeekNextIo</i> callback routine to scan the queue for matching items. The <i>PeekContext</i> parameter is passed to the <i>CbdqPeekNextIo</i> callback routine to loop through matching items. The meaning of <i>PeekContext</i> and the criteria for an item to match a given <i>PeekContext</i> are entirely dependent on the minifilter driver.

If the queue is protected by a <a href="https://msdn.microsoft.com/0585fc2a-0d0b-434d-92b3-da07a9385444">spin lock</a>, rather than a <a href="https://msdn.microsoft.com/e2142b6d-f460-4f80-be0f-e00b5d43731c">mutex object</a> or <a href="https://msdn.microsoft.com/be18a6e6-863d-4a0c-9bcd-a36ace0b54fe">resource variable</a>, the caller of <i>FltCbdqRemoveNextIo</i> can be running at IRQL &lt;= DISPATCH_LEVEL. If a mutex or resource is used, the caller must be running at IRQL &lt;= APC_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544624">FLT_CALLBACK_DATA_QUEUE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541796">FltCbdqDisable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541799">FltCbdqEnable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541802">FltCbdqInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541815">FltCbdqInsertIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541821">FltCbdqRemoveIo</a>
 

 

