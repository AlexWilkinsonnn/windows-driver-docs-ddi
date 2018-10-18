---
UID: NC:d3dkmthk.PFND3DKMT_CREATECONTEXTVIRTUAL
title: PFND3DKMT_CREATECONTEXTVIRTUAL
author: windows-driver-content
description: The D3dkmtCreateContextVirtual callback function creates a virtual context.
ms.assetid: 26a19776-6d90-4795-802e-2e769b24859d
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
-	PFND3DKMT_CREATECONTEXTVIRTUAL
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_CREATECONTEXTVIRTUAL callback function

## -description

The D3dkmtCreateContextVirtual callback function creates a virtual context.

## -prototype

```cpp
//Declaration

PFND3DKMT_CREATECONTEXTVIRTUAL Pfnd3dkmtCreatecontextvirtual; 

// Definition

NTSTATUS Pfnd3dkmtCreatecontextvirtual 
(
	D3DKMT_CREATECONTEXTVIRTUAL *
)
{...}

```

## -parameters

### -param *

[in, out] Pointer to a [D3DKMT_CREATECONTEXTVIRTUAL](ns-d3dkmthk-_d3dkmt_createcontextvirtual.md) structure.

## -returns

Returns NTSTATUS.
