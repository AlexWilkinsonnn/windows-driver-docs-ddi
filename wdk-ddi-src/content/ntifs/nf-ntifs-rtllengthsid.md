---
UID: NF:ntifs.RtlLengthSid
title: RtlLengthSid function
author: windows-driver-content
description: The RtlLengthSid routine returns the length, in bytes, of a valid security identifier (SID).
old-location: ifsk\rtllengthsid.htm
tech.root: ifsk
ms.assetid: 5d96061d-f1a2-4e45-b76e-5ada61d8accd
ms.date: 4/16/2018
ms.keywords: RtlLengthSid, RtlLengthSid routine [Installable File System Drivers], ifsk.rtllengthsid, ntifs/RtlLengthSid, rtlref_8bbf6a04-413c-4f50-9f51-1ddd8bce58ff.xml
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	ntdll.dll
api_name:
-	RtlLengthSid
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLengthSid function


## -description


The <b>RtlLengthSid</b> routine returns the length, in bytes, of a valid security identifier (SID). 


## -parameters




### -param Sid [in]

Pointer to the SID structure. Must point to a valid SID. 


## -returns



If the SID structure is valid, <b>RtlLengthSid</b> returns the length, in bytes, of the SID structure.

If the SID structure is not valid, the return value is undefined. Before calling <b>RtlLengthSid</b>, pass the SID to <a href="https://msdn.microsoft.com/library/windows/hardware/ff553314">RtlValidSid</a> to verify that it is valid. 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552256">RtlEqualPrefixSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552260">RtlEqualSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552998">RtlInitializeSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553083">RtlLengthRequiredSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553236">RtlSubAuthoritySid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553314">RtlValidSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>
 

 

