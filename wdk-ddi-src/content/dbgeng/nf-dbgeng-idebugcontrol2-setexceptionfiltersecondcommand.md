---
UID: NF:dbgeng.IDebugControl2.SetExceptionFilterSecondCommand
title: IDebugControl2::SetExceptionFilterSecondCommand (dbgeng.h)
description: The SetExceptionFilterSecondCommand method sets the command that will be executed by the debugger engine on the second chance of a specified exception.
old-location: debugger\setexceptionfiltersecondcommand.htm
tech.root: debugger
ms.assetid: c95fa025-9455-4a8e-99ef-84030255575c
ms.date: 05/03/2018
ms.keywords: IDebugControl interface [Windows Debugging],SetExceptionFilterSecondCommand method, IDebugControl2 interface [Windows Debugging],SetExceptionFilterSecondCommand method, IDebugControl2.SetExceptionFilterSecondCommand, IDebugControl2::SetExceptionFilterSecondCommand, IDebugControl3 interface [Windows Debugging],SetExceptionFilterSecondCommand method, IDebugControl3::SetExceptionFilterSecondCommand, IDebugControl::SetExceptionFilterSecondCommand, IDebugControl_39380f22-4c68-40fe-b277-f7eace77bcee.xml, SetExceptionFilterSecondCommand, SetExceptionFilterSecondCommand method [Windows Debugging], SetExceptionFilterSecondCommand method [Windows Debugging],IDebugControl interface, SetExceptionFilterSecondCommand method [Windows Debugging],IDebugControl2 interface, SetExceptionFilterSecondCommand method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetExceptionFilterSecondCommand, dbgeng/IDebugControl3::SetExceptionFilterSecondCommand, dbgeng/IDebugControl::SetExceptionFilterSecondCommand, debugger.setexceptionfiltersecondcommand
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
-	dbgeng.h
api_name:
-	IDebugControl.SetExceptionFilterSecondCommand
-	IDebugControl2.SetExceptionFilterSecondCommand
-	IDebugControl3.SetExceptionFilterSecondCommand
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::SetExceptionFilterSecondCommand


## -description


The <b>SetExceptionFilterSecondCommand</b>  method sets the command that will be executed by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> on the second chance of a specified <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exception</a>.


## -parameters




### -param Index [in]

Specifies the index of the exception filter whose second-chance command will be set.  <i>Index</i> must not refer to the specific event filters as these are not exception filters and only exception events get a second chance.  If <i>Index</i> refers to the default exception filter, the second-chance command is set for all exceptions that do not have an exception filter.


### -param Command [in]

Receives the second-chance command for the exception filter.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
</table>
 




## -remarks



For more information about <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546653">GetExceptionFilterSecondCommand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556678">SetEventFilterCommand</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

