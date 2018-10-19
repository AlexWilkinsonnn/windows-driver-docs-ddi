---
UID: NF:dbgeng.IDebugOutputCallbacks2.Output2
title: IDebugOutputCallbacks2::Output2
author: windows-driver-content
description: Returns notifications for the IDebugOutputCallbacks2 interface.
old-location: debugger\idebugoutputcallbacks2_output2.htm
tech.root: debugger
ms.assetid: 2FFF9B54-6E77-4D46-B6C0-5BADD208BFCC
ms.date: 05/03/2018
ms.keywords: DEBUG_OUTCBI_ANY_FORMAT, DEBUG_OUTCBI_DML, DEBUG_OUTCBI_EXPLICIT_FLUSH, DEBUG_OUTCBI_TEXT, IDebugOutputCallbacks2 interface [Windows Debugging],Output2 method, IDebugOutputCallbacks2.Output2, IDebugOutputCallbacks2::Output2, Output2, Output2 method [Windows Debugging], Output2 method [Windows Debugging],IDebugOutputCallbacks2 interface, dbgeng/IDebugOutputCallbacks2::Output2, debugger.idebugoutputcallbacks2_output2
ms.topic: method
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
-	IDebugOutputCallbacks2.Output2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugOutputCallbacks2::Output2


## -description


Returns notifications for the <a href="https://msdn.microsoft.com/D35D8960-AD9F-4493-B6CD-3E3049CC3BBD">IDebugOutputCallbacks2</a> interface.


## -parameters




### -param Which [in]

 The kind of notification that is coming in. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DEBUG_OUTCBI_EXPLICIT_FLUSH"></a><a id="debug_outcbi_explicit_flush"></a><dl>
<dt><b>DEBUG_OUTCBI_EXPLICIT_FLUSH</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
Indicates that the callback wants notifications
of all explicit flushes.

</td>
</tr>
<tr>
<td width="40%"><a id="DEBUG_OUTCBI_TEXT"></a><a id="debug_outcbi_text"></a><dl>
<dt><b>DEBUG_OUTCBI_TEXT</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
Indicates that the callback wants
content in text form.

</td>
</tr>
<tr>
<td width="40%"><a id="DEBUG_OUTCBI_DML"></a><a id="debug_outcbi_dml"></a><dl>
<dt><b>DEBUG_OUTCBI_DML</b></dt>
<dt>0x00000004
</dt>
</dl>
</td>
<td width="60%">
Indicates that the callback wants
content in markup form.

</td>
</tr>
<tr>
<td width="40%"><a id="DEBUG_OUTCBI_ANY_FORMAT"></a><a id="debug_outcbi_any_format"></a><dl>
<dt><b>DEBUG_OUTCBI_ANY_FORMAT</b></dt>
<dt>0x00000006</dt>
</dl>
</td>
<td width="60%">
Indicates that the callback wants
content in any format.

</td>
</tr>
</table>
 


### -param Flags [in]

Flags that are part of the notification payload.


### -param Arg [in]

Arguments that are part of the notification payload.


### -param Text [in, optional]

A pointer to text that is part of the notification payload.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/D35D8960-AD9F-4493-B6CD-3E3049CC3BBD">IDebugOutputCallbacks2</a>
 

 

