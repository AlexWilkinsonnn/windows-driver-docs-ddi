---
UID: NF:portcls.IPinName.GetPinName
title: IPinName::GetPinName
author: windows-driver-content
description: The GetPinName method retrieves the friendly name of an audio endpoint.
old-location: audio\ipinname_getpinname.htm
tech.root: audio
ms.assetid: 97fa159c-ce71-4ce2-8d40-def7671d014c
ms.date: 5/8/2018
ms.keywords: GetPinName, GetPinName method [Audio Devices], GetPinName method [Audio Devices],IPinName interface, IPinName interface [Audio Devices],GetPinName method, IPinName.GetPinName, IPinName::GetPinName, audio.ipinname_getpinname, audmp-routines_438a3c13-6571-45ab-ad7a-6ef71336c17f.xml, portcls/IPinName::GetPinName
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPinName.GetPinName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPinName::GetPinName


## -description


The <code>GetPinName</code> method retrieves the friendly name of an audio endpoint.


## -parameters




### -param Irp [in]

Specifies a pointer to an I/O request packet (IRP) structure. 


### -param Pin [in]

Specifies a pointer to the underlying kernel streaming (KS) pin.


### -param Data [out]

Specifies a pointer to the buffer that holds the data for the <code>GetPinName</code> method.


## -returns



The <code>GetPinName</code> method returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



If a client needs the current pin name of an endpoint, but has determined that the miniport driver does not support the <code>GetPinName</code> method, the client uses the friendly name of the topology bridge pin. For more information about pin categories and friendly names, see <a href="https://msdn.microsoft.com/fd4a4afd-2c17-4002-87ae-21501b1d75c1">Pin Category Property</a> and <a href="https://msdn.microsoft.com/e0937d20-dd5b-453f-99f6-4e501f0f0e5b">Friendly Names for Audio Endpoint Devices</a>. 

<div class="alert"><b>Note</b>   In Windows 7, the user-mode audio stack does not support customization of the Speakers endpoint name. So in Windows 7, the <code>GetPinName</code> method only works with endpoints that do not have the Speakers friendly name. The following list shows the KS node type categories that are assigned the Speakers friendly name:<dl>
<dd>
KSNODETYPE_SPEAKER

</dd>
<dd>
KSNODETYPE_DESKTOP_SPEAKER

</dd>
<dd>
KSNODETYPE_ROOM_SPEAKER

</dd>
<dd>
KSNODETYPE_LOW_FREQUENCY_EFFECTS_SPEAKER

</dd>
</dl>
</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/e0937d20-dd5b-453f-99f6-4e501f0f0e5b">Friendly Names for Audio Endpoint Devices</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536837">IPinName</a>



<a href="https://msdn.microsoft.com/fd4a4afd-2c17-4002-87ae-21501b1d75c1">Pin Category Property</a>
 

 

