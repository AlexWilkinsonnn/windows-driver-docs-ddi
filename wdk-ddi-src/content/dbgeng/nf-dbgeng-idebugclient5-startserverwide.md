---
UID: NF:dbgeng.IDebugClient5.StartServerWide
title: IDebugClient5::StartServerWide (dbgeng.h)
description: The StartServerWide method starts a debugging server.
old-location: debugger\startserverwide.htm
tech.root: debugger
ms.assetid: 7a36f278-45eb-4ee9-9bdf-370c546245c0
ms.date: 05/03/2018
ms.keywords: IDebugClient5 interface [Windows Debugging],StartServerWide method, IDebugClient5.StartServerWide, IDebugClient5::StartServerWide, StartServerWide, StartServerWide method [Windows Debugging], StartServerWide method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::StartServerWide, debugger.startserverwide
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
- IDebugClient5.StartServerWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::StartServerWide


## -description


The <b>StartServerWide</b> method starts a debugging server.


## -parameters




### -param Options [in]

Specifies the connections options for this server.  These are the same options given to the <b>.server</b> debugger command or the WinDbg and CDB <b>-server</b> command-line option.  For details on the syntax of this string, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537823">Activating a Debugging Server</a>.


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



The server that is started will be accessible by other <a href="https://msdn.microsoft.com/13F9D82A-4C04-425A-A063-B349DB5C8E08">debuggers</a> through the transport specified in the <i>Options</i> parameter.

For more information about debugging servers, see Debugging Server and Debugging Client.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540465">DebugConnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553247">OutputServers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558810">StartProcessServer</a>
 

 

