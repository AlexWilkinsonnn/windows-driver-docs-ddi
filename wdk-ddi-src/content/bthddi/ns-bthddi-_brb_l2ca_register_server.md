---
UID: NS:bthddi._BRB_L2CA_REGISTER_SERVER
title: "_BRB_L2CA_REGISTER_SERVER" (bthddi.h)
description: A profile driver uses the _BRB_L2CA_REGISTER_SERVER structure to register itself as a server capable of receiving L2CAP connections from remote Bluetooth devices.
old-location: bltooth\_brb_l2ca_register_server.htm
tech.root: bltooth
ms.assetid: b7eca29a-7e3c-4cfc-b285-42faca263c5e
ms.date: 04/27/2018
ms.keywords: "_BRB_L2CA_REGISTER_SERVER, _BRB_L2CA_REGISTER_SERVER structure [Bluetooth Devices], bltooth._brb_l2ca_register_server, bth_structs_c803cec6-8a80-4d75-9c81-fd479ee37a97.xml, bthddi/_BRB_L2CA_REGISTER_SERVER"
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
-	bthddi.h
api_name:
-	_BRB_L2CA_REGISTER_SERVER
product:
- Windows
targetos: Windows
req.typenames: 
---

# _BRB_L2CA_REGISTER_SERVER structure


## -description


A profile driver uses the _BRB_L2CA_REGISTER_SERVER structure to register itself as a server capable
  of receiving L2CAP connections from remote Bluetooth devices.


## -struct-fields




### -field Hdr

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the remote Bluetooth device to receive notifications for. Specify BTH_ADDR_NULL to
     receive notification for any incoming connections.


### -field PSM

The Protocol/Service Multiplexer (PSM) that accepts connection requests.


### -field IndicationFlags

An optional flag or combination of flags that indicates whether the profile driver will accept
     pairing notifications in addition to connection notifications. The following table lists the possible
     flag settings. 
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
INDICATION_PAIR_DEVICE

</td>
<td>
The profile driver will accept notifications when a device is paired.

</td>
</tr>
<tr>
<td>
INDICATION_UNPAIR_DEVICE

</td>
<td>
The profile driver will accept notifications when a device is unpaired.

</td>
</tr>
<tr>
<td>
INDICATION_UNPERSONALIZE_DEVICE

</td>
<td>
The profile driver will accept notifications when a device is unpersonalized.

</td>
</tr>
</table>
 


### -field IndicationCallback

A 
     <a href="https://msdn.microsoft.com/d3ca900d-1dd6-49da-ae94-855de3fbd086">L2CAP Callback Function</a>,
     implemented by the profile driver, that the Bluetooth driver stack should call to notify the profile
     driver about incoming L2CAP connections.


### -field IndicationCallbackContext

The context to be passed to the callback function that is specified in the 
     <b>IndicationCallback</b> member.


### -field ReferenceObject

A pointer to an object to pass to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff558678">ObReferenceObject</a> and 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a> functions to
     maintain a reference count. Profile drivers should provide this object in such a way that the Bluetooth
     driver stack can increase the count of the object for as long as the driver stack can call the callback
     function specified in the 
     <b>IndicationCallback</b> member. The Bluetooth driver stack will decrease the reference count of the
     object when the profile driver 
     <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">builds and sends</a> a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536862">
     BRB_L2CA_UNREGISTER_SERVER</a> request.


### -field ServerHandle

Handle to the L2CAP server, if successfully returned. When the profile driver should no longer
     receive remote connect indications it should pass this handle to 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536862">
     BRB_L2CA_UNREGISTER_SERVER</a>.


## -remarks



To register itself as a L2CAP server, a profile driver should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536618">
    BRB_L2CA_REGISTER_SERVER</a> request.

After the profile driver registers itself, it should then 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536621">BRB_REGISTER_PSM</a> request so the Bluetooth
    driver stack will accept connections from the PSM.

If successful, the Bluetooth driver stack can then notify the profile driver when remote devices
    attempt to create a L2CAP connection to the profile driver on a particular PSM.

A profile driver can specify zero the 
    <b>Psm</b> member of the _BRB_L2CA_REGISTER_SERVER structure--which means that the PSM is unspecified--and
    the profile driver will subsequently issue a <b>BRB_REGISTER_PSM</b> BRB to obtain a dynamic PSM to register for
    connection notifications. For more information about PSMs, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536865">_BRB_PSM</a>.

After the profile driver has registered itself, the Bluetooth driver stack can notify it when a remote
    device attempts to connect to it by calling the 
    <a href="https://msdn.microsoft.com/d3ca900d-1dd6-49da-ae94-855de3fbd086">L2CAP Callback Function</a> that the
    profile driver implements and specifies in the 
    <b>IndicationCallback</b> member.

For more information about L2CAP servers and PSMs, see 
    <a href="https://msdn.microsoft.com/26a8238d-717a-438f-84d0-047ce9618928">Accepting
    L2CAP Connections in a Bluetooth Profile Driver</a>.

When the profile driver receives notification of a connection attempt, it should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536616">
    BRB_L2CA_OPEN_CHANNEL_RESPONSE</a> BRB to either accept or reject the connection attempt. For more
    information about accepting or rejecting L2CAP connection attempts, see the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536860">_BRB_L2CA_OPEN_CHANNEL</a> structure.

After a connection is established, the profile driver can issue other BRBs to communicate with the
    remote device.

To stop receiving remote connection notifications, a profile driver should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536862">
    BRB_L2CA_UNREGISTER_SERVER</a> request.

While this procedure allows a profile driver to accept incoming connection requests, it does not
    automatically advertise a service using SDP. To advertise a service using SDP, a profile driver must
    submit an SDP record using the SDP APIs. For more information about advertising services with SDP, see 
    <a href="https://msdn.microsoft.com/833f2eea-d7e6-4f19-979e-3bb4db47fa43">Communicating with SDP
    Servers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536618">BRB_L2CA_REGISTER_SERVER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536862">BRB_L2CA_UNREGISTER_SERVER</a>



<a href="https://msdn.microsoft.com/d3ca900d-1dd6-49da-ae94-855de3fbd086">L2CAP Callback Function</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558678">ObReferenceObject</a>
 

 

