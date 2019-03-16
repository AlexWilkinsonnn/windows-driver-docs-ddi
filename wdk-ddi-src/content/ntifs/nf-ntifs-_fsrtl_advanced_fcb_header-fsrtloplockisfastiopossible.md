---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlOplockIsFastIoPossible
title: FsRtlOplockIsFastIoPossible function (ntifs.h)
description: FsRtlOplockIsFastIoPossible checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file.
old-location: ifsk\fsrtloplockisfastiopossible.htm
tech.root: ifsk
ms.assetid: ba482fbf-862c-48b4-b8f9-aaab6c5527ee
ms.date: 04/16/2018
ms.keywords: FsRtlOplockIsFastIoPossible, FsRtlOplockIsFastIoPossible function [Installable File System Drivers], fsrtlref_94131dc4-e2ee-4ec0-92b9-39cd8a7d6e41.xml, ifsk.fsrtloplockisfastiopossible, rxprocs/FsRtlOplockIsFastIoPossible
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlOplockIsFastIoPossible
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlOplockIsFastIoPossible function


## -description


<b>FsRtlOplockIsFastIoPossible</b> checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file. 


## -parameters




### -param Oplock [in]

Opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546150">FsRtlInitializeOplock</a>. 


## -returns



<b>FsRtlOplockIsFastIoPossible</b> returns <b>FALSE</b> if there are outstanding opportunistic locks on the file that prevent fast I/O from being performed; <b>TRUE</b> otherwise. 




## -remarks



<b>FsRtlOplockIsFastIoPossible</b> determines whether fast I/O can be performed on a file, according to the following conditions: 

<ul>
<li>
If the <i>Oplock</i> parameter is <b>NULL</b>, or if the value of *<i>Oplock</i> is <b>NULL</b>, there are no outstanding opportunistic locks on the file, and fast I/O can be performed on the file. 

</li>
<li>
If an exclusive opportunistic lock was granted for the file, but no oplock break is in progress, fast I/O can be performed on the file. 

</li>
</ul>
For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543404">FltOplockIsFastIoPossible</a> instead of <b>FsRtlOplockIsFastIoPossible</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543404">FltOplockIsFastIoPossible</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545767">FsRtlCheckOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545825">FsRtlCurrentBatchOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546150">FsRtlInitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547112">FsRtlOplockFsctrl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547328">FsRtlUninitializeOplock</a>
 

 

