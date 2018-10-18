---
UID: NF:fltkernel.FltCurrentBatchOplock
title: FltCurrentBatchOplock function
author: windows-driver-content
description: A minifilter driver calls FltCurrentBatchOplock to determine whether there are any batch or filter opportunistic locks (oplocks) on a file.
old-location: ifsk\fltcurrentbatchoplock.htm
tech.root: ifsk
ms.assetid: 00eb27ee-2c6d-47c7-b3a6-63a6a7aac2fb
ms.date: 4/16/2018
ms.keywords: FltApiRef_a_to_d_7835829e-3397-47c3-bc12-c77f8d844927.xml, FltCurrentBatchOplock, FltCurrentBatchOplock function [Installable File System Drivers], fltkernel/FltCurrentBatchOplock, ifsk.fltcurrentbatchoplock
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
-	FltCurrentBatchOplock
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCurrentBatchOplock function


## -description


A minifilter driver calls <b>FltCurrentBatchOplock</b> to determine whether there are any batch or filter opportunistic locks (oplocks) on a file. 


## -parameters




### -param Oplock [in]

Opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>. 


## -returns



<b>FltCurrentBatchOplock</b> returns <b>TRUE</b> if there are current outstanding batch or filter oplocks; <b>FALSE</b> otherwise. 




## -remarks



<b>FltCurrentBatchOplock</b> returns <b>FALSE</b> if no batch or filter opportunistic locks are currently held. 

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541844">FltCheckOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543398">FltOplockFsctrl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543404">FltOplockIsFastIoPossible</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544598">FltUninitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545825">FsRtlCurrentBatchOplock</a>
 

 

