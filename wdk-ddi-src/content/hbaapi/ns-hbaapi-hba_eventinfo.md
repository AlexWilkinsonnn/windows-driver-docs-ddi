---
UID: NS:hbaapi.HBA_EventInfo
title: HBA_EventInfo
author: windows-driver-content
description: The HBA_EventInfo structure contains information about an event of the indicated type.
old-location: storage\hba_eventinfo.htm
tech.root: storage
ms.assetid: fc6b73ac-f86c-4978-9d71-9bd8398c116b
ms.date: 03/29/2018
ms.keywords: "*PHBA_EVENTINFO, HBA_EVENTINFO, HBA_EVENTINFO structure [Storage Devices], HBA_EventInfo, HBA_EventInfo structure [Storage Devices], PHBA_EVENTINFO, PHBA_EVENTINFO structure pointer [Storage Devices], hbaapi/HBA_EventInfo, hbaapi/PHBA_EVENTINFO, storage.hba_eventinfo, structs-Fibre_6885fdc8-d2ce-40b3-ba2a-2e423f287780.xml"
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
-	HeaderDef
api_location:
-	hbaapi.h
api_name:
-	HBA_EVENTINFO
product:
- Windows
targetos: Windows
req.typenames: HBA_EVENTINFO, *PHBA_EVENTINFO
---

# HBA_EventInfo structure


## -description


The HBA_EventInfo structure contains information about an event of the indicated type.


## -struct-fields




### -field EventCode

Contains a code indicating the type of event. The following table lists the values that this member can have:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
HBA_EVENT_LIP_OCCURRED

</td>
<td>
A loop initialization primitive event occurred.

</td>
</tr>
<tr>
<td>
HBA_EVENT_LINK_UP

</td>
<td>
A link up event occurred. 

</td>
</tr>
<tr>
<td>
HBA_EVENT_LINK_DOWN

</td>
<td>
A link down event occurred. 

</td>
</tr>
<tr>
<td>
HBA_EVENT_LIP_RESET_OCCURRED

</td>
<td>
A loop initialization primitive resest event occurred.

</td>
</tr>
<tr>
<td>
HBA_EVENT_RSCN

</td>
<td>
An RSCN event occurred.

</td>
</tr>
<tr>
<td>
HBA_EVENT_PROPRIETARY

</td>
<td>
A proprietary event occurred. 

</td>
</tr>
</table>
 


### -field Event


### -field Event.Link_EventInfo

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556124">HBA_Link_EventInfo</a> that holds information associated with a link event. 


### -field Event.RSCN_EventInfo

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557188">HBA_RSCN_EventInfo</a> that holds information associated with a link event.


### -field Event.Pty_EventInfo

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557125">HBA_Pty_EventInfo</a> that holds information associated with a link event.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556124">HBA_Link_EventInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557125">HBA_Pty_EventInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557188">HBA_RSCN_EventInfo</a>
 

 

