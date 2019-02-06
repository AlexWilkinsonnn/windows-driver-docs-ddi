---
UID: NF:dbgeng.IDebugSymbols3.SetSymbolPathWide
title: IDebugSymbols3::SetSymbolPathWide (dbgeng.h)
description: The SetSymbolPathWide method sets the symbol path.
old-location: debugger\setsymbolpathwide.htm
tech.root: debugger
ms.assetid: 44ee3342-3677-4eee-8ddf-d0a01e9bb309
ms.date: 05/03/2018
ms.keywords: IDebugSymbols3 interface [Windows Debugging],SetSymbolPathWide method, IDebugSymbols3.SetSymbolPathWide, IDebugSymbols3::SetSymbolPathWide, SetSymbolPathWide, SetSymbolPathWide method [Windows Debugging], SetSymbolPathWide method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols3::SetSymbolPathWide, debugger.setsymbolpathwide
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
-	IDebugSymbols3.SetSymbolPathWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::SetSymbolPathWide


## -description


The <b>SetSymbolPathWide</b>  method sets the symbol path.


## -parameters




### -param Path [in]

Specifies the new symbol path.  This is a string that contains symbol path elements separated by semicolons (;).  Each symbol path element can specify either a directory or a symbol server.


## -returns



This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



For more information about manipulating the symbol path, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560150">Using Symbols</a>.  For an overview of the symbol path and its syntax, see <a href="https://msdn.microsoft.com/705df98f-717f-40ad-a424-101826970691">Symbol Path</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538110">AppendSymbolPath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549155">GetSymbolPath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

