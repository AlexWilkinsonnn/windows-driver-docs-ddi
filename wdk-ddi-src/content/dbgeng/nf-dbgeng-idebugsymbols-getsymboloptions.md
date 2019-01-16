---
UID: NF:dbgeng.IDebugSymbols.GetSymbolOptions
title: IDebugSymbols::GetSymbolOptions
description: The GetSymbolOptions method returns the engine's global symbol options.
old-location: debugger\getsymboloptions.htm
tech.root: debugger
ms.assetid: a9da40fa-59b7-4d2b-978f-1785a51eeaed
ms.date: 05/03/2018
ms.keywords: GetSymbolOptions, GetSymbolOptions method [Windows Debugging], GetSymbolOptions method [Windows Debugging],IDebugSymbols interface, GetSymbolOptions method [Windows Debugging],IDebugSymbols2 interface, GetSymbolOptions method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetSymbolOptions method, IDebugSymbols.GetSymbolOptions, IDebugSymbols2 interface [Windows Debugging],GetSymbolOptions method, IDebugSymbols2::GetSymbolOptions, IDebugSymbols3 interface [Windows Debugging],GetSymbolOptions method, IDebugSymbols3::GetSymbolOptions, IDebugSymbols::GetSymbolOptions, IDebugSymbols_70c05823-d1a1-4769-8584-e191255c4deb.xml, dbgeng/IDebugSymbols2::GetSymbolOptions, dbgeng/IDebugSymbols3::GetSymbolOptions, dbgeng/IDebugSymbols::GetSymbolOptions, debugger.getsymboloptions
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Dbghelp.h
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
-	IDebugSymbols.GetSymbolOptions
-	IDebugSymbols2.GetSymbolOptions
-	IDebugSymbols3.GetSymbolOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols::GetSymbolOptions


## -description


The <b>GetSymbolOptions</b> method returns the engine's global symbol options.


## -parameters




### -param Options [out]

Receives the symbol options bit-set.  For a description of the bit flags, see <a href="https://msdn.microsoft.com/4a501ea3-431c-4c11-8826-154eb8799a64">Setting Symbol Options</a>.


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



For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537930">AddSymbolOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554535">RemoveSymbolOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556798">SetSymbolOptions</a>
 

 

