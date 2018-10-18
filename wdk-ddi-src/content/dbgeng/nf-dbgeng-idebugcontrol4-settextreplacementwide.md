---
UID: NF:dbgeng.IDebugControl4.SetTextReplacementWide
title: IDebugControl4::SetTextReplacementWide
author: windows-driver-content
description: The SetTextReplacementWide method sets the value of a user-named alias.
old-location: debugger\settextreplacementwide.htm
tech.root: debugger
ms.assetid: bbd3fbc0-6dbe-4200-8fe8-e7ca9e4c9478
ms.date: 5/3/2018
ms.keywords: IDebugControl4 interface [Windows Debugging],SetTextReplacementWide method, IDebugControl4.SetTextReplacementWide, IDebugControl4::SetTextReplacementWide, SetTextReplacementWide, SetTextReplacementWide method [Windows Debugging], SetTextReplacementWide method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::SetTextReplacementWide, debugger.settextreplacementwide
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
-	IDebugControl4.SetTextReplacementWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::SetTextReplacementWide


## -description


The <b>SetTextReplacementWide</b>  method sets the value of a user-named alias.  


## -parameters




### -param SrcText [in]

Specifies the name of the user-named alias.  The <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> makes a copy of this string.  If <i>SrcText</i> is the same as the name of an automatic alias, the automatic alias is hidden by the new user-named alias.


### -param DstText [in, optional]

Specifies the value of the user-named alias.  The debugger engine makes a copy of this string.  If <i>DstText</i> is <b>NULL</b>, the user-named alias is removed.


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



Before executing commands or evaluating expressions, the debugger engine will replace the alias specified by <i>SrcText</i> with the value of the alias (specified by <i>DstText</i>).

If <i>SrcText</i> is an asterisk (<b>*</b>) and <i>DstText</i> is <b>NULL</b>, all user-named aliases are removed.  This is the same behavior as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554548">RemoveTextReplacements</a> method.

When an alias is changed by this method, the event callbacks are notified by passing the DEBUG_CES_TEXT_REPLACEMENTS flag to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> callback method.

For an overview of aliases used by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560047">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551041">Interacting with the Engine</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549280">GetTextReplacement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553268">OutputTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554548">RemoveTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556809">SetTextMacro</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537997">ad (Delete Alias)</a>



<a href="https://msdn.microsoft.com/6e42122b-5a18-403b-a19a-1346bea8da12">as, aS (Set Alias)</a>
 

 

