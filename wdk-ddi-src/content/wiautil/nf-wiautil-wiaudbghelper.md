---
UID: NF:wiautil.wiauDbgHelper
title: wiauDbgHelper macro (wiautil.h)
description: The wiauDbgHelper function formats a message and writes it to a log file, or debugger, or both.
old-location: image\wiaudbghelper.htm
tech.root: image
ms.assetid: 5be1ede7-13a0-4ef4-93bd-8a1adc5baa9e
ms.date: 05/03/2018
ms.keywords: image.wiaudbghelper, wiauDbgHelper, wiauDbgHelper function [Imaging Devices], wiauFncs_be2f3b11-e1a0-4728-856e-ce686344f166.xml, wiautil/wiauDbgHelper
ms.topic: macro
req.header: wiautil.h
req.include-header: Wiautil.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wiautil.h
api_name:
- wiauDbgHelper
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiauDbgHelper macro


## -description


The <b>wiauDbgHelper</b> function formats a message and writes it to a log file, or debugger, or both.


## -parameters




### -param a




### -param b




### -param c




### -param d








#### - fmt [in]

Pointer to a string that controls how an item or items in a variable argument list is to be formatted.


#### - fname [in]

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgHelper</b> is inserted.


#### - marker

Marks the beginning of a variable argument list.


#### - prefix [in]

Pointer to a string containing a prefix (such as "ERROR " or "WARN ") associated with the message. 


## -remarks



The <b>wiauDbgHelper</b> function is a general-purpose function that is used internally by many of the other <b>wiauDbg</b><b><i>Xxx</i></b> functions. While it can be used in WIA minidrivers, there are other limited-purpose functions provided that are more convenient to use.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549627">wiauDbgDump</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549633">wiauDbgError</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549637">wiauDbgErrorHr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550161">wiauDbgTrace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550163">wiauDbgWarning</a>
 

 

