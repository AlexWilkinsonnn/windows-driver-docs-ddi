---
UID: NN:printerextension.IPrinterQueueEvent
title: IPrinterQueueEvent
author: windows-driver-content
description: Provides the event delegate for printer queue events.
old-location: print\iprinterqueueevent_interface.htm
tech.root: print
ms.assetid: AA4B2578-61C9-47C3-A114-4B873B475124
ms.date: 04/20/2018
ms.keywords: IPrinterQueueEvent, IPrinterQueueEvent interface [Print Devices], IPrinterQueueEvent interface [Print Devices],described, print.iprinterqueueevent_interface, printerextension/IPrinterQueueEvent
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	Printerextension.h
api_name:
-	IPrinterQueueEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterQueueEvent interface


## -description


Provides the event delegate for printer queue events.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterQueueEvent</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IPrinterQueueEvent</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterQueueEvent</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh846196">OnBidiResponseReceived</a>
</td>
<td align="left" width="63%">
Called when a bidi response  is received.

</td>
</tr>
</table> 


## -remarks



An event sink that implements <b>IPrinterQueueEvent</b> and the event source, <a href="https://msdn.microsoft.com/library/windows/hardware/hh439635">IPrinterQueue</a> are connected via the <a href="http://msdn.microsoft.com/library/windows/desktop/ms694318(v=vs.85).aspx">IConnectionPoint</a> mechanism. You must retrieve a pointer to the <b>IConnectionPoint</b> interface by invoking <b>QueryInterface</b> on the <b>IPrinterQueue</b> object.

<div class="alert"><b>Note</b>  It is mandatory to implement <b>IDispatch::Invoke</b> on the event sink that implements <b>IPrinterQueueEvent</b>, since that is the mechanism via which events are raised. It is sufficient to provide stub implementations of the other methods on the <b>IDispatch</b> interface.
</div>
<div> </div>



## -see-also




<a href="http://msdn.microsoft.com/library/windows/desktop/ms694318(v=vs.85).aspx">IConnectionPoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439635">IPrinterQueue</a>
 

 

