---
UID: NF:fltkernel.FltAllocateFileLock
title: FltAllocateFileLock function (fltkernel.h)
description: The FltAllocateFileLock routine allocates and initializes a new FILE_LOCK structure.
old-location: ifsk\fltallocatefilelock.htm
tech.root: ifsk
ms.assetid: f5a96fc2-e6b8-44df-a827-d10d693f6f2b
ms.date: 04/16/2018
ms.keywords: FltAllocateFileLock, FltAllocateFileLock routine [Installable File System Drivers], FltApiRef_a_to_d_f59cead3-059a-4457-9339-c90cc007ca63.xml, fltkernel/FltAllocateFileLock, ifsk.fltallocatefilelock
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows XP with SP2 or Windows Server 2003 with SP1.
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltAllocateFileLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltAllocateFileLock function


## -description


The <b>FltAllocateFileLock</b> routine allocates and initializes a new <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure. 


## -parameters




### -param CompleteLockCallbackDataRoutine [in, optional]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551073">PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE</a>-typed callback routine to be called when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> request is completed. This parameter is optional and can be <b>NULL</b>. 


### -param UnlockRoutine [in, optional]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551951">PUNLOCK_ROUTINE</a>-typed callback routine to be called when the byte range is unlocked. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltAllocateFileLock</b> returns a pointer to the newly allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure. 




## -remarks



<b>FltAllocateFileLock</b> allocates a new <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure from paged pool and initializes it.

The returned <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure can be used to lock a byte range in a file by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543427">FltProcessFileLock</a>. 

When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure is no longer needed, it can be uninitialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544595">FltUninitializeFileLock</a>. The uninitialized <b>FILE_LOCK</b> structure can then be initialized for reuse by calling <b>FltInitializeFileLock</b>. 

To free an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542969">FltFreeFileLock</a>. 

When the <i>CallbackData</i> parameter passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543427">FltProcessFileLock</a> represents a fast I/O operation, the callback specified in <i>CompleteLockCallbackDataRoutine</i> is not invoked. Only when the I/O operation in <i>CallbackData</i> is an IRP, and <i>CompleteLockCallbackDataRoutine</i> is not NULL, will the callback routine be called.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541834">FltCheckLockForReadAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541837">FltCheckLockForWriteAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542969">FltFreeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543273">FltInitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543427">FltProcessFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544595">FltUninitializeFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545640">FsRtlAllocateFileLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551073">PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551951">PUNLOCK_ROUTINE</a>
 

 

