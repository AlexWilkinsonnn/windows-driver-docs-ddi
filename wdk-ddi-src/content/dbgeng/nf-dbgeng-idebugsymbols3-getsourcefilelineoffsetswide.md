---
UID: NF:dbgeng.IDebugSymbols3.GetSourceFileLineOffsetsWide
title: IDebugSymbols3::GetSourceFileLineOffsetsWide
author: windows-driver-content
description: The GetSourceFileLineOffsetsWide method maps each line in a source file to a location in the target's memory.
old-location: debugger\getsourcefilelineoffsetswide.htm
tech.root: debugger
ms.assetid: f774dde1-3498-423b-bf09-239d3d3421b4
ms.date: 5/3/2018
ms.keywords: GetSourceFileLineOffsetsWide, GetSourceFileLineOffsetsWide method [Windows Debugging], GetSourceFileLineOffsetsWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSourceFileLineOffsetsWide method, IDebugSymbols3.GetSourceFileLineOffsetsWide, IDebugSymbols3::GetSourceFileLineOffsetsWide, dbgeng/IDebugSymbols3::GetSourceFileLineOffsetsWide, debugger.getsourcefilelineoffsetswide
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
-	IDebugSymbols3.GetSourceFileLineOffsetsWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetSourceFileLineOffsetsWide


## -description


The <b>GetSourceFileLineOffsetsWide</b>  method maps each line in a source file to a location in the target's memory.


## -parameters




### -param File [in]

Specifies the name of the file whose lines will be turned into locations in the target's memory.  The symbols for each module in the target are queried for this file.  If the file is not located, the path is dropped and the symbols are queried again.


### -param Buffer [out, optional]

Receives the locations in the target's memory that correspond to the lines of the source code.  The first entry returned to this array corresponds to the first line of the file, so that <code>Buffer[i]</code> contains the location for line <code>i+1</code>.  If no symbol information is available for a line, the corresponding entry in <i>Buffer</i> is set to DEBUG_INVALID_OFFSET.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferLines [in]

Specifies the number of PULONG64 objects that the <i>Buffer</i> array can hold.


### -param FileLines [out, optional]

Receives the number of lines in the source file specified by <i>File</i>.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, the number of lines in the source file exceeded the number of entries in the <i>Buffer</i> array and some of the results were discarded.

</td>
</tr>
</table>
 




## -remarks



For more information about using the source path, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545423">FindSourceFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548305">GetSourceEntriesByLine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

