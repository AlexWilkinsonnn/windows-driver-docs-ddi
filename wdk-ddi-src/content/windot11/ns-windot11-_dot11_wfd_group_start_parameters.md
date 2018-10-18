---
UID: NS:windot11._DOT11_WFD_GROUP_START_PARAMETERS
title: "_DOT11_WFD_GROUP_START_PARAMETERS"
author: windows-driver-content
description: The DOT11_WFD_GROUP_START_PARAMETERS structure is included with an OID_DOT11_WFD_GROUP_START_PARAMETERS request. The structure contains startup parameters for a Group Owner (GO).
old-location: netvista\dot11_wfd_group_start_parameters.htm
tech.root: netvista
ms.assetid: DA17F7DB-E6E7-4934-8AAF-73800ABF1432
ms.date: 2/16/2018
ms.keywords: "*PDOT11_WFD_GROUP_START_PARAMETERS, DOT11_WFD_GROUP_START_PARAMETERS, DOT11_WFD_GROUP_START_PARAMETERS structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_GROUP_START_PARAMETERS, PDOT11_WFD_GROUP_START_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_GROUP_START_PARAMETERS, netvista.dot11_wfd_group_start_parameters, windot11/DOT11_WFD_GROUP_START_PARAMETERS, windot11/PDOT11_WFD_GROUP_START_PARAMETERS"
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
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
-	Windot11.h
api_name:
-	DOT11_WFD_GROUP_START_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DOT11_WFD_GROUP_START_PARAMETERS, *PDOT11_WFD_GROUP_START_PARAMETERS
product:
- Windows 10 or later.
---

# _DOT11_WFD_GROUP_START_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_GROUP_START_PARAMETERS</b> structure is included with an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451800">OID_DOT11_WFD_GROUP_START_PARAMETERS</a> request. The structure contains startup parameters for a Group Owner (GO).


## -syntax


```cpp
typedef struct _DOT11_WFD_GROUP_START_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_WFD_CHANNEL  AdvertisedOperatingChannel;
} DOT11_WFD_GROUP_START_PARAMETERS, *PDOT11_WFD_GROUP_START_PARAMETERS;
```


## -struct-fields




### -field Header

The type, revision, and size of the <b>DOT11_WFD_GROUP_START_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following.

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_ GROUP_START_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_GROUP_START_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field AdvertisedOperatingChannel

The channel information originally sent to the Client in a GO Negotiation or Invitation exchange. This is the preferred channel for starting the group. The miniport must ensure regulatory compliance when starting the Group Owner.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451800">OID_DOT11_WFD_GROUP_START_PARAMETERS</a>



 

 


