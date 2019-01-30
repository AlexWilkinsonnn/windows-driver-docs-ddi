---
UID: NF:wdm.ClfsLsnContainer
title: ClfsLsnContainer function (wdm.h)
description: The ClfsLsnContainer routine returns the logical container identifier contained in a specified LSN.
old-location: kernel\clfslsncontainer.htm
tech.root: kernel
ms.assetid: 006edbf7-b3f8-45f2-902e-03d86e83b0a0
ms.date: 04/30/2018
ms.keywords: ClfsLsnContainer, ClfsLsnContainer routine [Kernel-Mode Driver Architecture], Clfs_87c1e289-57b7-414d-a78e-8074a75d1262.xml, kernel.clfslsncontainer, wdm/ClfsLsnContainer
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsLsnContainer
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsLsnContainer function


## -description


The <b>ClfsLsnContainer</b> routine returns the logical container identifier contained in a specified LSN.


## -parameters




### -param plsn [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541824">CLFS_LSN</a> structure from which the container identifier is retrieved.


## -returns



<b>ClfsLsnContainer</b> returns the logical container identifier contained in the LSN that is supplied by the caller. The logical container identifier is not necessarily the same as the identifier of the physical container on stable storage.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541569">ClfsLsnBlockOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541585">ClfsLsnCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541615">ClfsLsnRecordSequence</a>
 

 

