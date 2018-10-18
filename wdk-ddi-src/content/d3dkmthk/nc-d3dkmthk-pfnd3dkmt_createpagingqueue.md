---
UID: NC:d3dkmthk.PFND3DKMT_CREATEPAGINGQUEUE
title: PFND3DKMT_CREATEPAGINGQUEUE
author: windows-driver-content
description: The PFND3DKMT_CREATEPAGINGQUEUE callback function creates a paging queue.
ms.assetid: c0aa3399-4862-4836-a183-141caa8264d4
ms.date: 
ms.topic: callback
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3dkmthk.h
api_name: 
-	PFND3DKMT_CREATEPAGINGQUEUE
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_CREATEPAGINGQUEUE callback function

## -description

The PFND3DKMT_CREATEPAGINGQUEUE callback function creates a paging queue.

## -prototype

```cpp
//Declaration

PFND3DKMT_CREATEPAGINGQUEUE Pfnd3dkmtCreatepagingqueue; 

// Definition

NTSTATUS Pfnd3dkmtCreatepagingqueue 
(
	D3DKMT_CREATEPAGINGQUEUE *
)
{...}

```

## -parameters

### -param *

Pointer to a [D3DKMT_CREATEPAGINGQUEUE](ns-d3dkmthk-_d3dkmt_createpagingqueue.md) structure.

## -returns

Returns NTSTATUS.
