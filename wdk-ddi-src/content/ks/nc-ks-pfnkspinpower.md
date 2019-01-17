---
UID: NC:ks.PFNKSPINPOWER
title: PFNKSPINPOWER
description: An AVStream minidriver's AVStrMiniPinPower routine is called for pin-centric pins when the device is waking or entering a sleep state.
old-location: stream\avstrminipinpower.htm
tech.root: stream
ms.assetid: 6362ca08-cf8d-4e54-b144-10b2252f05c5
ms.date: 04/23/2018
ms.keywords: AVStrMiniPinPower, AVStrMiniPinPower routine [Streaming Media Devices], PFNKSPINPOWER, avstclbk_fd047ae3-b574-4dad-a16b-2152193fb2cd.xml, ks/AVStrMiniPinPower, stream.avstrminipinpower
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
-	UserDefined
api_location:
-	ks.h
api_name:
-	AVStrMiniPinPower
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSPINPOWER callback function


## -description


An AVStream minidriver's <i>AVStrMiniPinPower</i> routine is called for pin-centric pins when the device is waking or entering a sleep state.


## -parameters




### -param Pin [in]

Points to a pin-centric <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure for which to register the callback.


### -param State [in]

Specifies the device power state being requested. Set this parameter to one of the following DEVICE_POWER_STATE enumeration values: <b>PowerDeviceD0</b>, <b>PowerDeviceD1</b>, <b>PowerDeviceD2</b>, or <b>PowerDeviceD3</b>.


## -returns



None




## -remarks



<div class="alert"><b>Warning</b>  Do not attempt to obtain the filter control mutex from within either the Sleep or Wake callback. Doing so induces a risk of deadlock. For more information about mutexes, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.</div>
<div> </div>
The minidriver specifies an address for routines of this type in the <i>Sleep </i>and/or <i>Wake </i>parameters of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563525">KsPinRegisterPowerCallbacks</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562550">KsFilterRegisterPowerCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563525">KsPinRegisterPowerCallbacks</a>
 

 

