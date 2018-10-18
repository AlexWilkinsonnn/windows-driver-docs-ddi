---
UID: NS:d3dkmthk._D3DKMT_TRACKEDWORKLOADDEADLINE
title: _D3DKMT_TRACKEDWORKLOADDEADLINE
author: windows-driver-content
description: Arguments used to set the tracked workload deadline.
ms.assetid: 96ac46b8-5328-4196-8ced-b5aaf869abdf
ms.date: 
ms.topic: struct
ms.keywords: _D3DKMT_TRACKEDWORKLOADDEADLINE, D3DKMT_TRACKEDWORKLOADDEADLINE, 
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_TRACKEDWORKLOADDEADLINE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmthk.h
api_name: 
-	_D3DKMT_TRACKEDWORKLOADDEADLINE
product:
-	Windows
targetos: Windows
tech.root: display
---

# _D3DKMT_TRACKEDWORKLOADDEADLINE structure

## -description

Arguments used to set the tracked workload deadline.

## -struct-fields

### -field Type

Indicates the type of the deadline.

### -field VBlankOffsetHundredsNS

If *Type* is equal to [D3DKMT_TRACKEDWORKLOADDEADLINETYPE_VBLANK](ne-d3dkmthk-_d3dkmt_trackedworkloaddeadlinetype.md), the deadline value indicates the offset to the next VBLANK (vertical blanking interval), in hundreds of nanoseconds.

### -field AbsoluteQPC
 
If *Type) is equal to [D3DKMT_TRACKEDWORKLOADDEADLINETYPE_ABSOLUTE](ne-d3dkmthk-_d3dkmt_trackedworkloaddeadlinetype.md), the deadline value indicates the absolute QPC (query performance counter) value.

## -remarks

## -see-also
