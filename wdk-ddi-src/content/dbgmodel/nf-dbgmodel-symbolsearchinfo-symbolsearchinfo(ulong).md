---
UID: NF:dbgmodel.SymbolSearchInfo.SymbolSearchInfo(ULONG)
title: SymbolSearchInfo(ULONG) function (dbgmodel.h)
description: The search record passed to EnumerateChildrenEx in order to restrict symbol searches.
ms.date: 10/04/2018
keywords: ["SymbolSearchInfo function"]
f1_keywords:
 - "dbgmodel/SymbolSearchInfo"
 - "SymbolSearchInfo"
ms.keywords: SymbolSearchInfo
req.header: dbgmodel.h
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
- apiref
api_type: 
- HeaderDef
api_location: 
- dbgmodel.h
api_name: 
- SymbolSearchInfo
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# SymbolSearchInfo(ULONG) function


## -description

The search record passed to EnumerateChildrenEx in order to restrict symbol searches.

A given kind of symbol (as indicated by the SymbolKind enumeration) searched may have its own derived type.

## -parameters

### -param derivedSize
The derived size.

## -returns
This function is a constructor and does not return a value.

## -remarks

## -see-also

[dbgmodel.h header](./index.md)
