---
UID: NF:ntddk.RtlParent
title: RtlParent macro
author: windows-driver-content
description: The RtlParent routine returns a pointer to the parent of the specified node in a splay link tree.
old-location: ifsk\rtlparent.htm
tech.root: ifsk
ms.assetid: 940c9234-6c4e-421d-a3e3-87ba2d786248
ms.date: 4/16/2018
ms.keywords: RtlParent, RtlParent routine [Installable File System Drivers], ifsk.rtlparent, ntddk/RtlParent, rtlref_85e6ffbf-9d34-47f5-b5c2-1d57a1a57056.xml
ms.topic: macro
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	RtlParent
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlParent macro


## -description


The <b>RtlParent</b> routine returns a pointer to the parent of the specified node in a splay link tree. 


## -parameters




### -param Links [in]

Pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.


## -remarks



<b>RtlParent</b> can be called repeatedly in conjunction with <b>RtlLeftChild</b> and <b>RtlRightChild</b> to walk a splay link tree. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlParent</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553010">RtlInitializeSplayLinks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553017">RtlInsertAsLeftChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553022">RtlInsertAsRightChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553072">RtlIsRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553080">RtlLeftChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553200">RtlRightChild</a>
 

 

