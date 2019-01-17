---
UID: NF:hbaapi.HBA_SendRPS
title: HBA_SendRPS function
description: The HBA_SendRPS routine sends a read port status block (RPS) request to the indicated agent port or domain controller.
old-location: storage\hba_sendrps.htm
tech.root: storage
ms.assetid: 6a79896a-0591-40dd-8e2d-6e3796556564
ms.date: 03/29/2018
ms.keywords: HBA_SendRPS, HBA_SendRPS routine [Storage Devices], fibreHBA_rtns_753d25be-cb77-4e65-ab1b-1f2b77d65ec8.xml, hbaapi/HBA_SendRPS, storage.hba_sendrps
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
-	HBA_SendRPS
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_SendRPS function


## -description


The <b>HBA_SendRPS</b> routine sends a read port status block (RPS) request to the indicated agent port or domain controller. 


## -parameters




### -param Handle [in]

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the local HBA through which the request is sent. 


### -param HbaPortWWN

<p>Contains a 64-bit worldwide name (WWN) that uniquely identifies the local port through which the RPS request is sent. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. </p>


### -param Agent_wwn

<p>Contains, when non-<b>NULL</b>, a 64-bit WWN that uniquely identifies the port to query for the status of the port referenced by <i>object_wwn. </i>If this member is <b>NULL</b>, it is ignored, and the domain controller identified by <i>agent_domain </i>is queried. </p>


### -param Agent_domain

<p>Contains the domain number for the domain controller to query for the status of the port referenced by <i>object_wwn. </i>If <i>agent_wwn </i>is non-<b>NULL</b>, this member is ignored.</p>


### -param Object_wwn

<p>Contains a 64-bit WWN that uniquely identifies the port for which status information is retrieved. If this member is <b>NULL</b>, it is ignored, and status information is retrieved for the port identified by <i>object_port_number</i>. </p>


### -param Object_port_number

<p>Contains the relative port number of the port for which status information is retrieved. The meaning of the relative port number is defined by the hardware vendor that contains the port, and it is the responsibility of the software that receives the status query to interpret this number. If <i>object_wwn </i>is non-<b>NULL</b>, this member is ignored.</p>


### -param pRspBuffer [out]

Pointer to a buffer that receives the results of the RPS request, if the request succeeds. If the destination port or domain controller rejects the request, this buffer holds the link service reject (LS_RJT) payload data. If the amount of returned data exceeds the buffer size specified in <i>RspBufferSize</i>, the data is truncated to the buffer size<i>. </i>The payload data is in big-endian format (higher order bytes are in lower addresses). 


### -param pRspBufferSize

<p>On input, indicates the size, in bytes, of the buffer pointed to by <i>pRspBuffer</i>. On return, this member indicates the size, in bytes, of the response data. A buffer size of 56 bytes is sufficient for the largest response. </p>




## -returns



The <b>HBA_SendRPS</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_SendRPS</b> returns one of the following values.

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
Returned if the complete payload of a reply to the RPS request was successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>handle</i> does not contain a port with a name that matches <i>hbaPortWWN</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ELS_REJECT</b></dt>
</dl>
</td>
<td width="60%">
Returned if the destination port referenced by <i>agent_wwn </i>or the domain controller referenced by <i>agent_domain </i>rejected the request node identification information data (RNID) that identifies the source HBA. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the execution of the RPS request. 

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

