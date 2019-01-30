---
UID: NC:ndis.NDIS_SWITCH_REFERENCE_SWITCH_PORT
title: NDIS_SWITCH_REFERENCE_SWITCH_PORT (ndis.h)
description: The ReferenceSwitchPort function increments the Hyper-V extensible switch reference counter for an extensible switch port.
old-location: netvista\ReferenceSwitchPort.htm
tech.root: netvista
ms.assetid: 5FD2E931-AC9F-4157-9C45-F93261FC834D
ms.date: 05/02/2018
ms.keywords: NDIS_SWITCH_REFERENCE_SWITCH_PORT, NDIS_SWITCH_REFERENCE_SWITCH_PORT callback, ReferenceSwitchPort, ReferenceSwitchPort callback function [Network Drivers Starting with Windows Vista], ndis/ReferenceSwitchPort, netvista.ReferenceSwitchPort
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	ReferenceSwitchPort
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_SWITCH_REFERENCE_SWITCH_PORT callback function


## -description



The <i>ReferenceSwitchPort</i> function increments the Hyper-V extensible switch reference counter for an extensible switch port.




## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh598204">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param SwitchPortId [in]

An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port for which the extensible switch reference counter is incremented.

<div class="alert"><b>Note</b>  The <i>SwitchPortId</i> parameter must specify the identifier of a port that is in a created state. Identifiers for ports that are in a teardown or deleted state cannot be specified. For more information about port states, see <a href="https://msdn.microsoft.com/1E2075E3-D7CC-4364-ABB2-D5969DB361B5">Hyper-V Extensible Switch Port and Network Adapter States</a>.</div>
<div> </div>

## -returns



If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.






## -remarks



The extensible switch extension calls <i>ReferenceSwitchPort</i> to increment the reference counter for an extensible switch port. While the reference counter has a nonzero value, the protocol edge of the extensible switch will not issue an object identifier (OID) set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598273">OID_SWITCH_PORT_DELETE</a> to delete the extensible switch port. 

After the extension calls <i>ReferenceSwitchPort</i>, it must call <a href="https://msdn.microsoft.com/976D3A69-C539-4C8E-9664-F85717E5F712">DereferenceSwitchPort</a> to decrement the reference counter.

The extension calls <i>ReferenceSwitchPort</i> after the port has reached the <i>Port created</i> state. The extension must not call <i>ReferenceSwitchPort</i> after the connection has reached the <i>Port tearing down</i> or <i>Port not created</i> states. For more information about these states, see <a href="https://msdn.microsoft.com/1E2075E3-D7CC-4364-ABB2-D5969DB361B5">Hyper-V Extensible Switch Port and Network Adapter States</a>.

 The extension must call <i>ReferenceSwitchPort</i> when it performs any operation that requires the port to be in an active state. For example, the extension must  call <i>ReferenceSwitchPort</i> before it issues an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598277">OID_SWITCH_PORT_PROPERTY_ENUM</a>.

The extension calls <i>ReferenceSwitchPort</i> after the port has reached the <i>Port created</i> state. The extension must not call <a href="https://msdn.microsoft.com/8F4C76FA-A386-4A3D-8C9F-3CFF69382702">ReferenceSwitchNic</a> after the port has reached the <i>Port tearing down</i> state. For more information about these states, see <a href="https://msdn.microsoft.com/1E2075E3-D7CC-4364-ABB2-D5969DB361B5">Hyper-V Extensible Switch Port and Network Adapter States</a>.

<div class="alert"><b>Note</b>  When the extension calls <i>ReferenceSwitchPort</i>, it does not have to synchronize the call with its code that handles OID requests. As a result, it is possible for the extension to call <i>ReferenceSwitchPort</i> while the protocol edge of the extensible switch issues an OID request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598279">OID_SWITCH_PORT_TEARDOWN</a>. However, if the call to <i>ReferenceSwitchPort</i> completes with NDIS_STATUS_SUCCESS, the extension can still issue the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598277">OID_SWITCH_PORT_PROPERTY_ENUM</a> OID request after it handles the OID_SWITCH_PORT_TEARDOWN OID request.</div>
<div> </div>



## -see-also




<b></b>



<a href="https://msdn.microsoft.com/58C72F81-07B9-45FE-A8BA-0405DBE4CA20">DereferenceSwitchNic</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598204">NdisFGetOptionalSwitchHandlers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598273">OID_SWITCH_PORT_DELETE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598277">OID_SWITCH_PORT_PROPERTY_ENUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598279">OID_SWITCH_PORT_TEARDOWN</a>
 

 

