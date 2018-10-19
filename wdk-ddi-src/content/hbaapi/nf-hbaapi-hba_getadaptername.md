---
UID: NF:hbaapi.HBA_GetAdapterName
title: HBA_GetAdapterName function
author: windows-driver-content
description: The HBA_GetAdapterName routine retrieves the text string that identifies the HBA name that corresponds to the indicated adapter index.
old-location: storage\hba_getadaptername.htm
tech.root: storage
ms.assetid: ec17efca-2cb9-4ab4-b98f-7319f6145e4e
ms.date: 03/29/2018
ms.keywords: HBA_GetAdapterName, HBA_GetAdapterName routine [Storage Devices], fibreHBA_rtns_f483472a-9b5e-4120-b0bf-e3c5253a3f03.xml, hbaapi/HBA_GetAdapterName, storage.hba_getadaptername
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_GetAdapterName
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_GetAdapterName function


## -description


The <b>HBA_GetAdapterName</b> routine retrieves the text string that identifies the HBA name that corresponds to the indicated adapter index.


## -parameters




### -param AdapterIndex [in]

Indicates the index of the HBA for which the name will be returned.


### -param AdapterName [in, out]

Pointer to memory area in which the HBA name will be returned. The HBA name will be a string of the form

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>mfgdomain-model-adapterindex</pre>
</td>
</tr>
</table></span></div>
where <b>mfgdomain</b> is derived from the domain name owned by the manufacturer of the HBA, <b>model</b> is a vendor-specific identifier of the HBA product model, and <b>adapterindex</b> is a decimal representation of the HBA index in <i>AdapterIndex. </i>For example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>com.HotBiscuitsAdapters-HBA1040A-1</pre>
</td>
</tr>
</table></span></div>
For a description of the formatting of the adapter name, see the <i>Fibre Channel HBA API</i> specification published by the T11 committee.


## -returns



The <b>HBA_GetAdapterName</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556044">HBA_AdapterAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

