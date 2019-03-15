---
UID: NS:avc._AVC_PEER_DO_LOCATOR
title: _AVC_PEER_DO_LOCATOR (avc.h)
description: The AVC_PEER_DO_LOCATOR describes nonvirtual (peer) instances of avc.sys.
old-location: stream\avc_peer_do_locator.htm
tech.root: stream
ms.assetid: a1ef8626-1920-422b-a0ed-4da9ac495f74
ms.date: 04/23/2018
ms.keywords: "*PAVC_PEER_DO_LOCATOR, AVC_PEER_DO_LOCATOR, AVC_PEER_DO_LOCATOR structure [Streaming Media Devices], PAVC_PEER_DO_LOCATOR, PAVC_PEER_DO_LOCATOR structure pointer [Streaming Media Devices], _AVC_PEER_DO_LOCATOR, avc/AVC_PEER_DO_LOCATOR, avc/PAVC_PEER_DO_LOCATOR, avcref_6e8543dc-a712-4031-8f48-cf789d320551.xml, stream.avc_peer_do_locator"
ms.topic: struct
req.header: avc.h
req.include-header: Avc.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- avc.h
api_name:
- AVC_PEER_DO_LOCATOR
product:
- Windows
targetos: Windows
req.typenames: AVC_PEER_DO_LOCATOR, *PAVC_PEER_DO_LOCATOR
---

# _AVC_PEER_DO_LOCATOR structure


## -description


The AVC_PEER_DO_LOCATOR describes nonvirtual (peer) instances of <i>avc.sys</i>.


## -struct-fields




### -field NodeAddress

Set to the NodeAddress of the device whose driver instance is to be located.


### -field Generation

Set to the Generation obtained with the NodeAddress.


### -field DeviceObject

On success, points to the FDO of the <i>avc.sys</i> instance. The caller must release the reference to this object (by using <b>ObDereferenceObject</b>) when finished with it.


## -remarks



This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554152">AVC_FUNCTION_FIND_PEER_DO</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554145">AVC_FUNCTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554152">AVC_FUNCTION_FIND_PEER_DO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554177">AVC_MULTIFUNC_IRB</a>
 

 


