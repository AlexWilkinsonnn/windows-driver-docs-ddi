---
UID: NF:dbgeng.IDebugControl4.SetSpecificFilterArgumentWide
title: IDebugControl4::SetSpecificFilterArgumentWide (dbgeng.h)
description: The SetSpecificFilterArgumentWide method sets the value of filter argument for the specific filters that can have an argument.
old-location: debugger\setspecificfilterargumentwide.htm
tech.root: debugger
ms.assetid: 416c4de2-f200-491a-a319-fb0a4fd86f86
ms.date: 05/03/2018
ms.keywords: IDebugControl4 interface [Windows Debugging],SetSpecificFilterArgumentWide method, IDebugControl4.SetSpecificFilterArgumentWide, IDebugControl4::SetSpecificFilterArgumentWide, SetSpecificFilterArgumentWide, SetSpecificFilterArgumentWide method [Windows Debugging], SetSpecificFilterArgumentWide method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::SetSpecificFilterArgumentWide, debugger.setspecificfilterargumentwide
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugControl4.SetSpecificFilterArgumentWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::SetSpecificFilterArgumentWide


## -description


The <b>SetSpecificFilterArgumentWide</b>  method sets the value of filter argument for the specific filters that can have an argument.


## -parameters




### -param Index [in]

Specifies the index of the specific filter whose argument will be set.  <i>Index</i> must be the index of a specific filter that has an argument.


### -param Argument [in]

Specifies the argument for the specific filter.  The interpretation of this argument depends on the specific filter.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
<i>Index</i> does not refer to a specific filter that has an argument.

</td>
</tr>
</table>
 




## -remarks



For a list of specific filters that have argument and the interpretation of those arguments, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548386">GetSpecificFilterArgument</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

