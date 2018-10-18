---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL
title: D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL
author: windows-driver-content
description: Specifies the attributes of the authenticated channel to be created by the user-mode driver's CreateAuthenticatedChannel(D3D11_1) function.
old-location: display\d3d11_1ddiarg_createauthenticatedchannel.htm
ms.assetid: 0b3a20db-aa03-4017-a10a-ae84a6ed31c8
ms.date: 5/10/2018
ms.keywords: D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL, D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL structure [Display Devices], d3d10umddi/D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL, display.d3d11_1ddiarg_createauthenticatedchannel
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
api_name:
-	D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL
---

# D3D11_1DDIARG_CREATEAUTHENTICATEDCHANNEL structure


## -description


Specifies the attributes of the authenticated channel to be created by the user-mode driver's <a href="https://msdn.microsoft.com/90b43bc3-6569-4799-8be3-e4e60f59164f">CreateAuthenticatedChannel(D3D11_1)</a> function.


## -struct-fields




### -field ChannelType

Specifies the type of channel, as a member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406343">D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE</a> enumeration.


### -field hChannel

A handle to the authenticated channel object.


## -see-also




<a href="https://msdn.microsoft.com/90b43bc3-6569-4799-8be3-e4e60f59164f">CreateAuthenticatedChannel(D3D11_1)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406343">D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE</a>
 

 

