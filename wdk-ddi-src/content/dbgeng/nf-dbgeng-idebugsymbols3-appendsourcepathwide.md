---
UID: NF:dbgeng.IDebugSymbols3.AppendSourcePathWide
title: IDebugSymbols3::AppendSourcePathWide
description: The AppendSourcePathWide method appends directories to the source path.
old-location: debugger\appendsourcepathwide.htm
tech.root: debugger
ms.assetid: 54f78169-4253-4dea-921f-981658df311e
ms.date: 05/03/2018
ms.keywords: AppendSourcePathWide, AppendSourcePathWide method [Windows Debugging], AppendSourcePathWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],AppendSourcePathWide method, IDebugSymbols3.AppendSourcePathWide, IDebugSymbols3::AppendSourcePathWide, dbgeng/IDebugSymbols3::AppendSourcePathWide, debugger.appendsourcepathwide
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
-	IDebugSymbols3.AppendSourcePathWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::AppendSourcePathWide


## -description


The <b>AppendSourcePathWide</b>  method appends directories to the source path.


## -parameters




### -param Addition [in]

Specifies the directories to append to the source path.  This is a string that contains source path elements separated by semicolons (;).  Each source path element can specify either a directory or a source server.


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
</table>
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



The source path is used by the engine when searching for source files.

For more information about manipulating the source path, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.  For an overview of the source path and its syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556906">Source Path</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548358">GetSourcePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548367">GetSourcePathElement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556781">SetSourcePath</a>
 

 

