---
UID: NC:d3dumddi.PFND3DDDI_UNLOCK2CB
title: PFND3DDDI_UNLOCK2CB
author: windows-driver-content
description: The pfnUnlock2Cb function unlocks an allocation that was locked by a call to the pfnLock2Cb function.
old-location: display\pfnunlock2cb.htm
tech.root: display
ms.assetid: 642C6A05-DA8C-453A-B1AA-030C59F32DA5
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_UNLOCK2CB, PFND3DDDI_UNLOCK2CB callback, d3dumddi/pfnUnlock2Cb, display.pfnunlock2cb, pfnUnlock2Cb, pfnUnlock2Cb callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dumddi.h
api_name:
-	pfnUnlock2Cb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_UNLOCK2CB callback function


## -description


The <b>pfnUnlock2Cb</b> function unlocks an allocation that was locked by a call to the <a href="https://msdn.microsoft.com/C046F34A-4304-4B96-8D7A-7A951016437F">pfnLock2Cb</a> function.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn894603">D3DDDICB_UNLOCK2</a> structure that describes the allocation to unlock.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



