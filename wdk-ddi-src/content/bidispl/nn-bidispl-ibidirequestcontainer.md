---
UID: NN:bidispl.IBidiRequestContainer
title: IBidiRequestContainer
author: windows-driver-content
description: The IBidiRequestContainer interface allows an application or other objects to compose and retrieve a list of bidi requests.
old-location: print\ibidirequestcontainer.htm
tech.root: print
ms.assetid: 21dfcbe8-2fc1-4495-af54-5d4c83b8bb79
ms.date: 04/20/2018
ms.keywords: IBidiRequestContainer, IBidiRequestContainer interface [Print Devices], IBidiRequestContainer interface [Print Devices],described, _win32_IBidiRequestContainer, bidispl/IBidiRequestContainer, gdi.ibidirequestcontainer, print.ibidirequestcontainer
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Bidispl.h
api_name:
-	IBidiRequestContainer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiRequestContainer interface


## -description


The <b>IBidiRequestContainer</b> interface allows an application or other objects to compose and retrieve a list of bidi requests.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IBidiRequestContainer</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IBidiRequestContainer</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IBidiRequestContainer</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/69a97816-2994-4eec-b2ab-a545195e3776">AddRequest</a>
</td>
<td align="left" width="63%">
Adds a request to the request list.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/1aa7b934-c56b-4bfb-800e-950e1dbd5ba3">GetEnumObject</a>
</td>
<td align="left" width="63%">
Enumerates the number of requests in the list.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/4215ca86-9ceb-451d-8e67-992a8a3f9bab">GetRequestCount</a>
</td>
<td align="left" width="63%">
Gets the number of requests in the list.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>



<a href="https://msdn.microsoft.com/42b5e6cf-b434-4734-86f3-b3b9d15ea468">Print Spooler Components</a>
 

 

