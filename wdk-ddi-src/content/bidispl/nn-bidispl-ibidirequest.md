---
UID: NN:bidispl.IBidiRequest
title: IBidiRequest (bidispl.h)
description: The IBidiRequest interface allows an application or other objects to compose a bidi request.
old-location: print\ibidirequest.htm
tech.root: print
ms.assetid: e7b16853-7f1d-45e4-af5e-4ae9cbb9b191
ms.date: 04/20/2018
ms.keywords: IBidiRequest, IBidiRequest interface [Print Devices], IBidiRequest interface [Print Devices],described, _win32_IBidiRequest, bidispl/IBidiRequest, gdi.ibidirequest, print.ibidirequest
ms.topic: interface
req.header: bidispl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
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
- Bidispl.h
api_name:
- IBidiRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiRequest interface


## -description


The <b>IBidiRequest</b> interface allows an application or other objects to compose a bidi request.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IBidiRequest</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IBidiRequest</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IBidiRequest</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/4c857ff4-02c1-487b-bdb0-44d62a4cf4a1">GetEnumCount</a>
</td>
<td align="left" width="63%">
Gets the number of output items.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0757dbc2-850b-4267-9339-b87591f85767">GetOutputData</a>
</td>
<td align="left" width="63%">
Gets the output data coming back from the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/d3d37fd2-b3fa-4664-ba4b-c355197d9b40">GetResult</a>
</td>
<td align="left" width="63%">
Gets the result code.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/8db7b5cd-b03f-4973-8711-8ac022bfb2b5">SetInputData</a>
</td>
<td align="left" width="63%">
Sets the data to send to the device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/ca4f7ea4-fcad-42b0-a63a-eee3706e5cbf">SetSchema</a>
</td>
<td align="left" width="63%">
Sets the bidi schema string.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>



<a href="https://msdn.microsoft.com/42b5e6cf-b434-4734-86f3-b3b9d15ea468">Print Spooler Components</a>
 

 

