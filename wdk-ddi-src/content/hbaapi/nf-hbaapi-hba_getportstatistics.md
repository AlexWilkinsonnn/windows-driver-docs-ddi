---
UID: NF:hbaapi.HBA_GetPortStatistics
title: HBA_GetPortStatistics function
author: windows-driver-content
description: The HBA_GetPortStatistics routine retrieves statistics for the indicated port on the HBA.
old-location: storage\hba_getportstatistics.htm
tech.root: storage
ms.assetid: 282eccaf-7cb9-4675-9cc3-9261ed1322ca
ms.date: 3/29/2018
ms.keywords: HBA_GetPortStatistics, HBA_GetPortStatistics routine [Storage Devices], fibreHBA_rtns_cd33c55b-4c61-4353-ba28-8497e09b49dd.xml, hbaapi/HBA_GetPortStatistics, storage.hba_getportstatistics
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
-	HBA_GetPortStatistics
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_GetPortStatistics function


## -description


The <b>HBA_GetPortStatistics</b> routine retrieves statistics for the indicated port on the HBA.


## -parameters




### -param Handle

<p>Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/Ff557097(v=VS.85).aspx"><b>HBA_OpenAdapter</b></a> that identifies the HBA on which the port is located. </p>


### -param PortIndex [in]

Contains an index that identifies which port on the HBA to query for statistics. 


### -param PortStatistics

<p>Contains a structure of type <a href="https://msdn.microsoft.com/library/Ff557110(v=VS.85).aspx"><b>HBA_PortStatistics</b></a> that holds the statistics that were retrieved for the port. </p>




## -returns



The <b>HBA_GetPortStatistics</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetPortStatistics</b> returns one of the following qualifiers.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the statistics for the port were successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the retrieval of the statistics. 

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557110">HBA_PortStatistics</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

