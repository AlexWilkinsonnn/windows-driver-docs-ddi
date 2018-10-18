---
UID: NN:dbgeng.IDebugRegisters
title: IDebugRegisters
author: windows-driver-content
description: IDebugRegisters interface
old-location: debugger\idebugregisters.htm
tech.root: debugger
ms.assetid: a2587ea7-20cd-43be-ba71-750e699ee0ce
ms.date: 5/3/2018
ms.keywords: IDebugRegisters, IDebugRegisters interface [Windows Debugging], IDebugRegisters interface [Windows Debugging],described, IDebugRegisters_ca710692-a977-4276-b779-2b66311938dc.xml, dbgeng/IDebugRegisters, debugger.idebugregisters
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
-	IDebugRegisters
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugRegisters interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugRegisters</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IDebugRegisters</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugRegisters</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546575">GetDescription</a>
</td>
<td align="left" width="63%">
Returns the description of a register.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546806">GetFrameOffset</a>
</td>
<td align="left" width="63%">
Returns the location of the stack frame for the current function.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546881">GetIndexByName</a>
</td>
<td align="left" width="63%">
Returns the index of the named register.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546916">GetInstructionOffset</a>
</td>
<td align="left" width="63%">
Returns the location of the current thread's current instruction.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547960">GetNumberRegisters</a>
</td>
<td align="left" width="63%">
Returns the number of registers on the target computer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548403">GetStackOffset</a>
</td>
<td align="left" width="63%">
Returns the current thread's current stack location.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597624">GetValue</a>
</td>
<td align="left" width="63%">
Gets the value of one of the target's registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549480">GetValues</a>
</td>
<td align="left" width="63%">
Gets the value of several of the target's registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553242">OutputRegisters</a>
</td>
<td align="left" width="63%">
Formats and sends the target's registers to the clients as output.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597642">SetValue</a>
</td>
<td align="left" width="63%">
Sets the value of one of the target's registers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556883">SetValues</a>
</td>
<td align="left" width="63%">
Sets the value of several of the target's registers.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550835">IDebugRegisters2</a>
 

 

