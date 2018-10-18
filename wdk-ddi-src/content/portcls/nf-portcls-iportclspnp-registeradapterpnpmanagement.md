---
UID: NF:portcls.IPortClsPnp.RegisterAdapterPnpManagement
title: IPortClsPnp::RegisterAdapterPnpManagement
author: windows-driver-content
description: The RegisterAdapterPowerManagement method registers the PnP management interface of the adapter with PortCls.
old-location: audio\iportclspnp_registeradapterpnpmanagement.htm
tech.root: audio
ms.assetid: D9A54562-0ABC-4BEA-A9E3-F1A0A4EBC095
ms.date: 5/8/2018
ms.keywords: IPortClsPnp interface [Audio Devices],RegisterAdapterPnpManagement method, IPortClsPnp.RegisterAdapterPnpManagement, IPortClsPnp::RegisterAdapterPnpManagement, RegisterAdapterPnpManagement, RegisterAdapterPnpManagement method [Audio Devices], RegisterAdapterPnpManagement method [Audio Devices],IPortClsPnp interface, audio.iportclspnp_registeradapterpnpmanagement, portcls/IPortClsPnp::RegisterAdapterPnpManagement
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 10, version 1511 and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortClsPnp.RegisterAdapterPnpManagement
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsPnp::RegisterAdapterPnpManagement


## -description


The <code>RegisterAdapterPowerManagement</code> method registers the PnP management interface of the adapter with PortCls.


## -parameters




### -param pUnknown [in]

Specifies a pointer to <b>IUnknown</b> of <a href="https://msdn.microsoft.com/library/windows/hardware/mt604850">IAdapterPnpManagement</a>. 


### -param DeviceObject [in]

Specifies a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.


## -returns



The <code>RegisterAdapterPowerManagement</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the appropriate error code.




## -remarks



When the <code>RegisterAdapterPowerManagement</code> method registers the PnP management interface for the adapter with PortCls, it allows the adapter driver to be notified of PnP state change events.

For more information,  see <a href="https://msdn.microsoft.com/FCAD7F8B-AA9B-430A-BCAF-04E13FA15382">Implement PnP Rebalance for PortCls Audio Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt604859">IPortClsPnp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536876">IPortClsPower::UnregisterAdapterPowerManagement</a>
 

 

