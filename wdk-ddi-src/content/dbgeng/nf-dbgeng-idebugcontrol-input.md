---
UID: NF:dbgeng.IDebugControl.Input
title: IDebugControl::Input (dbgeng.h)
description: The Input method requests an input string from the debugger engine.
old-location: debugger\input.htm
tech.root: debugger
ms.assetid: 8a37bce1-762b-4a08-a677-ed2e484c1bba
ms.date: 05/03/2018
ms.keywords: IDebugControl interface [Windows Debugging],Input method, IDebugControl.Input, IDebugControl::Input, IDebugControl_10615761-d032-439f-955b-220def3835a9.xml, Input, Input method [Windows Debugging], Input method [Windows Debugging],IDebugControl interface, dbgeng/IDebugControl::Input, debugger.input
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Dbgeng.h
api_name:
-	IDebugControl.Input
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::Input


## -description


The <b>Input</b>  method requests an input string from the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>.


## -parameters




### -param Buffer [out]

Receives the input string from the engine.


### -param BufferSize [in]

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.


### -param InputSize [out, optional]

Receives the number of characters returned in <i>Buffer</i>.  If <i>InputSize</i> is <b>NULL</b>, this information is not returned.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the buffer was not big enough to hold the whole input string and it was truncated.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



For an overview of input in the debugger engine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550970">InputWide</a>
 

 

