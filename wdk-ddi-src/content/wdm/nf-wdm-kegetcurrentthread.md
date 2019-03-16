---
UID: NF:wdm.KeGetCurrentThread
title: KeGetCurrentThread function (wdm.h)
description: The KeGetCurrentThread routine identifies the current thread.
old-location: kernel\kegetcurrentthread.htm
tech.root: kernel
ms.assetid: 0fbc9f6d-698b-4fa5-86c4-3f6ef0cc50fb
ms.date: 04/30/2018
ms.keywords: KeGetCurrentThread, KeGetCurrentThread routine [Kernel-Mode Driver Architecture], k105_fa2d3ae9-9ac8-4c50-bf51-5d6751a2b81e.xml, kernel.kegetcurrentthread, wdm/KeGetCurrentThread
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeGetCurrentThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeGetCurrentThread function


## -description


The <b>KeGetCurrentThread</b> routine identifies the current thread. 


## -parameters






## -returns



<b>KeGetCurrentThread</b> returns a pointer to an opaque thread object. 




## -remarks



This routine is identical to <a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a>.

A caller of <b>KeGetCurrentThread</b> can use the returned pointer as an input parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff553062">KeQueryPriorityThread</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553246">KeSetBasePriorityThread</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553265">KeSetPriorityThread</a>. However, the memory containing the thread object is opaque; that is, it is reserved for exclusive use by the operating system.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553062">KeQueryPriorityThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553246">KeSetBasePriorityThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553265">KeSetPriorityThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a>
 

 

